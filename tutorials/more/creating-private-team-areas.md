# Creating private team areas

Locksmith can be used to create separate areas of your store for different teams, clubs, vendors, organizations, or other groups. These areas are intended to be private, only for the eyes of those members. This guide also applies even if there is only a single customer that should gain access to each area.

To summarize, you will create a landing page that you can link all of your customers to, and then use Locksmith to lock down and redirect customers to their own content. The rest of the guide explains, in greater detail, how to do all of this.

{% hint style="warning" %}
**The setup for this can become involved**, particularly if you have a large number of groups that you want to set this up for. Before you go all in with setting this up, it might be best to follow the steps in this guide for just one or two groups, that way you can more quickly get a feel for how this will work for your store.
{% endhint %}

## Step 1: Create the content for each group

For each group, create the collection of products that applies to them. Or, if you prefer that your customers are redirected to a single product, or some other page, you can use those instead.

## Step 2: Create the landing page

This can just be a regular Shopify Page, more info on that here:\
\
[https://help.shopify.com/en/manual/online-store/themes/theme-structure/pages](https://help.shopify.com/en/manual/online-store/themes/theme-structure/pages)

Call it whatever makes sense for you. You don't have to actually add any content to the page, since customers will be immediately redirected away from this page.

**Optional: Add a link to this page to your navigation menu**. This is how customers will find their content. Label the link whatever applies to your store, such as "Shop", or "Your collection", or "Member area", etc. If you do not add a link to your navigation menu, you will need to have another method of making sure your customers find, or are sent, the link to your landing page.

## Step 3: Decide how you want to grant access

While it is possible to use almost any of Locksmith's key condition types for this ([complete list here](https://www.locksmith.guide/basics/creating-keys)), there are two common types for determining access:

* Customer tags ([more info here](https://www.locksmith.guide/keys/customer-account-keys))
* Passcodes ([more info here](https://www.locksmith.guide/keys/passcode-keys))

## Step 4: Add the lock and keys to your landing page

1. [Create a Locksmith lock](https://www.locksmith.guide/basics/creating-locks) directly on your landing page.&#x20;
2. For each of your customer groups, add a matching key that grants access _to this landing page_ (we'll create the individual collection locks in the next step). This key should define how you want customers to ultimately gain access to their collection - **so whatever you chose in step 3.**
3. For each of the keys that you create, use Locksmith's redirect feature to redirect customer to the actual collection that you are granting access to. You can set up a redirect directly within the key settings, when creating a key. Simple use the input labelled "Redirect URL". [More info on redirecting with Locksmith here](https://www.locksmith.guide/tutorials/more/redirecting-using-locksmith#redirecting-customers-after-theyve-gained-access).

## Step 5: Add the locks and keys to each of your collections

For each of your collections, add a lock to it and add a key that defines how you want customers to gain access. **This key should match whatever key you used in Step 4.** Except, of course, leave out the redirect on this one.

***

Once you follow those steps, you will end up with a landing page that redirects customers to their own content. The redirect will happen after the customer has gained access via signing in or giving the passcode (or whatever access method you've chosen).

Feel free to contact Locksmith support at **team@uselocksmith.com** for any questions regarding this.
