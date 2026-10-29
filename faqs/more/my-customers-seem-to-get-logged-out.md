---
description: >-
  When customers sign in and then seem to be signed out a click later, the
  cause is usually where they signed in, or which address they ended up on.
---

# My customers sign in, then seem to get logged out

Locksmith doesn't sign anyone out. It reads the sign-in your Shopify store already has: when a lock opens for signed-in customers, Locksmith asks Shopify whether this visitor is signed in, on this page, right now. So if a lock starts asking a customer to log in again, Shopify isn't seeing them as signed in on that page. These are the usual reasons.

### They signed in somewhere else

A Shopify customer account belongs to one store. Signing in to a different site doesn't sign anyone in to your store, even when the two sites look related: a trade or wholesale portal, a sister store, a booking system.

Look at your store's menus and buttons for anything labelled "Log in", "Account" or "Portal" that leads to another site. A customer who signs in there and then comes back to your store is a guest as far as your store is concerned, so your locks will ask them to log in. (With Shopify's new customer accounts, your store's own sign-in page lives on shopify.com or an `account.` address. That one is fine: it's your store's.)

### A link sends them to a different address

Shopify keeps a customer's sign-in for the address of your store they were using. If a menu link, button or page section has a full web address typed into it (rather than a link to one of your store's pages), it can send customers to another address for your store. Most of your store's other addresses, including its `.myshopify.com` address, redirect to your primary domain, which avoids this. An **alias domain** doesn't: it shows your store without redirecting, and Shopify doesn't support customer accounts pages on alias domains, so customers may not be signed in there.

In Shopify, **Settings** → **Domains** shows your domains and which ones redirect. Then check your menu links (**Content** → **Menus**) and any buttons in your theme for full addresses, and point them at your store's own pages instead.

### It isn't a sign-out, it's a different lock

If a customer is signed in but a page tells them they don't have access (rather than asking them to log in), the lock on that page, or another lock covering it, needs more than signing in, like a customer tag. By default, Locksmith's message for signed-in customers who don't qualify is different from the one guests see, which is a good way to tell these apart (unless you've customized them to read alike).

### Shopify itself

Now and then, Shopify stops showing a customer as signed in on the storefront even though they signed in, and Locksmith sees what Shopify shows. If nothing above fits, have the customer sign out and back in, and write to us.

### Finding out which it is

Try it yourself in a [fresh private browsing window](../../tutorials/more/how-to-use-a-private-browsing-session.md): sign in the way your customers do, then click around the way they do. When a lock asks you to log in again, look at the address bar. If the address has changed (a different domain, or a different site entirely), that's where the sign-in was lost.

If you can't find it, write to us with a screenshot of what your customer sees, with the address bar showing, and we'll look at it with you.
