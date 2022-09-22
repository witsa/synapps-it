---
title: "Proprietà Bordi"
parent: L'attore
grand_parent: Concetti
nav_order: 6
---

{% include table_of_content.html %}


# Proprietà Bordi

Questa categoria raggruppa le proprietà relative al modo di rappresentare i bordi dell'attore.

{% assign sorted = site.base_actor_properties | where: 'section', 'border' | sort: 'order' %}

{% for property in sorted %}

{% include actor_property.md property=property %}

{% endfor %}
