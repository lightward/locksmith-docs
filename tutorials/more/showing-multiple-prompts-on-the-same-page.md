---
description: >-
  How to set up Locksmith to show more than one input form when using more than
  one condition type on the same page
---

# Showing multiple prompts on the same page

Many of Locksmith's access conditions require input from your customers, whether that be a login, or just a code entry or a confirm button press. Sometimes you might wish to give your customers flexibility by providing multiple different ways for a customer to gain access. For example, perhaps they can enter a passcode OR subscribe to your mailing list. Setting that up would look something like this:

<figure><img src="../../.gitbook/assets/Screenshot 2024-08-08 at 12.58.38.png" alt=""><figcaption></figcaption></figure>

By default, **Locksmith only shows one entry method at a time to customers**. In the above example, you'd see something like this:

<figure><img src="../../.gitbook/assets/Screenshot 2024-08-08 at 14.14.40.png" alt=""><figcaption><p>Newsletter prompts are prioritized over passcode prompts according to Locksmith's internal rules</p></figcaption></figure>

## Editing messages to show both forms

To include a specific form for a key condition that you're using, you can mix and match the following liquid variable outputs in your Locksmith messages:

<table><thead><tr><th width="267">Form/condition type</th><th>Liquid code used to include the form</th></tr></thead><tbody><tr><td>passcode</td><td><code>{{ locksmith_passcode_form }}</code></td></tr><tr><td>mailing list signup (i.e. Klaviyo or Mailchimp)</td><td><code>{{ locksmith_email_form }}</code></td></tr><tr><td>confirmation</td><td><code>{{ locksmith_confirmation_form }}</code></td></tr><tr><td>login - for store accounts. If you are not using legacy customer accounts, this is just a button pointing to the sign in page</td><td><code>{{ locksmith_customer_login_form }}</code></td></tr><tr><td>registration -  for store accounts. only applicable if you are using the legacy customer account system</td><td><code>{{ locksmith_customer_registration_form }}</code></td></tr></tbody></table>

## Example

Continuing the passcode/klaviyo example from above, add this:

```
Subscribe to our mailing list to continue!

{{ locksmith_email_form }}

Or, enter the passcode:

{{ locksmith_passcode_form }}
```

Which results in this:

<figure><img src="../../.gitbook/assets/Screenshot 2024-08-08 at 14.31.04.png" alt=""><figcaption></figcaption></figure>

## Which message should you edit?

The easiest way to make sure your locked pages display correctly when using multiple prompts is to simply **copy/paste the same exact message to each of your messages**. Technically only one of them will be used - which is based on Locksmith's internal sorting rules. But, for simplicity, use consistent messages:

<figure><img src="../../.gitbook/assets/Screenshot 2024-08-08 at 14.26.43.png" alt=""><figcaption></figcaption></figure>
