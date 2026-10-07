# Use Locksmith and Appfox Subscriptions to grant access based on subscriptions

You can use Locksmith alongside [Appfox Subscriptions](https://apps.shopify.com/appfox-subscriptions) to lock content so that it can only be accessed by active subscribers. Appfox tags customers automatically based on subscription status, which is all Locksmith needs.

**Note**: This guide covers recurring subscriptions. If you want to grant access based on a _single purchase_, that is a built-in Locksmith feature, no third party app required. [More info on that here](https://www.locksmith.guide/tutorials/selling-digital-content-on-shopify).

### How Appfox Subscriptions tags customers

Appfox applies a single tag, exactly as written here: **Active Subscriber**

**The tag is added when:**

* A new subscription is created and is active
* A paused subscription is resumed (reactivated)

**The tag is removed when:**

* A subscription is paused
* A subscription is cancelled

Subscriptions normally end through a pause or a cancel, and the tag is removed in both cases.

**There is nothing to enable or configure.** Appfox applies and removes the tag automatically as soon as the app is installed and subscriptions start coming in.

Appfox's own documentation on the tag is here: [Active Subscriber customer tag](https://subscriptions-docs.getappfox.com/active-subscriber-tag)

This is the simplest possible pattern for Locksmith: one tag, present while the subscription is active, gone when it isn't. That means **a single key condition is all you need** — no inverted conditions, and no combo keys.

### Appfox setup

If you haven't already, install [Appfox Subscriptions](https://apps.shopify.com/appfox-subscriptions) and use their instructions to set up a recurring subscription for one of your products. Tagging is on by default, so there's no additional configuration step.

One thing to keep in mind is that even if you aren't offering a subscription to an actual physical product, you can still use a subscription app and just label the subscription product as something like "Exclusive Access" or "Membership".

### Locksmith setup

1. Open the Locksmith app and create a lock on the content you want to restrict — a product, collection, page, blog, and so on. Guide: [Creating locks](https://www.locksmith.guide/basics/creating-locks)
2. Add the key condition **Permit if the customer is tagged with...** and enter **Active Subscriber**. This is a regular (non-inverted) condition. Guide: [Creating keys](https://www.locksmith.guide/basics/creating-keys)
3. Save the lock.

<figure><img src="../../.gitbook/assets/Screenshot 2026-10-07 at 4.37.55 PM.png" alt=""><figcaption></figcaption></figure>

That's all it takes! Locksmith will now only grant access to accounts tagged **Active Subscriber**, which Appfox adds when a subscription becomes active. When the customer cancels or pauses their subscription, Appfox removes the tag and they automatically lose access to the locked content.

### Good to know

**Tag text must match exactly.** Locksmith matches the tag exactly as written, so enter **Active Subscriber** exactly as shown, including the capital letters.

**Failed payments do not remove the tag.** If a customer's subscription payment fails, Appfox keeps the Active Subscriber tag in place while the subscription is in a failed billing state — so that customer keeps access to your locked content while Appfox retries billing. After the final retry, Appfox pauses or cancels the subscription and the tag is removed at that point, so access doesn't stay open indefinitely on a failed card. If you need access to end sooner than that, you'd need to handle it separately, for example by removing the tag with Shopify Flow when a payment failure occurs.

**Customers with more than one subscription.** If a customer holds two active subscriptions and pauses or cancels just one of them, Appfox currently removes the Active Subscriber tag even though the other subscription is still active — which means that customer would lose access. Appfox has noted this as a known limitation and is working on a fix so the tag stays in place while any subscription is active. For most stores, which run one subscription per customer, this doesn't come up.

**Access is checked at page load.** Locksmith checks the customer's tags at the moment they visit your store, so tag changes take effect on their next page load rather than retroactively.

### If you need different access for different plans

Appfox applies the same Active Subscriber tag regardless of which plan a customer is on. That's ideal when all of your plans unlock the same content — monthly and yearly subscribers all get in with no extra setup.

If you need _tiered_ access, where a Gold subscriber sees more than a Silver subscriber, you'll need a way to distinguish the tiers by tag. Options include:

* Adding tier-specific tags with Shopify Flow or another automation tool, then creating one Locksmith key per tier
* Using Locksmith's [has purchased...](https://www.locksmith.guide/keys/more/has-purchased) key condition against the specific subscription product for each tier, with the "Only look at orders in the last..." field set to match your billing interval

### Helpful resources

* [Customer account keys](https://www.locksmith.guide/keys/customer-account-keys)
* [Creating locks](https://www.locksmith.guide/basics/creating-locks)
* [Creating keys](https://www.locksmith.guide/basics/creating-keys)

### Summary

Appfox Subscriptions adds the Active Subscriber tag while a subscription is active and removes it on pause or cancel, with no setup required. Lock your content in Locksmith and add a single **is tagged with Active Subscriber** key — access then follows subscription status automatically, with no code and no integration on either side.

**Feel free to ask questions if you're having any issues with any of that!** We can be contacted via email at [team@uselocksmith.com](mailto:team@uselocksmith.com).
