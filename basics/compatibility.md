# Compatibility with other apps and Shopify features

Locksmith works in and around the online storefront theme layer – an arena shared by many, many other apps. Locksmith's interoperability is excellent; its internal Liquid engine is very good at injecting its code in the right places, without causing issues for themes or apps. Because of this, **in the vast majority of cases, you won't need to worry about Locksmith's compatibility**.

Having said that, there are a few places where there are specific points of compatibility or incompatibility.

### Locksmith and the Shop App

We're pleased to announce that Locksmith is now compatible with the Shop app. Shopify has updated its policies to allow stores using Locksmith to remain eligible for the Shop app, provided all other Shop app eligibility requirements are met.

Shopify's policies prohibit the use of password control and age verification apps, such as Advanced Registration, B2B Login Access Management, Login to View Price, and MagicPass Wholesale, for stores wishing to use the Shop app. However, Locksmith is now explicitly listed as an exception to this rule.

When you use Locksmith to lock certain products, your store will still remain eligible to display on Shop, and your locked products will not be included in your Shop Store. This ensures that merchants can maintain the control Locksmith provides while remaining eligible for the Shop app.

For more details on Shop app eligibility requirements, including prohibited product types or other restrictions, please refer to Shopify's [Shop app eligibility requirements](https://help.shopify.com/en/manual/online-sales-channels/shop/eligibility/requirements).\
\
**Variant Locks and the Shop App**

Locksmith’s variant-level locks don’t automatically remove locked variants from the Shop app, as the app manages visibility at the product level. While Locksmith adds a metafield to exclude locked products or collections from the Shop app, Shopify doesn’t support sales channel visibility controls for individual variants.

If a product includes locked variants, the Shop app will flag it with a warning (“This product is hidden by a third-party app”) and prevent it from being listed.

**Workaround for Variant Visibility on the Shop App**\
To keep unlocked variants available while hiding locked ones, you can create duplicate products:

* One product with only unlocked variants, published to the Shop app.
* Another product with locked variants, excluded from the Shop app.

This solution offers greater control but may increase inventory management complexity. For guidance on using duplicate products, refer to our tutorial on [price tiers](https://www.locksmith.guide/tutorials/more/price-tiers#using-product-duplicates-1). You can also explore [inventory management tips](https://www.locksmith.guide/tutorials/more/price-tiers#inventory).

## Officially unsupported apps

The following apps have known compatibility issues with Locksmith - although they _may_ work in some cases, with the correct settings.

* Any other **access control apps** that work in a similar way to Locksmith will almost certainly not work well alongside Locksmith, as they tend to inject code into the same areas of your theme.
* [Bold Custom Pricing: Wholesale](https://apps.shopify.com/customer-pricing) - but only when using [Locksmith's variant locking ](../tutorials/more/locking-variants/)and [manual locking](../tutorials/more/manual-mode.md) features.&#x20;
* Any app that controls price at the variant level - but only when using [Locksmith's variant locking ](../tutorials/more/locking-variants/)and [manual locking](../tutorials/more/manual-mode.md) features.&#x20;
* Locksmith's [manual locking](../tutorials/more/manual-mode.md) feature, and many times full-page locks, can _**not**_ generally be used to hide content being displayed by other third-party apps, including prices, buttons, widgets etc.&#x20;
* [Gempages](https://apps.shopify.com/gempages) - while it is possible to use the apps together _in some cases_, there are still many compatibility issues between the two apps.
* [Weglot](https://apps.shopify.com/weglot) - Locksmith's [location detection key condition](../keys/visitor-location-keys.md) is not compatible with Weglot, but you should otherwise be fine using both apps at the same time if not using location detection.

## Other areas of incompatibility

* Predictive searches - Locksmith generally cannot remove products from searches that dynamically show search results as you type. This includes built-in theme searches, and most apps that add predictive searches to your theme. That being said, it is possible to manage the appearance of specific products in store searches using product metafields: [more information on that here](https://community.shopify.com/c/ecommerce-marketing/hiding-a-product-from-search-engine/td-p/484788).
*   [The Checkout area](https://help.shopify.com/en/manual/checkout-settings) - Apps are pretty heavily limited in their ability to make changes to the checkout area, for security reasons. This means that Locksmith cannot restrict access to payment methods, shipping methods, shipping addresses, or anything else that is shown during the checkout process. If you wish to use Locksmith to restrict customers ability to check out,&#x20;

    you now have two options:

    1. **Use Locksmith on the cart page**, before checkout begins. This is the traditional approach—more on that [here](https://www.locksmith.guide/tutorials/more/protecting-against-bots).
    2. **Use our checkout validation feature**, which allows you to set up a single rule: products with a specific tag can only be purchased by customers who have a specific customer tag. This can help block unauthorized purchases—_without_ modifying the checkout UI itself. Learn how to set that up [here](https://www.locksmith.guide/tutorials/more/setting-up-checkout-validation-with-locksmith).
* Protecting against bot/resellers - Locksmith can’t fully prevent purchases made by bots or resellers—especially when they’re using direct-to-checkout links, which bypass the Online Store entirely. Since Locksmith works within the Online Store channel, it can’t intervene at the checkout layer directly.\
  \
  However, we _do_ now offer a **checkout validation** feature, which can help you block unwanted purchases **after** a customer reaches checkout. This is a powerful way to add another layer of control over who gets to buy what. Learn how to set it up here:\
  [Setting up checkout validation with Locksmith](https://www.locksmith.guide/tutorials/more/setting-up-checkout-validation-with-locksmith)\
  \
  There are also other strategies you can use alongside Locksmith to reduce the risk of bot purchases. While these aren't built into Locksmith itself, we've outlined a helpful approach here:\
  [Protecting against bots (without using Locksmith directly)](https://www.locksmith.guide/tutorials/more/protecting-against-bots)
* Locksmith cannot block RSS feeds from locked blogs.
* Locksmith can only hide products published to the **Online Store** sales channel, and absolutely cannot help with protecting, hiding, or restricting purchases on other channels.
* Locksmith is **not** compatible with [**headless or custom storefronts**](https://www.shopify.com/plus/solutions/headless-commerce) (e.g. sites built with Next.js, Hydrogen, custom frontend frameworks). Locksmith relies on Shopify's Liquid rendering engine and only works within the Online Store sales channel. In fully custom storefronts, there is no theme for Locksmith to work with, and no way for it to insert or enforce access logic.
