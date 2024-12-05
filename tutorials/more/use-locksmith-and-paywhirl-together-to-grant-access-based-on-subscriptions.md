# Use Locksmith and PayWhirl together to grant access based on subscriptions

You can use Locksmith alongside a dedicated subscription app to lock content so that the content can only be accessed by active subscribers. This guide covers how to use PayWhirl, but any recurring payment service that offers the "auto-tagging" feature would work with Locksmith.

**Note**: This guide covers recurring subscriptions. If you want to grant access based on a _single purchase,_ that is a built-in Locksmith feature, no third party app required. [More info on that here](https://www.locksmith.guide/tutorials/selling-digital-content-on-shopify).

### PayWhirl Setup: <a href="#recharge-setup" id="recharge-setup"></a>

If you haven't already, install the PayWhirl app and use their instructions to set up a recurring subscription for one of your products. Start by creating a product on your store, and then linking it to a subscription through PayWhirl. You can find the full setup instructions here:

{% embed url="https://docs.paywhirl.com/en/collections/2664862-shopify-subscription-app" %}

**Important: You'll need to configure PayWhirl to tag customers who subscribe.** To do this, click on the Workflows tab in PayWhirl, and then click on "Create customer tagging":

<figure><img src="../../.gitbook/assets/Screenshot 2024-06-19 at 7.45.13 PM.png" alt=""><figcaption></figcaption></figure>

Next, click on "Tag active subscribers", and then "Create and activate workflow". Your setup should look something like this on the Workflows screen when you're done:\


<figure><img src="../../.gitbook/assets/Screenshot 2024-06-19 at 7.45.49 PM.png" alt=""><figcaption></figcaption></figure>

### Locksmith Setup: <a href="#locksmith-setup" id="locksmith-setup"></a>

Open up the Locksmith app and create a lock by searching for the page, product, collection, etc that you want to limit access to.&#x20;

Once the lock is created, add the following key:

<figure><img src="https://www.locksmith.guide/~gitbook/image?url=https%3A%2F%2F277214568-files.gitbook.io%2F%7E%2Ffiles%2Fv0%2Fb%2Fgitbook-x-prod.appspot.com%2Fo%2Fspaces%252F-MUeGWHuijBPr8Og1Gta%252Fuploads%252FgNsxsDnSeGgDiaN2ErKn%252FScreen%2520Shot%25202022-11-08%2520at%25209.57.16%2520PM.png%3Falt%3Dmedia%26token%3D58f6f9f9-951f-4400-b234-dd423914721a&#x26;width=768&#x26;dpr=4&#x26;quality=100&#x26;sign=5b72439eb35df1eb339cc57b62b92f0387bb389d283889602e9f12f6a1121487" alt=""><figcaption></figcaption></figure>

Here's a refresher on how to create keys:&#x20;

{% embed url="https://www.locksmith.guide/basics/creating-keys" %}

That's all it takes! Locksmith will now only grant access to accounts tagged with "Active Subscriber", which will be added to accounts that have an active subscription via PayWhirl. Based on the Workflow settings you set up already, the tag will be removed when the customer cancels or is otherwise unsubscribed. As a result, they'll also automatically lose access to the locked content.&#x20;

### Advanced setup for multiple tiers: <a href="#advanced-setup-for-multiple-tiers" id="advanced-setup-for-multiple-tiers"></a>

#### If all of your plans are accessing the same content... <a href="#if-all-of-your-plans-are-accessing-the-same-content" id="if-all-of-your-plans-are-accessing-the-same-content"></a>

E.g. - you have a monthly, yearly, etc option - no additional setup needed: the same tag will get added to a customer account to matter what plan they have, and customers using all plans will be able to access the content.

#### If you have multiple plan tiers to access _different_ content, depending on the tier... <a href="#if-you-have-multiple-plan-tiers-to-access-different-content-depending-on-the-tier" id="if-you-have-multiple-plan-tiers-to-access-different-content-depending-on-the-tier"></a>

E.g. Gold, Silver, Bronze tiers, but the access for each tier is different.

In PayWhirl, you'd create a recurring order product for each of your tiers.

In Locksmith, add a lock to the content that is associated with a particular membership level. You will end up with at least one lock for each tier, maybe multiple, depending what content you are locking!

Use the following key:

<figure><img src="https://www.locksmith.guide/~gitbook/image?url=https%3A%2F%2F277214568-files.gitbook.io%2F%7E%2Ffiles%2Fv0%2Fb%2Fgitbook-x-prod.appspot.com%2Fo%2Fspaces%252F-MUeGWHuijBPr8Og1Gta%252Fuploads%252F2nBCdyKIBd0v511jYowZ%252FScreen%2520Shot%25202022-11-08%2520at%25209.58.37%2520PM.png%3Falt%3Dmedia%26token%3Df47a2b7f-0124-4cd0-bce6-262d51519f2e&#x26;width=768&#x26;dpr=4&#x26;quality=100&#x26;sign=7dd6a9fc3da1a133fa7e53bc5bf5643dd30d1090fce639b2853762b9ad108b70" alt=""><figcaption></figcaption></figure>

Make sure to fill out the "Only look at orders in the last..." field with the appropriate subscription length that matches your PayWhirl subscription:

<figure><img src="https://www.locksmith.guide/~gitbook/image?url=https%3A%2F%2F277214568-files.gitbook.io%2F%7E%2Ffiles%2Fv0%2Fb%2Fgitbook-x-prod.appspot.com%2Fo%2Fspaces%252F-MUeGWHuijBPr8Og1Gta%252Fuploads%252FSReSPYv5Fs87cqVJMH3B%252FScreen%2520Shot%25202022-11-08%2520at%252010.00.23%2520PM.png%3Falt%3Dmedia%26token%3De53349f0-8b99-4481-8344-da5e328b9b83&#x26;width=768&#x26;dpr=4&#x26;quality=100&#x26;sign=4842b7ea9c175f59c120ddb6c2cf3c36f5202e766cdb2fcbfb8e5fbcf065b5a8" alt=""><figcaption></figcaption></figure>

If there is any content that can be accessed by more than one type of membership level, just add them both as Locksmith keys:

<figure><img src="https://www.locksmith.guide/~gitbook/image?url=https%3A%2F%2F277214568-files.gitbook.io%2F%7E%2Ffiles%2Fv0%2Fb%2Fgitbook-x-prod.appspot.com%2Fo%2Fspaces%252F-MUeGWHuijBPr8Og1Gta%252Fuploads%252FZaTaMuQ0PswHZSM4XOfq%252FScreen%2520Shot%25202022-11-08%2520at%252010.01.36%2520PM.png%3Falt%3Dmedia%26token%3Db1a3f6a0-7893-4f29-a151-9520988bbea8&#x26;width=768&#x26;dpr=4&#x26;quality=100&#x26;sign=c2d58dd760ff95e7bdd9005ec96b962f761394b4a3828180e01c064b7ac53b4b" alt=""><figcaption></figcaption></figure>

**Feel free to ask questions if you're having any issues with any of that!** We can be contacted via email at team@uselocksmith.co&#x6D;**.**
