# Restricting the cart for mixed products and combinations of products

{% hint style="warning" %}
This is an incomplete guide! In an effort to share the information we have as soon as possible, this guide has been started and published here in what we consider to be an incomplete state. If something is missing, please let us know by emailing us at [team@uselocksmith.com](mailto:team@uselocksmith.com).
{% endhint %}

Locksmith can be used to restrict checkout from the cart page by creating a lock for the cart. This lock can be used to hide the whole cart page, or to only lock the checkout buttons on the cart page. Locksmith has a few cart specific key conditions that can be used to check specific attributes of a customers' cart. This guide will primarily focus on the use of the “has a certain product in their cart” key condition.

## Preventing access to the checkout from the cart

Our guide on setting up a cart lock is linked below. That guide covers both locking the whole cart page and locking the checkout button.

{% content-ref url="restricting-checkout-from-the-cart.md" %}
[restricting-checkout-from-the-cart.md](restricting-checkout-from-the-cart.md)
{% endcontent-ref %}

Locking the checkout button can be a better option here. This will allow customers to still be able to edit the products in the cart, even when the checkout button is locked.

## Managing cart access based on products in the cart

There are three general ways of restricting access to the checkout via your Shopify cart based on mixed products or combinations of products. Keep in mind, this isn’t an exhaustive list.

### Preventing checkout with mixed products from two different groups of products. Eg. Wholesale and Retail

The "Look for products matching…" field on the "has a certain product in their cart" key condition can be used to check for a product title, or product tags. For example, "tag:wholesale will check for any products with the "wholesale" tag.&#x20;

You will need to create three separate keys for your cart lock. Our guide on adding keys is here for reference: [Creating keys](https://www.locksmith.guide/basics/creating-keys)

#### 1. You’ll need a key that grants access if a customer _does_ have products tagged with the "wholesale" products tag (for example) in the cart, but only if the customer doesn't have any products tagged with "retail" in the cart.

* Create a key and then select the "has a certain product in their cart" key condition and add “tag:wholesale” to the "Look for products matching…" field on the condition.
*   Then [_combine_](../../keys/more/combining-key-conditions.md) a second "has a certain product in their cart" key condition with the first, add “tag:retail” to the "Look for products matching…" field on the condition, and then [_invert_](../../keys/more/inverting-conditions-in-locksmith.md) the condition.\
    \
    [Combining Key Conditions\
    ](../../keys/more/combining-key-conditions.md)[Inverting conditions in Locksmith\
    \
    ](../../keys/more/inverting-conditions-in-locksmith.md)You should have a key that looks like the following image.\


    <figure><img src="../../.gitbook/assets/Screenshot 2023-11-07 at 9.37.20 pm.png" alt=""><figcaption><p>Image 1. Key with key condition combination to allow access for wholesale products with no retail.</p></figcaption></figure>



#### 2. The second key will use a set of conditions that are the inverse of the fist key, to grant access to customers who don't have any products tagged with "wholesale" in the cart but do have products tagged with "Retail" in the cart.

* Create a new key by clicking the “+Add key” button and then select the "has a certain product in their cart" key condition and add “tag:retail” to the "Look for products matching…" field on this condition.
*   Then combine a second "has a certain product in their cart" key condition with the first, add “tag:wholesale” to the "Look for products matching…" field on the condition, and then invert this condition.\
    \
    You should have a key that looks like the following image.\


    <figure><img src="../../.gitbook/assets/Screenshot 2023-11-07 at 9.39.21 pm.png" alt=""><figcaption><p> Image 2. Key with key condition combination to allow access for retail products with no wholesale.</p></figcaption></figure>



#### 3. _This third key is only required, if you have another set of products, other than wholesale and retail, that can be purchased with anything product._

The third key can be used to grant access for when there are no products with the "wholesale" or "retail" tags in the cart. This will require the combination of two inverted "has a certain product in their cart" key conditions, one of each product tag.

You should have a key that looks like the following image.

<figure><img src="../../.gitbook/assets/Screenshot 2023-11-07 at 9.41.57 pm.png" alt=""><figcaption><p> Image 3. Key with key condition combination to allow access when no wholesale or retail products are in the cart.</p></figcaption></figure>

### Something else not covered here?

Let us know by emailing us at **team@uselocksmith.com**
