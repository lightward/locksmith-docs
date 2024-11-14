---
description: >-
  How to get past this Shopify error when attempting to create the seo.hidden
  metafield definition for products
---

# I am getting an "already taken" error when trying to create a metafield definition for seo.hidden

{% hint style="info" %}
The Locksmith app has the ability to automatically manage the seo.hidden metafield for locked products in your store. [More information about that here](../../tutorials/more/automatically-hide-from-sitemaps-and-manage-seo-metafield.md). \
\
If you've toggled this setting on at any point, but still wish to create a definition for this metafield, this guide can help.
{% endhint %}

Shopify allows you to create metafield definitions for products, and other content, in your store, even if the metafield already exists on your products. This is typically done by viewing your unstructured metafields and pressing the "Add definition" button. You can find more general information on creating metafield definitions [in this Shopify guide](https://help.shopify.com/en/manual/custom-data/metafields/metafield-definitions).

For reasons unknown, Shopify has decided to exclude the `seo.hidden` metafield from this list, even if some of your products have this metafield.

There is a simple trick to get around this.

1. Go to the "Product metafield definitions" page. It should look something like this:

<figure><img src="../../.gitbook/assets/Screenshot 2024-11-13 at 23.42.37.png" alt=""><figcaption></figcaption></figure>

2. In the URL bar for your browser, paste add in the following _to the end of the already existing URL_:

<pre><code><strong>/migrate/seo/hidden
</strong></code></pre>

You should end up with something like:

{% code overflow="wrap" %}
```
https://admin.shopify.com/store/YOUR-SHOP-URL/settings/custom_data/product/metafields/migrate/seo/hidden
```
{% endcode %}

3. You'll be brought to the page to create a definition for `seo.hidden`. Change the type to "Integer" all other settings are up to you.

<figure><img src="../../.gitbook/assets/Screenshot 2024-11-13 at 23.46.21 (1).png" alt=""><figcaption></figcaption></figure>

