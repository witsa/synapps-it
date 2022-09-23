---
title: "Proprietà Taglie"
parent: L'attore
grand_parent: Concetti
nav_order: 4
---

{% include table_of_content.html %}


# Proprietà Taglie

I parametri di questa categoria permettono di dimensionare l'attore con la taglia desiderata.

{% assign sorted = site.base_actor_properties | where: 'section', 'size' | sort: 'order' %}

{% for property in sorted %}

{% include actor_property.md property=property %}

{% endfor %}
