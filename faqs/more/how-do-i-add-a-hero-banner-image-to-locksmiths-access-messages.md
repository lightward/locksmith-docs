---
description: >-
  This guide provides an example of how to add a banner image above your access
  message content in your Shopify online store.
---

# How do I add a hero banner image to Locksmith's access messages

{% hint style="info" %}
**Note:** While we can provide examples and guidance, we're unable to write custom code for individual store customisations. This example is meant as a starting point for your own implementation.
{% endhint %}

Locksmith's access messages can be modified using text, HTML, CSS, JavaScript and Liquid code. We cover this and where to edit Locksmith's access messages in our customising messages guide, linked below:

{% content-ref url="../../tutorials/more/customizing-messages.md" %}
[customizing-messages.md](../../tutorials/more/customizing-messages.md)
{% endcontent-ref %}

## Adding a hero banner above your access content:&#x20;

The following code can be added to your "Guest message content" field, above your existing message:

### Hero banner CSS and HTML:

```
<style>
    .hero-image {
        /* Replace the URL here with the URL to your image */
        background-image: url("https://www.w3schools.com/howto/photographer.jpg");
    
        /* Set a specific height */
        height: 300px;
        
        /* Position and center the image to scale nicely on all screens */
        background-position: center;
        background-repeat: no-repeat;
        background-size: cover;
        position: relative;
    }       
</style>
            
            
<div role="banner" class="hero-image">
</div>
```

The above code is based on an example from W3 School, here: [https://www.w3schools.com/howto/howto\_css\_hero\_image.asp](https://www.w3schools.com/howto/howto_css_hero_image.asp)

<figure><img src="../../.gitbook/assets/Screenshot 2024-12-11 at 8.10.56 pm.png" alt=""><figcaption><p>Example image of where the above example code can be added to the "Guest message content" field to include a hero banner above the lock's guest message content.</p></figcaption></figure>

## Customising this example:&#x20;

* To replace the example image with your own, replace the URL with the quotes for the `background-image` with the URL of your banner image
* Adjusting the height of the hero banner by changing the `height` value (300px in this example) to suit your needs

## Modify this code to display a collection-specific banner image (advanced):

<details>

<summary>This section describes how to modify a Shopify image URL so that Locksmith’s default access message content can be used to display collection-specific hero banners.</summary>

It’s possible to add some Liquid code if you would like to display a collection-specific banner image to multiple collections without needing to customise the above code for each image and then applying that to each collection lock.

### To set this up:

1.  **Image titles:**

    You’ll need to title each banner image with the corresponding collection handle. For example, if your collection is located at my-store.myshopify.com/collections/**collection-a**, then the image title for this collection should be **collection-a**.
2.  **Image file types:**

    Make sure all your collection banner images are of the same file type. This can be any file type compatible with [Shopify’s file requirements](https://help.shopify.com/en/manual/shopify-admin/productivity-tools/file-uploads#file-requirements) (or wherever you’ve stored your images), so long as they’re consistent.
3.  **Image file paths:**

    Images stored with Shopify will have a file path similar to the following example, where the image is titled **collection-a**:

    `https://cdn.shopify.com/s/files/1/1234/5678/9012/files/collection-a.jpeg`\


    This path should remain the same for all your images, except for the image title.
4.  **Modifying the image link:**

    You can modify a link for one of your images by replacing the image title with the following Liquid:

    `{{ collection.handle }}`\


    This will give you URL like this:

    `https://cdn.shopify.com/s/files/1/1234/5678/9012/files/{{ collection.handle }}.jpeg`
5.  **Updating the style code:**

    The URL can then be added to the background-image style element’s URL.\


    <figure><img src="../../.gitbook/assets/Screenshot 2024-12-12 at 4.41.12 pm.png" alt=""><figcaption></figcaption></figure>
6.  **Editing the default message content:**

    [Locksmith’s default access messages](../../tutorials/more/customizing-messages.md#default-messages) are located in the Locksmith app’s Settings tab. By adding this modified hero banner image code to a message field in Locksmith’s settings—instead of a specific lock’s settings page—the code will apply to any lock that is using the default message.

#### **(Optional) Limiting the scope of the hero banner code to collection and product pages:**

The banner code can be wrapped in some Liquid so that it runs only on collection and product pages. Here’s an example of Liquid for this purpose:

```
{% raw %}
{% if template == "collection" or "product" %}
  banner code goes here
{% endif %}
{% endraw %}
```

</details>

## Uploading and storing images:

Shopify has some documentation on uploading and managing files here: [https://help.shopify.com/en/manual/shopify-admin/productivity-tools/file-uploads](https://help.shopify.com/en/manual/shopify-admin/productivity-tools/file-uploads)



## Related articles:

{% content-ref url="../../tutorials/more/customizing-messages.md" %}
[customizing-messages.md](../../tutorials/more/customizing-messages.md)
{% endcontent-ref %}

{% content-ref url="../../tutorials/more/customizing-the-passcode-form.md" %}
[customizing-the-passcode-form.md](../../tutorials/more/customizing-the-passcode-form.md)
{% endcontent-ref %}

{% content-ref url="../../tutorials/more/customizing-the-email-list-signup-form.md" %}
[customizing-the-email-list-signup-form.md](../../tutorials/more/customizing-the-email-list-signup-form.md)
{% endcontent-ref %}
