---
layout: default
---

{% assign redirects = site.urls | where_exp: "item", "item.redirect_to != nil" %}

{% for page in redirects %}
  [{{ page.url }}]({{ page.url | relative_url }}) `{{ page.redirect_to }}`

  ---
{% endfor %}