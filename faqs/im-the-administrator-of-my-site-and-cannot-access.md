# I'm the administrator of my site and I cannot access pages because of Locksmith locks.

Locksmith locks your customer facing website so that it can only be accessed under certain circumstances. Some merchants set up more nuanced conditions and Locksmith can get in the way as you navigate your own website.

{% hint style="info" %}
_Note: Using this guide requires that customer accounts are enabled in your store, and that you have a customer account for your own store._
{% endhint %}

### To let Locksmith know to let your customer account through, set up the following lock:

Click the "Start a Liquid lock" on the main page of Locksmith.

<figure><img src="../.gitbook/assets/Screenshot 2024-07-16 at 12.58.50.png" alt=""><figcaption></figcaption></figure>

Next enter this into the "Liquid condition area":

```
customer.tags contains "admin"
```

That will look like this:

<figure><img src="../.gitbook/assets/Screenshot 2024-07-16 at 13.01.34.png" alt=""><figcaption></figcaption></figure>

Press **Create lock** to continue. For your key, use the following..

Select "if (always permit)" from the list of key condition types.

<figure><img src="../.gitbook/assets/Screenshot 2024-07-16 at 13.03.06.png" alt=""><figcaption><p>You can simply type "always" to filter the list.</p></figcaption></figure>

It should end up saying "Permit...always", like so:

<figure><img src="../.gitbook/assets/Screenshot 2024-07-16 at 13.03.19.png" alt=""><figcaption></figcaption></figure>

That's it, for your lock setup. Make sure to save the lock!

### Create a "customer" account for your store:

Now, if you haven't already, create a _customer_ account for your store, and go into your "Customers" area and add "admin" as a tag to your own customer account. You can now access any content in your store while signed in with this account.

Remember this is just a way to test what your customers are seeing, so this means you need to **sign in with your customer account** to gain access to locked content. If customer accounts are not enabled on your store, you won't be able to use this method.

{% hint style="info" %}
**Note:** Locksmith won't lock down your website during [theme edit mode](https://help.shopify.com/en/manual/online-store/themes/customizing-themes/edit), so you always have the option to view your store that way.
{% endhint %}



**As always, feel free to contact us via email at team@uselocksmith.com if you have any questions.**&#x20;
