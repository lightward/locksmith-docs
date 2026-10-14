# Grow your subscriber lists with Klaviyo

Locksmith allows you to present your customers with a form to subscribe to a Klaviyo email list, which the customer must enter before they gain access to the locked content:

<div data-full-width="false"><figure><img src="../../.gitbook/assets/Screenshot 2025-07-31 at 11.55.24.png" alt=""><figcaption></figcaption></figure></div>

## Setup

To get started, create a new lock or navigate to the lock you'd like to use, then add the key condition labelled "if the customer subscribes to a Klaviyo list".

<figure><img src="../../.gitbook/assets/Screenshot 2026-10-14 at 12.09.10 PM.png" alt=""><figcaption><p>You can optionally filter the list by typing "klaviyo" as the filter.</p></figcaption></figure>

{% hint style="info" %}
You'll notice that Locksmith also supports _only_ checking if a customer is already on a list (as opposed to subscribing them). This is a separate key condition, and it also supports checking segments! [We have a dedicated guide on that here](use-a-klaviyo-list-or-segment-as-an-access-control-list.md).
{% endhint %}

You'll need to create a Klaviyo API key and give it to Locksmith (see below). Once you do that, you'll be presented with your Klaviyo lists, and you'll be able to choose which one to use like so:

<figure><img src="../../.gitbook/assets/Screenshot 2026-10-14 at 12.22.40 PM.png" alt=""><figcaption></figcaption></figure>

{% hint style="info" %}
As noted within the key condition setup, Klaviyo has their own policies regarding double opt in, and it is typically enabled by default. This setting is adjusted under Settings > API keys, in the "Default opt-in settings" section. There, choose "Double opt-in" or "Single opt-in". This is not a setting that is controlled by Locksmith.
{% endhint %}

### Klaviyo API Access

The first time you select this, Locksmith will prompt you for a Klaviyo API key:

<figure><img src="../../.gitbook/assets/Screenshot 2026-10-14 at 12.13.53 PM.png" alt=""><figcaption></figcaption></figure>

In your Klaviyo dashboard, go to Settings > API keys. You can also use the "from your Klaviyo account" link within Locksmith to go directly there:

<figure><img src="../../.gitbook/assets/Screenshot 2026-10-14 at 11.55.50 AM.png" alt=""><figcaption></figcaption></figure>

The API keys page lists each private key with an "Access Level" column. Use this to see an existing key's access level without recreating it.

Creating a private API key requires Owner or Admin access to the Klaviyo account.

Click the "Create Private API Key" button and name the key. "Select Access Level" offers "Custom Key", "Read-Only Key", and "Full Access Key". For Locksmith, choose one of the following:

* **Custom Key** — the API Scopes table appears on the right. It has "No Access", "Read Access", and "Read/Write Access" columns. The radio button in the "Read/Write Access" column is labelled "Full Access". With "Custom Key" selected, every scope starts at "No Access". Set each required scope to "Full Access": "List", "Profiles", "Segments", and "Subscriptions". Missing any one of these scopes can prevent the integration from working.
* **Full Access Key** — grants full access to every scope in one click. Use this as a simpler alternative to setting the four required scopes individually.

<figure><img src="../../.gitbook/assets/Screenshot 2026-10-14 at 11.59.40 AM.png" alt=""><figcaption><p>Klaviyo Private API Key Scopes</p></figcaption></figure>

{% hint style="warning" %}
Klaviyo does not allow you to add or edit scopes on a private API key after creating it. If an existing key has the wrong scopes, create a new key with the correct scopes and connect that key instead. [https://help.klaviyo.com/hc/en-us/articles/7423954176283](https://help.klaviyo.com/hc/en-us/articles/7423954176283)
{% endhint %}

Copy the API key:

<figure><img src="../../.gitbook/assets/Screenshot 2026-10-14 at 12.01.13 PM.png" alt=""><figcaption><p><strong>Copying the Klaviyo Private API Key</strong></p></figcaption></figure>

Then, head back to Locksmith, where you'll be able to paste in the key. Click "Continue", and Locksmith will present you with a list of Klaviyo lists, to which your new subscribers will be saved.

Once your Locksmith configuration is to your liking, hit the "Save" button. From here on out, new visitors to your locked resource will be required to subscribe before proceeding.

#### Replacing your Klaviyo API key

Disconnect the existing Klaviyo connection from the **Settings** page in the Locksmith app:

<figure><img src="../../.gitbook/assets/Screenshot 2026-10-14 at 12.29.13 PM (1).png" alt=""><figcaption></figcaption></figure>

The Settings page does not offer a reconnect control.\
\
To reconnect, open a lock that uses a Klaviyo key. Return to its Klaviyo key condition. Locksmith prompts you to enter a private API key there. Enter the new key in that prompt.

{% hint style="info" %}
**Note**: any customers who are already in your list will be seamlessly granted access when they enter their email address, and will not be added as a duplicate.
{% endhint %}

## Troubleshooting

If visitors enter an email address on a locked page and see "Something went wrong, please refresh and try again," check the connected private API key. This can happen when the lock is configured correctly and the list is selected in Locksmith, but Klaviyo rejects the subscription request because the key lacks required scopes. Klaviyo returns a permission error, and Locksmith cannot complete the subscription.

Create a new private API key with Full Access to "List", "Profiles", "Segments", and "Subscriptions". Then connect the new key in Locksmith.

## Related articles:

{% content-ref url="customizing-the-email-list-signup-form.md" %}
[customizing-the-email-list-signup-form.md](customizing-the-email-list-signup-form.md)
{% endcontent-ref %}

{% content-ref url="use-a-klaviyo-list-or-segment-as-an-access-control-list.md" %}
[use-a-klaviyo-list-or-segment-as-an-access-control-list.md](use-a-klaviyo-list-or-segment-as-an-access-control-list.md)
{% endcontent-ref %}

{% content-ref url="../../keys/more/newsletter-keys.md" %}
[newsletter-keys.md](../../keys/more/newsletter-keys.md)
{% endcontent-ref %}
