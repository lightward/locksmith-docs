---
description: >-
  How to use the Locksmith app to hide product prices and buy buttons on your
  Shopify Online Store
---

# Hiding product prices and/or the add to cart button

Locksmith can hide prices and buy buttons for locked products, so that customers can still browse your shop, but can only see prices and purchase products if certain conditions are met.

This is built into every lock's settings — no theme code required. Locksmith integrates directly with your theme's own price and buy-button code, so hiding follows the locked products wherever your theme displays them.

Here is an example of a product page that has been set up with Locksmith to hide prices:

![](../.gitbook/assets/HidingProductPrices-LoginToPurchase.png)

Then, when the customer meets the conditions, the product pages will appear normally:

![](../.gitbook/assets/HidingProductPrices-AddToCart.png)

{% hint style="info" %}
**Note:** The results may look different depending on your Locksmith conditions, theme, or other settings.
{% endhint %}

Use the following two steps to set it all up:

## 1. Create a lock

The first step is to create a lock that covers the products that you would like to hide prices on. To do this, open up Locksmith and use the search bar on the main page of the app. If this is all of your products (most common), you can simply search for "all" and choose the "All Products" collection:

{% hint style="warning" %}
**Warning**: make sure to choose "Collection: All" and **not** "Collections Listing"
{% endhint %}

If you are only wanting to apply price hiding to some of your products, you can instead create a lock on different collection(s) or products that you want prices hidden for.

Once you've created the lock, you'll choose the conditions for access. Many merchants use the "Permit if customer is tagged with..." key condition, which lets you manually approve accounts for price access by adding a customer tag:

That's the most common way to set it up, but you have the freedom to choose whatever key conditions work for your setup.

## 2. Turn on hiding

In the lock editor, find the **Price & add-to-cart hiding** card, just below your keys. It has two settings:

* **Hide buy buttons** — hides the add-to-cart button, dynamic checkout buttons (like "Buy it now"), and quantity selectors for the locked products. This is what keeps locked products out of the cart.
* **Hide price** — hides the locked products' prices.

When you turn either setting on, Locksmith scans your published theme to find the places where it can integrate, and shows you a compatibility result for each setting. Save your lock, and Locksmith updates your theme automatically — and re-checks your theme every time it installs from then on, so theme updates are picked up on their own.

Where the buy buttons were, your visitors will see your lock's message content instead (a "Log in to purchase" button, a passcode prompt, or whatever fits your key conditions) — styled to match your theme.

## What gets hidden

Wherever your theme renders the locked products through its own templates: the product page, collection and search grids, featured-product sections, and quick-view popups. Unlocked products are never affected — hiding follows the locked products individually.

## Good to know

{% hint style="warning" %}
**Hiding prices without hiding buy buttons?** Prices always appear in the cart and at checkout — Shopify doesn't provide a way to hide them there. If you're hiding prices, we recommend hiding buy buttons too, so locked products can't reach the cart in the first place. The app will remind you about this combination.
{% endhint %}

{% hint style="warning" %}
While Locksmith hides the price visually, it may still be possible for someone viewing the page source (or using the browser console) to find it. This is because of things like SEO markup and analytics tools, which reproduce the price in the source — but not visually on the page — for their own usage.
{% endhint %}

{% hint style="info" %}
Prices displayed by **third-party apps** (page builders, currency converters, wishlist apps, and so on) render outside your theme's own code, so they aren't hidden automatically — but Locksmith support may still be able to help with these. Feel free to reach out.
{% endhint %}

{% hint style="info" %}
If your theme already contains **hand-written Locksmith code** (from the manual approach linked at the end of this page), the automatic settings may not work well alongside it — the app will show a warning if it detects this. Write to us if you'd like help transitioning.
{% endhint %}

## If your theme shows "Incompatible"

Every theme is different, and occasionally Locksmith won't find a spot it can safely integrate with. If that happens, the app says so rather than guessing.

**This isn't the end of the road.** Hiding can almost always still be set up by hand, and we're glad to do that work for you — [write to us](../policies/contact.md) and we'll get your theme sorted.

### Themes we know the automatic settings can't integrate with

* **Palo Alto** (by Presidio) — both prices and buy buttons.

These themes build their prices in a way Locksmith's automatic integration can't hook into safely, so the app reports Incompatible instead of guessing. Manual code still works on them, and we'll write it for you.

If your theme isn't on this list and still reports Incompatible, that's worth telling us about — it usually means we can add support for it.

## Advanced: adjusting what Locksmith found

The scan's results are visible — and editable — on your theme's hiding profile page (**Themes → your theme → hiding profile**). Each automatic definition can be adjusted (its Liquid variable, whether it shows your replacement message), removed, or restored, and there's a reset if you'd like to return to the theme defaults. Your edits survive re-scans.

## Setting it up by hand

If the automatic settings don't fit your store — an Incompatible theme, prices rendered by another app, or a message you'd rather place yourself — price hiding can also be built directly into your theme's code:

{% content-ref url="more/hiding-prices-manually.md" %}
[hiding-prices-manually.md](more/hiding-prices-manually.md)
{% endcontent-ref %}
