---
description: How to use Locksmith's 'timeout' feature to limit access time
---

# Grant access for a limited time when using passcodes or secret links

This feature is available only when using "[passcode](../../keys/passcode-keys.md)" or "[secret link](../../keys/secret-link-keys.md)" key conditions. In specific, the following key conditions types:\
\
&#xNAN;_&#x50;ermit if the customer..._

* gives the passcode
* gives one of many passcodes
* gives a passcode from an input list
* arrives via a secret link
* arrives using a secret link from an input list

The setup is pretty straightforward. You'll see the corresponding option, when setting up one of the above key condition types, and can adjust the time period like so:

<figure><img src="../../.gitbook/assets/Screen Shot 2023-04-12 at 2.02.40 PM.png" alt=""><figcaption></figcaption></figure>

## Caveats

#### 1. Using this setting with the "Remember for signed-in customers"

Since most folks using the timeout setting are wanting to heavily limit their customers' access period, we typically recommend that anyone using the timeout setting makes sure to turn the "Remember for signed-in customers" setting OFF. While the two settings can technically be used together, doing this can provide you the most consistent results.

That being said, if, for any reason, you have set a longer access period (months, years), it may actually make more sense to keep the "Remember for signed-in customers" setting turned on. This will help Locksmith maintain access (via customer metafields) for the full period of time, as long as the customer is signed in.

#### 2. Access time is evaluated at time of page load

As stated under the option itself, Locksmith won't refresh the page for the visitors, so visitors' access period will only time out when they load or refresh a page.

#### &#x20;3. The setting won't apply retroactively

When adding this setting to an already-existing key condition, it will only be applied to new visitors. As in, it will not apply retroactively.&#x20;

If you _do_ want to reset access for all visitors, the easiest way to do this is to delete your key condition( press the "Remove" button on the condition) and recreate it with a different passcode or secret link.

#### 4. Every time a visitor uses the same passcode or secret link, the timeout timer for that particular passcode/link is reset

In other words, the timer is always based on the _most recent_ Locksmith submission/validation. If a customer resubmits a passcode or re-uses a secret link, the timer starts from then, even if that code/link was already used.&#x20;

To prevent this kind of thing, you can set up your codes/links so that they have limited uses (or even one use only). Check out the corresponding guides for more information on how to do that:

* [Secret links](../../keys/secret-link-keys.md)
* [Passcodes](../../keys/secret-link-keys.md)

#### 5. When using the timeout feature, do not use the same passcodes or secret links as you are using in your key conditions that do not time out

Using the same passcodes or secret links for key conditions that time out, as those that _do not_ time out will result in none of your key conditions timing out as expected.

#### 6. On rare occasions, page caching may prevent visitors access from timing out

It is possible for pages in your online store to be cached based on Shopify features and Theme settings. This may prevent the page from timing out exactly when expected. Because of this, the setting should be considered to be simply an extra tool in your toolbox, and not depended on to be exact and precise.

####
