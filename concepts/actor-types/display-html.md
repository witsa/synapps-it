---
title: "Visualizzazione | HTML"
parent: "Attori"
grand_parent: Concetti
---

{% include links_actor.md apiClass="Actor.Display.Html" %}

# HTML

L'attore HTML consente di incorporare codice HTML e CSS nella scena.

È un attore molto utile ad esempio per la formattazione del testo o l'aggiunta di classi CSS.

{% include table_of_content.html %}

Son contenu est **jokerable**.

## Propriétés spécifiques

{% assign sorted = site.display_html_properties | sort: 'order' %}

{% for property in sorted %}

{% include actor_property.md property=property %}

{% endfor %}

# Champs d'informations

## Contenu complété

{% include field_completed_content.md %}

# Variantes

## Icône

Une variante de l'acteur HTML offrant la possibilité d'intégrer une icône choisie parmi les icônes intégrées à Synapps.

Le contenu de l'acteur est complété par une additionnelle *icône*.
