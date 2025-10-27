# Grow your subscriber lists with Klaviyo

Locksmith allows you to present your customers with a form to subscribe to a Klaviyo email list, which the customer must enter before they gain access to the locked content:

<div data-full-width="false"><figure><img src="../../.gitbook/assets/Screenshot 2025-07-31 at 11.55.24.png" alt=""><figcaption></figcaption></figure></div>

## Setup

To get started, create a new lock or navigate to the lock you'd like to use, then add the key condition labelled "if the customer subscribes to a Klaviyo list".

<figure><img src="../../.gitbook/assets/Screenshot 2025-07-31 at 11.59.02.png" alt=""><figcaption><p>You can optionally filter the list by typing "klaviyo" as the filter.</p></figcaption></figure>

{% hint style="info" %}
You'll notice that Locksmith also supports _only_ checking if a customer is already on a list (as opposed to subscribing them). This is a separate key condition, and it also supports checking segments! [We have a dedicated guide on that here](use-a-klaviyo-list-or-segment-as-an-access-control-list.md).
{% endhint %}

You'll need to create a Klaviyo API key and give it to Locksmith (see below). Once you do that, you'll be presented with your Klaviyo lists, and you'll be able to choose which one to use like so:

<figure><img src="../../.gitbook/assets/Screenshot 2025-07-31 at 12.23.54 (1).png" alt=""><figcaption></figcaption></figure>

{% hint style="info" %}
As noted within the key condition setup, Klaviyo has their own policies regarding double opt in, and it is typically enabled by default. This setting is adjusted in your Klaviyo dashboard - it is not a setting that is controlled by Locksmith.
{% endhint %}

### Klaviyo API Access

The first time you select this, Locksmith will prompt you for a Klaviyo API key:

<figure><img src="../../.gitbook/assets/Screenshot 2024-04-03 at 2.47.34 PM.png" alt=""><figcaption></figcaption></figure>

In your Klaviyo dashboard, go to Settings > Account > API Keys. You can also use the "from your Klaviyo account" link within Locksmith to go directly there:

<figure><img src="../../.gitbook/assets/Screenshot 2023-11-03 at 7.17.58 PM.png" alt=""><figcaption></figcaption></figure>



Click the  "Create Private API Key" button to create a key for Locksmith. You'll see the new key on the next screen.&#x20;

The scopes that Locksmith needs _full access_ to from the Klaviyo API key are "List", "Profiles", "Segments", and "Subscriptions":

<figure><img src="../../.gitbook/assets/Screenshot 2025-10-27 at 12.52.02 PM.png" alt=""><figcaption></figcaption></figure>



Copy the API key:

<figure><img src="../../.gitbook/assets/Screenshot 2023-11-03 at 7.32.15 PM.png" alt=""><figcaption></figcaption></figure>



Then, head back to Locksmith, where you'll be able to paste in the key. Click "Continue", and Locksmith will present you with a list of Klaviyo lists, to which your new subscribers will be saved.

Once your Locksmith configuration is to your liking, hit the "Save" button. From here on out, new visitors to your locked resource will be required to subscribe before proceeding.

{% hint style="info" %}
**Note**: any customers who are already in your list will be seamlessly granted access when they enter their email address, and will not be added as a duplicate.
{% endhint %}

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

