---
description: How to tell Locksmith to completely ignore specific files in your theme
---

# Disabling Locksmith for certain theme files

Locksmith does its work by adding its code to your theme's files. Sometimes you may want to keep Locksmith from modifying a file in particular, whether it's for a customization, or some other reason.

To support this, Locksmith has a "Liquid assets to ignore" option. Configure it like so:

1. From within the Locksmith application, click "Settings".
2. Scroll to the bottom of the screen to the "Advanced" section.
3. For each Liquid asset you'd like to have Locksmith ignore, add its filename to the "Liquid asset blacklist" box.

That will look like this:

![](<../../.gitbook/assets/Screen Shot 2022-08-02 at 7.25.25 PM.png>)

{% hint style="info" %}
**Note**: Use full file names. (e.g. "sections/collection-list.liquid" or "templates/gift\_card.liquid"), and enter them **one per line**.
{% endhint %}

**Please note:** If you need to use the ignore list because Locksmith is causing unexpected problems with your theme, please let us know! Feel free to use the ignore list for any purpose, but do get in touch at [team@uselocksmith.com](mailto:team@uselocksmith.com) if there's a bug we can help resolve. :)
