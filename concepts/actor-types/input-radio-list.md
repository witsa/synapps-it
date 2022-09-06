---
title: "Interazione | Elenco di scelte"
parent: "Elenco attori"
grand_parent: Concetti
---

{% include links_actor.md apiClass="Actor.Input.RadioList" %}

# Elenco di scelte

![SynApps]( {{ site.baseurl }}/assets/concepts/actor/input_radio_list/sample01.gif)

Un attore di interazione che visualizza un elenco di caselle di controllo. Questo elenco può essere una struttura ad albero.

{% include table_of_content.html %}

# Proprietà

## Selezoioen

La proprietà *selezione* è una stringa che contiene il valore corrispondente alla scelta fatta nell'elenco delle opzioni..

Esempio:

<div class="code-example" markdown="1">
E' stata selezionata l'opzione 1:
</div>

```text
value1
```

Se il valore è una stringa vuota, non viene selezionato alcun valore.

## Le opzioni

La proprietà *Opzioni* è una stringa `JSON` che contiene la matrice delle opzioni.

Un'opzione è un oggetto `JSON` che ha le seguenti proprietà:

| CAMPI | DESCRIZIONE | IMPOSTAZIONE PREDEFINITA |
|--------|-------------|------------|
| `value` |  Il valore dell'opzione. Questo è il suo identificatore unico nell'elenco. Di preferenza, il valore è una stringa. | - |
| `text` | Il testo che appare accanto alla casella di controllo. | - |
| `disabled` | Indica se l'opzione deve apparire disabilitata. | `false` |

Esempio:

<div class="code-example" markdown="1">

![SynApps]( {{ site.baseurl }}/assets/concepts/actor/input_radio_list/sample01.gif)

</div>

```json
[
  {
    "value": "value1",
    "text": "Option 1"
  },
  {
    "value": "value2",
    "text": "Option 2"
  },
  {
    "value": "value3",
    "text": "Option 3"
  }
]
```

## Stato della validazione

{% include property_validation.md %}

## Dimensione

{% include property_size.md %}

# Campi d'informazione

## Testo selezionato

Il campo informativo *Testo selezionato* contiene il testo corrispondente all'opzione selezionata.

## lenco delle opzioni

La tabella delle opzioni è accessibile nel campo informativo *Elenco delle opzioni*.

# Eventi

## `onSelected`

L'evento `onSelected` viene attivato quando la selezione cambia.

> [⚡ `onSelected`]({{ site.baseurl }}/script-api/Actor.Input.RadioList.html#event:onSelected){:target="_blank"}
