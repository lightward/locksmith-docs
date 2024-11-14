---
description: >-
  How to see which key was used, or how many times a passcode has been used to
  access your locked content.
---

# How do I know which customers have used a certain key?

Locksmith does not keep any usage statistics. However this guide suggests some workarounds which might help in certain cases.

## 1. Autotagging

Many of Locksmith's key conditions support a customer auto-tagging feature. When enabled, this feature **automatically adds a tag to any customer who gains access to a resource** in your online storefront, using that particular key condition.

Here's how to find it, using a passcode condition as an example:

![](<../../.gitbook/assets/2024-10-24 12.35.25.gif>)

Keep in mind that this feature **only works if a customer is signed in** when visiting the locked page. If a visitor is not signed in, Locksmith will not make any record that they used the passcode, secret link, etc.

## 2. Tracking how many times a passcode as been used.

Locksmith allows you to set a usage limit for passcodes, and the number will count down each time the passcode is submitted. If you set it to a very high number to begin with, you can check in on the number to see how much it has been used:

<figure><img src="../../.gitbook/assets/Screenshot 2024-10-24 at 12.38.56 PM.png" alt=""><figcaption></figcaption></figure>

Keep in mind that is only works for the single **passcode key condition type (labelled "Permit if customer gives the passcode")**.&#x20;

The one-of-many passcode key conditions and the passcode-from-input-list key conditions do not work in the same way so it's not possible to use this tactic for them. If you're using more than one passcode, try setting those up in separate keys with a usage limit on each.

## 3. If using secret links and the Mechanic app

If using secret link key condition, it is possible to tag orders that come through after a customer has used a secret link. It's possible to set up a task with [Mechanic](https://mechanic.dev/), our other app, that tags orders with the Locksmith secret link a customer used, when placing an order. Optionally, this task tags the customer as well:\
\
[ Tag online orders by ?ls= Locksmith secret link used, with Mechanic](https://tasks.mechanic.dev/tag-orders-by-locksmith-secret-link)
