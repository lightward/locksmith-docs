---
description: Things to know about switching to New Customer Accounts in your Shopify store.
---

# Shopify's New Customer Accounts and Locksmith

Shopify has introduced a redesigned customer account system — referred to as **"new customer accounts"** (or sometimes "customer accounts"), replacing what is now called **"legacy customer accounts"**. This guide explains what the new system is, how it differs from the legacy system, and what you need to know when using Locksmith alongside it.

{% hint style="info" %}
**Not sure which system your store is using?** Go to **Settings → Customer accounts** in your Shopify admin. You'll see whether you're on "Legacy customer accounts" or the newer "Customer accounts" system.
{% endhint %}

### What are Shopify's new customer accounts?

The new customer account system is Shopify's modernized approach to customer login and account management. The most significant change is that it uses **passwordless authentication**: instead of signing in with an email and password, customers receive a one-time 6-digit verification code by email each time they log in. Customers can also sign in through the Shop app.

A few other things worth knowing about the new system:

* **Accounts are created automatically.** There's no longer a traditional registration form. When a customer checks out or enters their email on the login page, an account is created for them automatically upon email verification.
* **Login is hosted by Shopify, not your theme.** The sign-in page lives on Shopify's infrastructure (on a subdomain like `account.yourstore.com`), separate from your Online Store theme.
* **Legacy accounts are being deprecated.** Shopify has announced that legacy customer accounts will eventually be sunset. A final date will be announced later in 2026. It's worth planning your migration sooner rather than later.

For a full comparison of the two systems, refer to [Shopify's official documentation](https://help.shopify.com/en/manual/customers/customer-accounts).

***

### How Locksmith works with new customer accounts

The good news: **Locksmith's core functionality works with both legacy and new customer accounts.** All of the standard customer account key conditions — checking if someone is signed in, checking customer tags, verifying email address, checking purchase history, and so on — continue to work exactly as you'd expect.

{% hint style="info" %}
As always, Locksmith does **not** create a separate account system or customer database. It uses whichever customer account system you have active in your Shopify store.
{% endhint %}

When a visitor tries to access locked content and a customer account key condition is in use, Locksmith will present an access denied message and prompt the customer to sign in. Once they're signed in, Locksmith checks their account for the relevant condition (e.g. a customer tag) and grants access if the condition is met.

***

### What's different with new customer accounts

While Locksmith's key conditions themselves work the same way, there are a few important differences in behavior when using the new customer account system.

#### The login form comes from Shopify, not your theme

With legacy customer accounts, Locksmith displays the login template directly from your theme when a visitor needs to sign in. With new customer accounts, **the sign-in experience is hosted by Shopify** and lives outside of your theme. Locksmith will still show its access denied message (which you can customize), but the sign-in form itself is Shopify's — it cannot be edited through your theme files.

You can still fully customize the message that Locksmith shows _before_ the sign-in link. More on that here:

[Customizing messages →](https://www.locksmith.guide/tutorials/more/customizing-messages)

[Customizing the customer login page →](https://www.locksmith.guide/tutorials/more/customizing-the-customer-login-page)

#### The registration form cannot be locked

With legacy customer accounts, it's possible to place a Locksmith lock directly on the customer registration form — for example, to prevent customers from signing up without an invitation. This is **not possible with new customer accounts**, because there is no traditional registration form. Accounts are created automatically when a customer verifies their email.

If you need to control who can access your content, the recommended approach is still to use a customer tag key condition and manually tag the customers you want to approve. More on that workflow here:

[Approving customer registrations →](https://www.locksmith.guide/tutorials/approving-customer-registrations)

#### Login page customization is more limited

With legacy accounts, you can customize the login template in your theme (removing the "Register" link, adjusting styling, etc.) and Locksmith will pick those changes up automatically. With new customer accounts, the sign-in page is managed by Shopify, so **theme-based customizations to the login page do not apply**.

You can still customize Locksmith's landing page — the page a visitor sees when they're denied access — with as much HTML, CSS, and Liquid as you need. Only the actual Shopify-hosted sign-in form is outside of your control.

***

### Summary: What works, and what's different

| Feature                                  | Legacy accounts | New customer accounts |
| ---------------------------------------- | --------------- | --------------------- |
| "Is signed in" key condition             | ✅ Works         | ✅ Works               |
| Customer tag key conditions              | ✅ Works         | ✅ Works               |
| Email-based key conditions               | ✅ Works         | ✅ Works               |
| Purchase history key conditions          | ✅ Works         | ✅ Works               |
| Custom Liquid key conditions             | ✅ Works         | ✅ Works               |
| Customizing Locksmith's access message   | ✅ Works         | ✅ Works               |
| Login form displayed inside your theme   | ✅ Works         | ❌ Not applicable      |
| Locking the registration form            | ✅ Works         | ❌ Not applicable      |
| Customizing the login template via theme | ✅ Works         | ❌ Not applicable      |

***

### Related guides

[Customer account keys →](https://www.locksmith.guide/keys/customer-account-keys)

[Approving customer registrations →](https://www.locksmith.guide/tutorials/approving-customer-registrations)

[Customizing the customer login page →](https://www.locksmith.guide/tutorials/more/customizing-the-customer-login-page)

[Customizing messages →](https://www.locksmith.guide/tutorials/more/customizing-messages)

***

As always, feel free to reach out to us directly at [**team@uselocksmith.com**](mailto:team@uselocksmith.com) if you have any questions!
