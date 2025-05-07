---
hidden: true
noIndex: true
---

# Creating locks with the Admin API (WIP)

{% hint style="warning" %}
**Important**: Locksmith support cannot help write or troubleshoot these requests for you. However, if there is anything unclear in our documentation, please feel free to contact us with questions.
{% endhint %}

#### Example body request

```
{
  "resource_id": 1234567,
  "resource_type": "product",
  "enabled": true,
  "options": {
    "hide_links_to_resource": false,
    "hide_resource": false,
    "hide_resource_from_sitemaps": false,
    "manual": false,
    "noindex": true
  },
  "keys": []
}
```

#### Body Parameters

| `resource_id`                         | integer | Shopify resource ID. This number can be found at the end of the resource URL in your **Shopify Admin.** Leave blank for shop locks.                                           |
| ------------------------------------- | ------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| `resource_type`                       | string  | Type of resource - `product`, `collection`, `page`, or `shop` . Other types of locks unsupported.                                                                             |
| `enabled`                             | boolean | Whether the lock is active.                                                                                                                                                   |
| `options`                             | object  | Lock behavior options. See below.                                                                                                                                             |
| `options.hide_links_to_resource`      | boolean | Hide navigation links pointing to the resource on storefront. [See documentation](../tutorials/more/hiding-navigation-links-for-locked-resources.md).                         |
| `options.hide_resource`               | boolean | Hide the resource from product grids. [See documentation](../tutorials/more/hiding-products-from-product-grids.md).                                                           |
| `options.hide_resource_from_sitemaps` | boolean | Remove resource from sitemap generation. [See documentation](../tutorials/more/automatically-hide-from-sitemaps-and-manage-seo-metafield.md).                                 |
| `options.manual`                      | boolean | Indicates a manual lock. [See documentation.](../tutorials/more/manual-mode.md)                                                                                               |
| `options.noindex`                     | boolean | Add `noindex` meta tag to the storefreont rendering to prevent search engine indexing. [See documentation](../faqs/more/how-does-locksmith-affect-search-engines-and-seo.md). |
| `keys`                                | array   | List of key definitions that grant access; can be empty on creation.                                                                                                          |

***
