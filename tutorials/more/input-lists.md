---
description: How to use Locksmith's Input List feature to work with large numbers of inputs
---

# Input lists

Locksmith gives you the ability to use input lists for managed sets of [**passcodes**](../../keys/passcode-keys.md)**,** [**secret links**](../../keys/secret-link-keys.md), or [**email addresses**](../../keys/customer-account-keys.md). They're useful when you have a _very large_ number of possible inputs.

{% hint style="info" %}
**Note**: Any time you have 1000+ inputs, it is recommended to use input lists over their vanilla counterparts. Input lists can handle millions of entries, so you have a lot of flexibility here.
{% endhint %}

## Step 1: Add your inputs to an external file

Input lists are stored externally! So you'll need to create a file that is accessible via a URL, adding all of the values to it that you would like to use.

The most straightforward way to do it is to simply use Google sheets:\
\
[https://www.google.com/sheets](https://www.google.com/sheets)

**Google Sheets** must be formatted as a document having a single column of input values, one value per row:

<figure><img src="../../.gitbook/assets/Screenshot 2025-08-22 at 11.44.48 AM.png" alt=""><figcaption></figcaption></figure>

### Supported file formats

In addition to Google Sheets, sources may be of the following formats:

* TXT (one input value per line)
* CSV (a single column of input values, one value per row)
* JSON (an array of strings)
* Microsoft Excel XLSX (a spreadsheet having a single column of input values, one per row)
* JSON array provided by a Mechanic cache endpoint ([read more about Mechanic here](https://apps.shopify.com/mechanic))

{% hint style="warning" %}
**Important**: The source file must be either unauthenticated OR must be a Google Sheet or Google Doc that has been shared with the following email address: **input-lists@locksmith-app.iam.gserviceaccount.com.** \
\
&#xNAN;_&#x49;f you send a notification directly to this email address, it may bounce. However, as long as the document is properly shared with that email address, Locksmith will be able to access it._
{% endhint %}

## Step 2: Locksmith Configuration

Input lists are configured in your Locksmith account settings. To find this area, open the Locksmith app and go to the Settings area (using the left-hand navigation):

<figure><img src="../../.gitbook/assets/Screen Shot 2022-11-08 at 9.31.31 PM.png" alt=""><figcaption></figcaption></figure>

Input lists are available in the "Extensions" area:

<figure><img src="../../.gitbook/assets/Screen Shot 2022-11-08 at 9.34.37 PM.png" alt=""><figcaption></figcaption></figure>

### Options

An input list has four options:

* **Name**
* **Source URL**&#x20;
* Input values are **case-sensitive** (enable to require an exact case match)
* **Default usage limit per input list item** - allows you to specify a default usage limit for any items that you add to the list. This is a great way to add **unique inputs** - simply enter **1** as the usage limit and each input can only be used once.
* **Partial match** - when this option is enabled, Locksmith will accept submissions that **contain** an input list value, rather than requiring an exact match. This is useful for matching part of an email address ( e.g. the domain of the email address) or other partial string. Partial matching is available for any input list (including when they are used for passcodes, secret links, and email addresses) but for performance reasons, can only be used with input lists that have **fewer than 1000 values**. If you need to grant access to a larger list of values, and then a few partial matches, you can create two separate input lists and two separate keys.

### Syncing <a href="#syncing" id="syncing"></a>

When an input list is synchronized with its source, any new items found in the source file will be added to Locksmith's copy of the list. Any items that are  _no longer_ found in the source file will be _removed_ from Locksmith's copy of the list.

Input lists that are sourced from Google Drive will be automatically synchronized whenever the source file is changed. (When used with Google Sheets, this allows for interesting flexibility: one could use a Google Form that saves data to a Google Sheets file, which then feeds into an input list. Whenever the form is submitted, Locksmith would automatically sync a new value into the input list.)

All other input lists are automatically synchronized on a regular basis (currently at [midnight UTC](https://time.is/UTC), subject to change without notice).

All input lists may be synchronized manually, by using the "Sync input list" button for the respective list.

## Step 3: Use with specific key conditions

Once you've created at least one input list, you may use it when configuring a new key condition in your lock settings, by choosing one of the "Permit if..." options that mentions input lists. When adding keys to you locks, use the corresponding options...

### Email Addresses&#x20;

When configuring your key condition, select the "Permit if the customer has an email address from an input list…" option to have Locksmith compare customer inputs with items in your input list:<br>

<figure><img src="../../.gitbook/assets/Screen Shot 2022-11-08 at 9.39.11 PM.png" alt=""><figcaption></figcaption></figure>

More information on using customer account key conditions here:

{% content-ref url="../../keys/customer-account-keys.md" %}
[customer-account-keys.md](../../keys/customer-account-keys.md)
{% endcontent-ref %}

### Passcodes

When configuring your key condition, select the "Permit if the customer gives a passcode from an input list…" option to have Locksmith compare customer input with items in your input list\
<br>

<figure><img src="../../.gitbook/assets/Screen Shot 2022-11-08 at 9.41.27 PM.png" alt=""><figcaption></figcaption></figure>

As with Locksmith's other passcode conditions, you may configure this condition to "remember" returning customers who are logged in. If this option is enabled, Locksmith will compare previously-accepted passcodes from the customer's records with _current_ items in the selected input list. This means that _removing_ previously-used items from the input list will result in the relevant returning customers being "forgotten".

More information on using passcodes here:

{% content-ref url="../../keys/passcode-keys.md" %}
[passcode-keys.md](../../keys/passcode-keys.md)
{% endcontent-ref %}

### Secret links

When configuring your key condition, select the "Permit if the customer arrives using a secret link code from an input list…" option to match the visitor's current URL with items in your input list:

<figure><img src="../../.gitbook/assets/Screen Shot 2022-11-08 at 9.54.03 PM.png" alt=""><figcaption></figcaption></figure>

As with standard secret link keys, Locksmith will be trying to find matching secret link codes in the following parts of the URL:

* The URL's "search" portion. For example, in a URL that looks like "https://example.com/?foo=bar\&baz\&ls=qux", Locksmith will consider items in your input list having the value "foo=bar\&baz\&ls=qux".
* Any component in the URL's "search" portion. For example, in a URL that looks like "https://example.com/?foo=bar\&baz\&qux", Locksmith will consider items in your input list having one of these values: "foo=bar", "baz", "ls=qux".
* The "ls" query parameter, if present. For example, in a URL that looks like "https://example.com/?foo=bar\&baz\&ls=qux", Locksmith will consider items in your input list having the value "qux".

This means that you may form your shared URLs in any of the following ways, using an example secret link code of "foobar" to illustrate:

* [https://example.com/?foobar](https://example.com/?foobar)
* [https://example.com/?ls=foobar](https://example.com/?ls=foobar)

Feel free to combine either option with other query parameters, like so:

* [https://example.com/?foobar\&utm\_source=baz&..](https://example.com/?foobar\&utm_source=baz&..).
* [https://example.com/?ls=foobar\&utm\_source=baz&..](https://example.com/?ls=foobar\&utm_source=baz&..).

As with Locksmith's other secret link condition, you may configure this condition to "remember" returning customers who are logged in. If this option is enabled, Locksmith will compare previously-accepted secret link codes from the customer's records with  _current_ items in the selected input list. This means that _removing_ previously-used items from the input list will result in the relevant returning customers being "forgotten".

More information on using secret links here:

{% content-ref url="../../keys/secret-link-keys.md" %}
[secret-link-keys.md](../../keys/secret-link-keys.md)
{% endcontent-ref %}
