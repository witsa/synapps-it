---
title: "Catégorie Bordure"
parent: Acteur
grand_parent: Concepts
---

{% include table_of_content.html %}


# Catégorie Disposition

Cette catégorie regroupe les propriétés relatives à la disposition de l'acteur.

{% assign sorted = site.base_actor_properties | where: 'section', 'border' | sort: 'order' %}

{% for property in sorted %}

{% include actor_property.md property=property %}

{% endfor %}