# How do I hide my Shopify store's header and footer

The Locksmith can be used to lock most resources in your store, preventing their content from appearing between the header and footer of the site. However, Locksmith doesn't have a built in way to lock or hide the header and footer in your theme.&#x20;

It's worth noting that some locks have an option that can be used to conditionally hide specific menu navigation links for locked resources. More on that in our guide below:

{% content-ref url="../../faqs/more/how-do-i-hide-menu-navigation-links-to-my-locked-resources.md" %}
[how-do-i-hide-menu-navigation-links-to-my-locked-resources.md](../../faqs/more/how-do-i-hide-menu-navigation-links-to-my-locked-resources.md)
{% endcontent-ref %}

## Custom options

{% hint style="info" %}
In many cases, some Liquid code can be used to hide the store's header or footer section. However, this customisation isn't something that we can set up or maintain for you.
{% endhint %}

The intent here is to illustrate that conditionally hiding the site's header and footer can be set up with some custom Liquid.

In general, this can be straightforward to set up, if you have a little experience with Liquid and editing your theme's code. Alternatively, a developer or theme designer should be able to help with this.

### Examples of the header section being conditionally hidden

The header and footer section groups are typically located in the theme.liquid layout file in Shopify 2.0 themes. A Liquid condition can be set up to show or hide these sections based on a Liquid attribute, such as a customer being signed into a store account, or a customer viewing products from a specific collection.

{% hint style="info" %}
In the example below the Dawn theme has been used and the header section is titled "`header-group".`
{% endhint %}

#### Hiding the header unless a customer is signed in

```
{% raw %}
{% if customer %}
    {% sections 'header-group' %}
{% endif %}
{% endraw %}
```

#### Hiding the header unless a customer's account has a specific customer tag

```
{% raw %}
{% if customer.tags contains "example-tag" %}
    {% sections 'header-group' %}
{% endif %}
{% endraw %}
```

#### Hiding the header using some of Locksmith's manual code

Locksmith has "manual code" that can sometimes be used to hide the store's header and footer. The code used in this example will interact with all locks in your store. You may need to consider using some additional Liquid to limit this section hiding to specific locked resources if needed.

The following code can be added to the top of the theme.liquid layout file to include Locksmith's variables that will support the function of Locksmith's manual code:

```
{% raw %}
{% capture var %}{% render 'locksmith-variables', variable: 'access_granted', scope: 'subject', subject: product %}{% endcapture %}{% if var == 'true' %}{% assign locksmith_access_granted = true %}{% else %}{% assign locksmith_access_granted = false %}{% endif %}
{% endraw %}
```

The `{% sections 'header-group' %}` can be wrapped in Locksmith's manual code to show the header, if the resource that's currently being viewed isn't locked:

```
{% raw %}
{% if locksmith_access_granted %}
    {% sections 'header-group' %}
{% endif %}
{% endraw %}  
```

We have some more information on Locksmith's manual code in the guide here:

{% content-ref url="manual-mode.md" %}
[manual-mode.md](manual-mode.md)
{% endcontent-ref %}

## Need something custom set up for your store?

There's a Shopify directory here if you're looking to hire someone to help with something like this: [https://www.shopify.com/partners/directory](https://www.shopify.com/partners/directory)

## Something else not covered here?&#x20;

Let us know by emailing us at: **team@uselocksmith.com**
