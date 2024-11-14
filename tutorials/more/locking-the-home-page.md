---
description: >-
  How to create a lock that covers the home page of your Online Store sales
  channel in Shopify
---

# Locking the home page



## Option 1 - locking your entire store

Locksmith gives you the ability to lock your entire store, which you can select when creating a new lock:

<figure><img src="../../.gitbook/assets/Screenshot 2024-03-21 at 11.31.17.png" alt=""><figcaption></figcaption></figure>

Once the lock for your entire store is created, you'll see an option labelled _"_Allow access to the home page"**. It is unchecked by default** - **leave it that way to ensure that the home page is locked.**

<figure><img src="../../.gitbook/assets/Screenshot 2024-03-21 at 11.34.34.png" alt=""><figcaption></figcaption></figure>

## Option 2 - create a lock that ONLY covers the home page

This can be done using a simple custom lock. Choose "Start a Liquid lock" from the list when creating a new lock:

<figure><img src="../../.gitbook/assets/Screenshot 2024-03-21 at 11.39.52.png" alt=""><figcaption></figcaption></figure>

For the "Liquid condition", use `template == "index"`

<figure><img src="../../.gitbook/assets/Screenshot 2024-03-21 at 11.41.36.png" alt=""><figcaption></figcaption></figure>

Press "Create lock" to finish the lock creation. Make sure to add your keys on the following page like normal.
