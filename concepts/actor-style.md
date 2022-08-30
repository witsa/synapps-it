---
title: "Stile attore"
parent: Concetti
---

{% include table_of_content.html %}

# Stile di un attore

## Definizione

Le proprietà di un [attore](./actor.md) vengono inizializzate con valori predefiniti. Queste sono definite secondo lo stile utilizzato dall'attore.
Inizialmente, un attore utilizza lo stile `default`. E' possibile impostare altri stili per modificarne i valori predefiniti.

![SynApps](../assets/concepts/actor-style-01.png)

Il cambio di stile si effettua tramite script. *A_VENIRE collegamento al documento*

La définition de style peut s'effectuer par script. *A_VENIRE collegamento al documento*

Ogni tipo di dato prevede uno stile.

Uno stile è sempre derivato da un altro (quindi almeno su quello predefinito!).

## In Studio

### Gestione degli stili

La modifica degli stili degli attori è attualmente da realizzarsi in JSON.

![SynApps](../assets/styles.png)


Di seguito un esempio di definizione JSON dello stile di un attore Impilamento:
```json
{
  "layout/stack": [
    {
      "name": "pink",
      "definition": {
        "backgroundColor": "pink",
        "color": "brown"
      }
    },
    {
      "name": "green",
      "definition": {
        "backgroundColor": "lightGreen"
      }
    },
    {
      "name": "shadow",
      "definition": {
        "borderRadius": "5px",
        "paddingTop": "1em",
        "paddingBottom": "1em",
        "paddingRight": "1em",
        "paddingLeft": "1em",
        "marginTop": "1em",
        "marginBottom": "1em",
        "marginRight": "1em",
        "marginLeft": "1em",
        "boxShadow": "0 0 5px 3px #888"
      }
    },
    {
      "name": "other-shadow",
      "basedOn": "shadow",
      "definition": {
        "borderRadius": "15px",
        "boxShadow": "0 0 15px 7px #888"
      }
    }
  ]
}

```

Si noterà la definizione di `other-shadow` basata su `shadow` che eredita le definizioni di quest'ultimo, ridefinendo `borderRadius` e `boxShadow`.

### Utilizzo nel Designer

In ogni attore, il campo **Stile** permette il cambio con un altro appropriato al suo tipo.

![SynApps](../assets/concepts/actor-style-02.png)

Osserva il colore dello sfondo:

![SynApps](../assets/concepts/actor-style-03.png)

È impostato sul valore predefinito: Nessuno.

Dopo aver cambiato lo stile in `pink`, il valore visualizzato del campo viene impostato su `pink`. Tuttavia, non bisogna confondersi: è il suo valore predefinito che è cambiato. Se fosse stato impostato un colore diverso da quello predefinito, sarebbe stato mantenuto.

![SynApps](../assets/concepts/actor-style-04.png)
