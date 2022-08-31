---
title: "Compositi"
parent: Concetti
---

{% include table_of_content.html %}

# Composito

Raggruppando e programmando gli attori esistenti, Synapp Studio permette di creare nuovi attori. I nuovi attori cosi assemblati, formano quello che viene definito un *composito*.

I compositi sono riutilizzabili e possono essere condivisi tra gli utenti.
Synapp Studio contiene un insieme di compositi che viene continuamente arricchito.

Un composito può essere utilizzato in qualsiasi scena e anche all'interno di un altro composito.

 ![Composites](../assets/composite-actors.png)

## Impostato una volta, utilizzabile ovunque

Come detto, un composito è costituito da 2 o più attori per creare una nuova funzionalità o rappresentazione e può essere utilizzato all'infinito nelle scene. Pertanto, se si apporta una modifica alla definizione di un composito, questa si rifletterà su tutte le sue istanze.

Immaginiamo di dover rappresentare una mappa di sfondo. Su di essa sono sovrapposti una decina di blocchi che illustrano le zone di temperatura. Ognuno di questi è composto da un'icona a forma di termometro e da un valore con la sua unità, collegato a un determinato ULI.
Sarà opportuno creare un unico composito assemblando una volta sola alcuni attori, collegamenti e programmazione.
Successivamente sarà possibile utilizzare il composito come un attore aggiungendolo dieci volte alla nostra scena.


## Scatola nera

Quando si aggiunge un'istanza di composito a una scena, il dettaglio della sua definizione non viene visualizzato nella mappa degli attori. Il suo comportamento sarà identico a quello degli altri attori. È solo nella sua definizione che è possibile visualizzare e modificare la sua struttura. 

## Proprietà specifiche

Un composito può essere configurato con proprietà specifiche, come qualsiasi altro attore. Nella sua definizione, è possibile aggiungere dei parametri aggiuntivi svolgeranno il ruolo di proprietà specifiche..

> 💡 **SUGGERIMENTO**<br>
I valori definiti nel composito serviranno come valori predefiniti per le diverse istanze del composito.

Nella definizione di un composito, le proprietà specifiche sono accessibili tramite collegamento o script.

## Fornitore di dati

In un composito è possibile utilizzare qualsiasi attore, tranne ovviamente se stesso. In particolare, è possibile utilizzare i fornitori di dati per accedere alle variabili di un REDY. Un composito viene visualizzato solo quando i dati da recuperare sono disponibili.

È anche possibile utilizzare fornitori di variabili relative. Si può quindi usare un provider padre nei [[globals]](./project/global-data-sources.md) o ottenerlo dal [data context].(./context.md).

## Creazione di un composito

Accedere alla sezione del progetto dedicata alla gestione dei [Compositi](../assets/composites.png).

Nella parte superiore della sezione si trova l'albero dei compositi. Per crearne uno nuovo, fare clic con il pulsante destro del mouse su una cartella e scegliere un modello di partenza.


> 💡 **CONSIGLIO**<br>
> Assegnare al proprio composito un nome parlante. In questo modo lo si riconoscerà facilmente nell'elenco degli attori. Prossimamente, sarà possibile inserire un logo.
>
> Allo stesso modo, dare al composito una chiave esplicita. Sarà anche più facile identificare l'istanza del composito nelle scene, anche se si conserva la chiave generata automaticamente.


la definizione di un composito è molto simile a quella di una scena.

## Gestione dei compositi

Per gestire i compositi di un progetto si può procedere esattamente come per la gestione delle [scene](./scene.md). È quindi possibile aggiungere/rimuovere cartelle, aggiungere/rimuovere compositi, copiare/incollare, ecc.

# Compositi di evidenza

Di seguito vengono presentati una serie di compositi degni di nota che è possibile copiare e incollare liberamente nelle proprie creazioni.

## Rappresentazione di Bruciatori, Valvole Pompe singole e doppie

Di seguito sono riportati 4 compositi per visualizzare:

- Bruciatore
- Valvola
- Pompa singola
- Doppia pompa

![SynApps]( {{ site.baseurl }}/assets/concepts/composites/ressources.gif)


### Bruciatore

{% include st/composites/burner.md %}

### Valvola

{% include st/composites/valve.md %}

### Pompa semplice

{% include st/composites/simple-pump.md %}

### Pompa doppia

{% include st/composites/dual-pump.md %}

## Planning settimanale

Un esempio di un composito per visualizzare e modificare una risorsa planning settimanale. Le dimensioni delle celle sono configurabili.

*Compatibile con il touchscreen!*

> ✔️ **CONSIGLIO**<br>
> Per impostazione predefinita, le celle sono `1cmx1cm` in modo che un dito possa accedervi. Se si desidera una visualizzazione più
> piccola, scegliere `15px` come larghezza della cella e lasciare `1cm` come altezza.

![SynApps]( {{ site.baseurl }}/assets/concepts/composites/planning-hebdo.gif)


{% include st/composites/planning-hebdo.md %}
