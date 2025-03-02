# Importing customers in bulk

{% hint style="info" %}
Just a quick note: **Locksmith does not create a separate database of customers**. Any customers that you import here are imported as regular Shopify customers and will appear in your Shopify [Customers area](https://help.shopify.com/en/manual/customers/manage-customers). Our bulk import is simply an additional tool with a couple extra options to create/import customers.&#x20;
{% endhint %}

To get started using Locksmith's Customers area, use the "Customers" button, found in the footer navigation on any page of the app:

<figure><img src="../../.gitbook/assets/Screen Shot 2022-09-09 at 1.58.30 PM.png" alt=""><figcaption></figcaption></figure>

There are two options for importing your customers: using a plain list of email addresses, or by loading in a CSV file that you create with your spreadsheet application.

## Importing using email addresses

The only thing you'll need: a list of emails to be used, one per line(or separated by a space).

You'll also see options to:

* add one or more **customer tags** to each customer that's created (useful for pre-approving wholesale accounts, for example)
* set an **account password** (which would allow your customers to sign in immediately, using that password).

If you'd like to customize which tags or what password is used _per customer_, try using a CSV instead - read on!

## Importing using a CSV

For the most flexibility, set up your customer records in your spreadsheet application (like Excel, Google Sheets), and load it into Locksmith for a bulk import:

### Supported column names

_All columns are optional, unless noted._

* Email (required!)
* First name
* Last name
* Accepts marketing (can be "true" or "false")
* Note
* Tags (comma-delimited)
* Password
* etc...

Since this information is just forwarded to your Shopify store, you'll be using the same format that Shopify uses. For more complete information on CSV files for Shopify customers (and what other columns are available), [check out this page](https://help.shopify.com/en/manual/customers/import-export-customers).

## Results

Locksmith will give you a preview of the customers to be imported:

![](https://d33v4339jhl8k0.cloudfront.net/docs/assets/5ddd799f2c7d3a7e9ae472fc/images/5e27859a2c7d3a7e9ae68e67/5e27859a2876c.png)

And after you click the "Start Import" button at the bottom of the page, you'll see the results:

![](https://d33v4339jhl8k0.cloudfront.net/docs/assets/5ddd799f2c7d3a7e9ae472fc/images/5e27859a04286364bc9436f4/5e27859a995e5.png)

In addition to skipping any invalid e-mails, you'll notice that Locksmith will also automatically skip any emails that already have a customer account, and it'll let you know which ones it skipped.

**For questions, get ahold of us via email at team@uselocksmith.com**
