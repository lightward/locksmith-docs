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

## Uploading and storing images:

Shopify has some documentation on uploading and managing files here: [https://help.shopify.com/en/manual/shopify-admin/productivity-tools/file-uploads](https://help.shopify.com/en/manual/shopify-admin/productivity-tools/file-uploads)

## Related guides:

{% content-ref url="../../tutorials/more/customizing-messages.md" %}
[customizing-messages.md](../../tutorials/more/customizing-messages.md)
{% endcontent-ref %}

{% content-ref url="../../tutorials/more/customizing-the-passcode-form.md" %}
[customizing-the-passcode-form.md](../../tutorials/more/customizing-the-passcode-form.md)
{% endcontent-ref %}

{% content-ref url="../../tutorials/more/customizing-the-email-list-signup-form.md" %}
[customizing-the-email-list-signup-form.md](../../tutorials/more/customizing-the-email-list-signup-form.md)
{% endcontent-ref %}
