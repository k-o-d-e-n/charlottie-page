---
layout: page
title: What's New
include_in_header: true
hidden: false
---

# Changelog

{% for version in site.data.versions %}
{% assign vID = version.v | replace: ".", "_" %}
{% assign descr = site.data.changelog[vID] %}
{% if descr.major_badge %}### `{{ descr.major_badge }}`{% endif %}
## **Version {{ version.v }}**

{% if version.ytID %}
<div class="aspect-ratio">
    <iframe frameborder="0" scrolling="no" marginheight="0" marginwidth="0" type="text/html" src="https://www.youtube.com/embed/{{ version.ytID }}"></iframe>
</div>
<br>
{% endif %}

{% if descr.features %}
**Features:**
{% for feature in descr.features -%}
- {{ feature }};
{% endfor %}
{% endif %}
{% if descr.improvements %}
**Improvements:**
{% for improv in descr.improvements -%}
- {{ improv }};
{% endfor %}
{% endif %}
{% if descr.imperfections %}
**Fixed imperfections:**
{% for imperf in descr.imperfections -%}
- {{ imperf }};
{% endfor %}
{% endif %}
{% if descr.bugs %}
**Fixed bugs:**
{% for bug in descr.bugs -%}
- {{ bug }};
{% endfor %}
{% endif %}
<br>
{% if descr.major_badge %}
____________________

<br>
{% endif %}
{% endfor %}