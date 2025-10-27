---
description: >-
  Locksmith allows you to use an already-existing Klaviyo list or segment to
  determine who gets access to your locked content.
---

# Use a Klaviyo list or segment as an access control list

The "Klaviyo member" key condition in Locksmith can check your Klaviyo lists or segments directly, to see if the current visitor should have access, and will grant or deny access accordingly.&#x20;

To set this up, choose the key condition labelled "if the customer is a member of a Klaviyo list or segment":

<figure><img src="../../.gitbook/assets/Screenshot 2025-07-31 at 12.52.18 (1).png" alt=""><figcaption><p>Optional: Use the filter box and type "klaviyo" for quick access.</p></figcaption></figure>

{% hint style="info" %}
Please note that this particular key condition does NOT subscribe new members, but you'll notice in the screenshot above that Locksmith _also_ has a key condition for subscribing new members. [More information on that here](klaviyo.md).
{% endhint %}

## API Key access

The first time you access one of our Klaviyo key conditions, you'll need to set up Locksmith's API access to your Klaviyo account. This is covered in detail in our guide here:

[#klaviyo-api-access](klaviyo.md#klaviyo-api-access "mention")

However, one IMPORTANT detail is, if you are using segments, you need to make sure that your API Key also grants permissions for segments, in addition to the other requirements. So - just to be clear - if you are using segments, you should have an API key that grants "Full access" to:

* Lists
* Profiles
* Segments
* Subscriptions

<figure><img src="../../.gitbook/assets/Screenshot 2025-10-27 at 12.52.02 PM.png" alt=""><figcaption></figcaption></figure>

## Setup

Take note of these settings:

<div align="left"><figure><img src="../../.gitbook/assets/Screenshot 2025-07-31 at 13.00.44.png" alt=""><figcaption></figcaption></figure></div>

### List or segment

You can choose between a list or a segment. They function the same in practice, in that Locksmith asks Klaviyo directly whether or not the supplied email address is on the list or segment

### "Only check signed-in customers" setting

This setting changes the behavior of this key condition significantly!

If left off (the default), Locksmith will prompt the visitor to enter their email address. The email address is the ONLY thing the customer needs to enter in this case, there is no requirement to sign in. This is what that would look like in your storefront:

<div align="left"><figure><img src="../../.gitbook/assets/Screenshot 2025-07-31 at 13.11.20.png" alt=""><figcaption><p>This is the default input prompt message displayed to customers, but - like all of our default message prompt - can be customized as needed.</p></figcaption></figure></div>

If turned ON, customers will be required to sign in. Then, once signed in, Locksmith will either grant or deny access depending on if the customer is found in the configured list or segment. Here is an example of Locksmith's sign in page:

<div align="left" data-full-width="false"><figure><img src="../../.gitbook/assets/Screenshot 2025-07-31 at 13.14.42 (1).png" alt=""><figcaption><p>The login button in this case brings the customer to the customer sign in page for your store. If you are using Shopify's Legacy customer account system, the customer will instead be presented with the entire customer login form right on the page.</p></figcaption></figure></div>

{% hint style="info" %}
**Tip**: Have multiple Klaviyo lists that you want to check? You can add separate keys to represent each list you'd like to check. To do this, after creating your first key and closing the configuration popup, click the "+ Add another key" button, and you can do it all over again, selecting a different Klaviyo list.
{% endhint %}
