---
title: "Visualizzazione | Schermo"
parent: "Elenco attori"
grand_parent: Concetti
---

> 🚧 en cours de rédaction...

{% include links_actor.md apiClass="Actor.Display.Screen" %}

# Schermo

Attore che permette la visualizzazione di qualsiasi scena

{% include table_of_content.html %}

# Proprietà specifiche

{% assign sorted = site.display_screen_properties | sort: 'order' %}

{% for property in sorted %}

{% include actor_property.md property=property %}

{% endfor %}

## Superamento

{% include property_overflow.md %}

> ![SynApps]( {{ site.baseurl }}/assets/concepts/actor/display_screen/showHide.PNG)

Il valore predefinito è **Automatico**

# Campo d'informazione

## Scena visualizzata

La scena visualizzata dall'attore Schermo è memorizzata nella proprietà `displayedScene` disponibile via collegamento o script.

# Eventi specifici

> 🚧 in fase di redazione ... 
