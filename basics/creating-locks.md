---
description: How to use Locksmith's in-app search bar to create a lock
---

# Creating locks

Locks are how Locksmith controls access to content in your store. To create a lock, simply search for the resource you want to protect, select it, and then configure your access conditions (keys). A single lock can protect more than one resource — see [Protecting multiple resources with one lock](#protecting-multiple-resources-with-one-lock) below. This guide walks you through everything you need to know to get started.

### **What Is Searchable**

Use the search bar within Locksmith to find and lock any of the following resource types:

* **Products**
* **Collections**
* **Pages** — more info on Shopify pages here: [Pages](https://help.shopify.com/en/manual/online-store/os/pages)
* **Variants** — more info on Shopify product variants here: [Variants](https://help.shopify.com/en/manual/products/variants)
* **Blogs** — more info on Shopify blogs here: [Blogs](https://help.shopify.com/en/manual/online-store/os/blogs)
* **Blog posts** (also called articles) — articles must be tagged first; the tag is then searchable. More info on blog posts here: [Articles](https://help.shopify.com/en/manual/online-store/os/blogs/writing-blogs)
* **Product vendors**

To search, type the name of your resource into the search bar. Use specific terms. For example, "Long Sleeved T-shirt" rather than a broad term like "shirt".

![](../.gitbook/assets/creatingLocks-Add_new_lock_search.png)

### What is not searchable

The following cannot be directly locked via search:

* **Product tags** — to lock products that share a tag, create an Automated Collection and lock that instead.
* **Third-party app pages —** sometimes, a liquid lock can handle this, using the canonical\_url object.
* **Any page outside of your Online Store**
* **Menus and menu links** — menu links aren't directly lockable, but links pointing to lockable resources (such as products or collections) can be hidden from unauthorized visitors. To enable this, turn on the "Hide any links to this \[resource] in your shop's navigation menus" option under the lock's Settings.

### Specifying a resource type when searching

If a search returns too many results, or returns an error, you can narrow things down by specifying the resource type using this syntax:

* `product:snowboard`
* `collection:snowboards`
* `page:about snowboards`
* `blog:life is snowboarding`

{% hint style="info" %}
**Hint**: If you're searching for a resource, but not getting the result you're looking for, try updating Locksmith to re-sync. Head over to the Help page in the app, and click the Update Locksmith button.
{% endhint %}

### Protecting multiple resources with one lock

A single lock can protect more than one resource at a time, as long as they're **the same type** — for example, several products, or several collections. This is handy when the same access rule should apply to a group of resources: you set up the keys once, on one lock, instead of recreating the same key over and over.

Once you've created a lock, scroll to the **Protected resources** section of the lock editor. Use the **Add [resource]** button to search for and attach more resources of the same type, and use the remove control on any chip to detach one. These changes are staged and take effect when you **Save** the lock, alongside any other settings you've changed.

<figure><img src="../.gitbook/assets/creating-locks-protected-resources.png" alt="The Protected resources section of the lock editor, showing two attached products and an Add product button"><figcaption>The Protected resources section lists everything a lock protects. Use Add to attach more.</figcaption></figure>

Clicking **Add [resource]** opens a picker where you can search your store and select another resource to attach:

<figure><img src="../.gitbook/assets/creating-locks-resource-picker-modal.png" alt="The resource picker modal, showing a product search and a list of products to select"><figcaption>The resource picker. Search, then select a resource to add it to the lock.</figcaption></figure>

{% hint style="info" %}
**Mixing types isn't supported.** A lock protects resources of a single type — a products lock holds products, a collections lock holds collections, and so on. To protect different kinds of resources, create a separate lock for each type.
{% endhint %}

{% hint style="warning" %}
**Don't see an "Add resource" button?** Multi-resource locks require Locksmith to have updated permissions on your store. If you installed Locksmith before this feature shipped, you may see a prompt to grant access — follow it, and the **Add [resource]** affordance will appear. Until then, each lock is limited to a single resource.
{% endhint %}

### Naming your lock

Locks can be given an optional **name** to make them easier to find in your lock list. Click the pencil icon next to the lock's title in the editor header, type a name, and confirm with Enter (or the checkmark). A name is purely for your own organization — it doesn't change what the lock protects.

If you don't name a lock, Locksmith labels it automatically using its resources: the first resource's title, plus a "+ N more" suffix and a count badge (for example, "4 collections") when the lock protects several resources.

### Locking your entire store

Click into the search bar and select "Entire store" from the dropdown.

![](<../.gitbook/assets/Screenshot 2024-05-01 at 7.03.58 PM.png>)

#### Excluding resources from the store lock

The store lock settings page includes options to keep certain areas accessible to everyone:

* Allow access to the home page
* Allow access to policy pages
* Allow access to customer areas

For anything not covered by those options, see our guide on excluding content from locks:

{% content-ref url="../keys/more/excluding-content-from-locks.md" %}
[excluding-content-from-locks.md](../keys/more/excluding-content-from-locks.md)
{% endcontent-ref %}

### Locking all products in your store

By default, Shopify stores feature an 'All' collection that automatically encompasses all products in the store. Locking this collection offers an efficient method to secure all products in your Shopify store simultaneously, without the need to lock the entire store.

This collection can be locked just like any other collection. Search for the collection title 'all', select 'Collection: All' from the list of results, and follow the steps to create your lock.

<figure><img src="../.gitbook/assets/2024-05-01 19.07.23 (1).gif" alt=""><figcaption></figcaption></figure>

### A note about Liquid locks

For resources that aren't searchable through the standard search bar, Locksmith offers "Liquid locks" — a more flexible option that lets you target nonstandard resources or custom groups of pages.

To start a Liquid lock, click into the search bar and select "Start a Liquid Lock".

<figure><img src="../.gitbook/assets/2024-05-01 19.12.16.gif" alt=""><figcaption></figcaption></figure>

For more detail, see our guide on Liquid locking basics:

{% content-ref url="../tutorials/more/liquid-locking-basics.md" %}
[liquid-locking-basics.md](../tutorials/more/liquid-locking-basics.md)
{% endcontent-ref %}

### Troubleshooting

_My resource isn't showing up in search_

If something isn't appearing in search results, try the following:

* Use fewer, more specific search terms.
* Search by name rather than pasting in a URL — URLs won't work in most cases.
* For variants, include the variant option in your search. For example: "Color" equals "blue".
* If you've recently created the resource, it may not yet be indexed — try updating Locksmith (see below).

_Updating Locksmith_

Updating Locksmith refreshes its index of your store's resources, which can resolve search issues.

1. Open the Locksmith app and navigate to the "Help" page.
2. Click on the "Update Locksmith" button. \
   ![](../.gitbook/assets/image.png)
3. When the blue bar at the bottom of the screen disappears, the update is complete. This should only take a few seconds.

\
As always, if you have questions or issues **please feel free to get in touch with us** at team@uselocksmith.com.
