---
description: >-
  Specify which payment methods are available at checkout based on customer
  tags, using Shopify's native payment customization functions.
---

# Restricting access to payment methods with Locksmith

Locksmith's payment customization feature lets you hide specific payment methods from customers who don't have a designated tag. For example, you could hide a "Net 30 / Invoice" payment option from regular customers, while making it available only to customers tagged as `wholesale`.

## How it works

Locksmith maintains a Shopify Function running natively in Shopify's checkout. When a customer reaches checkout, Shopify evaluates their tags against your configured rules and removes any payment methods they don't have access to — before the page renders. The customer never sees the hidden options.

## Prerequisites

* Locksmith installed on your Shopify store
* Customers tagged appropriately in Shopify (e.g. `wholesale`, `vip`, `net30`)
* The payment method names you want to restrict, as they appear at checkout

## Step 1: Open Locksmith Settings

Navigate to your Locksmith app and click **Settings** in the navigation.

Scroll down to the **Shopify Functions** section, where you'll find the **Payment Customization** card.

## Step 2: Enable the feature and grant permissions

Check **Enable this payment customization**.

Since this feature requires an additional Shopify permission (`write_payment_customizations`), Locksmith will need to request it. Click **Save** and then approve the permission request that follows. You'll be redirected back to Locksmith once access is granted.

Once access is approved, return to **Settings → Shopify Functions** to configure your rules.

## Step 3: Configure your rules

Each rule hides one payment method from customers who **don't** have at least one of the specified tags.

1. Click **Add payment method**
2. Enter the **payment method name** as it appears at checkout (e.g. `Cash on Delivery (COD)`, `Bank Deposit`, `Net 30`)
3. Enter one or more **customer tags** (comma-separated) — customers with at least one of these tags will see the payment method; everyone else won't
4. Repeat for additional payment methods (up to 3 rules)

{% hint style="info" %}
Payment method names are matched against what Shopify displays at checkout. If you're not sure of the name, check your Shopify **Settings → Payments** page.
{% endhint %}

**Case-insensitive matching** is enabled by default, so `Bank Deposit` and `bank deposit` are treated the same. You can turn this off if needed.

## Step 4: Save

Click **Save**. Locksmith will create the payment customization in Shopify immediately. You can verify it was created by checking **Settings → Payments → Payment customizations** in your Shopify admin.

## What customers experience

* Customers **with** the required tag: see the payment method at checkout as normal
* Customers **without** the required tag: the payment method doesn't appear — no error, no explanation, it's simply not offered

This works at the checkout level, so it applies regardless of how a customer reaches checkout.
