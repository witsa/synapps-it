---
title: "Proprietà Aspetto"
parent: L'attore
grand_parent: Concetti
nav_order: 1
---

{% include table_of_content.html %}


# Proprietà Aspetto

Questa categoria comprende le proprietà relative all'aspetto dell'attore..

{% assign sorted = site.base_actor_properties | where: 'section', 'aspect' | sort: 'order' %}

{% for property in sorted %}

{% include actor_property.md property=property %}

{% endfor %}
