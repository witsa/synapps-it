---
title: "REDY | Fornitore di variabili"
parent: "Elenco attori"
grand_parent: Concetti
---

{% include links_actor.md apiClass="REDY.Actor.WosVariableSource" %}

# Fornitore di variabili

L'attore Fornitore di variabili permette il collegamento con una variabile *WOS* in un REDY. Il fornitore si occupa di recuperare il valore della variabile definita dalla proprietà *Percorso* e lo inserisce nel campo informativo *Dati*. In alternativa, è possibile indicare un *Campo* specifico.

Inoltre, l'attore consente di definire il modo in cui si recupera e si aggiorna il valore della variabile e di attivare o meno la scrittura per permettere la modifica del valore nel REDY.

Il dato recuperato è disponibile per i collegamenti o per gli script..

L'attore serve come fornitore di base per qualsiasi [Fornitore di variabili relative](./redy-wos-relative-variable-source.md) o per i collegamenti di tipo [Fornitore di variabili](../binding.md#variable-provider) che puntano a lui..

{% include table_of_content.html %}

# Proprietà

## Percorso

Questa proprietà indica il *percorso* verso la variabile da interrogare. Si tratta di un percorso secondo il metodo REDY, ad esempio `:easy.RESS.R00001` o anche `:easy.RESS.R00001.Output`.

L'esploratore della parametrizzazione REDY aiuta nell'inserimento del percorso.

![SynApps](../../assets/concepts/actor/redy-variable-source/sample-01.gif)


## Campo delle Variabili REDY

Per impostazione predefinita, l'intera variabile viene recuperata e inserita nel campo *Data*. Se si desidera recuperare una parte della variabile, è possibile specificare il nome del campo da utilizzare scegliendo tra le seguenti possibilità:
- **Label** L'etichetta della variabile REDY. Ad esempio: `R00003` o `RunCount`.
- **Name** La descrisione della variabile REDY. Ad esempio: `Contatore 1`.
- **Valore** Il valore della variabile. Ad esempio: `true`, `"Testo"` o `23`, a seconda del tipo di variabile.
- **Stato** Lo stato se la variabile è una risorsa. Questo sarà il testo dello stato come definito in REDY. Ad esempio: ``ON'', ``Acceso''..
- **Percorso** L'intero percorso della variabile REDY. Ad esempio: `:easy.RESS.R00001` o anche `:easy.RESS.R00001.Output`.
- **ID** L'ID interno della variabile REDY.
- **Data** La data dell'ultimo aggiornamento della variabile REDY.
- **ID classe** Codice identificativo della classe a cui appartiene la variabile REDY.
- **URL dell'icona** L'URL dell'icona della variabile REDY. Utilizzabile direttamente, ad esempio, in un collegamento a un [Attore immagine](./display-image.md).
- **Lettura?** Indica se la variabile è accessibile dall'utente corrente in modalità lettura. Considerare il gruppo e il livello dell'utente.
- **Scrittura?** Indica se la variabile è modificabile dall'utente corrente. Tiene conto dei gruppi e del livello dell'utente.
- **Numero di figli** Il numero di figli presenti nella variabile REDY.
- **Figli** L'elenco dei figli della variabile REDY.

Se si desidera scrivere in questo campo, scegliere *Valore*. In questo modo, facendo una connessione con la scrittura abilitata ai dati dell'attore, si potrà scrivere sulla variabile REDY e inviare questo valore automaticamente se la proprietà *Scrittura su cambiamento* è attivata. Altrimenti, tramite script..

## Modalità

Questa proprietà consente di definire il comportamento dell'attore nella scena o quando viene modificato il *percorso* o il *campo* della variabile ricercata.

- **Automatico** Se tutte le condizioni sono soddisfatte, l'attore recupera automaticamente la variabile.
- **Manuale** L'attore attende un cambiamento di *modalità* o una richiesta da parte di uno script per recuperare la variabile.
- **Relativo** Il comportamento dell'attore sarà quello della modalità automatica, a partire dal momento in cui ha un collegamento di tipo [Fornitore di variabile relativa](./redy-wos-relative-variable-source.md) o [fornitore di variabile] (../binding.md#variable-provider) che puntano ad esso.

In ogni caso, questa modalità è completamente indipendente da quella di aggiornamento dell'attore.

## Auto rafraîchissement?

Cette propriété active/désactive l'auto rafraîchissement de la variable ciblée.

## Intervallo di aggiornamento

Questa proprietà definisce il ritmo di aggiornamento (in secondi) della variabile target quando è attivato l'aggiornamento automatico.


> ✔️ **CONSIGLIO**<br>
> Evitare di impostare tempi di aggiornamento troppo brevi. Al di sotto dei 10 secondi, occorre interrogarsi sulla pertinenza di una scelta di questo tipo..

## Écriture au changement?

Questa proprietà abilita/disabilita la modifica del valore di una variabile nel REDY se il *dato* viene modificato attraverso il collegamento o lo scripting.

# Eventi

## `onRequestDone`

L'évènement `onRequestDone` est déclenché à chaque fois que l'acteur a réaliser une requête pour obtenir ou rafraîchir la variable et le champ souhaité.

> [⚡ `onRequestDone`]({{ site.baseurl }}/script-api/REDY.Actor.WosVariableSource.html#event:onRequestDone){:target="_blank"}

## `onWriteDone`

L'evento `onRequestDone` viene attivato ogni volta che l'attore ha fatto una richiesta per ottenere o aggiornare la variabile e il campo desiderati.

> [⚡ `onWriteDone`]({{ site.baseurl }}/script-api/REDY.Actor.WosVariableSource.html#event:onWriteDone){:target="_blank"}

# Informazioni

## Dati

Questo campo contiene la variabile o il campo variabile designato dall'attore.

## Interrogazione in corso?

Questa informazione consente di sapere se l'attore sta eseguendo una query.

> 💡 **CONSIGLIO**<br>
Per poter verificare l'esecuzione di un'interrogazione, legare il campo Visibile? di un attore a questo valore.

## Prima interrogazione eseguita?

Questo dato sarà vero dopo l'esecuzione di una prima query.

# Uso

I fornitori possono essere creati nelle scene o nei compositi. Si possono anche creare globalmente nella sottosezione [Progetto/Fornitori dati](../project/variable-source.md) per renderli disponibili a tutto il synapp.


> ✔️ **CONSIGLIO**<br>
> Cercate di mutualizzare i fornitori variabili nelle scene e nei compositi. Ricordare per ogni fornitore di variabili vengono effettuate delle richieste di dati che potrebbero generare un traffico che potrebbe rivelarsi importante per il dispositivo su cui è in esecuzione la synapp. Questo aspetto è particolarmente sensibile per i dispositivi mobili come smartphone e tablet.
