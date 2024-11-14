---
description: >-
  An overview of the ways you can customize the the email list sign up prompt
  for our newsletter key conditions
---

# Customizing the email list signup form

This applies to Klaviyo and Mailchimp key condition types - the setup instructions for which are linked below:

* [Klaviyo](klaviyo.md)
* [Mailchimp](mailchimp.md)

## Adding a regular prompt

You can add any text prompt to the "Mailing list signup prompt" area, and it will be displayed right before the email input. The default prompt is shown below:

<figure><img src="../../.gitbook/assets/Screenshot 2024-08-02 at 12.37.37.png" alt=""><figcaption></figcaption></figure>

In addition, you can add any code to this area, and it will be rendered normally, as if adding it to the theme. Including:

* HTML - using regular HTML tags
* CSS - using \<style> _your CSS code here_ \</style>
* Javascript - using \<script> _your javascript code here_ \</script>
* Liquid - using [regular Liquid syntax](https://shopify.dev/api/liquid/basics)

## Adding content after the form

Use `{{ locksmith_email_form }}` to denote where the form (input and button) itself will go, and then add in content that you want to display before and after it.

```
<p>Subscribe to our mailing list to continue! </p>

{{ locksmith_email_form }}

<p> Content to be displayed after the form </p>
```

This results in the following:

<figure><img src="../../.gitbook/assets/Screenshot 2024-08-02 at 12.42.43.png" alt=""><figcaption></figcaption></figure>

## Editing the "Continue" and "One moment" text

To edit the text for the button, you'll need to follow Shopify's guide to "Edit default theme content":

{% embed url="https://help.shopify.com/en/manual/online-store/themes/customizing-themes/language/change-wording" %}

Once there, you'll find a Locksmith tab in which you can edit the text as needed:

<figure><img src="../../.gitbook/assets/Screenshot 2024-08-02 at 13.21.39 (1).png" alt=""><figcaption><p>You may need to press the "..." button to the right, which will give you the option to choose more tabs, if the "Locksmith" tab isn't visible right away.</p></figcaption></figure>

## Translating messages

We have a dedicated guide on adding translated messages here:

{% content-ref url="adding-translations-to-your-locksmith-messages.md" %}
[adding-translations-to-your-locksmith-messages.md](adding-translations-to-your-locksmith-messages.md)
{% endcontent-ref %}

## Including other form types

If you have multiple key condition types on the same lock, it might be useful to include other form types within the prompt, so that they display on the same page. We have a guide on doing this here:

{% content-ref url="showing-multiple-prompts-on-the-same-page.md" %}
[showing-multiple-prompts-on-the-same-page.md](showing-multiple-prompts-on-the-same-page.md)
{% endcontent-ref %}

Please note that this is NOT compatible with overriding/editing the form itself (as detailed in the next section).&#x20;

## Overriding or editing the form itself

{% hint style="warning" %}
**Note**: This is advanced and requires knowledge of code. If you choose to override the form, the coding and style is up to you, we are not able to create a new form for you or edit the code for you. With that said, you are still free to contact us with any troubleshooting questions that you have.
{% endhint %}

Use the following steps in order to override the form. The screenshots are taken from Chrome, but the steps are similar if using other browsers.

1. Once you've created a Mailchimp or Klaviyo key condition, open up your locked page in your storefront.&#x20;
2. Right click on the email list signup form to inspect the code.&#x20;

<figure><img src="../../.gitbook/assets/Screenshot 2024-08-02 at 13.08.39.png" alt=""><figcaption></figcaption></figure>

3.  This should take you to the "Elements" tab. There, find the \<div> element with the "locksmith-email-container" class:&#x20;

    ```php
    <div class="locksmith-email-container container page-width">
    ```

    \
    You can copy the entire element and all child elements like so:

<figure><img src="../../.gitbook/assets/Screenshot 2024-08-02 at 11.57.43.png" alt=""><figcaption></figcaption></figure>

4. Paste this directly into your "Mailing list signup prompt". You should end up with something like this:

<figure><img src="../../.gitbook/assets/Screenshot 2024-08-02 at 13.16.12.png" alt=""><figcaption><p>The "key_condition_id" will vary depending on you <em>actual</em> key condition id</p></figcaption></figure>

5. Save that, and open your locked page again on your storefront. If everything worked, your email list signup prompt and form should look exactly like it did before. But now you have the ability to edit it as needed. Please note that you must always include a `<form>` tag with an id of `locksmith_email_form` - otherwise Locksmith will try to include the form itself, and you'll end up with two forms - so don't remove that when editing the code.
