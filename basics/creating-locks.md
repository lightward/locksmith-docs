---
description: How to use Locksmith's in-app search bar to create a lock
---

# Creating locks

Locksmith uses the idea of _locks_ to restrict access to specific content in your store. You can granularly control which content is restricted by adding a lock to the applicable resource.

Use the search bar within Locksmith to place a lock on any content within your Shopify "Online Store". To use it, search for your resource by name:

![](../.gitbook/assets/creatingLocks-Add\_new\_lock\_search.png)

{% hint style="info" %}
**Hint:** Use specific search terms such as "Long Sleeved T-shirt". Pasting in URLs won't work in most cases.
{% endhint %}

### What is searchable

Here are the types of resources that you are able to lock (and search for) from within Locksmith:

* Products
* Collections
* Pages: [more info on Shopify pages here](https://help.shopify.com/en/manual/online-store/os/pages)
* Variants: [more info on Shopify product variants here](https://help.shopify.com/en/manual/products/variants)
* Blogs: [more info on Shopify blogs here](https://help.shopify.com/en/manual/online-store/os/blogs)
* Blog posts (also called articles): You must tag an article first, and then the article _tag_ will be searchable. [More info on blog posts here](https://help.shopify.com/en/manual/online-store/os/blogs/writing-blogs)
* Product vendors

### Specifying a resource type when searching

Locksmith allows you to specify the resource type to search for. This is helpful when you get many results from search term, but they aren't what you're looking for.&#x20;

Try this syntax in the search bar:&#x20;

* product:snowboard
* collection:snowboards
* page:about snowboards
* blog:life is snowboarding

{% hint style="info" %}
**Hint**: If you are attempting to search for one of the above resources, and it doesn't show up, the first thing to do is to update Locksmith(see "Updating Locksmith" below), which will update Locksmith's list of searchable resources in your store.
{% endhint %}

### What is not searchable

* Product tags: to lock a group of products with the same tag create an [Automated Collection](https://help.shopify.com/en/manual/products/collections/automated-collections), and then lock the collection using Locksmith.&#x20;
* Third party apps
* Any page that is not located inside of your Online Store
* Menus and menu links: Menu links are not directly searchable, but they can still be hidden from unauthorized access, as long as they point to one of the resource types in the list at the top of this page. In this case, just make sure the option to "Hide any links to this \[resource] in your shop’s navigation menus" is turned on (under Settings) for the corresponding lock.

### Locking your entire store

Simply click into the search bar:

![](<../.gitbook/assets/Screenshot 2024-05-01 at 7.03.12 PM.png>)

Once you do that, you'll see "**Entire store**" show up in the dropdown as an option to lock:

![](<../.gitbook/assets/Screenshot 2024-05-01 at 7.03.58 PM.png>)

#### Excluding resources form the store lock

The store lock's settings page has a few options for excluding resources from the store lock, so they remain accessible to everyone. Those options include:

* Allow access to the home page
* Allow access to policy pages
* Allow access to customer areas

For resources that you would like to exclude form the store lock that aren't covered by those lock options, we have guide on excluding content from locks here:

{% content-ref url="../keys/more/excluding-content-from-locks.md" %}
[excluding-content-from-locks.md](../keys/more/excluding-content-from-locks.md)
{% endcontent-ref %}

### Locking all products in your store

By default, Shopify stores feature an 'All' collection that automatically encompasses all products in the store. Locking this collection offers an efficient method to secure all products in your Shopify store simultaneously, without the need to lock the entire store.\
\
This collection can be locked just like any other collection. Search for the collection title 'all', select 'Collection: All' from the list of results, and follow the steps to create your lock.

<figure><img src="../.gitbook/assets/2024-05-01 19.07.23 (1).gif" alt=""><figcaption></figcaption></figure>

### Still having trouble?

If you are searching for something like a product or a collection (or something else that is definitely searchable), and it just isn't showing up, you may just need to switch up your search terms.&#x20;

* Try using fewer (but more specific) search terms.&#x20;
* Keep in mind that pasting in the URL of the item you are trying to search will not work in most cases, you will need to search by name.
* For variants that aren't appearing in search results, try including some information about the variant option. For example: "Color" equals "blue".

### Updating Locksmith

If you've created something recently and it's not showing up, an update to Locksmith can help.

1\. Open the Locksmith app and navigate to the "Help" page\
\
2\. Click on the "Update Locksmith" button:

<figure><img src="../.gitbook/assets/Screenshot 2024-11-12 at 8.24.28 AM.png" alt=""><figcaption></figcaption></figure>

3\. When the green bar at the bottom of the screen disappears, the update is finished. This should only take a handful of seconds.

### A note about Liquid locks

Locksmith also gives you the ability to create "Liquid locks". This can allow you to target nonstandard resources or groups of pages in your store with Locksmith locks that are otherwise not directly searchable. You can start a Liquid lock by clicking into the search bar and selecting "**Start a Liquid Lock**":

<figure><img src="../.gitbook/assets/2024-05-01 19.12.16.gif" alt=""><figcaption></figcaption></figure>

If you think a Liquid lock could help you, try your hand at [some Liquid code](https://shopify.dev/docs/themes/liquid/reference), or you can always write in to us for any questions about a specific use case.

Our more in depth guide on that is here:

{% content-ref url="../tutorials/more/liquid-locking-basics.md" %}
[liquid-locking-basics.md](../tutorials/more/liquid-locking-basics.md)
{% endcontent-ref %}

\
As always, if you have questions or issues **please feel free to get in touch with us** at team@uselocksmith.com.
