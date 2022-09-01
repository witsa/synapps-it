---
title: "Icone"
parent: "Progetto"
grand_parent: Concetti
nav_order: 7
---

{% include table_of_content.html %}

# Gestione delle icone in Synapps Studio

Le icone Synapps consentono di personalizzare e conferire carattere alla propria applicazione.

Sono immagini quadrate, di tipo `png`. Hanno dimensioni diverse per adattarsi alle esigenze del browser e dei dispositivi portatili. In totale sono 11.

## Logo del synapp

L'icona principale è quella che verrà utilizzata come logo del synapp. Si tratta dell'icona che viene visualizzata nello *splash screen*, cioè all'avvio del synapp, durante il suo caricamento. E' anche l'icona che lo rappresenta quando si visualizza un elenco di synapp.

La dimensione di questa icona è `255x255`.

## Icone per il browser

Le icone di dimensioni `16x16` e `32x32` sono utilizzate dai browser per illustrare i preferiti e le schede.

## Altre icone

Tutte le altre icone sono utilizzate da dispositivi mobili quando la synapp è installata su di essi in *progressive web app* (PWA). Vedere la procedura ([TODO]).


## Peso delle icone

Nel complesso, è meglio che le icone siano leggere: pochi KByte. Questo vale soprattutto per le 3 icone principali. Le altre vengono caricate una sola volta.

## Accesso alle icone

Le icone si trovano nella sottosezione "icone" della sezione "Progetto".

![SynApps]( {{ site.baseurl }}/assets/concepts/icons/iconsAccess.PNG)

## Barra degli strumenti delle icone

La barra degli strumenti delle icone è visibile nella parte superiore della finestra di gestione delle icone.

![SynApps]( {{ site.baseurl }}/assets/concepts/icons/iconsToolBar.PNG)

L'icona di aggiornamento viene utilizzata per ricaricare le icone che potrebbero essere state modificate nella cartella delle icone.

![SynApps]( {{ site.baseurl }}/assets/concepts/icons/refresh.PNG)

L'icona Elimina consente di ripristinare tutte le icone a quelle di base fornite da Synapps.

![SynApps]( {{ site.baseurl }}/assets/concepts/icons/deleteAll.PNG)

Infine, l'ultimo pulsante consente di aprire direttamente la cartella in cui si trovano le icone.

## Modifica / Reset / Generazione di icone

L'interfaccia di un'icona si presenta così:

![SynApps]( {{ site.baseurl }}/assets/concepts/icons/icon.PNG)

### Per modificare un'icona, esistono due possibilità:

- Facendo clic sull'icona è possibile definire manualmente l'icona che si desidera associare alla dimensione definita.

- Utilizzare il pulsante `Apri cartella icone progetto...` e sostituire l'icona desiderata.

>⚠️ **ATTENZIONE**<br>
>Nel secondo metodo, è necessario sostituire l'icona desiderata con un'immagine e darle lo STESSO NOME dell'icona da sostituire.

### Per ripristinare un'icona all'icona di base di Synapps Studio:

È sufficiente fare clic sul pulsante di cancellazione nella parte superiore dell'interfaccia dell'icona.

![SynApps]( {{ site.baseurl }}/assets/concepts/icons/iconToolBar.PNG)

### Per generare automaticamente un'icona da un'immagine:

Innanzitutto, è necessario posizionare un'immagine nell'angolo in alto a destra della finestra, facendo clic sull'apposita area.

![SynApps]( {{ site.baseurl }}/assets/concepts/icons/iconGen.PNG)

Una volta caricata l'immagine, è possibile generare icone per tutte le dimensioni utilizzando il pulsante sopra l'interfaccia del generatore di icone.

![SynApps]( {{ site.baseurl }}/assets/concepts/icons/iconGenReady.PNG)

È anche possibile generare l'immagine appropriata per una singola icona utilizzando il pulsante sopra l'interfaccia delle icone.

![SynApps]( {{ site.baseurl }}/assets/concepts/icons/iconGenReadyV2.PNG)
