---
description: >-
  Protect against bots, cart permalink exploits, and other unauthorized orders
  by requiring specific customer tags to purchase products with specific product
  tags.
---

# Setting up checkout validation with Locksmith

{% hint style="info" %}
Checkout validation is great for preventing unauthorized purchases — stopping bots, restricting high-demand products to approved customers, or enforcing wholesale/access rules at the point of sale.
{% endhint %}

## How it works

Locksmith's checkout validation blocks checkout for any cart that contains a tagged product unless the customer has one of the required customer tags. The check runs at checkout, so it catches direct-to-checkout links, cart permalink exploits, and other attempts to bypass storefront restrictions.

Each rule targets up to two product tags and up to two customer tags. A product matches if it has **either** product tag; a customer passes if they have **either** customer tag. You can create up to 25 rules per store.

## Prerequisites

* **Locksmith** installed on your store
* Products tagged appropriately in Shopify
* Customer tags set up for the customers you want to allow

## Step 1: Enable checkout validations in Locksmith

1. Open the **Locksmith** app from your Shopify admin.
2. Click **Settings** in the navigation.
3. Scroll down to the **Checkout validations** section.
4. Check **Enable checkout validations**.
5. Click **Save**.

After saving, Locksmith will prompt you to approve the **write\_validations** permission. This is required for Locksmith to create and manage checkout rules in Shopify.

{% hint style="warning" %}
If you previously set up checkout validation rules directly in your Shopify admin (Settings → Checkout → Checkout rules), those rules will be automatically removed when you grant this permission. You will need to recreate them here in the Locksmith settings UI.
{% endhint %}

## Step 2: Add a validation rule

Once the permission is approved and you return to the Settings page:

1. Under **Checkout validations**, click **Add checkout validation**.
2. Fill in the rule:
   * **Product tags** — the tag (or tags, comma-separated) on products that require validation. For example: `wholesale-only` or `restricted, members-only`.
   * **Customer tags** — the tag (or tags, comma-separated) a customer must have to be allowed through. For example: `wholesale` or `approved, vip`.
   * **Error message** *(optional)* — the message shown to blocked customers. You can use `{{product_title}}` to include the product name. Leave blank to use the default message.
3. Make sure **Active** is checked.
4. Click **Done**.
5. Click **Save** at the top of the page.

{% hint style="info" %}
Each field supports up to **two** comma-separated tags. If you enter more, only the first two will be used.
{% endhint %}

## Step 3: Test your rule

Use a private browsing session (without the customer tag) to verify the rule blocks checkout, and a second test with an account that has the tag to confirm it passes through.

[how-to-use-a-private-browsing-session.md](how-to-use-a-private-browsing-session.md "mention")

## Managing rules

* Rules can be toggled on or off individually using the **Active** checkbox without deleting them.
* Click **Edit** on any rule to update tags or the error message.
* Click **Delete** to remove a rule entirely.
* You can have up to **25 rules** active at once (a Shopify platform limit across all apps).