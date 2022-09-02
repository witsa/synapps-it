---
title: "Visualizzazione | Testo"
parent: "Elenco attori"
grand_parent: Concetti
---

{% include links_actor.md apiClass="Actor.Display.Text" %}

# Testo

Attore con funzione di visualizzazione del testo.

{% include table_of_content.html %}

Il testo da visualizzare piò contenere stringhe **Jolly**.

# Proprietà specifiche

{% assign sorted = site.display_text_properties | sort: 'order' %}

{% for property in sorted %}

{% include actor_property.md property=property %}

{% endfor %}

# Campi d'informazione

## Contenuto completato

{% include field_completed_content.md %}
