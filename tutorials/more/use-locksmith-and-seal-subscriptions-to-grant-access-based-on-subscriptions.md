# Use Locksmith and Seal Subscriptions to grant access based on subscriptions

You can use Locksmith with Seal Subscriptions to control access based on a customer’s subscription status. Seal Subscriptions supports auto-tagging customers depending on whether their subscription is active or inactive. Here’s how it works:

#### How Seal Subscriptions tags customers

* Seal Subscriptions can automatically tag customers when they have an active subscription.
* When a subscription becomes inactive (expired or cancelled), Seal doesn’t remove the active tag. Instead, it applies an additional tag for inactive subscribers.

Reference: [https://www.sealsubscriptions.com/articles/frequently-asked-questions/can-i-tag-customers-with-active-and-inactive-subscriptions-6y](https://www.sealsubscriptions.com/articles/frequently-asked-questions/can-i-tag-customers-with-active-and-inactive-subscriptions-6y)

#### Setting things up in Locksmith

1. Make sure Seal Subscriptions is configured to add both active and inactive tags to your customers.
2. Create a lock on the content you want to restrict (products, collections, pages, etc.). Guide: \
   [creating-locks.md](../../basics/creating-locks.md "mention")
3. Add a key condition: **Permit if the customer is tagged with...** and enter your active subscription tag. This is a regular (non-inverted) condition.
4. Now turn this into a combo key by adding the second condition _inside the same key_:
   * Click **Edit** on the key you just created.
   * Scroll to **+ Add key condition** and add **Permit if the customer is tagged with \<active subscriber tag>**
   * Enter your inactive subscription tag and (if needed) check [**invert**](../../keys/more/inverting-conditions-in-locksmith.md) so the condition reads **Permit UNLESS the customer is tagged with \<inactive subscriber tag>**&#x20;
   * Save the lock. You now have a single combo key that requires both conditions at once. See: \
     [combining-key-conditions.md](../../keys/more/combining-key-conditions.md "mention")\
     [inverting-conditions-in-locksmith.md](../../keys/more/inverting-conditions-in-locksmith.md "mention")
5. Result: customers must have the **active** tag, and must **not** have the **inactive** tag, to get access. The keys should look like the following example once setup:<br>

<figure><img src="../../.gitbook/assets/Screenshot 2025-09-10 at 12.30.24 PM.png" alt=""><figcaption></figcaption></figure>

#### Helpful resources

{% content-ref url="../../keys/customer-account-keys.md" %}
[customer-account-keys.md](../../keys/customer-account-keys.md)
{% endcontent-ref %}

{% content-ref url="../../keys/more/inverting-conditions-in-locksmith.md" %}
[inverting-conditions-in-locksmith.md](../../keys/more/inverting-conditions-in-locksmith.md)
{% endcontent-ref %}

{% content-ref url="../../keys/more/combining-key-conditions.md" %}
[combining-key-conditions.md](../../keys/more/combining-key-conditions.md)
{% endcontent-ref %}

#### Summary

Because Seal Subscriptions doesn’t remove active tags, you’ll need to use both a regular (non-inverted) condition (active tag) and an inverted condition (inactive tag) in Locksmith. This setup ensures that only customers with a current subscription can access your locked content.
