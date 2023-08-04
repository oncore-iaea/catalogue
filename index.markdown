---
# Feel free to add content and custom Front Matter to this file.
# To modify the layout, see https://jekyllrb.com/docs/themes/#overriding-theme-defaults

layout: default
---

# Codes

  <div class="row bg-dark text-light">
    <div class="col col-lg-2">Name</div>
    <div class="col col-lg-4">Description</div>
    <div class="col col-lg-2">Links</div>
    <div class="col col-lg-2">License</div>
    <div class="col col-lg-2">Tags</div>
  </div>
{% for item in site.data.catalogue%}
{% unless item.tags contains "data" %}
<div class="row" id="{{item.title}}">
      <div class="col-12 col-lg-2">{{ item.name }}</div>
      <div class="col-12 col-lg-4">{{ item.description | truncate: 900 }} </div> 
      <div class="col-12 col-lg-2">
{% if item.links %}
<ul class="dense">
{% for link in item.links %}
<li >
<a href="{{link.url}}">{{ link.name }}</a>
{% if link.notes %} ({{ link.notes }}) 
{% endif %}
</li>
{% endfor %}
</ul>
{% endif %}
</div>
<div class="col-12 col-lg-2">{{ item.license }}</div>
<div class="col-12 col-lg-2">{{ item.tags }}</div>
</div>
{% endunless %}
{% endfor %}

# Data

  <div class="row bg-dark text-light">
    <div class="col col-lg-2">Name</div>
    <div class="col col-lg-4">Description</div>
    <div class="col col-lg-2">Links</div>
    <div class="col col-lg-2">License</div>
    <div class="col col-lg-2">Tags</div>
  </div>
{% for item in site.data.catalogue%}
{% if item.tags contains "data" %}
<div class="row" id="{{item.title}}">
      <div class="col-12 col-lg-2">{{ item.name }}</div>
      <div class="col-12 col-lg-4">{{ item.description | truncate: 900 }} </div> 
      <div class="col-12 col-lg-2">
{% if item.links %}
<ul class="dense">
{% for link in item.links %}
<li >
<a href="{{link.url}}">{{ link.name }}</a>
{% if link.notes %} ({{ link.notes }}) 
{% endif %}
</li>
{% endfor %}
</ul>
{% endif %}
</div>
<div class="col-12 col-lg-2">{{ item.license }}</div>
<div class="col-12 col-lg-2">{{ item.tags }}</div>
</div>
{% endif %}
{% endfor %}
