# What order are different types of key conditions evaluated in?

When a key has multiple key conditions, Locksmith evaluates them in a specific order to provide the best user experience. The evaluation order is designed to prioritize conditions based on the level of control a user has over their authorization.

### Evaluation Order

Key conditions are evaluated in the following order:

1. **(always permit)**
2. **is signed in**
3. **is tagged with...**
4. **(the product) is tagged with...**
5. **has one of many email addresses**
6. **has a list of email addresses**
7. **the customer's email contains...**
8. **has purchased...**
9. **has not placed an order in the last 24 hours**
10. **has placed at least x orders**
11. **has a certain product in their cart**
12. **has a certain variant in their cart**
13. **has at least $x in their cart**
14. **(custom Liquid)**
15. **is visiting after a certain date and time**
16. **is visiting before a certain date and time**
17. **is visiting a certain domain**
18. **is visiting from a certain location (city, country, etc)**
19. **has a certain IP address**
20. **is visiting from certain locations**
21. **arrives via a secret link...**
22. **arrives using a secret link code from an input list...**
23. **has an email address from an input list...**
24. **subscribes to your Mailchimp list**
25. **subscribes to your Klaviyo list**
26. **is a member of a Klaviyo segment or list**
27. **gives the passcode...**
28. **gives a passcode from an input list...**
29. **gives one of many passcodes...**
30. **the customer confirms the prompt**

{% hint style="info" %}
When you create a key with multiple conditions, the display order will automatically update to reflect the above, _after you save the lock._ However, this is not the same as the display order when choosing new key conditions, which is simply organized so the more frequently-used key conditions appear near the top.
{% endhint %}

### Why This Order Matters

The evaluation order is important because:

1. **User Experience**: Conditions with less user control (like IP address) are checked first, so users aren't prompted for passcodes only to be denied by location.
2. **Performance**: Local checks (like customer tags) are performed before remote ones (like API calls to external services).
3. **Fail-Fast Principle**: If a user will be denied access regardless of their input, they find out immediately rather than after entering information.

### Multiple Keys on a Lock

When a lock has multiple keys, each key is evaluated independently. Access is granted if **any** key's conditions are all met. Within each key, **all** conditions must be satisfied for that key to grant access.&#x20;

### Related Topics

* [Combining key conditions](https://www.locksmith.guide/keys/more/combining-key-conditions)
* [Inverting conditions in Locksmith](https://www.locksmith.guide/keys/more/inverting-conditions-in-locksmith)
* [About key conditions](https://www.locksmith.guide/keys/about-key-conditions)
