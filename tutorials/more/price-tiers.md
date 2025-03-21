---
description: >-
  How to use the Locksmith app set up restricted prices levels on your Shopify
  Online Store
---

# Setting up multiple price tiers

Many, many merchants use Locksmith for managing different price levels **within the same store.**

Frequently, this means _wholesale and retail_. We'll use those terms in the rest of this article, but feel free to substitute them for whatever applies to your situation - for example:

* Members vs Non-members
* EU customers Vs. Non-EU customers

...or any other situations that require price tiers.

## **Customer management**

Before setting up your product tiers, you'll need to decide how you want your customers to gain access to the separate tiers. The most common way to do this is to use approved customer registrations. More information on setting this up here:

{% content-ref url="../approving-customer-registrations.md" %}
[approving-customer-registrations.md](../approving-customer-registrations.md)
{% endcontent-ref %}

So in this case, you would use customer tags to denote the customer tiers. So, for example, customers with the "wholesale" customer tag are considered wholesale customers, while customers without the "wholesale" tag are regular/retail customers.

## **Deciding between product duplicates or variants**&#x20;

Using Locksmith to sell products at two different prices levels means that **your products need to be duplicated in some way**. This can be achieved using either product duplicates _or_ by using variant tiers.&#x20;

Keep in mind that Locksmith itself does not create these alternate versions. No matter which one you choose, the work to duplicate the products will be done on your end.

### [**Using Product duplicates**](price-tiers.md#using-product-duplicates)

**Pros** -

* Allows you to have distinct sections in your store that are dedicated to different types of customers.&#x20;
* A straightforward approach

**Cons** -

* Introduces [collection filtering issues](../../faqs/faq-i-see-blank-spaces-in-my-collections-and-or-searches-when-locking.md).

### [**Using variant tiers**](price-tiers.md#using-variants)

**Pros** -&#x20;

* Uses the same products, collections, and navigation menus
* Avoids [collection filtering issues](../../faqs/faq-i-see-blank-spaces-in-my-collections-and-or-searches-when-locking.md)!

**Cons** -

* This is not a good option if your products already have many variants. Adding a price tier variant essentially doubles the number of product variants that each product has. The Shopify-wide **maximum** number of variants per product is 100.
* Can be seen as more complicated since managing individual variants is less straightforward than managing products.&#x20;
* Variant locks are **not** compatible with [passcode keys](../../keys/passcode-keys.md).&#x20;

## Option 1 - Using product duplicates <a href="#using-product-duplicates" id="using-product-duplicates"></a>

### Basic steps:

1. Use your Shopify admin area to create duplicate versions of every single one of your products that will be sold at more than one price.&#x20;
2. Once your product duplicates are created, create a collection of wholesale-only products - no mixing in other products from other parts of your store! Don't forget you can use[ Shopify's automated collection feature here](https://help.shopify.com/en/manual/products/collections/automated-collections).
3. Next, use Locksmith to [create a lock](../../basics/creating-locks.md) on your wholesale collection. This lock will cover all of the products in that collection.
4. On the next screen, use the "Keys" section to create a key that corresponds to [the method of access that you decided on earlier](price-tiers.md#customer-management).

That's it for the basic setup! There are some optional steps below...

### Optional: Locking your retail products

You may want to consider also adding a lock to your retail products, so that wholesale customers don't get confused after they sign in. We'll use a new lock with the opposite condition, to make sure that the customer can only view your retail products if they're  _not_ approved.

**To add a corresponding lock to your retail products**, following these steps:

1. Create a collection that covers all of your non-wholesale products.&#x20;
2. [Create a lock](../../basics/creating-locks.md) on this new collection: search for it by name in the Locksmith app
3. On the next screen, use the "Keys" section to create that has the [exact inverse condition of the key you created above](../../keys/more/inverting-conditions-in-locksmith.md).

That's it! Your wholesalers will now be prevented from seeing retail products once they're logged in. (Note: this trick doesn't prevent the wholesaler from arriving at your shop as a guest, adding retail products to the cart,  _then_ logging in to their wholesale account!)

### **Optional: Pointing your wholesale customers to your wholesale collection**

Now that you have a wholesale collection set up, you will want give your wholesale customers a way to find their content. You can do this by adding a "Wholesale" link to your navigation menu, that points directly to the Wholesale collection. This link will be visible to everyone, but once it's clicked, Locksmith will ask for access credentials.

Locksmith will automatically use the login template and style from your theme. The message is easily customizable:

{% content-ref url="customizing-messages.md" %}
[customizing-messages.md](customizing-messages.md)
{% endcontent-ref %}

### Optional: Hiding wholesale product prices

If you prefer to **leave your wholesale offerings open to the public**, but still want to hide the prices, this is also possible!&#x20;

This requires a few more steps, and we have a guide that covers that kind of thing here:

{% content-ref url="../hiding-prices.md" %}
[hiding-prices.md](../hiding-prices.md)
{% endcontent-ref %}

## Option 2 - Using variant tiers <a href="#using-variants" id="using-variants"></a>

To create price tiers using product variants, you'll need to use your Shopify admin area to **create an "Audience" option** _on each of your products that you want to add tiers to:_

<figure><img src="../../.gitbook/assets/Screenshot 2024-01-07 at 8.34.36 PM.png" alt=""><figcaption></figcaption></figure>

{% hint style="info" %}
**Note**: You can use whatever Option or value names you prefer! Just make sure that you _use consistent naming_ on each of your products. This will make creating the locks easier. If you have a large number of products, we recommend that you use the [export/import CSV method.](https://help.shopify.com/en/manual/products/import-export)
{% endhint %}

Next, **create a variant lock in the Locksmith app**:

![](https://d33v4339jhl8k0.cloudfront.net/docs/assets/5ddd799f2c7d3a7e9ae472fc/images/623f9cf4c1688a6d26a79d99/file-NA1ytkqrFL.png)

**Create a key**. If you are using customer tags to grant access, that will look like this:

<figure><img src="../../.gitbook/assets/Screenshot 2025-03-20 at 5.44.02 PM.png" alt=""><figcaption></figcaption></figure>

Additionally, **create a corresponding lock for the retail variant**. You should end up with two locks:

![](https://d33v4339jhl8k0.cloudfront.net/docs/assets/5ddd799f2c7d3a7e9ae472fc/images/623f9eea2ce7ed0fb0919f63/file-qZ4NUAbzkJ.png)

## Inventory

Managing inventory across multiple price tiers is a very common concern

**Separate inventory for each tier**

Some merchants love the ability to set inventory separately for wholesale and retail customers. If that is you, then you're already good to go, no matter which option you have chosen, since each product and variant has separate inventory.

**Same inventory across tiers**

If you have more retail purchases than wholesale, one option is to let Shopify track the retail products, and manually update your retail inventory when you receive a wholesale order.

If you absolutely need to sync inventory across your products or variants, you'll need to get another app involved. Namely, [the Mechanic app](https://apps.shopify.com/mechanic)! This app is made by the same folks here at Locksmith. It offers several automation "tasks" for syncing inventory levels:

* [Sync inventory for shared SKUs](https://usemechanic.com/task/sync-inventory-for-shared-skus)
* [Sync inventory across product variants](https://usemechanic.com/task/sync-inventory-across-product-variants)

{% hint style="info" %}
**Note**: if you are concerned about incurring a lot of extra cost by adding another app for managing inventory, both Locksmith and Mechanic have a "Pay what feels good" pricing policy. So, we're confidant that we can get you at a price that feels good while using both apps. [See the policy here](../../policies/pricing.md).
{% endhint %}
