# A Locksmith Overview

Locksmith is a simple yet powerful tool to help you make sure the right people see the right things in your Shopify store. In the spirit of the name of our app - :sparkles: Locksmith :sparkles: - you'll be using "locks" to determine _what content_ in your store is restricted and using "keys" to denote _how, when, and who_ gets access.

## Locks

Locks are created using the search bar within our Locksmith app. You can search for most resources in your store by name. More in depth information on the in-app search bar here:

{% content-ref url="creating-locks.md" %}
[creating-locks.md](creating-locks.md)
{% endcontent-ref %}

A **lock** restricts access to something on your shop.

You can lock:

* Your entire shop
* Pages
* Products
* Collections
* Prices - [more information here](../tutorials/hiding-prices.md).
* The shopping cart
* The login page
* The registration page (type 'register' into the Locksmith search bar)
* [Product variants](../tutorials/more/locking-variants/)
* And more, with custom Liquid locks: Create a custom lock by clicking the _Start a Liquid Lock_ link above the Locksmith search bar..

After searching, once you **select the search result you want to hide and click Save**. You'll see some useful options, such as:

* Is the lock currently active?
* Should it also protect the products in this collection? (Disabling this means only the collection page itself will be locked.)
* Should it hide the collection, and it's products, from search results and other lists?
* Should it hide links to this resource from navigation?
* Under Advanced: Is this a manual lock? (More on that [here](../keys/more/manual-mode.md).)

You'll see different options depending on what type of resource you’ve locked.

## Keys

A **key** permits access to the locked resource based on your criteria. They are created on the lock page using the "+ Add key" button:<br>

<figure><img src="../.gitbook/assets/2025-02-12 15.32.53.gif" alt=""><figcaption></figcaption></figure>

Keys allow you to specify the exact conditions that give your customers access to the locked resource.

* Check out the full list of keys in the dropdown menu on a lock page.
* You can also create your own custom keys with Liquid. Create a custom key by choosing _custom Liquid_ from the keys menu.

More information on creating keys here:

{% content-ref url="creating-keys.md" %}
[creating-keys.md](creating-keys.md)
{% endcontent-ref %}

## Chaining (Combining) conditions together: OR versus AND

Locksmith gives you flexibility to add multiple keys and logically combine them together to create unique unlock conditions.

### OR

* When you set up your key, you can create another key right away, by clicking on Add Another Key. This button allows you to add another separate key to your lock.
* Keys connected by the OR operator can **individually** open your lock whether or not the conditions on the other keys are met.

This allows you to specify multiple different conditions that a customer can use to access. When used, a customer only needs to meet one of the conditions in order to access.&#x20;

Notice that there are **multiple key symbols**, and each key is preceded by "Permit if the customer..." text:

<figure><img src="../.gitbook/assets/Screenshot 2025-02-12 at 3.34.17 PM.png" alt=""><figcaption></figcaption></figure>

### AND

* Adds another condition to the current key. Choose your first key, and click on the "**+ add key condition**" below the condition. You'll see another selector to add your _next_ condition.
* If you connect key conditions with AND, **all** of those conditions must be met before the visitor gets access.

Notice that there is **only one key symbol for each key**, and each condition is inset under the symbol and text:

<figure><img src="../.gitbook/assets/Screenshot 2025-02-12 at 3.34.57 PM.png" alt=""><figcaption></figcaption></figure>

{% content-ref url="../keys/more/combining-key-conditions.md" %}
[combining-key-conditions.md](../keys/more/combining-key-conditions.md)
{% endcontent-ref %}

## Inverting Keys

Use the inverse of a key for added flexibility.

* In the key, click the "invert" box in the upper right.&#x20;
* This creates the opposite effect for the key.&#x20;
* For example: _Permit if the customer is **not** visiting from the United States_. --When used on the Locations key.

Our guide that explains this a bit more is here:

{% content-ref url="../keys/more/inverting-conditions-in-locksmith.md" %}
[inverting-conditions-in-locksmith.md](../keys/more/inverting-conditions-in-locksmith.md)
{% endcontent-ref %}

## The "force open other locks" setting

If you have created several locks that cover overlapping content (e.g. locked collections with some of the same products inside), you may want to turn ON the "force open other locks" key setting. This setting tells Locksmith to grant access to **all of the content covered by the current lock**, even if other locks might apply:

{% content-ref url="../keys/more/using-the-force-open-other-locks-setting.md" %}
[using-the-force-open-other-locks-setting.md](../keys/more/using-the-force-open-other-locks-setting.md)
{% endcontent-ref %}

## Setting up cart/checkout validation

Locksmith has a feature you can use to create a checkout rule that ensures that products tagged with a specific _product_ tag cannot be purchased without a specific _customer_ tag:

{% content-ref url="../tutorials/more/setting-up-checkout-validation-with-locksmith.md" %}
[setting-up-checkout-validation-with-locksmith.md](../tutorials/more/setting-up-checkout-validation-with-locksmith.md)
{% endcontent-ref %}

\
Let us know if you have any questions for us! You can contact us via email at **team@uselocksmith.com**.
