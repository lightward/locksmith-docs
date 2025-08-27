# What should I do if my site is loading slowly?

If your online storefront is showing poor performance _after_ installing Locksmith or adjusting Locksmith settings, it's possible that an unintentionally aggressive Locksmith configuration is to blame.&#x20;

Start by using the following troubleshooting steps:

## 1. Temporarily disable Locksmith

This will help you figure out if Locksmith is actually causing your issue. If your site is still performing poorly after disabling Locksmith, it's probable that the issue lies elsewhere, and you will need to continue your search for the culprit outside of Locksmith.

Disabling Locksmith is done from with the **Disable Locksmith** button on the Settings page:

![](<../.gitbook/assets/Screen Shot 2022-08-02 at 5.49.32 PM.png>)

## 2. Disable specific lock settings

There are two lock settings known in Locksmith to _potentially_ cause speed issues in certain circumstances:

<figure><img src="../.gitbook/assets/Screenshot 2025-08-27 at 15.32.48 (1).png" alt=""><figcaption></figcaption></figure>

_The exact labels might differ slightly depending on if this is a product lock, collection lock, page lock etc._

When either option is enabled, it creates the possibility for Locksmith's suite of security checks to be run many times, slowing the rendering process of your storefront. Because of that, disabling these two settings **on all of your locks** will result in Locksmith removing its security checks from places where your storefront theme performs a "loop", e.g. the places where it cycles through lists of links/pages/collections/products/etc.

Keep in mind that it is typically safe to use either of these settings, but there are a few situations you'll want to look for if you are seeing speed issues.

{% hint style="info" %}
**Note**: If you only have a few locks, it might be simple to troubleshoot on your own, keep reading. However, if you have quite a few locks, please feel free to skip straight to contacting us at **team@uselocksmith.com** for help!
{% endhint %}

### The 'hide from navigation' setting

If you have this setting enabled, even on just one of your locks, AND you have a large navigation menu (25+ links, including sub-menus), this is very likely the culprit. Because of this, **it is not recommended to try to use this setting with large navigation menus**.

Try disabling this setting (on all locks) and then check if your site is loading better.

### The 'hide from searches and collections' setting

It is more rare that this setting will slow down your site. However, with certain themes, there may be unexpected loops in product or collection templates where Locksmith inserts its checks.&#x20;

If you see Locksmith _only_ loading slowly on collections or search results pages, that could be the signal that this setting is the issue.

{% hint style="info" %}
**Hint**: If you're not sure which setting is causing the issue, you may want to try only disabling only one of the two above settings at a time (for all locks)_._ Failing that, disable the second setting (again, for all locks)_._ This strategy would help you isolate the problem to one of the two settings.
{% endhint %}

## 3. If you have any developers working with you...

Enlist their help to find the specific assets in your storefront theme which contains Locksmith code that might be unnecessarily running too many times. It's simple to tell Locksmith to ignore specific files in your theme, and this fact can be used to your advantage here.&#x20;

To do this use the Settings > Advanced > "Liquid ignore list" field:

![](<../.gitbook/assets/Screen Shot 2022-08-02 at 7.25.25 PM (1).png>)

Using this settings will mean that Locksmith will strip itself out of that asset.

## Contact us for help!

If the above strategies do not provide anything useful, please do not hesitate to contact us via email at **team@uselocksmith.com**, and we'd be happy to help you troubleshoot this.

