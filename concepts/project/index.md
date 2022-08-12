---
title: "Progetto"
parent: Concetti
has_children: true
nav_order: 1
---

{% include table_of_content.html %}

# Il progetto

Il progetto è l'insieme degli elementi che permettono la realizzazione di un synapp. Il progetto è materializzato da una cartella nel file system. Contiene tutti i file di configurazione del synapp, le definizioni delle scene, dei compositi, delle librerie, delle immagini, ecc.

![Répertoire de projet](../../assets/quick-start/first-project/03.png)

## Creazione di un progetto
Per creare un nuovo progetto, fare clic sul pulsante **Nuovo progetto** nel menu **File**.

Viene visualizzata l'interfaccia di selezione del progetto di base.

È possibile scegliere se creare un progetto dai modelli di Studio o utilizzare un file come modello.

Per saperne di più su [creazione di un progetto](../../quick-start/first-project.md).

Per saperne di più sui [modelli di progetto](./project-model.md).

> ⚠️ **ATTENZIONE**<br>
> **Evitare di duplicare un progetto** per non creare problemi al momento della pubblicazione del synapp e nella gestione delle password degli host. Se lo avete fatto, per ripristinare la situazione, modificate a mano il `Guid' di uno dei due progetti nel file di figurazione, preferibilmente prima di aprirlo con Studio.
>
> Per duplicare correttamente un progetto, è sufficiente esportarlo come modello e creare il nuovo progetto a partire da quest'ultimo.
> 
## Aprire un progetto

Per aprire un progetto fare clic sul pulsante **Apri progetto** nel menu **File** e cercate la cartella che lo contiene.

## Visualizzare la cartella del progetto

Per visualizzare la cartella di progetto aperta, è sufficiente fare clic sul pulsante **Apri cartella di progetto...** nel menu **Progetto**.


# La sezione del progetto

La sezione *Progetto* di Synapps Studio consente di definire gli elementi essenziali per l'esecuzione e la costruzione dell'applicazione.

## Generale

Nella sezione *Generale* della sezione *Progetto* è possibile definire gli elementi essenziali del progetto.

### Nome del progetto
Qui è possibile modificare il nome del progetto.

### Nome ed etichetta del synapp
Nella sezione *Identità del synapp*, si può definire il nome del synapp che apparirà nel REDY, nonché l'*etichetta* che verrà usata per richiamare il synapp nel REDY.

### Numero di versione
È possibile inserire un numero di versione per tenere traccia dell'evoluzione del progetto corrente.

### Lingue del synapp
Nella sezione *Vari*, è possibile definire le lingue che saranno supportate dal proprio synapp.

Esempio: `fr,es,en` per indicare che saranno supportati *francese*, *spagnolo* e *inglese*. Il formato previsto è lo stesso dell'elenco delle lingue disponibili in [List of ISO 639-1 codes](https://en.wikipedia.org/wiki/List_of_ISO_639-1_codes).

### Stile globale del synapp
Nella sezione *Stile globale* è possibile definire il colore di sfondo e il colore di default del testo del synapp.

## Hosts

Nella sottosezione [hosts] (./hosts.md), si possono definire le ULI a cui collegarsi per costruire il proprio synapp.
È anche in questa sezione che si può pubblicare il proprio synapp in una ULI.

## Fornitori di dati

DIn questa sottosezione si possono definire i [fornitori dei dati globali](./global-data-sources.md) che saranno utilizzati dal proprio synapp.


## Icone

È possibile definire le [icone](./icons.md) del proprio synapp nella sottosezione dedicata.

## Inclusione

Nella sottosezione [inclusione](./includes.md) si possono definire i sorgenti `Javascript` e `CSS` che saranno inclusi al caricamento del synapp..

## Leggimi

Questa sottosezione consente di compilare e leggere le informazioni essenziali sul progetto. È la documentazione che è possibile scrivere autonomamente..

> In ogni modello di progetto, il *readme* fornisce gli elementi importanti che lo caratterizzano e spiega come personalizzarlo.

Il *readme* è scritto nel linguaggio `markdown` in un editor incorporato molto facile da usare. [Per ulteriori informazioni, consultare il sito] (https://fr.wikipedia.org/wiki/Markdown)

# Esecuzione del progetto

Dal menu **Esegui** è possibile il synapp in una cartella (`Ctrl+R`).
È anche possibile eseguire il proprio synapp nel browser (`Ctrl+Shift+R`).

## Cambiare l'host

Se il syapp è eseguito in una cartella è possibile cambiare l'host attivo utilizzando il menu che si trova nella fascia blu nella parte bassa dell'interfaccia di Studio

Ad esempio, creando diversi host che puntano allo stesso REDY ma con utenti diversi, si potrà vedere il comportamento del proprio synapp a seconda dei diritti dell'utente selezionato.

## Modifica della lingua di anteprima

Se si è dichiarato che il proprio synapp supporta diverse lingue è è possibile cambiare la lingua utilizzata dal menu che si trova nella fascia blu nella parte bassa dell'interfaccia di Studio.

È inoltre possibile cambiare questa lingua in qualsiasi momento nel *menu di Esegui*.
