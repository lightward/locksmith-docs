# My featured collections on my home page only show one product.

This error happens on specific themes (notably, the "Minimal" theme and similiar themes). There is a minor incompatibility with theses themes, but we can get it patched up for you pretty quickly!

Please get ahold of us if you would like us to make the edit. That being said, if you need an immediate update, here are the steps to fix it.

Start by opening the **sections/featured-collection.liquid** file in the theme editor and making the following replacements:

### Line 1

Before:

```
{% raw %}
{% assign featured = section.settings.featured_collection %}
{% endraw %}
```

After:

```
{% raw %}
{% assign featured_collection = section.settings.featured_collection %}
{% endraw %}
```

### Line 28

Before:

```
{% raw %}
{% for product in collections[featured].products limit: total_products %}
{% endraw %}
```

After:

```
{% raw %}
{% for product in collections[featured_collection].products limit: total_products %}
{% endraw %}
```

### Line 30

Before:

```
{% raw %}
{%- include 'locksmith-variables', locksmith_scope: 'subject', locksmith_subject: product, locksmith_subject_parent: collections[featured] %}
{% endraw %} ...
```

After:

```
{% raw %}
{%- include 'locksmith-variables', locksmith_scope: 'subject', locksmith_subject: product, locksmith_subject_parent: collections[featured_collection] %}
{% endraw %} ...
```

\
So, as you can see, you'll just be replacing "featured", with "featured\_collection" in a couple places. This will clear up the ambiguity on what the "featured" holds.&#x20;

Note: If your theme has been custom edited, the above line number may not be _exact_.

**As always, do contact us if you aren't feeling up to this!**  We are happy to do this for you. You can get in touch with the message button in the lower right corner.
