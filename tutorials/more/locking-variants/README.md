# Locking variants

Manage pricing and other options by creating multiple variants, and use Locksmith to manage access.

In addition to managing access to your products and collections, Locksmith can protect individual variants _within_ your product listings.

_New to product variants? Learn more here:_ [_help.shopify.com/manual/products/variants_](https://help.shopify.com/manual/products/variants)

**This is a powerful feature! It can allow you to tune your product listings in a way that previously required elaborate coding, or deep manual integration with other apps.**

With variant locking, you can:

* ... set up wholesale pricing on your existing products without creating duplicate products, then ensure that only your wholesalers can view those prices.
* ... reserve a certain amount of stock for a particular customer.
* ... allocate your inventory by distribution center, and restrict access regionally.
* ... add bulk quantities for your trade customers, only allowing pre-approved customers to access it.

**Note: This feature may conflict with other apps. See the&#x20;**_**Incompatibilities**_**&#x20;section below for more.**

### Creating a variant lock

Start by ensuring you've got at least one product variant set up in your catalog. (Learn how to set these up [for new products](https://help.shopify.com/manual/products/variants#creating-variants-for-a-new-product), and [for existing products](https://help.shopify.com/manual/products/variants#creating-additional-variants-of-an-existing-product).)

Then, open Locksmith, and search for the name of your variant:

![](https://d33v4339jhl8k0.cloudfront.net/docs/assets/5ddd799f2c7d3a7e9ae472fc/images/5e27859104286364bc9436df/5e278590ee4e7.png)

**Note:** if you don't see your variant in the search results, try opening up the "Help" page in Locksmith and pressing the \
Update Locksmith button there, and try your search again. This is sometimes necessary if you've very recently created your variant.

Next, select the variant and click Save. You may then add your keys.

That's it! :)

### Limiting the scope of a variant lock

It's possible to limit the scope of products the variant is hidden on using the product tag key condition. To learn more, please visit:

{% content-ref url="../../../keys/more/limiting-the-scope-of-variant-locks-using-the-product-tag-key-condition.md" %}
[limiting-the-scope-of-variant-locks-using-the-product-tag-key-condition.md](../../../keys/more/limiting-the-scope-of-variant-locks-using-the-product-tag-key-condition.md)
{% endcontent-ref %}

### Using passcodes with variant locks

Passcode keys don’t work by default when placed directly on a variant lock. This is because variants don’t have their own pages, and Locksmith only shows the passcode prompt by replacing full page content.

If you’d like customers to use a passcode to unlock specific variants, you’ll need to pair the variant lock with a separate landing page:

1. Create a new page in your Shopify admin (this can be a simple landing page).
2. Add a lock to that page using the passcode key you want.
3. Apply the same passcode key to your variant lock.
4. Direct customers to the landing page, where they’ll be prompted to enter the passcode. Once entered, they’ll have access to the locked variants.

### Compatibility with other apps and features

Because this feature allows you to filter out variants from view, it's likely that it will conflict with any other apps that _also_ operate in this way. To learn more about this, see the page here:

{% content-ref url="../../../basics/compatibility.md" %}
[compatibility.md](../../../basics/compatibility.md)
{% endcontent-ref %}

Variant locking is _not_ compatible with variants being displayed by other third-party apps, including page builder apps. To learn more about this, see the page here:

{% content-ref url="../../../faqs/locksmith-is-not-working-with-my-page-builder-app.md" %}
[locksmith-is-not-working-with-my-page-builder-app.md](../../../faqs/locksmith-is-not-working-with-my-page-builder-app.md)
{% endcontent-ref %}

{% hint style="danger" %}
Variant locks are **not** compatible with Locksmith's [manual locking](../manual-mode.md) feature.
{% endhint %}
