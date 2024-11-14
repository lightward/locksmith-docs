# Passcode-specific redirects

It's possible to use Locksmith's passcode keys to redirect visitors to specific URLs, based on which passcode they enter. Using this technique, a single page (or other locked resource) can act as a kind of switching station, pointing visitors to the content that's appropriate for them.

To accomplish this, set up multiple passcode keys, each one having a distinct passcode value. Then, for each key, use the triple-dot menu on the right to set a redirect URL, sending the visitor to the appropriate destination when they enter that passcode.

A demonstration:

{% embed url="https://www.loom.com/share/26e5e838ae3646088dbab844f7604421" %}

{% hint style="warning" %}
If you enter the same URL for the redirect as any of the lock's contents, then when a customer uses that key, the result will be an infinite loop. To prevent this from happening, you'll want to avoid adding redirect links to pages that are covered by the same lock.&#x20;
{% endhint %}

## Related articles

A more generalized guide on using redirects in Locksmith can be found here:

{% content-ref url="redirecting-using-locksmith.md" %}
[redirecting-using-locksmith.md](redirecting-using-locksmith.md)
{% endcontent-ref %}
