---
title: "REDY | Giornale degli eventi"
parent: "Elenco attori"
grand_parent: Concetti
---

{% include links_actor.md apiClass="REDY.Actor.WosEventLog" %}

# Giornale degli eventi

L'attore *Giornale degli eventi* visualizza la matrice contenente gli eventi presenti nel giornale del REDY.


# Proprietà

## Aggiornamento automatico?

Il registro viene aggiornato in base a un intervallo di tempo che può essere impostato. Il refresh può essere disabilitato.

## Intestazione e paginazione

Nell'intestazione della tabella si trovano le definizioni delle colonne. L'elenco delle colonne è personalizzabile. Per il momento si tratta di una tabella di chiavi in JSON:

```json
["id", "ack", "icon", "date", "nod", "site", "state", "todo"]
```

| clé de colonne | Description |
| ---- | ------|
| `id` | Indice evento |
| `ack` | Acquisizione |
| `icona` | Icona evento |
| `data` | Date dell'evento |
| `evento` | Risorsa all'origine dell'evento |
| `sito` | Il sito dell'elemento che ha causato l'evento |
| `stato` | Lo stato della risorsa |
| `todo` | ? |

Lasciare la proprietà * Colonne* vuota per visualizzarle tutte.

E' possibile di attivare / disattivare la visualizzaizone dell'intestazione delle colonne.

L'elenco degli eventi è impaginato, ovvero ne viene visualizzato solo un determinato numero alla volta. La navigazione da una pagina all'altra è affidata a dei pulsanti.

Una proprietà consente di rendere invisibili i pulsanti di paginazione.

## Filtri

È possibile impostare il filtraggio degli eventi in base alla data, agli eventi in corso, agli attributi (gruppo, insieme, zona, ...) o per risorsa.

# Eventi

## `onRequestDone`

L'evento `onRequestDone` viene attivato quando l'attore ha completato una richiesta al REDY per ottenere o aggiornare l'elenco da visualizzare.

> [⚡ `onRequestDone`]({{ site.baseurl }}/script-api/REDY.Actor.WosEventLog.html#event:onSelected){:target="_blank"}

# Esempi

## giornale con selezione del periodo di tempo:

> TODO
