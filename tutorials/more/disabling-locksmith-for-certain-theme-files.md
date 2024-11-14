---
description: How to tell Locksmith to completely ignore specific files in your theme
---

# Disabling Locksmith for certain theme files

Locksmith does its work by adding its code to your theme's files. Sometimes you may want to keep Locksmith from modifying a file in particular, whether it's for a customization, or some other reason.

To support this, Locksmith has a "Liquid assets to ignore" option.&#x20;

To configure it, head to the "Settings" page:

<figure><img src="../../.gitbook/assets/Screen Shot 2022-09-09 at 2.12.34 PM.png" alt=""><figcaption></figcaption></figure>

And then edit the file list under Advanced > Liquid assets to ignore:

<figure><img src="../../.gitbook/assets/Screen Shot 2022-09-09 at 2.01.30 PM.png" alt=""><figcaption><p>You'll notice that some files are added by default.</p></figcaption></figure>

{% hint style="info" %}
**Note**: Use full file names. (e.g. "sections/collection-list.liquid" or "templates/gift\_card.liquid"), and enter them **one per line**.
{% endhint %}

**Please note:** If you need to use the ignore list because Locksmith is causing unexpected problems with your theme, please let us know! Feel free to use the ignore list for any purpose, but do get in touch at [team@uselocksmith.com](mailto:team@uselocksmith.com) if there's a bug we can help resolve. :)
