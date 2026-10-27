---
description: >-
  Why a locked product can still end up in a cart or an order, and what
  closes that path.
---

# Someone bought a locked product. How?

Locksmith's locks work on the pages of your Online Store: when someone visits a locked page, Locksmith decides what they see. That's where its protection lives.

A cart and a checkout don't always go through those pages. A few ways a product can reach checkout without anyone visiting its locked page:

* **Cart permalinks and "Buy Now" links**, which go straight to checkout.
* **Ajax cart requests** (`/cart/add.js`) made with a product's variant ID, which Shopify serves without your theme.
* **Shopify's public product data** (like `/products/<handle>.json`), which can reveal a variant ID to someone who knows where to look. See [Can Locksmith lock Shopify's public JSON API?](can-locksmith-lock-shopifys-public-json-api-for-my-online-store.md)
* **A cart built before access changed.** Locksmith checks a page when it's visited, not what's already in the cart. Something added while a key was open stays in the cart.
* **Other sales channels and apps**, which don't render your theme.

Hiding prices and add-to-cart buttons changes what the page shows. It doesn't stop any of the routes above.

### What closes the path

**Checkout validation.** Locksmith can add a rule inside Shopify's checkout itself: products with a given tag can only be bought by a signed-in customer with a given tag. Because it runs in your store's checkout, it applies there however the cart was built. (Shopify decides which surfaces run checkout rules; point of sale, for one, doesn't.) [Setting up checkout validation](../../tutorials/more/setting-up-checkout-validation-with-locksmith.md)

It works with tags only: product tags and customer tags. It can't see passcodes, secret links, input lists or dates directly, so your buyers need customer accounts.

**If your lock uses a passcode, a secret link, or another key condition that supports auto-tagging**, you can connect the two with [customer auto-tagging](how-do-i-know-which-customers-have-used-a-certain-key.md). When a signed-in customer opens the lock with that key, Locksmith adds a tag of your choice to their account, and a checkout validation rule can require that tag. Buyers still need accounts, but you don't have to tag them yourself: entering the passcode while signed in does it. Two things to know:

* Auto-tagging only works for signed-in customers. Someone who enters the passcode as a guest gets into the page, but isn't tagged, so the checkout rule won't let them through.
* The tag stays on the account. It doesn't come off when a passcode times out or a date window closes, so a rule that requires it keeps letting that customer through.

**If your buyers don't have accounts**, the storefront lock is the protection, and the routes above stay open. An app that reviews or cancels orders after they're placed can catch what gets through. Our [usage agreement](../../policies/usage-agreement.md) has more on what Locksmith can and can't cover.

### Testing it

Test in a [fresh private browsing window](../../tutorials/more/how-to-use-a-private-browsing-session.md), not signed in, and try the route you're worried about directly. If an order goes through that shouldn't have, write to us with the order number and how it was placed, and we'll look at it with you.
