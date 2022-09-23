---
title: "Proprietà Testo"
parent: L'attore
grand_parent: Concetti
nav_order: 2
---

{% include table_of_content.html %}


# Proprietà Testo

I parametri relativi alla categoria Testo permettono di definire le caratteristiche del testo che appare nell'attore.

{% assign sorted = site.base_actor_properties | where: 'section', 'text' | sort: 'order' %}

{% for property in sorted %}

{% include actor_property.md property=property %}

{% endfor %}
