# Locking the search results page in your store

To get started, search for "search" from within Locksmith, like so:

![](https://d33v4339jhl8k0.cloudfront.net/docs/assets/5ddd799f2c7d3a7e9ae472fc/images/5e27859f2c7d3a7e9ae68e75/5e27859f78e77.png)

... and click on the "Search" search result. (So much searching!)

That's it! :)

## Protecting search forms, using Liquid code

Out of the box, this lock _only_ protects the /search url of your shop (as in [https://myexampleshop.com/search](https://myexampleshop.com/search)).

To hide the search boxes that your theme may include elsewhere in your shop, open up the Liquid file that contains the search form in question, and locate the actual search form. Wrap it with Liquid that looks like this:

```
{% raw %}
{% include 'locksmith-variables', locksmith_scope: 'search' %}

{% if locksmith_access_granted %}  
  <!-- your search form here! -->
{% endif %}
{% endraw %}
```

As you can see, this _does_ require manual coding. If you need a hand with this, let us know! :)
