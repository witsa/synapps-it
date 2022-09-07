---
title: "Interazione | Pulsante interruttore"
parent: "Elenco attori"
grand_parent: Concetti
---

{% include links_actor.md apiClass="Actor.Input.SwitchButton" %}

# Pulsante interruttore

![SynApps]( {{ site.baseurl }}/assets/concepts/actor/input_switch_button/sample01.gif)

Un attore di interazione che consente di visualizzare un interruttore a due stati.

{% include table_of_content.html %}

# Proprietà

## Valore

Questa proprietà consente di commutare l'interruttore.

## Texte pour vrai, texte pour faux

Queste due proprietà consentono di definire i testi che vengono visualizzati nell'interruttore quando il valore è `true` o `false`.

## Modalità per il vero, modalità per il falso

Queste due proprietà definiscono il modo colore dell'interruttore su `true` e `false`. Sono le stesse modalità dell'attore [*button*] (./input_button.md). La proprietà *Outline* consente anche di gestire le varianti di colore.

## Dimensione

{% include property_size.md %}

# Eventi

## `onSwitched`

L'evento `onSwitched` viene attivato quando si cambia lo stato l'attore.

> [⚡ `onSwitched`]({{ site.baseurl }}/script-api/Actor.Input.SwitchButton.html#event:onSwitched){:target="_blank"}
