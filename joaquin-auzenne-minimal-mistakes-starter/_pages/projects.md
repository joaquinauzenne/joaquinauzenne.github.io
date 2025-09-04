---
title: "Projects"
layout: archive
permalink: /projects/
author_profile: true
entries_layout: grid
---

{% include base_path %}

**Selected work highlighting bioinformatics, network science, and applied ML.**

{% for project in site.projects %}
  {% include archive-single.html type="grid" %}
{% endfor %}
