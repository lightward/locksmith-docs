# Restricting customers to a specific collection

With Locksmith, it is simple to lock down a specific collection, so that it can only be viewed by a specific set of customers. However, some merchants want to take it one step further and make sure that those customers can _only_ access their collection, while the rest of the store is restricted to them.

### Part 1: Create the collection lock

Add a lock to the collection that you want these customers to access. Use the search bar in Locksmith to search for the collection by name:\


<figure><img src="../../.gitbook/assets/Screenshot 2025-01-10 at 2.17.27 PM.png" alt=""><figcaption></figcaption></figure>

Under "Keys", choose how these customers will gain access. You can use whatever method of access you want. The most common way of granting access in this scenario is to use "customer tags" to grant access:

<figure><img src="../../.gitbook/assets/Screenshot 2025-01-10 at 2.18.44 PM.png" alt=""><figcaption></figcaption></figure>

Make sure the "Force open other locks" setting is turned on for this lock. Use the following guide to do this: [Using the "Force open other locks" setting](../../keys/more/using-the-force-open-other-locks-setting.md) . **This setting is important.**

<figure><img src="../../.gitbook/assets/Screenshot 2025-01-10 at 2.19.26 PM.png" alt=""><figcaption></figcaption></figure>

### Part 2: Create a lock covering the rest of the store

In order to make sure that these customers can't see the rest of your store, you need to actually add a lock to your "entire store":

![](<../../.gitbook/assets/Screenshot 2025-01-10 at 2.20.04 PM.png>)

For your key condition, you need to use the "invert" option to obtain the opposite of the first key condition:

<figure><img src="../../.gitbook/assets/Screenshot 2025-01-10 at 2.21.32 PM.png" alt=""><figcaption><p>The invert option in the context of the rest of the key condition settings.</p></figcaption></figure>

Use the guide here if you need more guidance on how to invert your key condition:

{% content-ref url="../../keys/more/inverting-conditions-in-locksmith.md" %}
[inverting-conditions-in-locksmith.md](../../keys/more/inverting-conditions-in-locksmith.md)
{% endcontent-ref %}

{% hint style="info" %}
If this is a private collection, no further action necessary. If the collection is meant to be viewed by all customers, you'll also want to use the ["force open other locks](../../keys/more/using-the-force-open-other-locks-setting.md)" setting on the lock for the entire store.
{% endhint %}
