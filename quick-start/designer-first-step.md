---
title: "Designer : Premiers pas"
parent: Guide de démarrage
nav_order: 4
---

[◀ Esecuzione](./synapp-run){: .btn } [Pubblicazione ▶](./synapp-publish){: .btn }

----------------

{% include table_of_content.html %}

# Primi passi con il Designer delle scene

Procediamo a modificare il progetto per visualizzare un messaggio di benvenuto nell'area dedicata.

Ma prima, esaminiamo alcuni concetti:

## La scena

Un synapp è composto da pagine che chiamiamo **scene**.

L'applicazione è costituita da una o più scene che l'utente visualizza navigando da una all'altra.

![SynApps](../assets/scenes-nav.png)

## Apertura del Designer

Selezionare una delle scene del progetto. Verrà visualizzato l'albero delle scene del progetto:

![SynApps](../assets/quick-start/designer-first-steps/01.png)

La scena con l'icona ![SynApps](../assets/start-scene-icon.png) è quella che il synapp visualizzerà per prima: è la **scena di avvio**. Ma non è questa ad essere modificata in questa sede.

Selezionare la scena **Accueil** per visualizzare il suo **designer**..

![SynApps](../assets/quick-start/designer-first-steps/02.png)

- Al centro viene visualizzata l'**anteprima** della scena <span style="color: red;">**A**</span>.
- Sotto l'elenco delle scene, a sinistra, si trova la **listaa degli attori** che appartengono alla scena selezionata.  <span style="color: red;">**B**</span>.
- A destra vengono visualizzati i **parametri** dell'oggetto selezionato nel pannello di sinistra attraverso un pannello chiamato **ispettore*.  <span style="color: red;">**C**</span>.

## L'attore

Ogni scena contiene le istruzioni e la programmazione degli elementi dell'interfaccia chiamati [**attori**](/synapps/concepts/actor/) che vanno dal più semplice dei pulsanti di azione a un attore che visualizza i dettagli di un riflesso.
Gli attori possono essere utilizzati per costruire e strutturare qualsiasi tipo di interfaccia, dai formulari ai dashboard.

![SynApps](../assets/scene-actors.png)

Sono organizzati in una struttura ad albero:

![SynApps](../assets/quick-start/designer-first-steps/04.png)


Il primo attore, l'attore **principale** della scena, `stack1` qui è di tipo [**Impilamento**](/synapps/concepts/actor-types/layout-stack.md).
È un attore di impaginazione. Il suo ruolo è quello di disporre, di collocare sull'interfaccia, gli attori che essa conterrà. Nel caso di una pila, gli attori vengono impilati verticalmente per impostazione predefinita.

Aggiungere ora un attore [**Testo**](/synapps/concepts/actor-types/display-text.md) all'impilamento.

### Aggiungere

Per aggiungere un attore, fare clic con il tasto destro del mouse su `stack1`. Appare il menu contestuale per le azioni sugli attori.

> **Nota:** La gestione delle scene si effettua anche tramite un menu contestuale sulle voci dell'albero.

![SynApps](../assets/quick-start/designer-first-steps/05.png)

Scegliere *Aggiungere l'attore...*. Viene visualizzato il pannello di selezione che rappresenta gli attori disponibili.

![SynApps](../assets/quick-start/designer-first-steps/06.png)


Fare clic sull'attore *Testo* nella sezione *Visualizzazione*.

L'attore `testo2` è stato aggiunto all'albero:

![SynApps](../assets/quick-start/designer-first-steps/07.png)

Nell'anteprima, l'attore è impilato sotto `testo1`.

![SynApps](../assets/quick-start/designer-first-steps/08.png)

### Cancellazione

Per eliminare il primo attore, che in questo caso non serve a nulla, si utilizza ancora una volta il menu contestuale dell'attore.

Fare clic con il pulsante destro del mouse sull'attore `text1` e scegliere *Cancella*.

L'attore è scomparso:

![SynApps](../assets/quick-start/designer-first-steps/09.png)

E nell'anteprima:

![SynApps](../assets/quick-start/designer-first-steps/11.png)


### Modifica

Procediamo ora a posizionare il testo al centro della scena. Verrà visualizzato sotto il testo esistente.

Qualora non fosse già selezionato, selezionare l'attore `text2`.

> **Nota:** è possibile selezionare un attore anche facendo clic sulla sua panoramica..

Soffermiamoci sull'ispettore:

![SynApps](../assets/quick-start/designer-first-steps/12.png)

Aprire la sezione *Layout*.

![SynApps](../assets/quick-start/designer-first-steps/13.png)

Questa sezione consente di gestire la disposizione dell'attore rispetto al suo attore padre. A questo punto è possibile modificare l'allineamento dell'attore e scegliere *centrato* in verticale e in orizzontale.

![SynApps](../assets/quick-start/designer-first-steps/14.png)

E nell'anteprima:

![SynApps](../assets/quick-start/designer-first-steps/15.png)

> **Remarque :** Les actions réalisées dans le designer sont *annulables*. <br>![SynApps](../assets/quick-start/designer-first-steps/10.png)<br>Scelta rapida da tastiera **Ctrl+Z** / **Ctrl+Shift+Z**

Diamo un'occhiata alle altre sezioni disponibili nella finestra dell'ispettore dell'attore.

Ora modificheremo il contenuto testuale del nostro attore:

Questa operazione va eseguita nella sezione *Specifico*.

![SynApps](../assets/quick-start/designer-first-steps/16.png)

Come suggerisce il nome, questa sezione varia a seconda del tipo di attore selezionato.

In questo caso è possibile modificare il testo visualizzato dall'attore facendo clic sul pulsante con una penna. Viene visualizzato il pannello di modifica del testo:

![SynApps](../assets/quick-start/designer-first-steps/17.png)

Digitiamo `Hello World' invece di `Text'. Cliccare poi sul pulsante per salvare quanto inserito.

> **Suggerimento** Scelta rapida da tastiera per salvare il testo inserito: **Ctrl+S**

Possiamo chiudere il pannello facendo clic altrove o direttamente sulla croce in alto a destra. La modifica è visibile nell'anteprima.

![SynApps](../assets/quick-start/designer-first-steps/18.png)


## Salvataggio ed esecuzione

Per salvare le modifiche apportate, fare clic sul pulsante dedicato nella barra delle azioni sopra l'anteprima della scena.

> **Suggerimento** Scelta rapida da tastiera per salvare la scena: **Ctrl+S**

Ora, se si esegue il synapp, si può vedere:

![SynApps](../assets/quick-start/designer-first-steps/19.png).

> **Suggerimento** Scelta rapida da tastiera per eseguire il synapp all'nterno di: **Ctrl+R**. Scelta rapida da tastiera per eseguire il synapp nel navigatore: **Ctrl+Shift+R**


## Ancora qualche modifica

### Uso della biblioteca
Cambiare il colore del testo. A tale scopo, prenderemo in esame la sezione *Testo* dell'ispettore e più precisamente il campo *Colore*.

![SynApps](../assets/quick-start/designer-first-steps/20.png).

Questo campo si aspetta un [colore CSS](/script-api/global.html#CssColorString){:target="_blank"} che può essere digitato oppure scelto utilizzando il selettore a disposizione. Possiamo provarne diversi e visualizzare il risultato.

![SynApps](../assets/quick-start/designer-first-steps/26.png).

Utilizzeremo la **libreria** di colori definita nel synapp e coglieremo l'occasione per affrontare il tema del **collegamento**.

La semplicità delle interfacce di editing si basa, tra l'altro, su questo concetto. I campi degli attori possono essere collegati ad altri elementi dell'applicazione, a un altro attore, a un colore, a un testo, a un'immagine e ai dati dell'ULI...

Fare clic sul pulsante a forma di ingranaggio posto a destra del campo *Colore* e scegliere *Collegamento a...*.

![SynApps](../assets/quick-start/designer-first-steps/21.png).

Viene quindi visualizzato il pannello di modifica dei collegamenti.

![SynApps](../assets/quick-start/designer-first-steps/22.png).

Al momento non sono stati definiti collegamenti. Ma se apriamo il menu a tendina, verranno visualizzate le possibili fonti di collegamento. Scegliere *Librerie/Colore*.

L'interfaccia è cambiata:

![SynApps](../assets/quick-start/designer-first-steps/23.png).

Nel campo *Colore* che è apparso, si può scegliere uno dei colori definiti nella libreria::

![SynApps](../assets/quick-start/designer-first-steps/24.png).

Scegliare `themeColor` e cliccare sul pulsante *Collegamento a...* per validare la creazione del link.

![SynApps](../assets/quick-start/designer-first-steps/25.png).

> **Nota:** La [Libreria dei colori](../concepts/colors.md), come tutte le altre librerie è accessibile nella sezione dedicata![SynApps](../assets/libraries.png).

## Prossima tappa
[Pubblicare il synapp nel REDY-PC](./synapp-publish).

---------------------

[◀ Esecuzione](./synapp-run){: .btn } [Pubblicazione ▶](./synapp-publish){: .btn }
