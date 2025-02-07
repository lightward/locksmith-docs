# How do I change where customers are redirected to after registration on Shopify

This guide is specific to Locksmith key conditions that require a customer to sign into a store account.

{% content-ref url="../../keys/customer-account-keys.md" %}
[customer-account-keys.md](../../keys/customer-account-keys.md)
{% endcontent-ref %}

Locksmith will automatically present locked content to customers after they sign into a store account and are granted access by a locks key conditions. Part of this involves redirecting customers back to the store location where they signed in for access.

However, Locksmith doesn't have a built in way to automatically redirect customers back to locked content after _registration_. This is because Locksmith doesn't handle the registration process at all.

{% hint style="info" %}
Locksmith uses the [built in customer account system that comes with your store](https://help.shopify.com/manual/customers/customer-accounts)! This means it doesn't create a separate registration form, sign-in form, or customer database.

All Shopify themes come with a registration form that includes Name, E-mail, and Password fields.
{% endhint %}

## Changing the default location customers are redirected to after registration

The default location customers are redirected to after registration is determined by the theme and is typically the customer account page. \
\
The team over at Helium apps have written blog post on how to change that location using their app _or_ some JavaScript:

[Helium - How to manually redirect customers after registration on Shopify](https://heliumdev.com/blog/shopify-redirect-after-registration)

## How to redirect customers to unlocked content after a customer creates an account

The access message and content that Locksmith presents for customer account key conditions can be modified to include a login and registration form on the same page. See our Customizing the customer login page guide:

{% content-ref url="../../tutorials/more/customizing-messages/customizing-the-customer-login-page.md" %}
[customizing-the-customer-login-page.md](../../tutorials/more/customizing-messages/customizing-the-customer-login-page.md)
{% endcontent-ref %}

We don't officially have support for a return redirect after customer registration, but it should be possible to achieve that using Helium's redirect script from the [above section](how-do-i-change-where-customers-are-redirected-to-after-registration-on-shopify.md#changing-the-default-location-customers-are-redirected-to-after-registration) and modifying that script a little.

Replace the following:&#x20;

```
var REDIRECT_PATH = '/checkout';
```

With this code:

```
var current_url = window.location.href;
var REDIRECT_PATH = '{{ current_url }}{% raw %}
{% if collection %}/collections/{{ collection.handle }}/products/{{ product.handle }}{% elsif product %}/products/{{ product.handle }}{% elsif page %}/pages/{{ page.handle }}{% else %}{% endif %}
{% endraw %}';
```

The above modification should only work to redirect customers to locked content if the registration form was submitted from the access message Locksmith presents, for product, collection and page locks. For other parts of the store, customers will be returned to the homepage.

## Related articles

{% content-ref url="../../tutorials/more/customizing-messages/customizing-the-registration-form.md" %}
[customizing-the-registration-form.md](../../tutorials/more/customizing-messages/customizing-the-registration-form.md)
{% endcontent-ref %}

{% content-ref url="../../tutorials/approving-customer-registrations.md" %}
[approving-customer-registrations.md](../../tutorials/approving-customer-registrations.md)
{% endcontent-ref %}

## Something else not covered here?&#x20;

Let us know by emailing us at: **team@uselocksmith.com**
