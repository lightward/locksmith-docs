# Combining key conditions

At times, you'll want to permit visitors to access a resource if _several_ conditions are met. This can be a method of increasing security: you might, for example, require visitors to arrive at your sale collection via a secret link, _but then_ you'll want them to _also_ provide their personal passcode.

All of Locksmith's key conditions can be combined with all other key conditions. (For the full list, see [Types of key conditions](https://docs.uselocksmith.com/article/492-types-of-key-conditions).) This is powerful! It means you can start to chain pieces of authorization logic together, to achieve really specific results.

## Setup

To configure a combination key, begin by creating a standard key using whatever your first condition ought to be. Then, use the "Edit" link (shown next to the condition description). Scroll down to "+ Add key condition". Locksmith will prompt you to add a second condition, which you then configure in exactly the same way as the first.

Note that you'll see another "+ Add key condition" link, appearing in the key settings of your second condition. Yes, you may continue chaining conditions as needed – there are no limits here. :)

Using the example from earlier, in which a secret link condition is combined with a passcode condition, here's a demonstration:

<figure><img src="../../.gitbook/assets/2024-04-16 23.34.42.gif" alt=""><figcaption></figcaption></figure>
