---
title: "Libredia dei colori"
parent: Concetti
---


{% include table_of_content.html %}

# Libreria dei colori

La libreria dei colori consente di memorizzare i codici colore per poterli utilizzare all'interno di un synapp.

Ogni progetto nasce con una libreria di colori già predisposta.

##Accesso alla libreria

I colori si trovano nella sezione della libreria a sinistra della finestra di Studio.

![SynApps]( {{ site.baseurl }}/assets/concepts/libraries/library.PNG)

All'interno di questa sezione si trova l'elenco dei colori disponibili.

![SynApps]( {{ site.baseurl }}/assets/concepts/libraries/libraryList.PNG)

## Creazione di dati nella libreria

Per creare nuove variabili cromatiche, fare clic sul pulsante Aggiungi in basso a sinistra della finestra.

![SynApps]( {{ site.baseurl }}/assets/concepts/libraries/addColor.PNG)

si apre una finestra che consente di inserire la `chiave' e il `valore' del colore.

La `Chave' è l'identificatore che verrà assegnato alla variabile colore.
<br>
Il `Valore` è il valore che assume la variabile colore, che deve essere [un codice esadecimale](https://htmlcolorcodes.com/fr/) o il [nome di un colore](https://developer.mozilla.org/fr/docs/Web/CSS/color_value) oppure un codice RGB nel formato RGB(X,X,X).
Un aiuto è disponibile durante la modifica.

![SynApps]( {{ site.baseurl }}/assets/concepts/libraries/newColor.PNG)

## Modifica dei dati della libreria

PPer modificare i dati nella libreria dei colori, fare clic direttamente sulla variabile che si desidera modificare.

A questo punto si apre l'interfaccia di modifica, che consente di inserire una nuova `chiave` e un nuovo `valore`.

## Uso dei colori della libreria in una synapp

Esistono due metodi per utilizzare i dati di una libreria all'interno di un synapp:

>- Attraverso un collegamento [liaisons](binding.md).
>- Attraverso uno [scripts](scripts/index.md).
>
>[⚡ Synapps.Synapp.html#colors]({{ site.baseurl }}/script-api/Synapps.Synapp.html#colors){:target="_blank"}


>Le variabili sono memorizzate in formato JSON con la seguente sintassi per ogni colore:
>
>`"Chiave"` : `"valore"`
>
> il file JSON può essere modificato direttamente all'interno dell'interfaccia.
