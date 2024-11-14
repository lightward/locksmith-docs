# Use Klaviyo as an access control list

By default, our Klaviyo key condition [signs up your customers for your Klaviyo mailing list](klaviyo.md), when they submit their email address. However, this key condition also supports using Klaviyo to establish a list of **email addresses who are preauthorized for your content.**

{% hint style="warning" %}
**Important**: This method only requires that a customer enters their email address (no account password required). If you wish to require that a customer signs in, you'll want to [check out our guide on customer accounts](../../keys/customer-account-keys.md).
{% endhint %}

{% hint style="info" %}
Klaviyo has their own policies regarding double opt in, and it is typically enabled by default. This setting is adjusted in your Klaviyo dashboard - it is not a setting that is controlled by Locksmith.
{% endhint %}

Once you've created a lock, select "subscribes to your Klaviyo list" from the list of available key conditions.

Then, after choosing your Klaviyo list, check the box labeled **"Only grant access if the customer is already on this list"**.&#x20;

As noted in the form, with this mode enabled, **Locksmith won't add anyone to your Klaviyo list**. Instead, access will only be granted for confirmed email addresses that are already on your list.

<figure><img src="../../.gitbook/assets/Screen Shot 2022-11-07 at 12.42.28 PM.png" alt=""><figcaption></figcaption></figure>

You may also want to edit the prompt under Messages > "Mailing list signup prompt" further down on the page - to reflect the fact that you're checking for preauthorized access, instead of looking for signups!

{% hint style="info" %}
**Tip**: Have multiple Klaviyo lists that you want to check? You can add separate keys to represent each list you'd like to check. To do this, after creating your first key and closing the configuration popup, click the "+ Add another key" button, and you can do it all over again, selecting a different Klaviyo list.
{% endhint %}
