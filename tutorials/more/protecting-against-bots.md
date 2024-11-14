---
description: >-
  A strategy to protect your products from bots and unapproved resellers
  purchasing from your Shopify Online Store
---

# Protecting against bots

{% hint style="warning" %}
**This is a legacy guide**. This technique may still be useful for some, but for those wishing to add a "Checkout rule" to their store via Locksmith, see our guide here:

[setting-up-checkout-validation-with-locksmith.md](setting-up-checkout-validation-with-locksmith.md "mention")
{% endhint %}

Many merchants that sell collectors items, limited edition items, or other types of highly exclusive items are plagued by bots purchasing their products, and come to Locksmith for help.

**Without using a checkout rule, Locksmith is NOT able to prevent bots and other unapproved resellers from purchasing from your store**.

This is because direct-to-checkout links, which allow products to be purchased without even visiting the Online Store, exist within the Shopify platform, and it's not possible for apps to get involved with this layer.

{% hint style="info" %}
**Note**: This also applies to merchants wanting to use Locksmith to give away free items to select customers. As soon as bots pick up on the presence of your free items, they may attempt to buy your entire stock, _even if those items are protected by Locksmith_.
{% endhint %}

While Locksmith itself cannot help here, there is a way you can prevent this from happening _without the need for any apps_.

## The solution: discount codes

So the general strategy here is to set your products up so that the _public_ price is something pretty high - **a price high enough so that the bots will ignore it**. Then, you'll use [Shopify's Discount feature](https://help.shopify.com/en/manual/discounts) to create a discount to bring the price back down to the original price that you'd like to sell at.

Thankfully, Shopify allows you to create discounts that can _only_ be used by specific "customer segments". [More information on creating customer segments here](https://help.shopify.com/en/manual/customers/customer-segmentation/customer-segments).&#x20;

So, for example, you could create a customer segment that's based on a specific customer tag:

![](<../../.gitbook/assets/Screen Shot 2022-07-29 at 12.15.32 PM.png>)

And then give the customer segment a description name:

![](<../../.gitbook/assets/Screen Shot 2022-07-29 at 12.16.00 PM (1).png>)

When setting up the discount code, use the "Customer eligibility" section to select the customer segment that can use this discount:

![](<../../.gitbook/assets/Screen Shot 2022-07-29 at 12.17.24 PM.png>)

The result of this is that you now have an avenue to make sure that only the customers you designate have a pathway to purchase that is secured all the way to the completion of the sale.&#x20;

You can absolutely use this strategy without further involvement with any apps, including Locksmith. The customers will simply use the product pages as normal, and enter the discount codes at checkout.

Again, the price they'll see here will be higher than what the customer is most likely expecting, so make sure you do everything you can to communicate with your customers about using the discount code. You can do this in the product description, in customer mailers, or when they contact you (more on that below).

That's it for the basic setup!&#x20;

## How Locksmith _can_ help

_Optionally_, Locksmith can still help get your product pages to a place that helps direct your non-bot customers to the right place. Locksmith has features that will help hide the price and add-to-cart buttons so that the public facing price doesn't scare customers away that stumble onto your product pages. More information, and set up guide, on hiding the price and add to cart button here:

{% content-ref url="../hiding-prices.md" %}
[hiding-prices.md](../hiding-prices.md)
{% endcontent-ref %}

So basically, when set up correctly, your customers would see something like this when they land on your product pages:

![](<../../.gitbook/assets/Screen Shot 2022-07-29 at 1.04.12 PM.png>)

{% hint style="info" %}
**Note**: You have flexibility in what you want the link to say, and where it points your customers to.
{% endhint %}

Then, when signed in with an approved account, they will be able to add to cart and purchase.

![](<../../.gitbook/assets/Screen Shot 2022-07-29 at 12.34.58 PM.png>)

{% hint style="warning" %}
**Remember**: Locksmith alone is not enough to prevent bots from purchasing the products out from under you - you'll need to combine this with the discount method outlined above.
{% endhint %}



For questions or help with setup, contact us via email at **team@uselocksmith.com!**
