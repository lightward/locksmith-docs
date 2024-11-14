# Why isn't my passcode, secret link, newsletter, or location key working?

{% hint style="info" %}
Tip: we call these "remote key conditions", because they involve making remote calls to Locksmith for verification.
{% endhint %}

You tested out your key, and it worked great. But now it stopped asking for verification. This can often happen when using one of these key types:

* [Passcode](../../keys/passcode-keys.md)
* [Secret link](../../keys/secret-link-keys.md)
* [Newsletter](../../keys/more/newsletter-keys.md)
* [Location](../../keys/visitor-location-keys.md)
* IP Address

For background, Locksmith remembers your previous access using the same mechanism Shopify uses to remember you: via browser cache.

The easiest way to move forward is by opening a private browsing session (sometimes called "incognito mode"), and _then_ proceeding to test Locksmith in your online storefront.

Detailed information on using private/incognito mode here:

{% content-ref url="../../tutorials/more/how-to-use-a-private-browsing-session.md" %}
[how-to-use-a-private-browsing-session.md](../../tutorials/more/how-to-use-a-private-browsing-session.md)
{% endcontent-ref %}

{% hint style="info" %}
**Note**: If you're using location keys, and you're changing your location with a VPN for testing purposes, the cause is the same in that Locksmith caches your access status. Using a private browsing session can still help with this in that you'll have fresh cache
{% endhint %}

{% hint style="success" %}
**Tip:** Each time you test, be sure to start a _**new**_ private browsing session. Remember, the cache in private browsing doesn't clear stored access until you close all private windows or stop the main Incognito process.
{% endhint %}

## Locksmith is remembering your browser.

When you open the key, Locksmith remembers it as long as your browser application remains running. To get around this, you'll need to use a private session (see above), or use a different browser or device.

In the case of location keys, if you're using a VPN to change your apparent location, it can even be useful to delete the browser cache _during the same browser session_. We have a guide on how to do this here:

{% content-ref url="../../tutorials/more/how-to-clear-cache-for-a-single-website.md" %}
[how-to-clear-cache-for-a-single-website.md](../../tutorials/more/how-to-clear-cache-for-a-single-website.md)
{% endcontent-ref %}

## Locksmith is remembering your account.

_If you were signed into a customer account when you opened the key_, Locksmith can remember access on that account. This is a toggle-able setting on those key condition types, and, when turned on, Locksmith will never ask again when you're signed in.

To turn this setting off, head into the lock and click on the link to the key condition. Next, scroll down in the pop up and disable the option "Remember for signed in customer":

<div align="center">

<img src="../../.gitbook/assets/Screen Shot 2022-08-02 at 9.42.52 PM.png" alt="">

</div>

Toggle the setting OFF, and **don't forget to save your lock**!
