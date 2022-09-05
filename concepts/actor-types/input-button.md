---
title: "Interazione | Pulsante"
parent: "Elenco attori"
grand_parent: Concetti
---

> 🚧 in fase di redazione …

{% include links_actor.md apiClass="Actor.Input.Button" %}

# Pulsante

Attore Pulsante.

{% include table_of_content.html %}

# Proprietà specifiches

{% assign sorted = site.input_button_properties | sort: 'order' %}

{% for property in sorted %}

{% include actor_property.md property=property %}

{% endfor %}

# Campi d'informazione

## Premuto?

Il campo informativo *Premuto?* è un booleano che è `true` quando il pulsante è premuto e ritorna a `false` quando il pulsante viene rilasciato.

## Contenuto Completato

{% include field_completed_content.md %}

# Elementi Specifici

> 🚧 in corso...

# Varianti

## Icona

La variante del pulsante attore offre la possibilità di aggiungere un'icona scelta tra quelle disponibili in Synapps.

Il contenuto del pulsante è completato da una *icona* e da un *testo* aggiuntivi.
