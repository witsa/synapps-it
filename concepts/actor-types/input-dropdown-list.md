---
title: "Interazione | Menu a tendina"
parent: "Elenco attori"
grand_parent: Concetti
---

{% include links_actor.md apiClass="Actor.Input.DropdownList" %}

# Menu a tendina

AUn attore di interazione che visualizza un menu a tendina contenente una serie di scelte.

{% include table_of_content.html %}

# Proprietà

## Selezione

La proprietà *selezione* è una stringa che contiene il valore corrispondente al valore scelto nell'elenco delle opzioni.

Esempio:

<div class="code-example" markdown="1">
l'option 1 est sélectionnée :
</div>

```text
value1
```

Se il valore è una stringa vuota, nessun valore è selezionato..

## Valore vuoto?

È possibile aggiungere automaticamente alla lista anche l'opzione *Vuoto*. Corrisponde al valore ``stringa vuota.

Se si inserisce una stringa nella proprietà *Testo per vuoto*, questa verrà visualizzata per prima nell' elenco delle opzioni, al posto della stringa vuota.

Il testo impostato nella proprietà *Testo se vuoto* verrà visualizzato nell'attore se non viene selezionato nulla.

## Le opzioni

La proprietà *Opzioni* è una stringa `JSON` che definisce l'elenco delle scelte del menu a tendina.

Ogni opzione è un oggetto `JSON` che ha le seguenti proprietà:

| CAMPI | DESCRIZION | IMPOSTAZIONE PREDEFINITA |
|--------|-------------|------------|
| `value` | Il contenuto della scelta. Si tratta dell'identificativo univoco nell'elenco. Il valore è preferibilmente una stringa. | - |
| `text` | Il testo che appare nel menu a tendina. | - |
| `disabled` | Indica se l'opzione deve apparire disabilitata. | `false` |

Esempio:

<div class="code-example" markdown="1">

![SynApps]( {{ site.baseurl }}/assets/concepts/actor/input_dropdown_list/sample01.png)


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

## Stato della convalida

{% include property_validation.md %}

## Dimensione

{% include property_size.md %}

# Campi informazione

## Testo selezionato

Il campo informativo *Testo selezionato* contiene il testo corrispondente all'opzione selezionata.

## Elenco delle opzioni

La tabella delle opzioni è accessibile nel campo informativo *Elenco delle opzioni*.

# Eventi

## `onSelected`

L'evento `onSelected` viene attivato quando la selezione cambia

> [⚡ `onSelected`]({{ site.baseurl }}/script-api/Actor.Input.DropdownList.html#event:onSelected){:target="_blank"}
