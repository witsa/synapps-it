---
title: "Visualizzazione | Immagine"
parent: "Elenco attori"
grand_parent: Concetti
---

{% include links_actor.md apiClass="Actor.Display.Image" %}

# Image

Si tratta di un attore che consente di visualizzare un'immagine.

{% include table_of_content.html %}

# Proprietà specifiche

{% assign sorted = site.display_picture_properties | sort: 'order' %}

{% for property in sorted %}

{% include actor_property.md property=property %}

{% endfor %}
