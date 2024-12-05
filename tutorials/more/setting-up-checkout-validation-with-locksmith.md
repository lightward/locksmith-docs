---
description: >-
  Learn how to set up checkout validation in Shopify using Locksmith. This
  feature ensures that products tagged with a specific product tag cannot be
  purchased without a specific customer tag.
---

# Setting up checkout validation with Locksmith

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

1. From the dropdown list, select **Require customer tag to purchase specific products**. This rule will restrict purchases based on product and customer tags.
2. In the **Product tag** field, add the product tag you want to use (e.g., `nobots`).
3. In the **Customer tag** field, add the customer tag that will allow the product to be purchased (e.g., `notabot`).
4. **Save** your changes:

<figure><img src="../../.gitbook/assets/Screenshot 2024-09-20 at 4.05.47 PM.png" alt=""><figcaption></figcaption></figure>

5. Click the **Turn on** button to enable the rule:

<figure><img src="../../.gitbook/assets/2024-09-20 16.11.27.gif" alt=""><figcaption></figcaption></figure>

You should be all set. :)\
\
Don't forget to test using a private browsing session to ensure the rule is working:\
[how-to-use-a-private-browsing-session.md](how-to-use-a-private-browsing-session.md "mention")\