---
title: Projects
layout: page
---

{% if site.data.projects.size > 0 %}
{% for project in site.data.projects %}
## [{{ project.name }}]({{ project.url }})

{{ project.description }}

**Tech:** {{ project.tech | join: ", " }}

---
{% endfor %}
{% else %}
*Projects coming soon.*
{% endif %}
