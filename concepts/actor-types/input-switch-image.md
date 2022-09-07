---
title: "Interazione | Immagine interruttore"
parent: "elenco attori"
grand_parent: Concetti
---

{% include links_actor.md apiClass="Actor.Input.SwitchImage" %}

# Immagine interruttore

![SynApps]( {{ site.baseurl }}/assets/concepts/actor/input_switch_image/sample01.gif)

Attore di interazione che mostra un interruttore a due stati presentando alternativamente delle immagini.

{% include table_of_content.html %}

# Proprietà

## Valore

Questa proprietà consente di commutare l'interruttore.

## Testo per vero, testo per falso

Queste due proprietà consentono di definire i testi che vengono visualizzati nell'interruttore in corrispondenza del valore `true` e del valore `false`..

# Eventi

## `onSwitched`

L'evento `onSwitched` viene attivato quando l'attore cambia di stato

> [⚡ `onSwitched`]({{ site.baseurl }}/script-api/Actor.Input.SwitchImage.html#event:onSwitched){:target="_blank"}


# Suggerimenti

Questo attore può essere molto utile per visualizzare un indicatore con un'immagine per ogni stato. È sufficiente scegliere le due immagini da visualizzare e disattivare l'attore per evitare che un clic del mouse lo commuti.
