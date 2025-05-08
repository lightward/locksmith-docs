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

Note that only the top 3 parameters are required. If left blank, the rest will use their defaults as noted.

| Parameter                             | Type    | Description                                                                                                                                                                   | Required                                                                                                 |
| ------------------------------------- | ------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------- |
| `resource_id`                         | integer | Shopify resource ID. This number can be found at the end of the resource URL in your **Shopify Admin.**                                                                       | <mark style="color:red;">Required</mark>. Unless creating a shop lock, in which case it can be left out. |
| `resource_type`                       | string  | Required. Type of resource - `product`, `custom_collection`, `smart_collection` `page`, `blog` , or `shop` . Other types of locks unsupported.                                | <mark style="color:red;">Required</mark>                                                                 |
| `keys`                                | array   | List of key definitions that grant access; can be an empty array on creation.                                                                                                 | <mark style="color:red;">Required</mark>                                                                 |
| `enabled`                             | boolean | Whether the lock is active.                                                                                                                                                   | <p>Optional<br>Default: true</p>                                                                         |
| `options`                             | object  | Lock behavior options. See below.                                                                                                                                             | Optional                                                                                                 |
| `options.hide_links_to_resource`      | boolean | Hide navigation links pointing to the resource on storefront. [See documentation](../tutorials/more/hiding-navigation-links-for-locked-resources.md).                         | <p>Optional<br>Default: false</p>                                                                        |
| `options.hide_resource`               | boolean | Hide the resource from product grids. [See documentation](../tutorials/more/hiding-products-from-product-grids.md).                                                           | <p>Optional</p><p>Default: false</p>                                                                     |
| `options.hide_resource_from_sitemaps` | boolean | Remove resource from sitemap generation. [See documentation](../tutorials/more/automatically-hide-from-sitemaps-and-manage-seo-metafield.md).                                 | <p>Optional</p><p>Default: false</p>                                                                     |
| `options.manual`                      | boolean | Indicates a manual lock. [See documentation.](../tutorials/more/manual-mode.md)                                                                                               | <p>Optional<br>Default: false</p>                                                                        |
| `options.noindex`                     | boolean | Add `noindex` meta tag to the storefreont rendering to prevent search engine indexing. [See documentation](../faqs/more/how-does-locksmith-affect-search-engines-and-seo.md). | <p>Optional<br>Default: true</p>                                                                         |

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
Using bad input while creating locks with this endpoint may occasionally result in invalid locks being created, which can in turn result in install failures for your store. It is your responsibility to test your storefront and delete any locks that aren't working as expected.
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
    "resource_id": 1234567890,
    "resource_type": "product",
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
    "resource_id": 1234567890,
    "resource_type": "product",
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
    "resource_id": 1234567890,
    "resource_type": "product",
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

##
