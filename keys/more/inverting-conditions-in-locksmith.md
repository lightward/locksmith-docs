# Inverting conditions in Locksmith

There are many instances in which it is useful for a key to grant access if the _opposite_ of your key condition is true.

Locksmith makes it easy to invert keys. To do so, simply click the box next to "invert" when you're editing the key:

<figure><img src="../../.gitbook/assets/2025-03-21 13.09.00.gif" alt=""><figcaption></figcaption></figure>

Notice that when this is done, the wording will update, inverting the key condition logic:

<figure><img src="../../.gitbook/assets/Screenshot 2025-03-21 at 1.09.41 PM.png" alt=""><figcaption></figcaption></figure>

Make sure to "Save" the lock, and you're done!

As always, **feel free to contact us via email** at team@uselocksmith.com.<br>

{% hint style="info" %}
**A note on inverted customer account keys**

When you invert a [customer account key condition](../customer-account-keys.md) — such as "is tagged with," "has purchased," or "email contains" — the inverted key will also grant access to visitors who are **not** signed in, since they technically meet the inverted condition — they have no customer account details (tags, email, purchase history, etc.) associated with them.

If you want to require sign-in, combine the inverted condition with an "is signed in" condition inside the same key:

[Combining key conditions](combining-key-conditions.md)
{% endhint %}
