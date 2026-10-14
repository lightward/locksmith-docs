---
description: >-
  Locksmith allows you to use an already-existing Klaviyo list or segment to
  determine who gets access to your locked content.
---

# Use a Klaviyo list or segment as an access control list

The "Klaviyo member" key condition in Locksmith can check your Klaviyo lists or segments directly, to see if the current visitor should have access, and will grant or deny access accordingly.

To set this up, choose the key condition labelled "if the customer is a member of a Klaviyo list or segment":

<figure><img src="../../.gitbook/assets/Screenshot 2026-10-14 at 12.43.02 PM.png" alt=""><figcaption><p>Optional: Use the filter box and type "klaviyo" for quick access.</p></figcaption></figure>

{% hint style="warning" %}
**Editorial note:** Retake this screenshot. It shows the July 2025 key condition picker.
{% endhint %}

{% hint style="info" %}
Please note that this particular key condition does NOT subscribe new members, but you'll notice in the screenshot above that Locksmith _also_ has a key condition for subscribing new members. [More information on that here](klaviyo.md).
{% endhint %}

## API Key access

The first time you access one of our Klaviyo key conditions, you'll need to set up Locksmith's API access to your Klaviyo account. This is covered in detail in our guide here:

[#klaviyo-api-access](klaviyo.md#klaviyo-api-access "mention")

Your API key must grant "Full access" to the same four scopes in every case. "Segments" is especially important when using this key condition:

* List
* Profiles
* Segments
* Subscriptions

<figure><img src="../../.gitbook/assets/Screenshot 2026-10-14 at 11.59.40 AM.png" alt=""><figcaption></figcaption></figure>

## Setup

Take note of these settings:

<div align="left"><figure><img src="../../.gitbook/assets/Screenshot 2026-10-14 at 12.53.19 PM.png" alt=""><figcaption></figcaption></figure></div>

### List or segment

Use the **Resource type** dropdown to choose a list or segment. Select **List** to show **Select a list...**, then choose from the radio buttons for lists in your Klaviyo account.

Use **Create a new list** to open Klaviyo in a new tab and create a list:

<figure><img src="../../.gitbook/assets/Screenshot 2026-10-14 at 12.54.57 PM.png" alt=""><figcaption></figcaption></figure>

Lists and segments function the same in practice. Locksmith asks Klaviyo whether the supplied email address is on the selected list or segment.

The key condition also states that it only checks existing list members. It does not add new subscribers.

### "Only check signed-in customers" setting

This setting changes the behavior of this key condition significantly!

<figure><img src="../../.gitbook/assets/2026-10-14 12.56.50.gif" alt=""><figcaption></figcaption></figure>

If left off (the default), Locksmith will prompt the visitor to enter their email address. The email address is the ONLY thing the customer needs to enter in this case, there is no requirement to sign in. This is what that would look like in your storefront:

<div align="left"><figure><img src="../../.gitbook/assets/Screenshot 2025-07-31 at 13.11.20.png" alt=""><figcaption><p>This is the default input prompt message displayed to customers, but - like all of our default message prompt - can be customized as needed.</p></figcaption></figure></div>

If turned ON, customers will be required to sign in. Then, once signed in, Locksmith will either grant or deny access depending on if the customer is found in the configured list or segment. Here is an example of Locksmith's sign in page:

<div align="left" data-full-width="false"><figure><img src="../../.gitbook/assets/Screenshot 2025-07-31 at 13.14.42.png" alt=""><figcaption><p>The login button in this case brings the customer to the customer sign in page for your store. If you are using Shopify's Legacy customer account system, the customer will instead be presented with the entire customer login form right on the page.</p></figcaption></figure></div>

### "Remember for signed-in customers" setting

Select **Remember for signed-in customers** to let Locksmith remember signed-in customers. It lets them in automatically next time.

{% hint style="info" %}
**Tip**: Have multiple Klaviyo lists that you want to check? You can add separate keys to represent each list you'd like to check. To do this, after creating your first key and closing the configuration popup, click the "+ Add another key" button, and you can do it all over again, selecting a different Klaviyo list.
{% endhint %}
