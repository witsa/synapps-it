---
title: "Interazione | Elenco di caselle di controllo"
parent: "Elenco attori"
grand_parent: Concetti
---

{% include links_actor.md apiClass="Actor.Input.CheckboxList" %}

# Elenco di caselle di controllo

Attore di interazione che visualizza un elenco di caselle di controllo. Questo elenco può essere una struttura ad albero. L'attore dispone di due modalità di selezione: semplice e multipla.

{% include table_of_content.html %}

# Proprietà

## Selezione

La proprietà *Selezione* è una stringa `JSON` che contiene l'elenco dei valori selezionati. Nel caso l'opzione  `Scelta multipla` sia disattivata, è possibile l'attivazione di una sola scelta alla volta.

Esempi di multiselezione:

<div class="code-example" markdown="1">
sono selezionate le opzioni 1 e 2
</div>

```json
["value1", "value2"]
```

<div class="code-example" markdown="1">
Nessun valore selezionato :
</div>

```json
[]
```

<div class="code-example" markdown="1">
Se la proprietà *Tutto è un valore vuoto* è selezionata, tutte le opzioni sono selezionate:
</div>

```json
null
```

In modalità di selezione singola, il formato della selezione rimane invariato.

Ad esempio: `["value1"]` ou bien `[]`.

## Selezione multipla
La proprietà *Selezione multipla?* definisce se l'attore è in modalità di selezione multipla o meno.

In caso di multiselezione, la proprietà *Con opzione tutti* definisce se la scelta "Tutti" è presente nell'elenco. La proprietà *Testo per Tutto* consente di definire il testo che viene visualizzato nell'opzione "Tutto".

## Le opzioni

La proprietà *Opzioni* è una stringa `JSON` che definisce l'insieme delle scelte possibili.

Ogni scelta dell'elenco è un oggetto `JSON` che ha le seguenti proprietà:

| CHAMPS | DESCRIPTION | PAR DÉFAUT |
|--------|-------------|------------|
| `value` | Il valore dell'opzione. Questo è il suo identificatore unico nell'elenco. Il valore è una stringa di caratteri. | - |
| `text` | Il testo che appare accanto alla casella di controllo. | - |
| `disabled` | Indica se l'opzione deve apparire disabilitata. | `false` |
| `options` | Una serie di opzioni che verranno visualizzate sotto la casella di controllo per creare una struttura ad albero. | `null` |
| `collapsed` | Indica se la casella di controllo deve nasconder o meno le sue sotto scelte. | `false` |

Esempio :

<div class="code-example" markdown="1">

![SynApps]( {{ site.baseurl }}/assets/concepts/actor/input_checkbox_list/sample01.png)



</div>

```json
[
  {
    "value": "item1",
    "text": "Élément 1"
  },
  {
    "value": "item2",
    "text": "Élément 2",
    "options": [
      {
        "value": "sub2Item1",
        "text": "Sous élément 1"
      },
      {
        "value": "sub2Item2",
        "text": "Sous élément 2"
      }
    ]
  },
  {
    "value": "item3",
    "text": "Élément 3",
    "collapsed": true,
    "options": [
      {
        "value": "sub3Item1",
        "text": "Sous élément 1",
        "disabled": true,
        "options": [
          {
            "value": "sub3sub1Item1",
            "text": "Sous sous élément 1"
          },
          {
            "value": "sub3sub1Item2",
            "text": "Sous sous élément 2"
          }
        ]
      },
      {
        "value": "sub3Item2",
        "text": "Sous élément 2"
      }
    ]
  }
]
```

## Stato di malidazione

{% include property_validation.md %}

## Taglie

{% include property_size.md %}

# Champi d'nformazione
I seguenti campi di informazione sono molto utili per creare collegamenti o script, in quanto le proprietà dell'attore sono spesso stringhe JSON.

## Valore e valori

In modalità di selezione singola, il campo informativo *Valore* contiene semplicemente il valore selezionato. In modalità multiselezione, il campo informativo *Valori* contiene l'elenco dei valori selezionati in forma di array `Javascript`.

## Testo e Testi

Come per i valori, il campo informativo *Testo* e *Testio* contiene rispettivamente il testo selezionato e la tabella dei testi selezionati.

## Tabella delle opzioni

L'elenco delle opzioni è accessibile nel campo informativo *Tabella delle opzioni*..

# Eventi

## `onSelected`

L'evento `onSelected` viene attivato quando la selezione cambia.

> [⚡ `onSelected`]({{ site.baseurl }}/script-api/Actor.Input.CheckboxList.html#event:onSelected){:target="_blank"}
