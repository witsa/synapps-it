---
title: "Visualizzazione | HTML"
parent: "Elenco attori"
grand_parent: Concetti
---

{% include links_actor.md apiClass="Actor.Display.Html" %}

# HTML

L'attore HTML consente di incorporare codice HTML e CSS nella scena.

È un attore molto utile ad esempio per la formattazione del testo o l'aggiunta di classi CSS.

{% include table_of_content.html %}

## Proprietà specifiche

{% assign sorted = site.display_html_properties | sort: 'order' %}

{% for property in sorted %}

{% include actor_property.md property=property %}

{% endfor %}

# Campi informazione

## Contenuto completato

{% include field_completed_content.md %}

# Varianti

## Icone

Una variante dell'attore HTML che offre la possibilità di inserire un'icona scelta tra quelle integrate in Synapps.

Il contenuto dell'attore è completato da un parametro addizionale *icona*.
