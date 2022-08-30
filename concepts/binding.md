---
title: "Collegamento"
parent: Concetti
nav_order: 6
---

{% include table_of_content.html %}

# Collegamenti

Il concetto di collegamento è un concetto importante nella soluzione Synapps. Infatti, grazie ad esso, è possibile stabilire comportamenti, modifiche di proprietà, in modo semplice.
Collegando tra loro le proprietà degli oggetti Synapps, è possibile automatizzare le modifiche, utilizzare le librerie, far corrispondere le dimensioni dei display, ecc.

## Definizione

Un collegamento rappresenta un oggetto che, quando viene attivato, sorveglia il cambiamento di un valore su una **sorgente** e lo registra immediatamente in una proprietà **target** di un attore.

Solo le proprietà degli attori possono essere target di collegamento. Viceversa, molti elementi di Synapps possono essere la fonte in un collegamento:

- La [synapp](./synapp.md)
- La [scena](./scene.md) o il [composito](./composite.md) che ospita l'attore di destinazione
- Un altro [attore](./actor/index.md) o se stesso
- Un elemento della libreria
  - un [colore](./colors.md)
  - un'[immagine](./pictures.md)
  - una [costante](./constants.md)
  - un [testo](./texts.md)
- Un [fonitore di variabili REDY](#il-tipo-di-collegmanto-al-provider-di-variabili)
- L'[host](./project/hosts.md)
- La [sessione](./session.md)
- L'[utente](./user.md)
- Il [display](./user-agent.md)
- 
Esempio: *un collegamento al **colore A** della libreria dei colori definito sulla proprietà **colore di sfondo** di un attore*
![La liaison vers une couleur de la librairie](../assets/concepts/bindings/01.png)

Un collegamento può anche essere impostato in modo da monitorare il target per registrare nella sorgente eventuali cambiamenti.

Esempio: * un legame con scrittura attiva alla proprietà **colore di sfondo** di un attore impostato sulla proprietà **colore di sfondo** di un altro attore e viceversa*.
![La liaison vers une couleur de la librairie](../assets/concepts/bindings/02.png)

## Creare un collegamento

Per creare un collegamento, aprire il menu delle opzioni di un parametro dell'attore e fare clic su *Collegamento a...*. Si aprirà la finestra di definizione del collegamento.

Il collegamento si costruisce definendo prima la fonte e poi le opzioni offerte dalla natura della fonte scelta.

Nell'esempio seguente, nella proprietà *Contenuto* di un attore *Testo* viene creato un collegamento al *nome* del synapp.

![Creazione di un collegamento](../assets/concepts/bindings/01.gif)

In sintesi, il collegamento è definito come segue:

| Target| Parametro del Target | Sorgente | Parametro sorgente |
| ------ | ------------- | ------ | ------------- |
| l'attore *Testo* | *Contenuto* | La synapp | *Nome* |


Ecco un altro esempio, questa volta con un collegamento alla proprietà *colore* di un altro attore:

![Creazione del collegmanto](../assets/concepts/bindings/02.gif)

Osservare il cambiamento del colore dell'attore *Testo 2* al variare del colore dell'attore *Testo 1*.

In sintesi, il vincolo questa volta è definito come segue:

| Target | Parametro del Target | Sorgente | Parametro sorgente |
| ------ | ------------- | ------ | ------------- |
| L'attore *Texte 2* | *colore* | l'attore *Texte 1* | *Colore* |

### Percorso della fonte

In realtà, quando definiamo la fonte di un collegamento, definiamo due cose:
- Con il tipo di fonte, si indica come il collegamento cercherà l'oggetto di partenza. Più avanti scopriremo che lo colloca nel suo contesto di dati.
- quindi, attraverso la scelta del campo sorgente, si indica il percorso che porta al valore da tenere sotto controllo.

Analizziamo più da vicino questo percorso. che è visibile nella finestra di definizione del collegamento nel campo *Percorso*.

Nel secondo esempio, si noti che il percorso è `properties.color` è lo stesso che consente di accedere al valore tramite script.

> 📌 **NOTA**<br>
Se lo si conosce, è possibile definire un percorso che non ha alcuna corrispondenza nell'elenco dei campi disponibili per una determinata sorgente.

### Attivazione della scrittura

Se si vuole che le modifiche apportate dal target vengano scritte nell'origine, è necessario abilitare l'opzione *Scrivere?*.

In questo modo sarà possibile, tra l'altro, scrivere il valore di una variabile REDY attraverso il collegamento *Fornitore variabile*.

Questo è anche utile per creare un uplink verso una sorgente che non accetta un collegamento. <br>Ad esempio, non è possibile creare un collegamento a un parametro di una scena. Al contrario, è possibile creare un collegamento sulla proprietà di un attore della scena e collegarlo a uno dei suoi parametri con la scrittura attivata. Pertanto, quando la proprietà cambia, cambia anche il parametro della scena.

### Sincronizzazione della fonte

Per impostazione predefinita, un collegamento attivo leggerà periodicamente il valore dall'origine per riportarlo sulla destinazione.

Si può definire una modalità diversa: disabilitando la sincronizzazione periodica, si otterrà una sola scrittura, la prima..

Questa soluzione è molto pratica quando ci si collega a un valore che non cambierà o, al contrario, a un valore che cambia ma di cui si vuole mantenere il valore iniziale.

### Errore nel collegamento

In alcuni casi, è possibile che al momento della creazione del collegamento la fonte definita non esista o non possa essere trovata. In questo caso il collegamento non andrà a buon fine e il valore rimarrà alla sua definizione iniziale.

> 📌 **NOTA**<br>
Attualmente non esiste nessuna segnalazione in Studio che indichi questo tipo di errore.

## Menu delle opzioni di un collegamento

Una volta definito un collegamento su una proprietà, il menu delle opzioni si arricchisce di possibilità.

### Modificare il link

È possibile tornare alla definizione di un collegamento in qualsiasi momento.

### Cancellare il link

DNel menu delle opzioni della proprietà dell' attore, fare clic su *Calcellare il link* per eliminare il collegamento esistente.

Si può anche scegliere l'opzione *Nessun collegamento* dall'elenco *Tipi di fonte* nella modifica del collegamento..

### Copiare/incollare un link

Un'opzione molto utile: è possibile copiare un link e incollarlo altrove. La definizione si trova negli appunti, per cui è possibile incollarla ovunque.

### Mostra/Nascondi valore iniziale

Quando si imposta un collegamento su una proprietà, il valore precedentemente immesso viene mantenuto. Serve per inizializzare la proprietà.

L'opzione *Mostra valore iniziale* permette di visualizzare e modificare questo valore anche dopo la creazione del collegamenti

Per non visualizzar il valore, fare clic su *Nascondi valore iniziale* nel menu delle opzioni.

## Script di trasformazione

Quando il valore sorgente viene passato alla destinazione, è possibile associarvi uno script di trasformazione. Allo stesso modo, è possibile eseguire uno script di trasformazione sul valore di destinazione quando viene attivata la scrittura del valore di origine. Si veda la sezione [ciclo di vita dell'attore] (./scripts/actor-life-cycle.md#transformations-de-liaison).

## Il collegamento al tipo di fonte *Fornitore variabile*

Questo tipo di origine consente di collegare una proprietà a un campo di una variabile REDY tramite un [fornitore di variabili](./actor-types/redy-wos-variable-source.md).

Si veda un'illustrazione [qui](../quick-start/display-redy-data.md)

Come nel caso di un attore [fornitore variabile relativa](./actor-types/redy-wos-relative-variable-source.md), è possibile recuperare il campo di una sottovariabile WOS da una variabile o risorsa definita in un fornitore padre

### Chiave del padre

Questo campo viene utilizzato per indicare il fornitore di servizi genitore. È il fornitore che eseguirà le richieste di lettura e scrittura. Se non viene fornito nulla, il padre verrà ricercato tra le informazioni del contesto dei dati.

### Percorso relativo

Questo campo consente di indicare il percorso relativo della variabile WOS di interesse rapportata alla variabile padre. Può essere lasciato vuoto, nel qual caso la variabile WOS sarà quella definita dal genitore.

### Campo

Questo parametro consente di indicare quale campo sarà l'origine del collegamento. Lasciare vuoto se si desidera che l'origine sia la variabile stessa.

### Modalità di recupero

Indicare se si desidera che i dati vengano recuperati ogni volta che il fornitore padre viene aggiornato o solo la prima volta.

## Collegamento al tipo di sorgente *Contesto*

Questo collegamento non definisce effettivamente come trovare la fonte. Tenterà di farlo solo con ciò che trova nel suo contesto di dati.

Per maggiori dettagli, vedere la sezione [Contesto dei dati](./data-context) pour plus de détails.
