# Customer account keys

Many of Locksmith's key conditions use the customer account system that comes by default with all Shopify stores to check for specific customer attributes before granting access. These are detailed below.

{% hint style="info" %}
**Note**: Locksmith does not create a separate account system or customer database! In order to use customer accounts with Locksmith, you'll first need to [make sure that customer accounts are activated in your store](https://help.shopify.com/en/manual/customers/customer-accounts#set-your-customer-account-preferences).
{% endhint %}

When these key conditions are used, **Locksmith will ask that a customer signs in first**, whenever a customer tries to access the locked content in your store. Locksmith does so by automatically displaying the login template from your theme:

![](<../.gitbook/assets/Screen Shot 2022-07-27 at 2.45.59 PM.png>)

Some of the options available to you include checking **if the customer**...

* **is signed in**\
  This condition requires all customers to log in. Once they're logged in, they'll be granted access to the locked resource.
* **is tagged with…**\
  This condition _first_ requires all visitors to log in with a customer account. Once the customer has logged into their account, they'll be granted access _if_ their customer account has the tag you've chosen in Locksmith.
* **is not tagged with…**\
  This condition grants access if the visitor is _not_ signed in with a customer account, _or_ if they are signed in with a customer account that does not have the specified tag.
* **has placed at least x orders**\
  This condition requires the visitor to be logged in with their customer account. If their lifetime order count is at least the number that you specify, they'll be granted access.
* **has purchased…**\
  This condition requires the visitor to be logged in with their customer account, prompting them to log in if they aren't already. If their last 50 orders contain a certain product (identified by SKU, title, or by product tag), they'll be granted access.
* **the customer's email contains…**\
  This condition requires the visitor to be logged in with their customer account. If their email address matches some text that you specify (say, "@mycompany.com"), they'll be granted access.
* **has one of many email addresses**\
  This condition requires the visitor to be logged in with their customer account. If their email address is on the list that you specify, they'll be granted access. Simply to set up, but not recommend if you have a large number of email addresses. See below for an alternate option.
* **has an email from an input list**\
  This condition requires the visitor to be logged in with their customer account. If their email address is on the list that you specify, they'll be granted access. This key condition is different than the above, in that it leverages [Locksmith's input list feature](../tutorials/more/input-lists.md), which lets you use a very large number of of email addresses. While not hard to set up, it does require a few more steps than the one-of-many-email-addresses key condition above.

## Inverting key conditions

Don't forget that all key conditions can be inverted! Which just means that Locksmith will check for _the opposite of_ the original condition. More info on that here:

{% content-ref url="more/inverting-conditions-in-locksmith.md" %}
[inverting-conditions-in-locksmith.md](more/inverting-conditions-in-locksmith.md)
{% endcontent-ref %}

## Liquid key conditions

If the list above does not include the exact customer attribute that you are wanting to check, you have the flexibility to use [any Liquid attribute that Shopify makes available on the customer object](https://shopify.dev/api/liquid/objects#customer). This is done by using a "custom Liquid" key condition.

Most notably, **this would allow you to use customer metafields** in order to grant access.  More complete information on custom liquid key conditions - including setup guide - here:

{% content-ref url="more/liquid-key-basics.md" %}
[liquid-key-basics.md](more/liquid-key-basics.md)
{% endcontent-ref %}

## More information related to customer accounts

Here are a few more links to guides that you might find useful as you set up Locksmith to work with your customer account system:

{% content-ref url="../tutorials/approving-customer-registrations.md" %}
[approving-customer-registrations.md](../tutorials/approving-customer-registrations.md)
{% endcontent-ref %}

{% content-ref url="../tutorials/more/customizing-messages/customizing-the-customer-login-page.md" %}
[customizing-the-customer-login-page.md](../tutorials/more/customizing-messages/customizing-the-customer-login-page.md)
{% endcontent-ref %}

{% content-ref url="../tutorials/more/customizing-messages/customizing-the-registration-form.md" %}
[customizing-the-registration-form.md](../tutorials/more/customizing-messages/customizing-the-registration-form.md)
{% endcontent-ref %}

{% content-ref url="../tutorials/more/customizing-messages/" %}
[customizing-messages](../tutorials/more/customizing-messages/)
{% endcontent-ref %}

As always, please feel free to reach out to us directly via email at **team@uselocksmith.com** if you have any questions!
