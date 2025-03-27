---
description: >-
  Granting access to content in your store only after the appropriate purchase
  has been made
---

# "Has purchased..." key

Locksmith allows you to check for a purchase of a specific product and _only_ grant access to your locked content if an applicable purchase has been made.

{% hint style="warning" %}
This key condition can only account for a customer's latest 50 orders (and in some cases only the latest 25). Learn more about this in the [Limitations](has-purchased.md#limitations) section.
{% endhint %}

{% hint style="info" %}
This key condition relies on [Shopify's customer account system](https://help.shopify.com/en/manual/customers/customer-accounts), the same that's used throughout Shopify for all Shopify stores. Customer accounts need to be enabled for your store in order for this key condition to function correctly.

Additionally, when this key condition is used, Locksmith will automatically prompt guests to sign in to their customer account when they visit a locked page.

[Learn more about customer account keys](../customer-account-keys.md)
{% endhint %}

## Setup

Once you [create a lock](../../basics/creating-locks.md) that covers the content that you want to require a purchase for, click the "+ Add key" button. In the condition selector that appears, select "if the customer has purchased...".

<div data-full-width="false"><figure><img src="../../.gitbook/assets/Screenshot 2024-05-29 at 2.28.28 PM.png" alt=""><figcaption></figcaption></figure></div>

Locksmith will examine the customer's order history for products matching what you enter.

{% hint style="warning" %}
**Important**: Whether you choose to enter the SKU, title (shown above), variant ID, or product tag, **they are all case sensitive**!
{% endhint %}

<figure><img src="../../.gitbook/assets/Screenshot 2024-05-29 at 2.31.22 PM.png" alt=""><figcaption></figcaption></figure>

## Options

#### Maximum quantity purchased

Sets a maximum allowed purchase amount. When used, Locksmith will only grant access if the customer has not yet purchased _this many_ units of the product

#### Only look at orders in the last...

Allows to you specify how far back, in days, you would like Locksmith to check for the purchase of the specified product. E.g. you may want to only allow access for 30 days after purchase.

#### Ignore cancelled orders

When ON - Cancelled orders will not fulfill the requirements for access. Default: ON.

#### Ignore unfulfilled or partially fulfilled orders

When ON - Unfulfilled orders will not fulfill the requirements for access. Default: OFF, most merchants will want to leave it this way.

#### Ignore orders that are not fully paid

When ON - Only orders with a payment status of "Paid" will fulfill the requirements for this lock. Default: ON.

{% hint style="danger" %}
**Caution**: This setting often causes issues for merchants _who are testing out their locks_. Consider turning this setting OFF while testing, but back ON for general use.
{% endhint %}

## Inverting this key condition

Like all key conditions, this one can be inverted. This is useful to verify that a customer has NOT yet purchased a specific product:

{% content-ref url="inverting-conditions-in-locksmith.md" %}
[inverting-conditions-in-locksmith.md](inverting-conditions-in-locksmith.md)
{% endcontent-ref %}

On its own, the inverted "_**unless**_ the customer has purchased..." key will grant access to anyone who has not purchased the product, including non-signed in customers. To require customers sign in, you'll want to _combine_ the "_**unless**_ the customer has purchased..." key with the "is signed in" key:

{% content-ref url="combining-key-conditions.md" %}
[combining-key-conditions.md](combining-key-conditions.md)
{% endcontent-ref %}

## Limitations

This key condition can only account for the 50 most recent orders for the current customer. In some cases, it can only account for the most recent 25 orders instead.

The stricter 25-order limit comes into play when a customer navigates to a URL that includes a page number, e.g. a URL with "?page=2" in it. This is because a page number in the URL limits Locksmith's ability to ask Shopify for the maximum number of orders possible (i.e. 50), leaving Locksmith to work with the default number of orders (i.e. 25).

{% hint style="info" %}
To work around this limit, consider setting up your Shopify store to auto-tag customers according to their order history. These customer tags can then be used in new Locksmith keys which grant access based on those tags.

Locksmith doesn't have customer auto-tagging built in, so merchants generally accomplish this by involving a second app.

* [Shopify Flow](https://apps.shopify.com/flow) has options for auto-tagging, and is available for free for all stores.
* [Mechanic](https://apps.shopify.com/mechanic) (also made by Lightward) has [a variety of tasks](https://tasks.mechanic.dev/?q=tag%20customer) that can be used for this purpose. Like Locksmith, Mechanic is also available under Lightward's [Pay What Feels Good](https://lightward.com/pricing) pricing policy.
{% endhint %}

## Related articles

{% content-ref url="../customer-account-keys.md" %}
[customer-account-keys.md](../customer-account-keys.md)
{% endcontent-ref %}

{% content-ref url="../../tutorials/selling-digital-content-on-shopify.md" %}
[selling-digital-content-on-shopify.md](../../tutorials/selling-digital-content-on-shopify.md)
{% endcontent-ref %}
