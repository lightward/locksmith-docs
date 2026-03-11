---
description: >-
  Restrict which payment methods are available at checkout based on customer
  tags, using Shopify's native payment customization functions.
---

# Hiding payment methods by customer tag

Locksmith's payment customization feature lets you hide specific payment methods from customers who don't have a designated tag. For example, you could hide a "Net 30 / Invoice" payment option from regular customers, while making it available only to customers tagged as `wholesale`.

## How it works

Locksmith uses a Shopify Function running natively in Shopify's checkout. When a customer reaches checkout, Shopify evaluates their tags against your configured rules and removes any payment methods they don't have access to — before the page renders. The customer never sees the hidden options.

## Prerequisites

* Locksmith installed on your Shopify store
* Customers tagged appropriately in Shopify (e.g. `wholesale`, `vip`, `net30`)
* The payment method names you want to restrict, exactly as they appear at checkout

## Step 1: Open Locksmith Settings

Navigate to your Locksmith app and click **Settings** in the navigation.

Scroll down to the **Shopify Functions** section, where you'll find the **Payment Customization** card.

## Step 2: Enable the feature and grant permissions

Check **Enable this payment customization**.

Since this feature requires an additional Shopify permission (`write_payment_customizations`), Locksmith will need to request it. Click **Save** and then approve the permission request that follows. You'll be redirected back to Locksmith once access is granted.

{% hint style="info" %}
If you don't see the permission request after saving, check that your browser isn't blocking popups from the Shopify admin.
{% endhint %}

Once access is approved, return to **Settings → Shopify Functions** to configure your rules.

## Step 3: Configure your rules

Each rule hides one payment method from customers who **don't** have at least one of the specified tags.

1. Click **Add payment method**
2. Enter the **payment method name** exactly as it appears at checkout (e.g. `Cash on Delivery (COD)`, `Bank Deposit`, `Net 30`)
3. Enter one or more **customer tags** (comma-separated) — customers with at least one of these tags will see the payment method; everyone else won't
4. Repeat for additional payment methods (up to 3 rules)

{% hint style="info" %}
Payment method names are matched against what Shopify displays at checkout. If you're not sure of the exact name, check your Shopify **Settings → Payments** page, or place a test order to see the checkout payment options.
{% endhint %}

**Case-insensitive matching** is enabled by default, so `Bank Deposit` and `bank deposit` are treated the same. You can turn this off if needed.

## Step 4: Save

Click **Save**. Locksmith will create the payment customization in Shopify immediately. You can verify it was created by checking **Settings → Payments → Payment customizations** in your Shopify admin.

## What customers experience

* Customers **with** the required tag: see the payment method at checkout as normal
* Customers **without** the required tag: the payment method doesn't appear — no error, no explanation, it's simply not offered

This works at the checkout level, so it applies regardless of how a customer reaches checkout.

## Troubleshooting

**The payment method is still visible after saving**\
Make sure the payment method name matches exactly what appears at checkout. Try enabling case-insensitive matching if there's any uncertainty about capitalization.

**The customization isn't being created**\
Check that the `write_payment_customizations` permission has been granted. You can verify this in Locksmith's Settings page — if the permission is missing, the rules form won't be shown and you'll see instructions to grant access.

**I have more than 3 payment methods I want to restrict**\
The current limit is 3 rules with up to 3 customer tags each. If you need more, consider consolidating customer tags (e.g. use a single `restricted-payments` tag across multiple customer groups).
