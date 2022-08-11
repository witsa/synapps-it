---
title: Comandare una risorsa
parent: Guida introduttiva
nav_order: 7
---

[◀ Visualizzazione di uno stato](./display-redy-data.md){: .btn } [Per approfondire ▶](./and-more){: .btn }

------

{% include table_of_content.html %}


# Comandare una risorsa

Si è visto in precedenza come visualizzare lo stato di una risorsa con una connessione di tipo *Fornitore di variabili*. È possibile utilizzare il medesimo meccanismo, abilitando la scrittura del campo appropriato della risorsa.
Nella maggior parte dei casi però, quando si deve eseguire un comando, sarà più semplice ed immediato usare il *Riflesso* della risorsa.

## Creazione di un riflesso

Per poter utilizzare il riflesso di una risorsa è necessario che questo sia attivato nella parametrizzazione del REDY. Come prima cosa è andiamo a definire il riflesso della risorsa consegna creata nella durante la tappa precedente.

Andare nei parametri della risorsa, scheda Identità. Definiamo in riflesso della risorsa di tipo *Riflesso Analogico*. Questa operazione permette di rendere la risorsa disponibile come un oggetto con proprietà conosciute.
Il riflesso è ora disponibile per la comunicazione con Synapps e più in generale con le API del REDY.

> Non dimenticare di rendere il riflesso comandabile.

![Reflet](../assets/quick-start/command-redy/03.gif)

> 📌 **NOTA**<br>
Tutte le risorse hanno uno o più tipi di riflessione possibili. Come minimo è disponibile il riflesso 'stato', che consente di visualizzare lo stato della risorsa. Gli altri tipi di strumenti sono più complessi e specifici al tipo di risorsa (riflesso analogico, riflesso digitale, valvola, pompa, ...).


## Attore Dettaglio del riflesso

In Studio, aprire la schena *Accueil*.

- Cancella re l'attore testo con il collegamanto al fornitore di dati creato in precedenza.
- Aggiungere l'attore **Dettagli del riflesso** disponibile nella sessione REDY dell'elenco degli attori.

![Reflet](../assets/quick-start/command-redy/04.png)

Il nuovo attore è visibile nella preview:

![Reflet](../assets/quick-start/command-redy/05.png)

L'attore appena creato permette di visualizzare un riflesso.

Procediamo ora ad assegnare all'attore creato il riflesso appena definito sull risorsa di tipo consegnaa attraverso il campo *Riflesso* presente nella sessione *Specifico* dell'attore:

![Reflet](../assets/quick-start/command-redy/06.gif)

> L'attore si occuperà ora di visualizzare e modificare lo stato della risorsa (per impostazione predefinita ogni 30 secondi)..

Per vedere come configurare questo attore [clicca qui](../concepts/actor-types/redy-reflect-details.md).

Da notare che vengono mostrati i limiti dei valori della risorsa e la sua unità di misura.

## Eseguire un comando

Dopo aver salvato la scena, eseguire la synapp. Il valore può essere modificato digitando direttamente il campo di immissione o utilizzando il cursore che appare a destra.

![Reflet](../assets/quick-start/command-redy/07.gif)


In ogni caso, appariranno dei pulsanti di convalida.

> Finché è in corso una modifica, lo stato della risorsa non viene aggiornato.

Se si fa clic su *Annulla*, lo stato torna al valore iniziale, confermando il comando viene inviato.

![Reflet](../assets/quick-start/command-redy/08.gif)


> 📌 **NOTA**<br>
L'attore dispone di altre modalità di controllo: una modalità automatica e una modalità manuale.

---------
[◀ Visualizzazione di uno stato](./display-redy-data.md){: .btn } [Per approfondire ▶](./and-more){: .btn }
