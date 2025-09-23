---
description: >-
  Protect against bots, cart permalink exploits, and other unauthorized orders
  using our checkout validation feature.
---

# Setting up checkout validation with Locksmith

{% hint style="info" %}
If you're seeing fraudulent orders on your free items, or challenges selling high-demand products to only approved customers, this is the solution for you!
{% endhint %}

## Prerequisites:

* You must have the **Locksmith app** installed.
* Your products should be tagged appropriately in Shopify.
* You'll want to have customer tags set up for specific customers.

## Step 1: Navigate to Checkout Rules in Shopify

1. **Go to your Shopify admin** and click **Settings:**\
   ![](<../../.gitbook/assets/Screenshot 2024-09-20 at 3.59.43 PM.png>)
2. Scroll down and click **Checkout:**\
   ![](<../../.gitbook/assets/Screenshot 2024-09-20 at 3.53.21 PM.png>)
3. **Scroll down** to the bottom of the Checkout settings to find the **Checkout rules** section.
4. Click **Add rule:**

<figure><img src="../../.gitbook/assets/Screenshot 2024-09-20 at 3.57.04 PM.png" alt=""><figcaption></figcaption></figure>

## Step 2: Add rule:

1. From the "Add a checkout rule" dropdown list, select **Require customer tag to purchase specific products**. This rule will restrict purchases based on product and customer tags.
2. In the **Product tag** field, add the product tag you want to use (e.g., `nobots`).
3. In the **Customer tag** field, add the customer tag that will allow the product to be purchased (e.g., `notabot`).
4. **Save** your changes:

<figure><img src="../../.gitbook/assets/Screenshot 2025-09-23 at 11.42.31 AM.png" alt=""><figcaption></figcaption></figure>

5. Click the **Turn on** button to enable the rule:

<figure><img src="../../.gitbook/assets/2025-09-23 11.49.58.gif" alt=""><figcaption></figcaption></figure>

You should be all set. :)\
\
Don't forget to test using a private browsing session to ensure the rule is working:\
[how-to-use-a-private-browsing-session.md](how-to-use-a-private-browsing-session.md "mention")

{% hint style="info" %}
**Please note:** Currently, it's only possible to set up one checkout validation rule per store that allows a specific customer tag to purchase products that have a specific product tag.\
\
This means that if you have multiple requirements for different products or customer tags, you'll need to prioritize which rule is most important or add global product tag that can be used on all products you want to require validation for.&#x20;
{% endhint %}
