---
description: >-
  Ask for a simple confirmation before granting access to content in your
  Shopify Online Store sales channel.
---

# Confirmation key condition

This is a straightforward key condition that allows access solely based on if the customer confirms the prompt that you set. Something like the following:

<figure><img src="../../.gitbook/assets/Screenshot 2024-03-18 at 15.17.27.png" alt=""><figcaption></figcaption></figure>

To use, simply choose the key condition labelled "Permit if the customer confirms the promp&#x74;_":_

<figure><img src="../../.gitbook/assets/Screenshot 2024-03-18 at 15.14.16.png" alt=""><figcaption><p>Choose the condition from the list, or type "confirm" - which will filter the list to only show the confirmation condition.</p></figcaption></figure>

## Set the desired prompt

Common use-cases/examples include:

* Please confirm that you are over the age of 21
* By clicking 'Yes', you agree to our Terms of Service for accessing this page
* Confirm if you have read the prerequisite material to access this advanced module
* Please confirm that you have not experienced any recent health complications that could prevent you from fully engaging with this experience
* etc

Any message that you decide to use can be added directly to the **Messages** area:

<figure><img src="../../.gitbook/assets/Screenshot 2024-03-18 at 11.05.22.png" alt=""><figcaption></figcaption></figure>

{% hint style="info" %}
You can also add messages directly to the condition setup if you need unique messages per condition. Or, you can set default messages the **Settings > Messages** area of the Locksmith app, and leave Lock > Messages blank to use it.
{% endhint %}

## Changing the button text

If you need to use something other than "Confirm" as your button text, this is done through your theme. <br>

1. Go to Online Store > Themes > "Edit default theme content". [More info on that, from Shopify, here](https://help.shopify.com/en/manual/online-store/themes/customizing-themes/language/change-wording).
2. Find the Locksmith tab, and edit the button as needed:

<figure><img src="../../.gitbook/assets/Screenshot 2024-03-18 at 11.17.52.png" alt=""><figcaption></figcaption></figure>

## Adding text after the button

If you want to add text that shows up _after_ the button, simply use `{{ locksmith_confirmation_form }}` to denote where the form will show up. Then add more text as desired:

<figure><img src="../../.gitbook/assets/Screenshot 2024-03-18 at 11.10.27.png" alt=""><figcaption></figcaption></figure>

This results in the following, when Locksmith renders the prompt on button for your visitors:

<figure><img src="../../.gitbook/assets/Screenshot 2024-03-18 at 11.10.10.png" alt=""><figcaption></figcaption></figure>

## Including other form types

If you have multiple key condition types on the same lock, it might be useful to include other form types within the prompt, so that they display on the same page. We have a guide on doing this here:

{% content-ref url="showing-multiple-prompts-on-the-same-page.md" %}
[showing-multiple-prompts-on-the-same-page.md](showing-multiple-prompts-on-the-same-page.md)
{% endcontent-ref %}

## Translations

You'll need to follow the regular workflow for translating anything in your theme. To get started with that, you'll likely want to use [Shopify's free Translate and Adapt app](https://apps.shopify.com/translate-and-adapt), or one of the paid apps from the app store. [More info on this, from Shopify, here](https://help.shopify.com/en/manual/markets/languages/translate-adapt-app).

Once you have a language/locale/translation set up for your theme, you'll see a Locksmith > "Confirmation button text" area which you can edit as needed, for each of your languages. In the Translate and Adapt app, that looks like this:

<figure><img src="../../.gitbook/assets/Screenshot 2024-03-18 at 11.27.37.png" alt=""><figcaption></figcaption></figure>

To add translatable messages to the input prompt, check out or guide here:

{% content-ref url="adding-translations-to-your-locksmith-messages.md" %}
[adding-translations-to-your-locksmith-messages.md](adding-translations-to-your-locksmith-messages.md)
{% endcontent-ref %}
