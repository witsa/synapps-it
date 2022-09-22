---
title: "Proprietà Layout"
parent: L'attore
grand_parent: Concetti
nav_order: 3
---

{% include table_of_content.html %}

Questa categoria ragruppa le proprietà relative al modo in cui l'attore si dispone all'interno di un attore di tipo Layout.
I parametri presenti variano in funzione del tipo di attore nel quale è posizionato.

# Proprietà Layout flessibile

Questa categoria raggruppa le proprietà relative alla disposizione dell'attore in un layout flessibile come l'[impilamento](../actor-types/layout-stack.md), Il [Box di visualizzazione](../actor-types/layout-view-box.md) o la [modale](../actor-types/layout-modal.md).

{% assign sorted = site.base_actor_properties | where: 'section', 'disposition_flex' | sort: 'order' %}

{% for property in sorted %}

{% include actor_property.md property=property %}

{% endfor %}

# Proprietà Layaut in un Canvas

Questa categoria raggruppa le proprietà relative alla disposizione dell'attore in un [canvas](../actor-types/layout-canvas.md).


In un attore [canvas](../actor-types/layout-canvas.md), i figli diretti sono disposti secondo delle coordinate relative ai suoi 4 bordi.


## Posizione alta
La posizione alta viene utilizzata per definire o scostamento verticale del bordo esterno superiore dell'attore rispetto al bordo interno superiore del canvas padre. I bordi considerati sono:
- bordo interno del canvas, ossia include il potenziale margine interno alto
- bordo esterno dell'attore figlio, cioè include il potenziale margine esterno alto.

## Posizione sinistra
La posizione sinistra viene utilizzata per definire lo scostamento orizzontale del bordo esterno sinistro dell'attore rispetto al bordo interno sinistro del canvas padre. I bordi considerati sono:
- bordo del canvas, cioè include il potenziale margine interno di sinistra.
- bordo esterno dell' attore figlio, cioè include il potenziale margine esterno sinistro.

## Posizione bassa
La posizione bassa definisce lo scostamento verticale del bordo esterno superiore dell'attore rispetto al bordo interno superiore del canvas padre. I bordi considerati sono:
- bordo interno del canvas, cioè include il potenziale margine interno inferiore
- bordo esterno dell' attore figlio, cioè comprende il potenziale margine esterno basso.

## Posizione destra
La posizione destra definisce lo scostamento orizzontale del bordo esterno destro dell'attore rispetto al bordo interno destro del canvas padre. I bordi considerati sono:
- bordo interno del canvas, ovvero include il potenziale margine interno destro
- bordo esterno dell'attore figlio, cioè comprende il potenziale margine esterno destro.

> 📌 **NOTA**<br>
Le posizioni superiore e sinistra sono quelle che vengono modificate quando l'attore viene spostato con il mouse all'interno dell'attore canvas.

> 💡 **CONSIGLIO**<br>
Se si usano due coordinate opposte allo stesso tempo (alto/basso *o* destra/sinistra) e non ci sono altri vincoli di dimensione, l'attore accetta di far rispettare ai suoi bordi le regole di posizione. Per esempio, per distribuire un attore sull'intera superficie di un canvas, si possono impostare tutte le posizioni a `0`. In questo modo, ogni bordo verrà incollato al bordo corrispondente dell'attore canvas.

## Link
> - Posizione alta: {% include actor_property_script.md propName="top" propPath="properties.top" scriptApiClass="Actor.BaseActorProperties" %}
> - Posizione bassa: {% include actor_property_script.md propName="bottom" propPath="properties.bottom" scriptApiClass="Actor.BaseActorProperties" %}
> - Posizione sinistra: {% include actor_property_script.md propName="left" propPath="properties.left" scriptApiClass="Actor.BaseActorProperties" %}
> - Position destra: {% include actor_property_script.md propName="right" propPath="properties.right" scriptApiClass="Actor.BaseActorProperties" %}
