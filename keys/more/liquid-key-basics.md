# Liquid key basics

Locksmith allows you to create a custom keys that use Liquid to determine whether or not the current visitor has access. This gives you a few more options than what comes with Locksmith's out-of-the-box key conditions.

Before continuing on, you may want to [check out Shopify's Liquid reference](https://shopify.dev/api/liquid), as that will give you a good idea of the kinds of things you can use when creating Liquid key conditions. Keep in mind that while Liquid key conditions can add more versatility, they are still limited to the scope of what's already available inside of Shopify's Liquid engine for the Online Store channel.&#x20;

{% hint style="info" %}
This is an advanced guide that requires knowledge of [Shopify's Liquid language](https://shopify.dev/api/liquid). If you're a developer type, read on! Otherwise, please note that Locksmith support is not able to write advanced custom Liquid keys for you. While we are happy to answer any questions you have along the way, if you need help writing these, you'll need to hire a paid Shopify expert. [Our list of partners is here](https://locksmith.partnerpage.io/). Alternatively, you can check [Shopify's own list of Shopify experts](https://www.shopify.com/partners/directory).
{% endhint %}

To create a Liquid key condition, start by selecting it from the key condition list. You'll be presented with the key condition area for Liquid key conditions:

<figure><img src="../../.gitbook/assets/2024-06-14 10.35.34.gif" alt=""><figcaption></figcaption></figure>

## The "Liquid condition"

This is where you'll write the primary condition, using Liquid. The condition simply needs to evaluate to true or false.

For example, consider if you simply wrote the following:

`{% if`**`false`**`%}`

This would result in this particular key never opening, since it's always false. This is not necessarily advisable(it would be the equivalent of adding no keys at all), but it's a proof of concept.

So, here are some examples of useful conditions.

#### **To check for a metafield**

`{% if customer.metafields.namespace.key == "matching-value" %}`

{% hint style="info" %}
The metafield must be public in order for it to be accessed this way. [More information on Shopify meta-fields here](https://shopify.dev/api/liquid/objects#metafield).
{% endhint %}

#### To check if the customer has at least 5 items in the cart currently

`{% if cart.item_count > 4 %}`

#### To check if the customer has spent at least $50 in the past

`{% if customer.total_spent > 5000 %}`

#### To check if the current page is a using the "collection" template

`{% if template == "collection" %}`

{% hint style="info" %}
For most themes, this should match any collection pages unless you've created custom templates. You can use this strategy for other resource types as well (products, pages, etc).
{% endhint %}

#### To check for a specific sub-string inside of the current URL

`{% if canonical_url contains "/special-product-handle" %}`

{% hint style="info" %}
The **canonical\_url** global Liquid object is accessible anywhere in the theme and always contains the entire URL of the current page, but does NOT contain any URL parameters. [More information from Shopify on it here](https://shopify.dev/api/liquid/objects#canonical\_url).
{% endhint %}

#### To check for some attribute of the request object

`{% if request.page_type == "index" %}`

{% hint style="info" %}
As seen here, another Liquid global object of note is the **request** object, and it can very useful in this context. [Check out Shopify's documentation on it here](https://shopify.dev/api/liquid/objects#request).
{% endhint %}

## The "Liquid prelude"

This is a place for you to write any code that that you may need to set up the Liquid condition. It does _not_ need to evaluate to true or false, but it does need to use valid Liquid syntax.

Basically, you can assign to any custom variable in the prelude, and then use that variable in the condition to ultimately decide whether or not the customer qualifies to use this key.

For example, your prelude could look something like this:

<pre><code>{% assign purchase_allowed = true %}
<strong>{% for item in cart.items %}
</strong>  {% if item.product.handle contains "members-only" %}
    {% assign purchase_allowed = false %}
  {% endif %}
{% endfor %}
</code></pre>

So now, in the "Liquid condition", you would have access to the `purchase_allowed` variable, so it would simply look like this:

`{% if purchase_allowed %}`

So that would give you even more flexibility to write different Liquid conditions that can be used to set up your locks and keys.

## Other resources

Relatedly, you can also use Liquid to create Locks! More information on that here:

{% content-ref url="../../tutorials/more/liquid-locking-basics.md" %}
[liquid-locking-basics.md](../../tutorials/more/liquid-locking-basics.md)
{% endcontent-ref %}



As always, feel free to check in with us via email at **team@uselocksmith.com**, if you have any questions about any of this!
