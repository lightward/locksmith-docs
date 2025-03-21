# Customizing messages

Most of the messages that Locksmith shows to your customers on the front end of your store are completely customizable!

You can edit the text itself as much as you need, plus you can add code, just like you would a template in your theme. That means you can use the following:

* HTML
* CSS (via the \<style> tag)
* Javascript (via the \<script> tag)
* Liquid ([Shopify's template language for themes](https://shopify.dev/docs/themes/liquid/reference/basics))

{% hint style="info" %}
If you are wanting to add translations to your messages, [check out our dedicated guide on that here](adding-translations-to-your-locksmith-messages.md).
{% endhint %}

In general, your messages can be edited in two places...

## Lock-specific messages:

\
To customize your messages for one lock only, go to the lock page and scroll down to the "Messages" area.

<figure><img src="../../.gitbook/assets/Screenshot 2025-03-20 at 5.46.05 PM.png" alt=""><figcaption></figcaption></figure>

## Default messages:

You can also customize the default messages, which will be used for all applicable locks when a lock-specific message is not present. To edit these, head over to the "Content" area of the "Settings" page:

<figure><img src="../../.gitbook/assets/Screen Shot 2022-11-08 at 9.00.15 PM.png" alt=""><figcaption></figcaption></figure>

\
Messages that [require a customer account](../../keys/customer-account-keys.md):
--------------------------------------------------------------------------------

\
Locksmith will only show the type of messages in the "Messages" area that apply to the key conditions you've selected in your lock(s). Most of the key conditions in Locksmith use customer data, and therefore require a sign in. In these cases, Locksmith will show you the following two editable messages:

* **Guest message content**: shown to customers that are not yet signed in.
* **Access denied content**: shown to customers that are signed in, but don't meet the requirements for the lock (e.g. don't have the specific customer tag that is required for access, if applicable)

\
Passcode and newsletter key conditions:
---------------------------------------

\
There are two other types of messages that will show up if you have selected the applicable key conditions:

* **Passcode prompt**: for ['passcode' conditions](../../keys/passcode-keys.md) only.&#x20;
* **Newsletter prompt**: for [Mailchimp and Klaviyo conditions](../../keys/more/newsletter-keys.md) only.&#x20;

\
These conditions both show a special prompt to the customer, asking for their submission before continuing. You can customize the message in the same places as outlined above.&#x20;

#### Condition-specific messages

For merchants that have multiple passcode or newsletter conditions _in one lock_, you can customize the messages at the condition level. This is done inside the condition popover in the input labelled "Custom input prompt, as shown below.&#x20;

**In most cases, you won't need to set the prompt at the condition level - simply use the lock level messages, as shown above - this is a convenience feature for when it's needed**.

<figure><img src="../../.gitbook/assets/Screenshot 2025-03-20 at 5.48.03 PM.png" alt=""><figcaption></figcaption></figure>

**Important**: If a message is set at this level, it will override any messages set at the other levels. If this is the case, you'll see a warning, just to let you know what's going on:

<figure><img src="../../.gitbook/assets/Screen Shot 2022-11-08 at 9.06.24 PM.png" alt=""><figcaption></figcaption></figure>

## Customizing the Continue button and loading message

Additionally, you can customize the submit buttons and loading text. To do this, head over to your theme's "Edit default theme content" settings:

![](<../../.gitbook/assets/Screenshot 2024-02-19 at 12.01.12 PM.png>)

... and open the "Locksmith" tab:

![](<../../.gitbook/assets/Screenshot 2024-02-19 at 12.07.40 PM.png>)

Locksmith will use the values you customize here when displaying content to your visitors.

## Related articles:

{% content-ref url="customizing-the-customer-login-page.md" %}
[customizing-the-customer-login-page.md](customizing-the-customer-login-page.md)
{% endcontent-ref %}

{% content-ref url="customizing-the-passcode-form.md" %}
[customizing-the-passcode-form.md](customizing-the-passcode-form.md)
{% endcontent-ref %}

{% content-ref url="customizing-the-email-list-signup-form.md" %}
[customizing-the-email-list-signup-form.md](customizing-the-email-list-signup-form.md)
{% endcontent-ref %}

{% content-ref url="customizing-the-registration-form.md" %}
[customizing-the-registration-form.md](customizing-the-registration-form.md)
{% endcontent-ref %}

{% content-ref url="adding-translations-to-your-locksmith-messages.md" %}
[adding-translations-to-your-locksmith-messages.md](adding-translations-to-your-locksmith-messages.md)
{% endcontent-ref %}

{% content-ref url="../../faqs/more/how-do-i-add-a-hero-banner-image-to-locksmiths-access-messages.md" %}
[how-do-i-add-a-hero-banner-image-to-locksmiths-access-messages.md](../../faqs/more/how-do-i-add-a-hero-banner-image-to-locksmiths-access-messages.md)
{% endcontent-ref %}
