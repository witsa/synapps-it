---
title: "Proprietà Effetti"
parent: L'attore
grand_parent: Concetti
nav_order: 7
---

{% include table_of_content.html %}


# Proprietà Effetti

I parametri all'interno di questa categoria permettono di agire sugli effetti visuali di rappresentazione dell'attore.

{% assign sorted = site.base_actor_properties | where: 'section', 'effects' | sort: 'order' %}

{% for property in sorted %}

{% include actor_property.md property=property %}

{% endfor %}
