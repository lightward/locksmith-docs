# Using the Admin API with Locks

{% hint style="warning" %}
**Important**: Locksmith support cannot help write or troubleshoot these requests for you. However, if there is anything unclear in our documentation, please feel free to contact us with questions.
{% endhint %}

Locks can be created via our Admin API using the following endpoint:

<mark style="color:green;">`POST`</mark> `/lock`&#x20;

This guide covers information specific to creating locks. See our general Admin API guide for more general information on forming these requests (including headers and authentication):

{% content-ref url="../developer-tools/locksmith-admin-api.md" %}
[locksmith-admin-api.md](../developer-tools/locksmith-admin-api.md)
{% endcontent-ref %}

## Body Parameters

A lock can protect **one or more resources of the same type**. Set the lock's type with the top-level `resource_type`, and list the resources it protects in the `resources` array — each entry an object with its own `resource_type`, `resource_id`, and optional `resource_options`. Every resource on a lock must be the same type (the three collection flavors — manual `custom_collection`, automated `smart_collection`, and the all-products `liquid:collection-all` — count as one type and can be combined).

A **shop lock** is the exception: pass `resource_type: "shop"` with no `resources` array, since it protects the entire storefront.

After creation, a lock's resources can also be managed individually using the dedicated resource endpoints (see [Managing a lock's resources](#managing-a-locks-resources) below).

Note that `resource_type` and `keys` are required. If left blank, the rest will use their defaults as noted.

| Parameter                             | Type    | Description                                                                                                                                                                   | Required                                                                                                                                                                                                                                                                                                |
| ------------------------------------- | ------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| `resource_type`                       | string  | The lock's resource type — `product`, `custom_collection`, `smart_collection`, `page`, `blog`, or `shop`. Determines how the lock is enforced; every entry in `resources` must be this same type. Other types of locks unsupported.                                | <mark style="color:red;">Required</mark>                                                                                                                                                                                                                                                                |
| `resources`                           | array   | The resources this lock protects. Each entry is an object with `resource_type`, `resource_id`, and an optional `resource_options` object. The `resource_id` is the Shopify resource ID, found at the end of the resource URL in your **Shopify Admin.** All entries must be the same type as the lock. Omit for a shop lock. <br><br><strong>Note</strong>: a resource can belong to only one lock. Attaching one that's already locked elsewhere is rejected — to add a resource to an existing lock, use the resource endpoints below rather than re-posting. | <mark style="color:red;">Required</mark>, except for shop locks                                                                                                                                                                                                                                                                |
| `name`                                | string  | An optional, human-friendly label for the lock, shown in the lock list. Has no effect on what the lock protects.                                                              | <p>Optional<br>Default: none</p>                                                                                                                                                                                                                                                                       |
| `keys`                                | array   | List of key definitions that grant access; can be an empty array on creation.                                                                                                 | <mark style="color:red;">Required</mark>                                                                                                                                                                                                                                                                |
| `enabled`                             | boolean | Whether the lock is active.                                                                                                                                                   | <p>Optional<br>Default: true</p>                                                                                                                                                                                                                                                                        |
| `options`                             | object  | Lock behavior options. See below.                                                                                                                                             | Optional                                                                                                                                                                                                                                                                                                |
| `options.hide_links_to_resource`      | boolean | Hide navigation links pointing to the resource on storefront. [See documentation](../tutorials/more/hiding-navigation-links-for-locked-resources.md).                         | <p>Optional<br>Default: false</p>                                                                                                                                                                                                                                                                       |
| `options.hide_resource`               | boolean | Hide the resource from product grids. [See documentation](../tutorials/more/hiding-products-and-other-content-from-lists-in-your-online-store.md).                            | <p>Optional</p><p>Default: false</p>                                                                                                                                                                                                                                                                    |
| `options.hide_resource_from_sitemaps` | boolean | Remove resource from sitemap generation. [See documentation](../tutorials/more/automatically-hide-from-sitemaps-and-manage-seo-metafield.md).                                 | <p>Optional</p><p>Default: false</p>                                                                                                                                                                                                                                                                    |
| `options.manual`                      | boolean | Indicates a manual lock. [See documentation.](../tutorials/more/manual-mode.md)                                                                                               | <p>Optional<br>Default: false</p>                                                                                                                                                                                                                                                                       |
| `options.noindex`                     | boolean | Add `noindex` meta tag to the storefreont rendering to prevent search engine indexing. [See documentation](../faqs/more/how-does-locksmith-affect-search-engines-and-seo.md). | <p>Optional<br>Default: true</p>                                                                                                                                                                                                                                                                        |

## Optional query parameters

Add these to the end of the /lock endpoint. For example:

`https://uselocksmith.com/api/unstable/lock?dryrun=true`

| Name      | Type    | Description                                                                               | Extra info                                                                                     |
| --------- | ------- | ----------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------- |
| `install` | boolean | If true, a theme install on your published theme is performed (if request is successful). | Recommended unless you are manually triggering an install later! See `POST /install` endpoint. |
| `dryrun`  | boolean | If true, changes are not persisted, but a success/error response is still returned.       | Useful for testing/debugging.                                                                  |

## Keys

Locksmith has a large variety of key conditions types and their corresponding options. The easiest way to create a valid key config is doing it **right inside the Locksmith app on a lock page**. Once created, the key config can be copy-pasted directly from the Locksmith app:

<figure><img src="../.gitbook/assets/Screenshot 2025-05-07 at 15.01.50.png" alt=""><figcaption></figcaption></figure>

If using multiple keys, make sure to create a valid JSON array and use it as the "keys" parameter in your request. Once you've created valid key configs, you can reuse them wherever you are using this API. Check the **examples below**.

## Responses

* `200` Success - the response body will contain the json representation of the newly created lock
* `400` Error - Post payload incorrectly formed
* `404` Error - Post URL incorrectly formed

{% hint style="danger" %}
Creating locks using invalid input may occasionally create malfunctioning locks. It is important that you test your storefront and delete any locks that aren't working as expected.
{% endhint %}

## Notes

* On success, the returned json object will contain fields you did not explicitly add. Note that fields prefixed with `_` are automatically generated by the backend and should not be included in request bodies.
* After creation, you can use the `GET /locks/:lock_id` endpoint to verify.

## Example cURL requests

```bash
# Create a minimal product-level lock with required fields only
curl -X POST https://uselocksmith.com/api/unstable/lock \
  -H "x-shopify-shop-domain: example-store.myshopify.com" \
  -H "x-locksmith-access-token: abcd1234" \
  -H "Content-Type: application/json" \
  -d '{
    "resource_type": "product",
    "resources": [
      { "resource_type": "product", "resource_id": 1234567890 }
    ],
    "keys": []
  }'
```

```bash
# Create a shop-level lock that applies to the entire storefront
curl -X POST https://uselocksmith.com/api/unstable/lock \
  -H "x-shopify-shop-domain: example-store.myshopify.com" \
  -H "x-locksmith-access-token: abcd1234" \
  -H "Content-Type: application/json" \
  -d '{
    "resource_type": "shop",
    "keys": []
  }'
```

```bash
# Create a product-level lock. Optional parameters included. without keys.
curl -X POST https://uselocksmith.com/api/unstable/lock \
  -H "x-shopify-shop-domain: example-store.myshopify.com" \
  -H "x-locksmith-access-token: abcd1234" \
  -H "Content-Type: application/json" \
  -d '{
    "resource_type": "product",
    "resources": [
      { "resource_type": "product", "resource_id": 1234567890 }
    ],
    "enabled": true,
    "options": {
      "hide_links_to_resource": true,
      "hide_resource": true,
      "hide_resource_from_sitemaps": true,
      "manual": false,
      "noindex": true
    },
    "keys": []
  }'
```

```bash
# minimal product level lock. WITH keys
curl -X POST "https://uselocksmith.com/api/unstable/lock" \
  -H "x-shopify-shop-domain: example-store.myshopify.com" \
  -H "x-locksmith-access-token: abcd1234" \
  -H "Content-Type: application/json" \
  -d '{
    "resource_type": "product",
    "resources": [
      { "resource_type": "product", "resource_id": 1234567890 }
    ],
    "keys": [
      {
        "options": {
          "customer_autotag": "",
          "force_open": false,
          "redirect_url": "",
          "inverse": false
        },
        "conditions": [
          {
            "type": "customer_tag",
            "inverse": false,
            "options": {
              "customer_tag": "approved"
            }
          }
        ]
      },
      {
        "options": {
          "customer_autotag": "",
          "force_open": false,
          "redirect_url": "",
          "inverse": false
        },
        "conditions": [
          {
            "type": "passcodes",
            "inverse": false,
            "options": {
              "passcodes": ["letmein"],
              "case_sensitive": true,
              "customer_remember": true
            }
          }
        ]
      }
    ]
  }'
```

```bash
# Create a named lock protecting MULTIPLE products at once
curl -X POST https://uselocksmith.com/api/unstable/lock \
  -H "x-shopify-shop-domain: example-store.myshopify.com" \
  -H "x-locksmith-access-token: abcd1234" \
  -H "Content-Type: application/json" \
  -d '{
    "name": "Wholesale catalog",
    "resource_type": "product",
    "resources": [
      { "resource_type": "product", "resource_id": 1234567890 },
      { "resource_type": "product", "resource_id": 1234567891 },
      { "resource_type": "product", "resource_id": 1234567892 }
    ],
    "keys": []
  }'
```

## Managing a lock's resources

Once a lock exists, you can attach, update, or detach individual resources without re-posting the whole lock. Every resource on a lock must be the same type (the three collection flavors — manual `custom_collection`, automated `smart_collection`, and the all-products `liquid:collection-all` — count as one type and can be combined). A resource can belong to only one lock; attaching one that's already locked elsewhere is rejected.

* <mark style="color:green;">`POST`</mark> `/locks/:lock_id/resources` \
  Attaches a resource to the lock. Body: an object with `resource_type`, `resource_id`, and optional `resource_options`.
* <mark style="color:blue;">`PATCH`</mark> `/locks/:lock_id/resources/:lock_resource_id` \
  Updates an attached resource.
* <mark style="color:red;">`DELETE`</mark> `/locks/:lock_id/resources/:lock_resource_id` \
  Detaches a resource from the lock. A lock with no resources is inactive (its keys are preserved) until one is re-added.

```bash
# Attach another product to an existing lock
curl -X POST https://uselocksmith.com/api/unstable/locks/55555/resources \
  -H "x-shopify-shop-domain: example-store.myshopify.com" \
  -H "x-locksmith-access-token: abcd1234" \
  -H "Content-Type: application/json" \
  -d '{
    "resource_type": "product",
    "resource_id": 1234567893
  }'
```

##
