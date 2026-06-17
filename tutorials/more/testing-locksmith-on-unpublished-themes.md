# Testing Locksmith on unpublished themes

By default, Locksmith will only automatically install itself to and update itself on the currently published theme, and does _not_ automatically install itself to unpublished themes. However, there is a way to test Locksmith on unpublished themes.

### **To test Locksmith on an unpublished theme:**

1. Head to the in-app "Themes" page.
2. Click the "**Install**" button for the theme you'd like to test Locksmith on:

<figure><img src="../../.gitbook/assets/Screenshot 2024-11-09 at 9.09.02 PM copy.png" alt=""><figcaption></figcaption></figure>

4. To preview the lock configuration you just installed, click the **three-dot menu** (…) next to the theme name, and select **Preview**:

<figure><img src="../../.gitbook/assets/Screenshot 2024-11-09 at 9.20.48 PM.png" alt=""><figcaption></figcaption></figure>

When testing your locks on unpublished or the currently published theme, we recommend using a brand new private browsing session each time:\
[how-to-use-a-private-browsing-session.md](how-to-use-a-private-browsing-session.md "mention")

{% hint style="warning" %}
⚠️ **Important:** If you're using a URL with the `shopifypreview.com` domain to test, Locksmith changes won't be reflected there. The Shopify theme editor's built-in preview bypasses Locksmith entirely, so locks, keys, and any manual locking code will appear as if they aren't in place.\
\
For accurate testing, always use the preview URL that includes `?fts=0&preview_theme_id=` followed by your theme ID in the URL parameters — as described in this guide.
{% endhint %}

{% hint style="info" %}
Please note: when making changes to your locks and Locksmith settings, Locksmith will only update those on the currently published theme.\
\
To update the unpublished theme after making changes in-app, just click the "Install" button for that theme next to the theme name again, as outlined above.
{% endhint %}

### To remove Locksmith from an unpublished theme:

1. Head to the in-app "Themes" page.
2. Click the "**Uninstall**" button for the theme you'd like to remove Locksmith from:

<figure><img src="../../.gitbook/assets/Screenshot 2024-11-09 at 9.09.02 PM.png" alt=""><figcaption></figcaption></figure>

### Setting a secondary theme:

Locksmith supports setting a **Secondary theme**, which receives automatic updates along with your published theme when changes are made in Locksmith.

1. In the **Unpublished themes** section, locate the theme you want to set as a secondary theme.
2. Click the **three-dot menu** (…) next to the theme name.
3. Select **Set as secondary theme**:

<figure><img src="../../.gitbook/assets/Screenshot 2024-11-09 at 9.20.07 PM.png" alt=""><figcaption></figcaption></figure>

This theme will now receive all future updates made in Locksmith, in addition to the published theme.
