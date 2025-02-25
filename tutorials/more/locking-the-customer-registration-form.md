# Locking the customer registration form

{% hint style="danger" %}
**Locking the default registration page with Locksmith will&#x20;**_**only**_**&#x20;work with Legacy Customer Accounts.** \
\
**The New Customer Account system creates an account as soon as the customer uses the login form, and so registration&#x20;**_**cannot**_**&#x20;be locked.** \
\
**In that case, we recommend approving customers with account tags instead, after they create an account.**&#x20;
{% endhint %}



To try this out, open up Locksmith, and start typing "registration", like so:

![](<../../.gitbook/assets/Screenshot 2025-01-29 at 11.11.23 AM.png>)

Click on the "Customer Registration" result and then click "Save." Locksmith will create a lock that covers your shop's registration page. From there, feel free to add whatever keys you like!

{% hint style="warning" %}
**Hint:** Key conditions based on things like customer tags won't ever allow access because a customer needs to create an account and sign in before they access! If you don't want any customers to register on their own, you can simply leave this lock with no keys. Otherwise, you'll want to use non-customer-account based key conditions such as [passcodes](../../keys/passcode-keys.md) or [secret links](../../keys/secret-link-keys.md).
{% endhint %}
