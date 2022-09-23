---
title: "Proprietà Spazi"
parent: L'attore
grand_parent: Concetti
nav_order: 5
---

{% include table_of_content.html %}


# Proprietà Spazi

Questa categoria raggruppa le proprietà relative ai margini dell'attore.

{% assign sorted = site.base_actor_properties | where: 'section', 'space' | sort: 'order' %}

{% for property in sorted %}

{% include actor_property.md property=property %}

{% endfor %}
