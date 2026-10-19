---
description: >-
  How to set up Locksmith locks to hide from collections, in-store searches, and
  any other lists and grids in your Shopify Online Store
---

# Hiding products and other content from lists in your online store

Locksmith allows you to hide _locked_ content from lists across your store. This includes hiding products from collections and search result pages - only showing them to visitors that have gained access to the appropriate lock(s). This is turned on in your lock settings on your lock page:

<figure><img src="../../.gitbook/assets/Screenshot 2025-07-15 at 15.07.49.png" alt=""><figcaption></figcaption></figure>

## Hide products from the following:

* Searches
* Collections
* Related products
* Featured products
* And more! Any time your theme is showing a list of products, this feature likely has the ability to filter locked products from it - _as long as the list is not displayed by a third party app._

## Other resource types

Although less commonly needed, you can also turn this feature on for page, blog, and article locks. In these cases, if your theme has a way to display "all pages", or "all blogs", for example, Locksmith can remove these from from those types of displays as well.

## Limitations

* Using **third party apps** that take over the display of your collections or searches will likely prevent Locksmith from hiding products correctly. Most filtering/search/display apps are **not compatible** with hiding products via Locksmith.
* Hiding a large number of products this way can introduce **blank spaces** to your collections. [More information and workarounds here](../../faqs/faq-i-see-blank-spaces-in-my-collections-and-or-searches-when-locking.md).
* While this setting is capable of hiding products from the search results _page_, it cannot always remove products from search results that are fetched dynamically (i.e. shows results as you type).
* This setting cannot hide filtering options in your theme's filter menu (shown on collection and search pages). Shopify builds the filter options, and their counts, from every matching product, locked or not, before your theme displays them. If your theme draws its filter menu itself, Locksmith's manual code can often hide a particular filter, or the whole filter area, from visitors who don't have access: write to us at **team@uselocksmith.com** and we'll add it for you. Filter counts will still include locked products, and filters displayed by a third-party filter app are out of Locksmith's reach.

For more specific information regarding how locksmith works with your in-store search, including some troubleshooting steps, see our guide here:

{% content-ref url="../../faqs/can-locksmith-hide-content-from-my-in-store-search.md" %}
[can-locksmith-hide-content-from-my-in-store-search.md](../../faqs/can-locksmith-hide-content-from-my-in-store-search.md)
{% endcontent-ref %}
