# Why is Locksmith adding information to my orders?

## Why is this happening?

For key conditions like passcodes, secret links, and location limits, Locksmith adds system information to the visitor's cart. **This is how we keep things fast** – the cart is the only place that Shopify can store visit-specific information.

This means that, on checkout, this data can make it all the way into your order records. If this is happening, you'll see something like this in your order information:

![](https://d33v4339jhl8k0.cloudfront.net/docs/assets/5ddd799f2c7d3a7e9ae472fc/images/5e1cee9704286364bc93d58c/5e1cee2660d81.png)

If you have a large number of keys in your shop, this value can get quite large!

{% hint style="info" %}
**Note:** You may see Locksmith notes in the order even if the order came from a customer _that does not have access_ to any of your locked content. Depending on your Locksmith settings, it may be necessary to cache the fact that the current customer does indeed not have access, which still keeps server pings to a minimum (and helps speed things up, as per the above).
{% endhint %}

## A (partial) solution

To allow Locksmith to automatically remove its information from an order's "Additional Details", head to your Locksmith _**Settings**_ area, and **enable the "Remove Locksmith information from orders" setting** next to _Advanced_ on the page. The setting looks like this:

<figure><img src="../../.gitbook/assets/Screenshot 2024-06-06 at 12.22.41 PM.png" alt=""><figcaption></figcaption></figure>

After you enable this setting, Locksmith may ask you for the additional permissions needed for updating your order records. Once you grant permission, Locksmith will take care of keeping its data out of your orders from that point onward.

## Locksmith notes still appearing in confirmation emails or third party apps?

{% hint style="info" %}
In most cases, this information won't be customer-facing. However, some third party invoicing apps will automatically include `cart.attributes` in their invoices. If your invoices include the Locksmith information in them, you may need to contact the support for your invoice service and ask them to exclude cart attributes from invoices.
{% endhint %}

The above setting does NOT help in all cases, particularly when your order information is sent off before Locksmith has the chance to remove its own information.

If you are having issues with this, your best bet is to contact us via email at **team@uselocksmith.com** and we can go through your other options with you.

## Removed Locksmith but still noticing order notes?

The notes are stored _on the customer's browser_, and the traces of this can still end up in the "Additional Details" section of some incoming orders. If you've deleted Locksmith, **seeing these in your orders is not an indication that Locksmith is still embedded in your theme**, just that the customer in question is running on the same browser "session" that they were running when you still had Locksmith installed on your store. You should see these drop off over time. However, if they are causing you issues, let us know at team@uselocksmith.com - we can help you out by adding a script to your theme that will delete the Locksmith cache from their browser as soon as customers visit (and before they place their next order).
