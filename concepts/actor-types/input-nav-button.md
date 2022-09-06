---
title: "Interazione | Bottone di Navigazione"
parent: "Elenco attori"
grand_parent: Concetti
---

> 🚧 in corso di redazione ...

{% include links_actor.md apiClass="Actor.Input.NavButton" %}

# Pulsante di navigazione

L'attore pulsante di navigazione consente, oltre a tutte le possibilità dell'[attore pulsante](./input-button.md), di navigare tra le scene e di modificare la scena visualizzata in un [attore schermo](./display-screen.md).

Le sue proprietà sono simili a quelle dell'attore pulsante descritte a [questo indirizzo](./input-button.md)..

Le proprietà supplementari sono elencate di seguito.

{% include table_of_content.html %}

# Proprietà specifiche

{% assign sorted = site.input_nav_button_properties | sort: 'order' %}

{% for property in sorted %}

{% include actor_property.md property=property %}

{% endfor %}

# Eventi specifici

> 🚧 en cours de rédaction...


