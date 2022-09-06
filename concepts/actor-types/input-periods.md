---
title: "Interazione | Periodi"
parent: "Elenco attori"
grand_parent: Concetti
---

{% include links_actor.md apiClass="Actor.Input.Period" %}

# Periodi

L'attore *Periodi* presenta una selezione di periodi tipici ed espone i limiti delle date corrispondenti al periodo selezionato.

![SynApps]( {{ site.baseurl }}/assets/concepts/actor/input_period/sample01.gif)

L'attore *Periodi* ha molte somiglianze con l'attore [*Elenco di pulsanti*] (./input-button-list.md) e possiede la maggior parte delle sue proprietà (*In riga*, *Dimensione*, *Modalità*, ...).

{% include table_of_content.html %}

# Proprietà

## Selezione

La proprietà `Selezione` riflette il valore correntemente selezionato.

I valori possibilie sono rappresentati da uno dei tra :

| - | - | - |
| `all` | Tutto |
| `today` | Oggi |
| `last24` | Ultime 24H |
| `week` | Settimana in corso |
| `weekprevious` | Settimana scorsa |
| `month` | Mese in corso |
| `monthprevious` | Mese scorso |
| `year` | Anno in corso |
| `yearprevious` | Anno scorso |

## Dimensione

{% include property_size.md %}

## Periodi attuali

Questa proprietà consente di definire i periodi presenti e il loro ordine di apparizione nell'attore sotto forma di un array `JSON` di possibili valori. Ad esempio:
```json
[ "today", "last24", "week", "weekprevious", "month", "monthprevious", "year", "yearprevious" ]
```

# Campi d'iformazione

## Data di inizio

Questo campo contiene la data di inizio (formato ISO) del periodo selezionato. Se non è stato selezionato alcun periodo, o se per definizione non ha inizio, il valore è `null`.

## Data di fine

Questo campo contiene la data di fine (formato ISO) del periodo selezionato. Se non è stato selezionato alcun periodo, o se per definizione non ha una fine, il valore è `null`.

## Testo seezionato

Il campo informativo *Testo selezionato* contiene il testo corrispondente all'opzione selezionata.

## Elenco delle opzioni

La tabella delle opzioni è accessibile nel campo informativo *Elenco delle opzioni*.

# Eventi

## `onSelected`

L'evento `onSelected` viene attivato quando la selezione cambia.

> [⚡ `onSelected`]({{ site.baseurl }}/script-api/Actor.Input.Period.html#event:onSelected){:target="_blank"}
