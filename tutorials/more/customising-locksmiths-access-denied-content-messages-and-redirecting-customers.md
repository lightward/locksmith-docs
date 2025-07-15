# Customizing Locksmith’s "Access denied content" messages, and redirecting customers

Locksmith access denied content is presented to customers who are signed in, but don’t meet the access requirements of the lock (e.g. the customer doesn’t have the specific customer tag that is required for access). Or when the lock has no keys.

## Key conditions that use the “Access denied content" filed:

* is tagged with…
* has one of many email addresses
* has an email address from an input list…
* the customer's email contains…
* has placed at least x orders
* has purchased…
* (custom Liquid) in some cases

{% content-ref url="../../keys/customer-account-keys.md" %}
[customer-account-keys.md](../../keys/customer-account-keys.md)
{% endcontent-ref %}

## 1. Modifying the default message

The "Access denied content" message field can be modified in the same way as Locksmith’s other access messages, including using code to modify the appearance and functionality of the message.

{% content-ref url="customizing-messages.md" %}
[customizing-messages.md](customizing-messages.md)
{% endcontent-ref %}

### The following code can be used in this field:

* HTML
* CSS (via the \<style> tag)
* Javascript (via the \<script> tag)
* Liquid (Shopify's template language for themes)

## 2. Adding the registration form to this page

Simply add the following Liquid to the "Access denied content" message field:&#x20;

```
{{ locksmith_customer_register_form }}
```

This will render the theme’s default registration form.&#x20;

## 3. Adding a custom registration form or content

Liquid code can be used to **render** a **snippet** or section from your theme that contains a custom form or message.

1. [render](https://shopify.dev/docs/api/liquid/tags/render) - Renders a snippet

```
{% render 'filename' %}
```

2. [section](https://shopify.dev/docs/api/liquid/tags/section) - Renders a section.

```
{% section 'name' %}
```

## 4. Automatically redirecting customers to another part of your store

A JavaScript redirect can can be added to the “"Access denied content" message field if you would like to automatically send customers who are denied access to your lock, to some other part of your store.&#x20;

This might be useful for a few different reasons:

* To take customers to a specific product they can purchase for access. For example, to buy a product, or membership, or subscription for access.
* To take customers to an information page.
* To take customers to a custom registration form
* To direct customers to an alternative resource

Simply add the following code to the "Access denied content" message field and modify the URL to your desired location.

<pre><code>&#x3C;script>
<strong>    window.location.replace("http://www.example.com");
</strong>&#x3C;/script>
</code></pre>



<figure><img src="../../.gitbook/assets/Screenshot 2024-08-05 at 1.31.39 PM.png" alt=""><figcaption></figcaption></figure>

## Related articles:&#x20;

{% content-ref url="adding-translations-to-your-locksmith-messages.md" %}
[adding-translations-to-your-locksmith-messages.md](adding-translations-to-your-locksmith-messages.md)
{% endcontent-ref %}

{% content-ref url="customizing-the-customer-login-page.md" %}
[customizing-the-customer-login-page.md](customizing-the-customer-login-page.md)
{% endcontent-ref %}

{% content-ref url="customizing-the-registration-form.md" %}
[customizing-the-registration-form.md](customizing-the-registration-form.md)
{% endcontent-ref %}

{% content-ref url="../selling-digital-content-on-shopify.md" %}
[selling-digital-content-on-shopify.md](../selling-digital-content-on-shopify.md)
{% endcontent-ref %}

{% content-ref url="recharge.md" %}
[recharge.md](recharge.md)
{% endcontent-ref %}

{% content-ref url="../../keys/more/newsletter-keys.md" %}
[newsletter-keys.md](../../keys/more/newsletter-keys.md)
{% endcontent-ref %}

{% content-ref url="../../faqs/more/how-do-i-change-where-customers-are-redirected-to-after-registration-on-shopify.md" %}
[how-do-i-change-where-customers-are-redirected-to-after-registration-on-shopify.md](../../faqs/more/how-do-i-change-where-customers-are-redirected-to-after-registration-on-shopify.md)
{% endcontent-ref %}

### Something else not covered here?

Let us know by emailing us at: **team@uselocksmith.com**
