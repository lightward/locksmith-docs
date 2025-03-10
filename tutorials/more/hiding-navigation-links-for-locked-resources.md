---
description: >-
  Use the Locksmith app to hide navigation links in your Shopify Online Store
  channel
---

# Hiding navigation links for locked resources

Locksmith allows you to hide _navigation links that point to locked resources_ - only showing them to visitors with access to your locks. This is turned on via the settings on your lock page:

<figure><img src="../../.gitbook/assets/Screenshot 2024-02-20 at 12.26.19 PM.png" alt=""><figcaption><p>The label may look slightly different depending on which resource type you are locking.</p></figcaption></figure>

You'll find this option on locks for the following resource types:

* Product
* Collection
* Page
* Blog
* Liquid locks

## Limitations

* Using **third party apps** to create your navigation will likely prevent Locksmith from being able to correctly hide your navigation links.
* Locksmith is generally not able to hide navigation menu links that are a part of a **mega menu**, whether via third party apps or a theme setting.&#x20;
* Locksmith is not able to hide empty navigation links that don't point to any resource.&#x20;
* This setting can only be turned on via your lock settings. This means that links pointing outside of your Online Store cannot be hidden through Locksmith.
* This setting cannot hide filtering options in your theme's filter menu, as filter items are displayed differently from product grids and navigation menus.

## Having issues with links not getting hidden?

The way you add in the links when creating your navigation menus may affect Locksmith's ability to remove links in your menus.

Specifically, it's important that you search for and select the resource directly and that you do NOT simply paste/type in the link. Selecting the resource directly means that there is a liquid resource associated with it, and Locksmith can more consistently detect the correct lock status that way. \
\
From the **Online Store > Navigation** area in your Shopify admin, It should look something like this when setting up:

<figure><img src="../../.gitbook/assets/2024-02-26 16.28.30.gif" alt=""><figcaption></figcaption></figure>

## Related articles

{% content-ref url="../../basics/creating-locks.md" %}
[creating-locks.md](../../basics/creating-locks.md)
{% endcontent-ref %}

{% content-ref url="how-do-i-hide-my-shopify-stores-header-and-footer.md" %}
[how-do-i-hide-my-shopify-stores-header-and-footer.md](how-do-i-hide-my-shopify-stores-header-and-footer.md)
{% endcontent-ref %}
