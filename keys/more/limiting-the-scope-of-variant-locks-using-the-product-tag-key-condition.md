# Limiting the scope of variant locks using the product tag key condition

By default, Locksmith's [variant locks](../../tutorials/more/locking-variants/) apply to all matching option/value combinations. For example, you'll typically see something like this:\


<figure><img src="../../.gitbook/assets/Screenshot 2024-01-31 at 15.38.03.png" alt=""><figcaption></figcaption></figure>

Once a variant lock is created, you can limit which products it applies to by using the key condition labelled "If the product is tagged with":

<figure><img src="../../.gitbook/assets/Screenshot 2024-01-31 at 15.43.48.png" alt=""><figcaption><p>Type "product" in the popover filter, as shown above, to more easily find the correct key condition</p></figcaption></figure>

You'll use any existing product tags to denote which products you want the variant lock to apply to, or create new product tags if needed.

If you want the lock to **apply to variants on one product tag only**, and leave all other products untouched, for example, you'll use an inverted key condition like so:

<figure><img src="../../.gitbook/assets/Screenshot 2024-01-31 at 15.50.35.png" alt=""><figcaption></figcaption></figure>

Then, **as a separate key,** add in your conditions for access to the product. So if you want to allow access to the variant with a sign in, that will look like this:

<figure><img src="../../.gitbook/assets/Screenshot 2024-01-31 at 15.56.22.png" alt=""><figcaption></figcaption></figure>

The result of this is that all matching variants will automatically be unlocked if the product is NOT tagged with "Snowboard". In other words, **the variant lock will only apply to products tagged with "Snowboard"**.
