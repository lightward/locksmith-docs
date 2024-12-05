---
description: >-
  Create a theme hiding profile to lock specific parts of your Shopify themes
  according to your Locksmith lock conditions
---

# How to hide theme sections, blocks, and snippets

By default, when you create a lock on a resource in your Shopify store, Locksmith prevents access to the direct URL for that resource only. E.g. creating a lock on a product prevents access to the content on the product page. For most locks, you can also directly toggle hiding inside of:

* Navigation menu links. [More information here](https://www.locksmith.guide/tutorials/more/hiding-navigation-links-for-locked-resources).
* Search results. [More information here](https://www.locksmith.guide/faqs/can-locksmith-hide-content-from-my-in-store-search).
* For products: product and collection grids/lists. [More information here](https://www.locksmith.guide/tutorials/more/hiding-products-from-product-grids).

If you are wanting to hiding anything beyond the above, or just want more granular control over what is hidden, you can use our "Theme hiding profile" feature.

## 1. Accessing theme hiding profiles

Because each theme is different, hiding profiles are added **per theme**. So, this feature is accessed via the Themes tab. Once there, press the "Edit theme hiding profile" button.&#x20;

<figure><img src="../../.gitbook/assets/Screenshot 2024-12-05 at 14.54.00 (1).png" alt=""><figcaption></figcaption></figure>

{% hint style="info" %}
You can also edit hiding profiles for unpublished themes by using the ellipses ("...")  button next to each unpublished theme shown.
{% endhint %}



## 2. Adding a hiding definition

A hiding definition hides a section, block, or snippet in your theme. One of the most common use-cases for this is to hide prices and/or add-to-cart buttons. To add hiding definitions for this use-case, use these steps:

1. Press the "Add new definition" button
2. Leave the "Selection method" at the default (Add by name)
3. In the "Name..." box, type in "price". Locksmith will show you all of sections, blocks, or snippets that have price in the name:

<figure><img src="../../.gitbook/assets/Screenshot 2024-12-05 at 15.13.05.png" alt=""><figcaption></figcaption></figure>

4. &#x20;Add each of the desired definitions. You'll need to repeat the search for each one.
5. Repeat the above 4 steps for every type that you want to hide. E.g. "quantity", "buy", etc. If you are hiding price and buy buttons, you will likely end up with something like this:

<figure><img src="../../.gitbook/assets/Screenshot 2024-12-05 at 15.21.24.png" alt=""><figcaption></figcaption></figure>

{% hint style="info" %}
If your theme is one of the free themes made by Shopify from the Shopify theme store, **and you are wanting to use this feature for price hiding or buy buttons hiding**, try the "theme hiding presets". Instead of choosing "Add by name" under "Selection method", choose "Add from theme presets", then choose either "Price" or "Buy buttons" and press "Add presets". You'll need to add add both preset if you are hiding both prices and buy buttons! Please note that presets will only match newer versions of these themes.
{% endhint %}



## 3. What to use for "Liquid variable"

Locksmith's locks work by looking at a specific variable in the theme and checking to see if that variable contains something that you've placed a lock on. "Liquid variable" is how you specify which Liquid object in the theme Locksmith should base the hiding on. Most use-cases for this feature are geared towards products and _most of the time_, theme developers simply use `product`. However, there are some exceptions. A "card product" file might assign to a variable called `card_product`, or a "featured product" file might use `featured_product`. \
\
If you are not locking a product, you'll want to use the applicable variable (`collection`, `cart`, `blog`, `shop`, etc).

Ultimately, what you put here depends on what is used in the theme, and if you want to ensure that this is right, **it will be necessary to open up your theme code editor to check what is used there**.

## 4. How "Replace" works

If the "Replace" checkbox is toggled on, instead of just hiding the content, Locksmith will replace it with the access denied message or access prompt. These messages can be customized in your locks. [More information about customizing messages here](https://www.locksmith.guide/tutorials/more/customizing-messages).

## 5. Save and test!

Once you've added all of your hiding definitions, save your hiding profile. Locksmith will perform an installation to the theme. Once the installation finishes, make sure to verify that everything is working as expected on the frontend of your store!&#x20;

{% hint style="info" %}
You can head back to the themes tab to check the status of a specific installation, whether it be for a published theme or not. Additionally, on the Themes tab, you can preview unpublished themes by pressing "Preview" under the ellipses ("...")  button.
{% endhint %}

## How is this different from Locksmith's "manual locking"

Hiding profiles are intended as a replacement for [manual locking](manual-mode.md), which is when Locksmith code is manually added to the theme. Hiding profiles function in almost the exact same way on the backend. Some differences are:

* Hiding profiles are easier to setup
* Hiding profiles don't need manual removal from your theme, they remove themselves when Locksmith is disabled/uninstalled.
* Hiding profiles rely on the modularity of Online Store 2.0 themes, so manual locking will still be necessary for legacy themes
* If the hiding target is not contained within a section, block, or snippet, manual locking will still be necessary
