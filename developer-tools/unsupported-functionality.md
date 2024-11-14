---
description: >-
  Here's a list of interesting ways to interact with Locksmith. None of these
  are officially supported. We can't troubleshoot your custom code. :)
---

# Unsupported functionality

## Create locks via the API

Example API payload:&#x20;

```
https://uselocksmith.com/api/unstable/lock

payload:

create_key_payload = {
"resource_id": shopify_product_id,
"resource_type": "product",
"resource_options": {},
"enabled": True,
"options": {
"hide_links_to_resource": False,
"hide_resource": False,
"hide_resource_from_sitemaps": False,
"manual": False,
"noindex": True
},
"keys": [
{
"options": {
"customer_autotag": "",
"force_open": False,
"redirect_url": "",
"inverse": False
},
"conditions": [
{
"type": "secret_link",
"inverse": False,
"options": {
"customer_remember": True,
"secret_link_code": secret_link_code
}
}
]
}
]
}
```

## Working with passcodes and secret links

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
      $.post('/cart/update.json', { attributes: { passcode: Locksmith.params.passcode } })
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

##

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
