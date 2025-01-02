---
description: How to use the Locksmith app to sell digital content on Shopify
---

# Selling digital content on Shopify

If you have special content that you want to monetize, and it **lives in your Shopify store**, Locksmith allows you to sell access to it via in-store purchases.

{% hint style="info" %}
**Note**: Selling digital content on Shopify might mean different things for different merchants. If you are simply wanting to sell _digital files that are sent to customers via email_, [see Shopify's guide on this here](https://help.shopify.com/en/manual/products/digital-service-product/selling-services-or-digital-products).
{% endhint %}

## **Step 1: Create your restricted content**

Common choices for this are to add your restricted content to one of the following:

* [Shopify's built-in blogging engine for your store](https://help.shopify.com/en/manual/online-store/blogs). Keep in mind that you are not restricted to a single blog, so you can have a general access blog for your site news, etc, and still use a restricted blog for your digital content.
* [Pages - Shopify's built in webpages for your store](https://help.shopify.com/en/manual/online-store/themes/theme-structure/pages).
* Product page - You can build custom product templates that also house your restricted content and combine it with [Locksmith's manual locking](../keys/more/manual-mode.md), so that the restricted portion only reveals itself _after the product has been purchased_. This option has a less straightforward setup, but is still available if desired. If this is you, the best place to start is by contacting us via email at **team@uselocksmith.com**.

Again, for best results, your content should live in your online store. However, there are some other options that might apply to you:

#### Secure file viewing or downloading

This requires another provider, and we recommend Dropbox: [Get started with this on Dropbox' website](https://help.dropbox.com/files-folders/share/set-link-permissions).

#### Secure video viewing

You can embed the videos to be viewed just like any of your other content. However, if you want to secure this process, you'll need to enlist the help of a third party video viewing service. We recommend private and unlisted videos on Vimeo, but keep in mind that making your videos private/unlisted on Vimeo **requires a paid Vimeo plan**! [Get started with this on Vimeo's website](https://vimeo.zendesk.com/hc/en-us/articles/224817847-Manage-your-video-s-privacy-settings).

#### **Other general content that doesn't live in Shopify**

If your content must live elsewhere, consider using iframes to embed your content into a Shopify page, which you can then lock. This is more of an _advanced technique_ and would require someone familiar with code. Locksmith support won't be able to code this kind of thing for you. This is also **less secure** because the original source of the iframe can't be locked by Locksmith.

####

## Step 2: Create your "access product"

### Requiring a simple one time purchase

You'll need to have at least one product that is clearly marked as the product that customers will purchase, in order to gain access to the locked content. Something like this:

![](<../.gitbook/assets/Screen Shot 2022-08-08 at 7.18.04 PM.png>)

### Requiring a recurring subscription charge for access

You'll need to **use a third party app** to set up the subscription service. We recommend ReCharge or PayWhirl, and we have in-depth guides for those here:

{% embed url="https://www.locksmith.guide/tutorials/more/recharge" %}

{% embed url="https://www.locksmith.guide/tutorials/more/use-locksmith-and-paywhirl-together-to-grant-access-based-on-subscriptions" %}

## Step 3: Setting up the lock

[Create a lock](../basics/creating-locks.md) on your subscription product (the one created in the previous step). For your key, use the condition labelled **"has purchased...**" to create a key condition that permits access if the customer has purchased the appropriate product:

<figure><img src="../.gitbook/assets/Screen Shot 2022-11-08 at 8.43.31 PM.png" alt=""><figcaption></figcaption></figure>

{% hint style="info" %}
**Note**: You can also specify a time window, using the option labelled "_Only look for orders in the last..._". With this, you could require - for example - that the customer has made the purchase within the last 365 days. This is a good way to limit the access period time, but you should still [use a recurring subscription app](selling-digital-content-on-shopify.md#requiring-a-recurring-subscription-charge-for-access) if you want an automatically recurring charge.
{% endhint %}

## Step 4: Making sure your customers are signed in when purchasing your "access product"

In order for Locksmith to register that a customer has actually purchased your "access product", it is important that you require that customers are actually signed in when the purchase is made.&#x20;

You can do that with either of the following ways:

**Make customer accounts required for your entire store**: This means that everyone must be signed into your store when they check out. [More information from Shopify on doing this](https://help.shopify.com/en/manual/checkout-settings/customer-accounts#set-your-customer-account-preferences). This might be considered overkill for some merchants, so if that's the case, use the next option.

**Use Locksmith to require that a customer is signed in when purchasing your "access product"**: Pretty simple - just add a lock directly to the "access product" and use "Permit if customer is signed in" as the key condition. You can [edit the locked landing page for this product](more/customizing-messages.md) by editing the "Guest message content" message to let the customer know that they need to sign in before access. Or, if you prefer, you can even [employ manual locking](hiding-prices.md) if you just want to hide the add-to-cart button instead of the whole page.

## Optional: Directing customers to your content after purchase

You may wish to direct customers to the content that they just purchased.&#x20;

### ... in order confirmation emails

We can use some custom code to conditionally add a link to your locked content if the customer has purchased the right product.

To set this up: head to **Settings -> Notifications** in your Shopify admin, then select  "**Customer notifications**" and click the link for "**Order confirmation**". To edit the code for this email, you'll need to click the "**Edit code**" button in the top right of the page. Insert this code and adjust as needed:

```
{% raw %}
{% for line_item in line_items %}
  {% if line_item.title == "Some Product" %}
    <p>Thank you for your purchase! You may now access <a href="https://awesomeco.myshopify.com/pages/some-locked-page">this locked page</a>.</p>
  {% endif %}
{% endfor %}
{% endraw %}
```

Feel free to add multiple copies of this code, if you need to send the customer to one of several pages.

### ... and in the order confirmation page, after checkout

The code above can also be modified to suit the order confirmation screen that your customers see, right after completing an order.

To set this up, locate the "Additional content and scripts" box, near the end of the Settings -> Checkout area in your Shopify admin.

Use this code:

```
{% raw %}
{% for line_item in order.line_items %}
  {% if line_item.title == "Some Product" %}
    <p>Thank you for your purchase! You may now access <a href="https://awesomeco.myshopify.com/pages/some-locked-page">this locked page</a>.</p>
  {% endif %}
{% endfor %}
{% endraw %}
```

... adjusting the "Some Product" for your actual product title, and "/pages/some-locked-page" part for the address to your locked content.

Feel free to add multiple copies of this code, if you need to send the customer to one of several pages.
