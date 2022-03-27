---
layout: page
title: Tutorials
include_in_header: true
hidden: false
---

# Tutorials

{% for tutorial in site.data.tutorials %}
{% assign tID = tutorial.title | replace: " ", "-" | downcase %}
{% assign descr = site.data.videos[tID] %}
## **{{ tutorial.title }}**

{% if tutorial.ytID %}
<div class="aspect-ratio">
    <iframe frameborder="0" scrolling="no" marginheight="0" marginwidth="0" type="text/html" src="https://www.youtube.com/embed/{{ tutorial.ytID }}"></iframe>
</div>
<br>
{% endif %}
**Duration:** {{ tutorial.dur | times: 1.0 | divided_by: 60 }} min
{% if descr.desc %}
**Description:**
{% for desc in descr.desc %}
{{ desc }}
{% endfor %}
{% endif %}
<br>
{% endfor %}