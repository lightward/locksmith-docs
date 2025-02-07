---
description: >-
  This guide shows you how to use the translation filter built into Liquid to
  simplify translating your Locksmith messages
---

# Adding translations to your Locksmith messages

## Step 1 - Edit your Locksmith message

Start by adding something like the following to one of your Locksmith messages. [More info on Locksmith messages here](customizing-messages/). You can use whatever keys you like, as long as it's prefixed with **locksmith:**

```
{{ "locksmith.foo.bar" | t }}
```

Make sure to include the quotes. In the app that looks like this:

<figure><img src="../../.gitbook/assets/Screenshot 2024-03-07 at 16.45.05.png" alt=""><figcaption><p>Any Liquid or HTML code will still be rendered as normal, so add as much of that as you need.</p></figcaption></figure>

**Saving a lock with any messages that contain the above formatting will trigger a Locksmith update** which will automatically edit (all of) the locale files in your theme so that they include a new editable and translatable attribute. This is an example of what that might look like from within the locale files in your theme:

<figure><img src="../../.gitbook/assets/Screenshot 2024-03-06 at 14.57.22.png" alt=""><figcaption></figcaption></figure>

{% hint style="info" %}
You can add this to any of Locksmith's messages, including the access denied content, guest message content, passcode prompt, etc.
{% endhint %}

## Step 2 - Adding the translations to your theme and locales

#### Default locale theme content

You can immediately open Online Store > Themes > "Edit default theme content" to edit what is shown there for your default language. If you're not sure how to edit the default content in your theme, check out [Shopify's guide on that here](https://help.shopify.com/en/manual/online-store/themes/customizing-themes/language/change-wording).

When editing the default theme content, you'll now see a Locksmith tab, with a section that corresponds to what you added to the section above:

<figure><img src="../../.gitbook/assets/Screenshot 2024-03-07 at 16.28.33.png" alt=""><figcaption><p>You might also see a "Forms" area in there. This is something automatically added by Locksmith, if you have certain condition types, in order to support translating the buttons for their forms.</p></figcaption></figure>

#### Translations

You'll need to install the free [Translate and Adapt](https://apps.shopify.com/translate-and-adapt) app from Shopify, or one of the other 3rd party alternatives. [More info on how to use the Translate and Adapt app here](https://help.shopify.com/en/manual/markets/languages/translate-adapt-app).

If you've added the Translate and Adapt app to your store, you'll see the link to it from within the "Theme content" area. While you can open the app from your apps list, you can also open directly from there:

<figure><img src="../../.gitbook/assets/Screenshot 2024-03-07 at 16.25.30 (1).png" alt=""><figcaption></figcaption></figure>

Once inside the "Translate and Adapt" app, **scroll down to find the Theme > "default theme content" area and press on it**.

Then, similarly to above, you'll see a Locksmith section that you are free to edit as much as you need.

**Do this for all of your store languages.**

<figure><img src="../../.gitbook/assets/Screenshot 2024-03-07 at 16.28.18 (2).png" alt=""><figcaption></figcaption></figure>

## Important caveat

The messages added with the above method are managed by Locksmith. If you delete the declaration in your messages (the `{{ "locksmith.foo.bar" | t }}` part), the corresponding messages will be deleted from (all of) your locale files.

If you want a persistent message, that isn't directly connected to, managed by, or deleted by Locksmith. You'll need to go with a more manual approach. Additionally, there are apps out there that can manage this kind of thing automatically.&#x20;

To start, head into the language "locale" file you'd like to update in your theme, and then add a new entry at the bottom. You might see one Locksmith entry already - **do not add it to that one**. Just create a new one. It can be called anything that works for you, such as"locksmith\_messages", with "passcode" inside of that entry. That looks like this: \
\
![](<../../.gitbook/assets/Screenshot 2024-01-22 at 4.33.42 PM.png>)



**Add this same entry into all desired locales files**, and update the "Enter Passcode" to the specific language.\
\
Next, in your passcode prompt message, use the translate filter on that variable. Here's an example: \


<figure><img src="../../.gitbook/assets/Screenshot 2024-01-22 at 4.37.03 PM.png" alt=""><figcaption><p>Any html or styling will need to be around that, like the &#x3C;p>&#x3C;/p> in the above example. </p></figcaption></figure>



\
