# IP address keys

Locksmith supports permitting visitors based on their IP address.

## Setup

Start by opening the settings for a lock you've created. Then, follow the steps shown to add a key that permits "if the customer has a certain IP address", as shown below:

![](<../../.gitbook/assets/Screenshot 2025-08-18 at 11.44.42 AM.png>)

![](<../../.gitbook/assets/Screenshot 2025-08-18 at 11.45.56 AM.png>)

This key can be configured with a series of IP addresses, one given per line. It can also be configured with CIDR definitions, allowing you to specify entire subnet ranges.

## Notes

This key condition can be inverted, resulting in a condition that permits _unless_ the visitor has a certain IP address. When used with a lock on your entire online store, this is a useful way to block certain visitors.

To accomplish this, invert the key condition, as shown below by clicking on the checkbox next to "invert". (To learn more about inverting conditions, see [Inverting keys in Locksmith](inverting-conditions-in-locksmith.md).)

![](<../../.gitbook/assets/Screenshot 2025-08-18 at 11.46.23 AM.png>)

Because of the way IP address detection works, a IP address key on your entire store will show _everyone_ a spinner graphic for a moment, before your store's content is loaded. This will only happen once, if the visitor has an accepted IP address.

{% hint style="danger" %}
**Important**: When used, this key condition has the potential to negatively affect the SEO of any content that is locked in this way. [More information on SEO and Locksmith here](../../faqs/more/how-does-locksmith-affect-search-engines-and-seo.md).
{% endhint %}
