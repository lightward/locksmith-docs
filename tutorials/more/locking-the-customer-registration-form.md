# Locking the customer registration form

{% hint style="info" %}
**Locking the default registration page with Locksmith will **_**only**_** work with Classic Customer Accounts.** \
\
**The New Customer Account system creates an account as soon as the customer uses the login form, and so registration cannot be locked.** \
\
**In that case, we recommend approving customers with account tags instead, after they create an account.**&#x20;
{% endhint %}



To try this out, open up Locksmith, and start typing "registration", like so:

![](https://d33v4339jhl8k0.cloudfront.net/docs/assets/5ddd799f2c7d3a7e9ae472fc/images/5e27858f2c7d3a7e9ae68e46/5e27858f1bbeb.png)

Click on the "Customer Registration" result and then click "Save." Locksmith will create a lock that covers your shop's registration page. From there, feel free to add whatever keys you like!

{% hint style="warning" %}
**Hint:** Key conditions based on things like customer tags won't ever allow access because a customer needs to create an account and sign in before they access! If you don't want any customers to register on their own, you can simply leave this lock with no keys. Otherwise, you'll want to use non-customer-account based key conditions such as [passcodes](../../keys/passcode-keys.md) or [secret links](../../keys/secret-link-keys.md).
{% endhint %}
