---
description: >-
  How to restrict access to the content in your Shopify Online Store based on
  the location of the IP visitor's IP address
---

# Visitor location keys

Locksmith can help you restrict access by _automatically_ detecting the location of the **IP address** of a visitor. The location condition supports many type of locations including:

* **Regions** (eg: North America, Asia, Antarctica)
* **Countries** (eg: Australia, Germany, Nauru)
* **Provinces/States** (eg: Texas, Nova Scotia, Sikkim)
* **Cities** (eg: Montreal, Chicago, Tokyo)
* **Towns** (eg: Český Krumlov, Santa Maddalena)

{% hint style="warning" %}
**Important**: Locksmith uses the word "location" in the generic sense. This "location key" feature from Locksmith does NOT correspond to the[ inventory management scheme that Shopify also calls "Locations"](https://help.shopify.com/en/manual/locations). Consider using [Shopify's "Markets" feature](https://help.shopify.com/en/manual/markets/managing-markets), if you need to restrict purchasing based on inventory location.
{% endhint %}

{% hint style="info" %}
**Also note**: If your store _is_ using the "[Shopify Markets](https://help.shopify.com/en/manual/markets)" feature, and you are looking for a way to automatically show content based on which "market" the customer is visiting from, we have [a dedicated guide to doing this here](https://www.locksmith.guide/tutorials/more/shopify-markets).
{% endhint %}

## Giving access to locations

Once you've created your lock, choose the Location key:

<figure><img src="../.gitbook/assets/Screenshot 2025-03-20 at 4.59.38 PM.png" alt=""><figcaption></figcaption></figure>

Next, in the key configuration box,  search for the location:&#x20;

<figure><img src="../.gitbook/assets/Screenshot 2025-03-20 at 5.01.15 PM.png" alt=""><figcaption></figcaption></figure>

Click the name of the area to add it to the key. Feel free to add additional locations:&#x20;

<figure><img src="../.gitbook/assets/Screenshot 2025-03-20 at 5.01.56 PM.png" alt=""><figcaption></figcaption></figure>

\
Save the key, and you're all set. Those locations will be given access to your locked content, but everyone else around the world won't.

## Hiding FROM locations

\
To make sure some locations _don't_ see your locked content, you'll use the same method.&#x20;

Add your location(s) to the key like normal, but this time click the "invert" box in the lower left of the key box:&#x20;

<figure><img src="../.gitbook/assets/Screenshot 2025-03-20 at 5.02.53 PM.png" alt=""><figcaption></figcaption></figure>

The result here is that customers around the world can get access to your locked content, all except for those in that location.&#x20;

## SEO Limitations

It is important to know that content protected under these key types will not be indexed properly, when used normally. This will strongly effect your SEO for any pages that are covered by these locks. This is because of Google's rules against cloaking. That is to say - we are not allowed to show different content to a search engine vs a regular visitor, as per Google regulations.

If you are using Location or IP address keys, and you still want your content to be indexed, you still have options!

If you have specific products that are not available in certain countries: You'll need to use manual locking to hide only the add-to-cart button. [More info on that here](../tutorials/hiding-prices.md).

If you have different versions for different countries: You can create separate versions of your products using variants, and setting up Locksmith to hide the variants depending on who is visiting. [More info on that here](../tutorials/more/locking-variants/).

## Shipping Address Limitations

Locksmith can only protect the frontend of your Online Store, and cannot extend its protections to Checkout. So, this does not prevent customers who have IP addresses located in an allowed location from choosing a specific shipping address that is in a blocked location at checkout. Locksmith is not able to control shipping destinations during checkout. For this, [check out Shopify's Shipping Profiles feature](https://help.shopify.com/en/manual/shipping/setting-up-and-managing-your-shipping/shipping-profiles).

{% content-ref url="../faqs/more/why-isnt-my-remote-key-condition-working.md" %}
[why-isnt-my-remote-key-condition-working.md](../faqs/more/why-isnt-my-remote-key-condition-working.md)
{% endcontent-ref %}

