---
description: >-
  Use Locksmith to only grant access to customers that subscribe to your
  newsletter
---

# Newsletter keys

Locksmith allows you to integrate directly with either **Mailchimp** or **Klaviyo**. When setup, Locksmith will ask customers for an email address when they arrive on a locked page. Once the email is entered, a customer is immediately granted access, and Locksmith will automatically send the subscription information to the corresponding service.

![](<../../.gitbook/assets/Screen Shot 2022-07-29 at 2.12.12 PM.png>)

{% hint style="info" %}
**Note**: Mailchimp and Klaviyo both have their own policies regarding double opt in, and it is typically enabled by default. This setting is adjusted in your Mailchimp or Klaviyo dashboards - it is not a setting that is controlled by Locksmith.
{% endhint %}

## Mailchimp

Detailed information on how to setup Mailchimp can be found here:

{% content-ref url="../../tutorials/more/mailchimp.md" %}
[mailchimp.md](../../tutorials/more/mailchimp.md)
{% endcontent-ref %}

## Klaviyo

If using Klaviyo, you have the option to simply request that visitors subscribe in order to gain access:

{% content-ref url="../../tutorials/more/klaviyo.md" %}
[klaviyo.md](../../tutorials/more/klaviyo.md)
{% endcontent-ref %}

Or, you can also use Klaviyo to grant access only to those who are _already_ subscribed to a specific list in your Klaviyo account:

{% content-ref url="../../tutorials/more/use-klaviyo-as-an-access-control-list.md" %}
[use-klaviyo-as-an-access-control-list.md](../../tutorials/more/use-klaviyo-as-an-access-control-list.md)
{% endcontent-ref %}

## Using your default Shopify mailing list

Shopify ships out of the box with a marketing mailing list service. If you would like to use Locksmith to grant access to those who have already subscribed to this, you can do so using a custom Liquid key condition.&#x20;

This is slightly different than the above options, in that **it will only grant access to a signed in customers - if the customer is already subscribed**! To start, check out our guide on this here:

{% content-ref url="liquid-key-basics.md" %}
[liquid-key-basics.md](liquid-key-basics.md)
{% endcontent-ref %}

The condition you're looking for is:

`{% if customer.accepts_marketing %}`

When set up, this will present the customer will the regular prompt to sign in (as opposed to the subscription prompt):

![](<../../.gitbook/assets/Screen Shot 2022-07-27 at 2.45.59 PM (1).png>)

If desired, you can adjust your message prompt to direct your customers to the page footer(in most stores) to subscribe to your newsletter. More information on editing messages here:

{% content-ref url="../../tutorials/more/customizing-messages.md" %}
[customizing-messages.md](../../tutorials/more/customizing-messages.md)
{% endcontent-ref %}

## Using other mail services

Locksmith does not support other mail services at this time.&#x20;

However, if you have a mail service that automatically tags customers that are subscribed, you can use Locksmith to check for a customer tag:

{% content-ref url="../customer-account-keys.md" %}
[customer-account-keys.md](../customer-account-keys.md)
{% endcontent-ref %}



Please feel free to contact us via email at **team@uselocksmith.com** if you have any questions!
