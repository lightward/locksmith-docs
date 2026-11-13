---
description: Using the key "Permit if any product tag matches any customer account tag"
---

# Granting access when customer tags match product tags

This key lets a signed-in customer see a locked product when **any one of their customer tags matches any one of that product's tags**. You can use one lock with this key to cover many customers and many products, without making a separate lock for each pairing.

This key works with:

* Product locks
* Collection locks
* Locks on Collection: All

### When to use this key

This key is mainly for stores that need a very large number of locks. Locksmith stores your lock settings in a snippet file in your theme, and Shopify limits snippet files to 256KB. Once a store has enough locks, that snippet can go over the limit.

With this key, you can replace many per-customer or per-product locks with a single lock. Access is controlled by the tags on your customers and products instead of by separate locks. For example, if you sell certain products only to specific wholesale accounts, you can give each account an organization tag (like `org-acme`), add that same tag to the products it should see, and let one lock handle all of it.

### How access is decided

When a customer views a product covered by this lock, Locksmith checks two things:

1. **Is the customer signed in?** Customers who aren't signed in are never granted access by this key.
2. **Does any customer tag match any product tag?** If at least one tag is the same on both, the customer gets access to that product. If none match, the product stays locked for them.

A customer with several tags can get access to several sets of products, and a product with several tags can be opened up for several groups of customers.

### Setting it up

1. **Tag your customers.** In your Shopify admin, add a tag to each customer who should have access, such as `org-acme`.
2. **Tag your products.** Add the same tag to every product those customers should be able to see.
3. **Create the lock.** In Locksmith, create a product lock, a collection lock, or a lock on Collection: All, depending on which products you want covered.
4. **Add the key.** Add a key to the lock, open the keys dropdown and choose "Permit if any product tag matches any customer account tag." You'll find it near the bottom of the list, just above "Always permit." Then save the lock.
5. **Test it.** Sign in as a customer with a matching tag and confirm you can see the product, then sign in as a customer without that tag and confirm it stays locked.

### Important things to know

#### Collection pages themselves stay locked

This key only applies to **products**. When you add it to a collection lock (including Collection: All), the collection page itself will never be unlocked by this key, even for customers whose tags match.

What the key does is unlock the individual products inside the locked collection. Customers with a matching tag will be able to see those products wherever they appear in other, unlocked collections.

If customers need to be able to open a collection page, that collection needs to be unlocked for them in some other way, or left unlocked.

#### Any matching tag grants access

Locksmith doesn't know which tags are meant for access control. **If any tag on the customer matches any tag on the product, the customer gets access**, even if the match is accidental.

For example, say a customer has a `sale` tag for an unrelated reason, and a locked product also has a `sale` tag. That customer will be able to see the product, even though you never meant to give them access.

To avoid this:

* **Use distinctive tags just for access.** A consistent prefix such as `access-` or `org-` (for example, `org-acme`) makes accidental matches very unlikely.
* **Review existing tags before turning the lock on.** Check that the customer and product tags you already use (for marketing, apps, or reporting) don't overlap in ways you don't intend.
* **Watch for tags added by other apps.** Some apps add tags to customers or products automatically, which can create new matches later on.

#### Large collections may show blank spaces

If a large collection has a mix of locked and unlocked products, customers may see blank spaces, short pages, or filtering that doesn't line up with what's actually visible. That happens because Shopify builds collection results one page at a time, and Locksmith can only remove locked products from within each page, so some pages come up partly empty.

Two approaches usually help:

* **Use a separate collection for each customer group**, so each collection only contains products that group can see.
* **Use an infinite scrolling app**, so hidden products don't leave gaps between pages.

For more detail, see our guide: [**FAQ: I see blank spaces in my collections and/or searches when locking**.](../../faqs/faq-i-see-blank-spaces-in-my-collections-and-or-searches-when-locking.md)
