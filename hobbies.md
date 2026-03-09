---
title: Hobbies
layout: page
---

{% if site.data.hobbies.size > 0 %}
{% for hobby in site.data.hobbies %}
## [{{ hobby.name }}]({{ hobby.url }})

{{ hobby.description }}

---
{% endfor %}
{% else %}
*Hobbies coming soon.*
{% endif %}
