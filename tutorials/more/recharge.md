# Earn recurring revenue on your exclusive content using ReCharge

You can use Locksmith alongside a dedicated subscription app to lock content so that the content can only be accessed by active subscribers. This guide covers how to use ReCharge, but it should be noted that any recurring payment service that offers the "auto-tagging" feature would work with Locksmith.

{% hint style="info" %}
**Note**: This guide only covers recurring purchases. if you want to grant access based on a _single purchase,_ that is a built-in Locksmith feature, no third party app required. [More info on that here](../selling-digital-content-on-shopify.md).
{% endhint %}

## ReCharge Setup:

If you haven't already, install the ReCharge app and use their instructions to set up a recurring subscription for one of your products:

[Get started with ReCharge here!](https://apps.shopify.com/subscription-payments)&#x20;

One thing to keep in mind is that even if you aren't offering a subscription to an actual physical product, you can still use ReCharge and just label the subscription product as something like "Exclusive Access" or "Membership".

**Recharge will automatically tag customers with "Active Subscriber"** if they have an active ReCharge subscription, making the setup very simple. Also note that this tag is removed if the customer ends their subscription.

## Locksmith Setup:

The Locksmith side of this is pretty straightforward. Open up the Locksmith app and create a lock by searching for the page, product, collection, etc that you want to limit access to.

Once the lock is created, add the following key:

<figure><img src="../../.gitbook/assets/Screen Shot 2022-11-08 at 9.57.16 PM.png" alt=""><figcaption></figcaption></figure>

That's all it takes! Locksmith will now only grant access to accounts tagged with "Active Subscriber", which will only be added to accounts that have an active subscription via ReCharge.

## Advanced setup for multiple tiers:

### If all of your plans are accessing the same content...

E.g. - you have a monthly, yearly, etc option - no additional setup needed: the same tag will get added to a customer account to matter what plan they have, and customers using all plans will be able to access the content.

### If you have multiple plan tiers to access _different_ content, depending on the tier...

E.g. Gold, Silver, Bronze tiers, but the access for each tier is different.

In ReCharge, you'd create a recurring order product for each of your tiers.

In Locksmith, add a lock to the content that is associated with a particular membership level. You will end up with at least one lock for each tier, maybe multiple, depending what content you are locking!&#x20;

Use the following key:

<figure><img src="../../.gitbook/assets/Screen Shot 2022-11-08 at 9.58.37 PM.png" alt=""><figcaption></figcaption></figure>

Make sure to fill out the "Only look at orders in the last..." field with the appropriate subscription length that matches you rReCharge subscription:

<figure><img src="../../.gitbook/assets/Screen Shot 2022-11-08 at 10.00.23 PM.png" alt=""><figcaption></figcaption></figure>

If there is any content that can be accessed by more than one type of membership level, just add them both as Locksmith keys:

<figure><img src="../../.gitbook/assets/Screen Shot 2022-11-08 at 10.01.36 PM.png" alt=""><figcaption></figcaption></figure>

**Feel free to ask questions if you're having any issues with any of that!** We can be contacted via email at team@uselocksmith.co&#x6D;**.**

## Related articles:

{% content-ref url="../selling-digital-content-on-shopify.md" %}
[selling-digital-content-on-shopify.md](../selling-digital-content-on-shopify.md)
{% endcontent-ref %}

{% content-ref url="use-locksmith-and-paywhirl-together-to-grant-access-based-on-subscriptions.md" %}
[use-locksmith-and-paywhirl-together-to-grant-access-based-on-subscriptions.md](use-locksmith-and-paywhirl-together-to-grant-access-based-on-subscriptions.md)
{% endcontent-ref %}

