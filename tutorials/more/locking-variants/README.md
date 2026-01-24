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

### Variant locks in multi-language stores

If your store uses multiple languages, it’s important to understand how Shopify translations can affect variant locking.

Locksmith’s variant locks match variant option values exactly. This means the lock checks the underlying option value string (for example, “480 packs” or “Large”), not just the variant’s position or how it appears visually on the page.

In multi-language stores, Shopify often translates variant option values per language. For example, a variant option value like:

**480 packs**

may become:

**480 doosjes**

**480 paquets**

**480 paquetes**

\
Although these variants appear equivalent to shoppers, they are different option value strings in Shopify’s data. When the option value changes due to translation, an existing variant lock targeting the original value will no longer match on the translated version.

This can make it appear as though a variant lock works in one language but not another, even though the lock is behaving as designed.

#### **To support multi-language stores, there are two recommended approaches:**

1. **Create language-specific variant locks**\
   Create additional variant locks for each translated option value, using the same key conditions. This allows variant labels to remain translated while ensuring the correct variants are locked in every language.<br>
2. **Keep variant option values consistent across languages**\
   Alternatively, configure translations so the variant option values themselves remain identical across languages. When the option value string is the same in every language, a single variant lock will apply consistently regardless of which language the customer is viewing.

{% hint style="info" %}
When troubleshooting language-specific variant locking issues, checking the variant option values shown on the translated product page (or in the product’s [product JSON](https://help.shopify.com/en/manual/shopify-admin/using-json)) is the fastest way to confirm whether translations are affecting the lock.
{% endhint %}

### Compatibility with other apps and features

Because this feature allows you to filter out variants from view, it's likely that it will conflict with any other apps that _also_ operate in this way. \
\
For **products** that are locked with Locksmith, we add a metafield to prevent them from being included on the Shop app sales channel. However, this automatic protection only applies at the **product** level. When **variants** are locked, Locksmith doesn’t add the metafield automatically, which means variant visibility on the Shop app needs to be managed manually by merchants.\
\
To learn more about this, see the page here:

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
