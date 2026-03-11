---
description: >-
  Learn how to use Locksmith's "before" and "after" date and time key
  conditions, including when to combine them within a single key versus adding
  them as separate keys.
---

# Using date and time key conditions

Locksmith includes two key conditions for controlling access by date and time.

* **Is visiting before a certain date and time**\
  Grants access if the current time is _before_ your chosen date.
* **Is visiting after a certain date and time**\
  Grants access if the current time is _after_ your chosen date.

These are best for _one-off_ moments. Think launches, limited sales, or short blackout periods.

If you need a recurring weekly schedule, use a weekly schedule key. See [Creating weekly schedules](creating-weekly-schedules.md).

## How each condition works

### "Permit if the customer is visiting **after** a certain date and time"

This grants access once the date and time has passed. Before that moment, access is denied.

**Example use case**

You're launching a collection on March 15 at 9:00 AM. Add a key that permits access _after_ that time:<br>

<figure><img src="../../.gitbook/assets/Screenshot 2026-03-11 at 3.18.50 PM.png" alt=""><figcaption></figcaption></figure>

Before 9:00 AM, visitors see your lock's denial message. After 9:00 AM, the collection opens automatically.

### "Permit if the customer is visiting **before** a certain date and time"

This grants access until the date and time arrives. After that moment, access is denied.

**Example use case**

You're running early access that ends March 20 at midnight. Add a key that permits access _before_ that time:

<figure><img src="../../.gitbook/assets/Screenshot 2026-03-11 at 3.01.40 PM.png" alt=""><figcaption></figcaption></figure>

Visitors can access until the deadline. Afterwards, the lock closes automatically.

## Combining date and time conditions

This is where **AND vs OR** matters. For deeper background, see [combining-key-conditions.md](../../keys/more/combining-key-conditions.md "mention"). You can also read the [overview explanation](https://www.locksmith.guide/basics/overview#chaining-combining-conditions-together-or-versus-and).

Here’s the rule:

* Conditions inside the **same key** use **AND** logic.
* Separate **keys** on the same lock use **OR** logic.

### Use AND to grant access _during_ a time window

If you want access only between two dates, use **one key**. Add both conditions to that single key.

**Example**

Open access from March 10 at 9:00 AM. Close it March 17 at 9:00 AM.

Set up one key:

* Permit if it's **after** March 10 at 9:00 AM
* **AND** permit if it's **before** March 17 at 9:00 AM

<figure><img src="../../.gitbook/assets/Screenshot 2026-03-11 at 3.07.18 PM.png" alt=""><figcaption></figcaption></figure>

Access is denied before March 10. Access is denied after March 17.

### Use OR to grant access _outside_ a time window

If you want to block access during a period, use **two keys**. No single moment can be both before a start and after an end.

**Example**

Block access during restocking. Restocking runs March 10 at 9:00 AM to March 17 at 9:00 AM.

Set up two keys:

* **Key 1:** Permit if it's **before** March 10 at 9:00 AM
* **Key 2:** **OR**, Permit if it's **after** March 17 at 9:00 AM
*

    <figure><img src="../../.gitbook/assets/Screenshot 2026-03-11 at 3.14.05 PM.png" alt=""><figcaption></figcaption></figure>

Before March 10, Key 1 grants access. After March 17, Key 2 grants access. During the window, neither key passes.

## Impossible combined time conditions to avoid

{% hint style="warning" %}
**Watch out for impossible conditions.**

If you have time keys combined with "AND", and your "after" time is later than your "before" time, the key never opens. No moment can satisfy both at once.
{% endhint %}

This will never work in a single combined key:

* Permit if it's after March 17
* **And** permit if it's before March 10

If you're trying to allow access outside a window, use two keys instead. See the **OR** example above.

## Quick reference

* Open access **after** a single date\
  One key: "after \[date]"
* Open access **until** a single date\
  One key: "before \[date]"
* Open access **during** a window\
  One key: "after \[start]" AND "before \[end]"
* Block access **during** a window\
  Two keys: "before \[start]" OR "after \[end]"
* Recurring weekly hours\
  Use a [weekly schedule](creating-weekly-schedules.md) key instead

## A note on time zones

Date and time keys use your store time zone. Set it in Shopify under **Settings > General**.

If you need help changing it, see Shopify’s guide: https://help.shopify.com/en/manual/intro-to-shopify/initial-setup/setup-business-settings#set-or-change-your-store-time-zone

## Related articles

{% content-ref url="../../basics/creating-keys.md" %}
[creating-keys.md](../../basics/creating-keys.md)
{% endcontent-ref %}

{% content-ref url="../../keys/more/combining-key-conditions.md" %}
[combining-key-conditions.md](../../keys/more/combining-key-conditions.md)
{% endcontent-ref %}

{% content-ref url="creating-weekly-schedules.md" %}
[creating-weekly-schedules.md](creating-weekly-schedules.md)
{% endcontent-ref %}
