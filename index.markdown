---
# Feel free to add content and custom Front Matter to this file.
# To modify the layout, see https://jekyllrb.com/docs/themes/#overriding-theme-defaults

layout: default
---

{% assign codes = "" | split: ',' %}
{% assign data = "" | split: ',' %}
{% for item in site.data.catalogue %}
{% if item.tags contains "data" %}
{% assign data = data | push: item %}
{% else %}
{% assign codes = codes | push: item %}
{% endif %}
{% endfor %}

# Codes

{% include codetable.liquid catalogue=codes %}

# Data

{% include codetable.liquid catalogue=data %}
