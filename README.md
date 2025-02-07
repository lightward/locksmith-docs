---
description: >-
  Basic guide to using the Locksmith app to restrict access to content in your
  Shopify Online Store
---

# Quick Start

Locksmith is a tool for merchants on Shopify to restrict access to the content in the "Online Store" sales channel of their Shopify store. It's a simple tool, and in some cases can be set up in only a few minutes.

### To get started, open up Locksmith from your apps list.

You'll be presented with the main page. The "Add new lock" section will be your first stop:

<figure><img src=".gitbook/assets/Screenshot 2024-02-25 at 20.49.16.png" alt=""><figcaption></figcaption></figure>

For a more detailed overview of what Locksmith is and how the app works, see our guide linked below:

{% content-ref url="basics/overview.md" %}
[overview.md](basics/overview.md)
{% endcontent-ref %}

### Create your first lock

To restrict access to something in your store, simply type in the name of a product, collection, page, variant, etc - you'll immediately start seeing search results. Alternatively, select a type from the dropdown to filter your search by resource type. Select the resource that you want, to place a lock on it:

![](.gitbook/assets/addProductResourceSearchBar.png)

{% hint style="warning" %}
**Note:**  This input does not work with URLs.
{% endhint %}

More information on (and help troubleshooting) lock creation here:

{% content-ref url="basics/creating-locks.md" %}
[creating-locks.md](basics/creating-locks.md)
{% endcontent-ref %}

### Create a key

On the next page, press the "Add key" button to create a key:

<figure><img src=".gitbook/assets/Screenshot 2024-04-15 at 13.12.33.png" alt=""><figcaption></figcaption></figure>

Next, add at least one condition to your key. The most commonly-used key conditions will show up first, but **you can search or keep scrolling for more options.**

<figure><img src=".gitbook/assets/Screenshot 2024-04-15 at 13.11.26.png" alt=""><figcaption></figcaption></figure>

Simply select the condition that you want to use. Some conditions may ask you for some additional settings, you'll be prompted if appropriate.

**There are over 20 out-of-the-box key conditions**, and you can even create custom conditions! You can also combine key conditions in different ways to create unique access scenarios. For more information on that, and the complete list of key conditions, see the page here:

{% content-ref url="basics/creating-keys.md" %}
[creating-keys.md](basics/creating-keys.md)
{% endcontent-ref %}

{% hint style="info" %}
**Note**: If you don't want to hide your product pages entirely, and instead only want to hide specific content on the product page, such as the prices or add-to-cart, we call this "manual locking", and it takes a couple extra steps beyond this guide. To get started with this, [check out our guide on that here](tutorials/hiding-prices.md).
{% endhint %}

### Wait for Locksmith to install to your theme

After you **save the lock**, Locksmith will usually take about 5-10 seconds to automatically update your theme. A green status bar will briefly show at the bottom of the page - once it is gone, the installation has finished.

You can now navigate to your locked content on your store front, and you should immediately see the restriction is now in place. Locksmith will automatically show the appropriate content, using the styling from your theme, on the page. The access denied content will correspond to the key condition that you used.&#x20;

So, for example, if you chose a condition requiring a sign-in:

![](.gitbook/assets/signInExample.png)

Or, if you chose a passcode-only entry method, you'll see a different prompt:

![](.gitbook/assets/passcodeExample.png)

Each key condition type will have a slightly different landing page, the above two examples are not a complete list. The messages displayed on these pages can be customized as much as you need:

{% content-ref url="tutorials/more/customizing-messages.md" %}
[customizing-messages.md](tutorials/more/customizing-messages.md)
{% endcontent-ref %}

{% hint style="danger" %}
**Important**: The Locksmith app only restricts content inside the "Online Store" sales channel. It won't work inside of other sales channels such as the Buy Button or the Wholesale sales channel. Additionally, Locksmith and the Shop App sales channel are incompatible and cannot be used at the same time.
{% endhint %}
