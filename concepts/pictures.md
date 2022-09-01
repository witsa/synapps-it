---
title: "Libreria delle immagini"
parent: Concetti
---

{% include table_of_content.html %}

# Libreria delle immagini

La libreria delle immagini consente la consultazione dei file immagine contenuti nella cartella `pictures` del progetto.

Lo scopo di questa libreria è quello di raccogliere tutte le immagini utilizzate nel progetto, in modo da avere un accesso più veloce ad esse e di conseguenza ottimizzare le prestazioni del synapp.

## Libreria delle immagini

Le immagini si trovano nella Biblioteca accessibile in alto a sinistra della finestra di Studio.

![SynApps]( {{ site.baseurl }}/assets/concepts/libraries/library.PNG)

In questa sezione è presente l'elenco delle immagini disponibili.

![SynApps]( {{ site.baseurl }}/assets/concepts/libraries/libraryList.PNG)


## Aggiunta di immagini alla libreria

Per aggiungere un'immagine alla libreria, l'immagine desiderata deve essere aggiunta alla cartella `pictures` del progetto.

Per accedere alla cartella è sufficiente premere il pulsante seguente:

![SynApps]( {{ site.baseurl }}/assets/concepts/libraries/addPicture5.PNG)

>📌*Nota*
>
>Si possono inserire cartelle e sottocartelle di immagini. <br>
>La funzione di aggiornamento esplora l'intera struttura dei file per referenziare tutte le immagini presenti nella cartella `pictures`.

In seguito all'aggiunta dell'immagine alla cartella, esistono due metodi per aggiungere l'immagine alla libreria.

**Aggiunta automatica**

Questa diventa disponibile per l'aggiunta tramite la funzione di aiuto:

![SynApps]( {{ site.baseurl }}/assets/concepts/libraries/helpAddPic.PNG)

In ogni caso, se l'immagine non viene visualizzata, è possibile effettuare un aggiornamento per rilevare eventuali aggiunte alla cartella `pictures`.

>📌*Nota*
>
>Quando si aggiungono più immagini alla cartella, è possibile utilizzare l'opzione `Aggiungi tutte le immagini` per aggiungere alla libreria tutte le immagini elencate.

**Aggiunta manuale**

'immagine può essere aggiunta manualmente come segue:

![SynApps]( {{ site.baseurl }}/assets/concepts/libraries/addPicture.PNG)

>Specificare il percorso dell'immagine dalla cartella `pictures`.
>![SynApps]( {{ site.baseurl }}/assets/concepts/libraries/addPicture2.PNG)

>L'anteprima dell'immagine è disponibile.<br>
>È anche possibile cambiare la chiave dell'immagine che si sta per aggiungere.<br>
>![SynApps]( {{ site.baseurl }}/assets/concepts/libraries/addPicture3.PNG)<br>
>Una volta inserite le informazioni, convalidare per aggiungere l'immagine alla libreria.




## Utilizzo delle immagini della libreria in una synapp

Esistono due metodi per utilizzare le immagini della libreria di immagini all'interno di un synapp::

>- Attraverso i [collegamenti](binding.md).
>- Attraverso gli [scripts](scripts/index.md).
>
>[⚡ Synapps.Synapp.html#pictures]({{ site.baseurl }}/script-api/Synapps.Synapp.html#pictures){:target="_blank"}
