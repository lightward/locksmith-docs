---
description: >-
  Here's a list of interesting ways to interact with Locksmith. None of these
  are officially supported. We can't troubleshoot your custom code. :)
---

# Unsupported functionality

## Working with passcodes and secret links

{% hint style="info" %}
**Note:** The examples below use jQuery. If jQuery isn’t already included in your theme, you’ll need to load it first.&#x20;
{% endhint %}

<details>

<summary>Including jQuery </summary>

To include jQuery you. can add the following script right before the example scripts in this section: &#x20;

```
<script src="https://ajax.googleapis.com/ajax/libs/jquery/3.5.1/jquery.min.js" type="text/javascript"></script>
```

</details>

The passcode and secret link can be extracted using the following:&#x20;

`Locksmith.params.passcode`

`Locksmith.params.secret_link`

Example usage: add the passcode as a cart attribute with javascript:&#x20;

```
<script>
  window.addEventListener('load', () => {
    if (Locksmith.params.passcode) {
      $.post('/cart/update.json', { attributes: { passcode: Locksmith.params.passcode } })
    }
  });
</script>
```



Second example: Do the same thing, but add the "secret" part of the secret link instead:&#x20;

```
<script>
  window.addEventListener('load', () => {
    if (Locksmith.params.secret_link) {
      $.post('/cart/update.json', { attributes: { secret-link: Locksmith.params.secret_link } })
    }
  });
</script>
```

## Working with Passcode/Secret Link expiry in UNIX timestamp

When you've set an expiration time in the passcode or secret link keys, you can see the expiration time as a UNIX timestamp. That's found in cart.json between the "-" and the ":" in the Locksmith entry:&#x20;

![](<../.gitbook/assets/Screenshot 2023-11-01 at 3.15.13 PM.png>)

The number before the "-" is the key id that was used to open the lock. What's after the colon is not valuable.&#x20;

## Clearing the Locksmith cart attribute

Locksmith adds information as a cart attribute when using remote keys. You can clear that manually with something like this. This triggers when the page loads:&#x20;

```
<script>
  window.addEventListener('load', () => {
    document.cookie="locksmith-params={};path=/;";
    $.post('/cart/update.json', {attributes: {locksmith: null}});
    document.cookie="locksmith-params={};path=/;";
  });
</script>
```

## Responsive background image for the passcode form

This code is designed to be added to the "Passcode prompt" field in Locksmith's settings, or the "Passcode prompt" field on a lock's settings page.

* Update `background-image:` attribute with the URL for your image
* Make sure you update the `padding-top:` attribute with your images aspect ratio. For example, calculate the aspect ratio of an image of size 1080\*1920 pixels like this: ((1080 / 1920) \* 100)% = 56.25%

```
<style>
    .locksmith-passcode-container {
        content: "";
        display: block;
        padding-top: 56.25%; /* Adjust this value based on the actual aspect ratio of your background image. For example, here is a calculation of the aspect ratio for an image of size 1080*1920 pixeles: ((1080 / 1920) * 100)% = 56.25% */
        flex-direction: column;
        justify-content: center; /* Aligns content vertically center */
        align-items: center; /* Aligns content horizontally center */
        height: 100%; /* Ensures the container takes full height of its parent */
    }
    #locksmith-content::before {
        content: "";
        position: absolute;
        top: 0;
        left: 0;
        width: 100%;
        height: 100%;
        background-image: url('https:// your image source here');
        background-size: cover;
        background-repeat: no-repeat;
        z-index: -1;
    }

    #locksmith-content {
        position: relative;
    }

    #locksmith-passcode-form {
        position: absolute;
        top: 50%; /* Aligns content vertically center */
        left: 50%; /* Aligns content vertically center */
        transform: translate(-50%, -50%); /* Adjusts the position of the passcode from so that its center aligns with the center of the div. */
        box-sizing: inherit;
        max-width: 475px; /* Sets the maximum width of the passcode form */
        width: 100%;
        padding: 20px 25.45px;
        z-index: 1;
    }
</style>
```

## Redirecting after customer registration

```
<script>
  (function() {
    var current_url = window.location.href;
    var REDIRECT_PATH = '{{ current_url }}{% raw %}
{% if collection %}/collections/{{ collection.handle }}{% endif %}
{% endraw %}/products/{{ product.handle }}';

    var selector = '#create_customer, form[action$="/account"][method="post"]',
        $form = document.querySelectorAll(selector)[0];

    if ($form) {
      $redirect = document.createElement('input');
      $redirect.setAttribute('name', 'return_to');
      $redirect.setAttribute('type', 'hidden');
      $redirect.value = REDIRECT_PATH;
      $form.appendChild($redirect);
    }
  })();
</script>
```



## Removing product information from Shopify Analytics in the page source

Sometimes, Shopify Analytics, Google Analytics, or Web Pixels can leave bits of information about your locked products in the page source. Locksmith can't filter that, since it's outside of your theme, but you may be able to replace the content with null values for just your locked resources. \


Here's an example of how that might work with Shopify Analytics scripts:&#x20;

```
{% raw %}
{% comment %}
  Find Shopify's analytics code and replace it with something free of
  potentially-sensitive details, if Locksmith thinks access should be denied.
{% endcomment -%}
​
{% capture replacement_script_tag -%}
  <script>window.ShopifyAnalytics = window.ShopifyAnalytics || {};
  window.ShopifyAnalytics.meta = window.ShopifyAnalytics.meta || {};
  window.ShopifyAnalytics.meta.currency = '{{ cart.currency.iso_code }}';</script>
{%- endcapture -%}
​
{% if locksmith_access_denied -%}
  {% assign content_for_header_pieces = content_for_header | split: "<script>" -%}
  {% for piece in content_for_header_pieces -%}
    {% unless piece contains "window.ShopifyAnalytics = window.ShopifyAnalytics || {};" -%}
      {% continue -%}
    {% endunless -%}
​
    {% assign complete_script_tag = piece | split: "</script>" | first | prepend: "<script>" | append: "</script>" -%}
    {% assign content_for_header = content_for_header | replace: complete_script_tag, replacement_script_tag -%}
    {% break -%}
  {% endfor -%}
{% endif -%}
{% endraw %}

```
