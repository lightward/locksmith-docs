---
description: >-
  Restricting access to only specific parts of a page in your Shopify Online
  Store
---

# 🛠️ Manual mode

Out of the box, Locksmith automatically protects all content between the header and footer, for everything covered by your locks.

Sometimes this can be too aggressive - you might want to allow visitors to preview your products without being able to see pricing, for example. Or, you might want to protect _just_ the checkout button in your cart.

**Locksmith comes with an advanced manual mode that allows for this sort of thing.** It disables Locksmith's full-page protection, stepping aside so that some custom code in your theme can take responsibility for hiding part of your content.

Two important notes:

* If a particular piece of content has multiple locks in play (for example, if the customer is viewing a product that is a part of several locked collections), manual locks will _only_ work if _all_ applicable locks have manual mode enabled.
* Remote keys require a special initialization step, when working with manual mode. For more on this, jump to the [interactions with remote keys section](manual-mode.md#interactions-with-server-keys), later in this article.

## Purpose-specific guides

Use these if you already know that you're using manual locking for one of the following:

* [Hiding product prices and/or the add to cart button](../hiding-prices.md)
* [How to hide theme sections, blocks, and snippets](how-to-hide-theme-sections-blocks-and-snippets.md)
* [Restricting checkout from the cart](restricting-checkout-from-the-cart.md)

## General guide

_Because each theme is a bit different, manual locking does require manual coding. If you install a new theme down the road, these changes will need to be re-applied._

### Step 1: Enable manual mode

{% hint style="info" %}
**Note**: _Before_ proceeding, it's important to understand that enabling manual mode will disable full-page locking for any content covered by this lock. Only proceed if you are okay with your content being open to the public for short time while you add in the code in the next step. If you are not okay with this, consider doing these steps in opposite order. The only downside is that you won't be able to see the code changes as you make them.
{% endhint %}

Moving on, the steps are as follows

1. Open up the Locksmith lock that you want to enable manual locking for.
2. Click on "Advanced" in the lock Settings section and tick the checkbox for "Enable manual locking". Then, hit save. Screenshot below...

![](<../../.gitbook/assets/Screenshot 2024-10-18 at 11.14.06 AM.png>)

That's it! Locksmith will hold off on its full-page protection with this enabled, and allow your custom code to enforce protection.

### Step 2: Updating your theme for manual locking

{% hint style="info" %}
**Note**: This part gets a little technical. If you are developer type that wants to take this on, proceed! Otherwise, the Locksmith team can help you add in the coding for most manual locks - within reason!
{% endhint %}

Manual locking leverages Liquid variables to empower you to render content however you'd like, based on Locksmith's permissions.

Locksmith's variables are loaded via the `locksmith-variables` snippet. It can be included two ways, depending on context:

#### Using \{% render %\}

This usage supports "exporting" a single variable at a time, by informing the snippet of the object you're interested in (e.g. a specific product), capturing the rendered result, and performing any post-processing of the captured value necessary. For booleans and arrays, post-processing _is_ necessary: the render tag necessarily results in a string. Boolean values are represented as their string equivalents, and arrays are represented as comma-delimited values.

The variable names that may be exported match Locksmith's standard list of variables; for variable names and definitions, [see Locksmith variables](../../developer-tools/locksmith-variables.md).

To access any supported variable, use this approach:

```
{% capture var %}{% render 'locksmith-variables', variable: 'access_granted', scope: 'subject', subject: product %}{% endcapture %}
{% if var == 'true' %}
  {% assign locksmith_access_granted = true %}
{% else %}
  {% assign locksmith_access_granted = false %}
{% endif %}
```

For variants, one additional argument is required for the render tag: `subject_parent`, defining the product that contains the variant you're checking in on.

```
{% render 'locksmith-variables', variable: 'access_granted', scope: 'subject', subject_parent: product, subject: variant %}
```

Feel free to adjust this code to taste. Only the capture and render tags need to be used exactly as written; process the rendered value string in whatever way you need to. Use the support button in the corner if you've got any questions. :)

#### Using \{% include %\}

The include tag has been [deprecated](https://help.shopify.com/en/themes/liquid/tags/deprecated-tags#include) by Shopify. Locksmith still uses this variable itself, in situations where overriding variables is important. You shouldn't need to use this on a regular basis, but we document it here for completeness.

1. `{% include 'locksmith-variables' %}` – In this mode, Locksmith will autodetect the applicable locks for the current url, and set up its access variables accordingly.
2. `{% include 'locksmith-variables', locksmith_subject: foobar %}` – In this mode, you specify the exact object that Locksmith should base its access decisions upon. Use this if you need to load up Locksmith's variables based on the cart, or a certain product, or some other Liquid variable, regardless of what url the user is on

For the code following this tag, all of Locksmith's standard variables are now automatically available, their names being prefixed with "locksmith\_". For example, you may now use "locksmith\_locked", "locksmith\_access\_granted", and "locksmith\_manual\_lock". The _values_ differ only in that arrays of integer IDs (e.g. "locksmith\_lock\_ids", "locksmith\_opened\_lock\_ids", and "locksmith\_key\_ids") are exported as arrays of numeric strings.

For (unprefixed) variable names and definitions, see [Locksmith variables](https://docs.uselocksmith.com/article/474-locksmith-variables).

After loading the Locksmith variables, wrap the code you'd like to conditionally hide like this:

```
{% if locksmith_access_granted %}
  You've got access!
{% endif %}
```

### Interactions with remote keys <a href="#interactions-with-server-keys" id="interactions-with-server-keys"></a>

Some keys that you can configure in Locksmith require contacting our servers, remotely, in order to determine if access should be granted. Remote keys include:

* [Passcode keys](../../keys/passcode-keys.md)
* [Secret link keys](../../keys/secret-link-keys.md)
* [Newsletter keys](../../keys/more/newsletter-keys.md)
* [Location keys](../../keys/visitor-location-keys.md)

{% hint style="info" %}
Locksmith used to refer to these as "server keys" (in contrast to "native keys").

These days, we refer to them as "remote keys" (in contrast to "local keys").
{% endhint %}

In most usages, remote keys don't require any theme configuration. Locksmith will render a loading screen, with a spinner animation; once it's finished initializing, it'll reload the page automatically, and your storefront's normal content will be displayed.

When using manual mode, Locksmith will show your storefront content immediately by design. Manual mode leaves you with the responsibility of updating your theme's code to show or hide content based on Locksmith's decisions. Without remote keys, this is a simple boolean: either access is granted, or denied. When combined with remote keys, we add a third state: either access is granted, or denied,  _or_ Locksmith hasn't finished initializing and the page should be refreshed.

To explain by example: in cases like[ price hiding](../hiding-prices.md), this means that there are three possibilities for the content you should display: either you should display the price (and add-to-cart form), or you should hide it, _or_ you should display a "please wait" message, coupled with some JavaScript that reloads the page when Locksmith has finished initializing in the background. This is necessary when using location-based, IP address, and secret links keys.&#x20;

To accomplish this, adapt this code for your own purposes:

```
{% if locksmith_access_granted %}
  <!-- the original add-to-cart button code -->
{% elsif locksmith_initialized %}
  <p>No access for you!</p>
{% else %}
  <p>Please wait&hellip;</p>
  <script>
    Locksmith.on('initialize', function () { window.location.reload(); });
  </script>
{% endif %}
```

The code above assumes that you've already exported the `locksmith_access_granted` and `locksmith_initialized` variables. Use one of these options to export those variables, making sure to do so _before_ making any content decisions:

```
{% capture var %}{% render 'locksmith-variables', variable: 'access_granted', scope: 'subject', subject: product %}{% endcapture %}
{% if var == 'true' %}
  {% assign locksmith_access_granted = true %}
{% else %}
  {% assign locksmith_access_granted = false %}
{% endif %}

{% capture var %}{% render 'locksmith-variables', variable: 'initialized', scope: 'subject', subject: product %}{% endcapture %}
{% if var == 'true' %}
  {% assign locksmith_initialized = true %}
{% else %}
  {% assign locksmith_initialized = false %}
{% endif %}
```

```
{% include 'locksmith-variables' %}
```

{% hint style="danger" %}
Manual locking is _**not**_ compatible with [variant locks](locking-variants/).
{% endhint %}
