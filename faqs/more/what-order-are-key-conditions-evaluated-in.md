When a lock has multiple key conditions, Locksmith evaluates them in a specific order to provide the best user experience. The evaluation order is designed to prioritize conditions based on the level of control a user has over their authorization.

## Evaluation Order

Key conditions are evaluated in the following order:

1. **(always permit)**
2. **is signed in**
3. **is not signed in**
4. **is tagged with...**
5. **the product is tagged with...**
6. **is not tagged with...**
7. **has one of many email addresses**
8. **has a list of email addresses**
9. **the customer's email contains...**
10. **has purchased...**
11. **has not placed an order in the last 24 hours**
12. **has placed at least x orders**
13. **has a certain product in their cart**
14. **has a certain variant in their cart**
15. **has at least $x in their cart**
16. **(custom Liquid)**
17. **is visiting after a certain date and time**
18. **is visiting before a certain date and time**
19. **is visiting a certain domain**
20. **Stripe subscription** (Note: This is now an always-deny condition)
21. **is visiting from certain countries**
22. **is visiting from a certain location (city, country, etc)**
23. **has a certain IP address**
24. **is visiting from certain locations**
25. **arrives via a secret link...**
26. **arrives using a secret link code from an input list...**
27. **has an email address from an input list...**
28. **subscribes to your Mailchimp list**
29. **subscribes to your Klaviyo list**
30. **is a member of a Klaviyo segment or list**
31. **gives the passcode...**
32. **gives a passcode from an input list...**
33. **gives one of many passcodes...**
34. **the customer confirms the prompt**
35. **provides a valid US NPI number**

## Why This Order Matters

The evaluation order is important because:

1. **User Experience**: Conditions with less user control (like IP address) are checked first, so users aren't prompted for passcodes only to be denied by location.

2. **Performance**: Simple checks (like customer tags) are performed before complex ones (like API calls to external services).

3. **Logic Flow**: The order ensures that fundamental access rights are established before checking more specific conditions.

4. **Fail-Fast Principle**: If a user will be denied access regardless of their input, they find out immediately rather than after entering information.

## Multiple Keys on a Lock

When a lock has multiple keys, each key is evaluated independently. Access is granted if **any** key's conditions are all met. Within each key, **all** conditions must be satisfied for that key to grant access.

## Related Topics

- [Combining key conditions](../keys/more/combining-key-conditions.md)
- [Inverting conditions in Locksmith](../keys/more/inverting-conditions-in-locksmith.md)
- [About key conditions](../keys/about-key-conditions.md)
