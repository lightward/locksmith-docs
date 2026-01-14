---
description: >-
  In this guide, we'll show you how to set up a product so that it can only be
  purchased by customers who haven't yet made a purchase. This is great for
  samples and first time free products.
---

# Restricting a product so that it can only be purchased by new customers

{% hint style="info" %}
**Note:** This functionality requires the customer to have or create an account for access. There's more on that below.
{% endhint %}

You'll start by locking your product. You can search for it by name in the Locksmith search bar to create that lock.&#x20;

{% content-ref url="../../basics/creating-locks.md" %}
[creating-locks.md](../../basics/creating-locks.md)
{% endcontent-ref %}

Next, you'll need to set a key with two different conditions:&#x20;

* **Permit if the customer is signed in, and**
* **permit&#x20;**_**unless**_**&#x20;the customer has purchased "\*"**

For Locksmith to determine whether a customer has made a previous purchase, you must require  customers be signed in to access this product. This is done by adding an "**is signed in**" key condition to your key.

The second condition checks the customer's order history to see if they've made any purchases at all. For this, combine the "**has purchased...**" key condition with the "is signed in" key condition. Adding an asterisk to the "Look for products matching..." field tells Locksmith to check for any purchase in the customers history. Finally, ensure you enable the "invert" option on this condition to block customers who have made a purchase before.

{% content-ref url="../../keys/more/combining-key-conditions.md" %}
[combining-key-conditions.md](../../keys/more/combining-key-conditions.md)
{% endcontent-ref %}

Here's what that should look like:\
<br>

<figure><img src="../../.gitbook/assets/Screenshot 2025-06-12 at 6.37.08 PM.png" alt=""><figcaption></figcaption></figure>

When the full key is created, your key should look like this:&#x20;

<figure><img src="../../.gitbook/assets/Screenshot 2025-06-12 at 6.38.09 PM.png" alt=""><figcaption></figcaption></figure>

When this is all set, the customer will be prompted to log in when they try to access the product. If they already have a purchase in their history, they'll see the Access Denied message.&#x20;

You can edit the access messages on the Locksimth app's settings page, or editi the access messages for specific locks on the lock's settings page. Our guide on edditing access messages is linked below.

{% content-ref url="customizing-messages.md" %}
[customizing-messages.md](customizing-messages.md)
{% endcontent-ref %}

## Related articles:

{% content-ref url="../../keys/more/has-purchased.md" %}
[has-purchased.md](../../keys/more/has-purchased.md)
{% endcontent-ref %}

{% content-ref url="../selling-digital-content-on-shopify.md" %}
[selling-digital-content-on-shopify.md](../selling-digital-content-on-shopify.md)
{% endcontent-ref %}
