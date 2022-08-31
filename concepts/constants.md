---
title: "Libreria delle costanti"
parent: Concetti
---

{% include table_of_content.html %}

# Libreria delle costanti

La libreria delle costanti consente di memorizzare delle stringhe per poterle utilizzare all'interno di un synapp..

## Accesso alla libreria

Le costanti si trovano nella sezione Libreria sulla sinistra della finestra di Studio.

![SynApps]( {{ site.baseurl }}/assets/concepts/libraries/library.PNG)

In questa sezione si trova l'elenco delle costanti disponibili.

![SynApps]( {{ site.baseurl }}/assets/concepts/libraries/libraryList.PNG)


## Creazione di dati nella libreria

Per creare nuove costanti, fare clic sul pulsante Aggiungi in basso a sinistra della finestra.

![SynApps]( {{ site.baseurl }}/assets/concepts/libraries/addConstant.PNG)

Si apre una finestra che consente di inserire la "chiave" e il "valore" della costante..

La `Clé` correspond à l'identifiant qui va être attribué à la constante.
<br>
Il `Valore' è il valore che assume la costante, che deve essere una stringa o un numero SENZA OPERATORE ( +, -, *, /, etc..).

![SynApps]( {{ site.baseurl }}/assets/concepts/libraries/newConstant.PNG)

## Modifica dei dati nella libreria

Per modificare i dati nella libreria delle costanti, fare clic direttamente sulla costante che si desidera modificare.

In questo modo si apre l'interfaccia di modifica, che consente di inserire una nuova "chiave" e un nuovo "valore".


## Utilizzo delle costanti della libreria in un synapp

Esistono due metodi per utilizzare i dati di una libreria all'interno di un synapp:

>- Il [collegamento](binding.md).
>- Lo [script](scripts/index.md).
>
>[⚡ Synapps.Synapp.html#colors]({{ site.baseurl }}/script-api/Synapps.Synapp.html#constants){:target="_blank"}


>Le costanti sono memorizzate in formato JSON con la seguente sintassi per ogni costante 
>
>`"chiave"` : `"Valore"`
>
> Il file JSON è modificabile direttamente dall'interfaccia..
