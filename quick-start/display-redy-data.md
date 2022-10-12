---
title: Visualizzare uno stato
parent: Guida introduttiva
nav_order: 6
---

[◀ Pubblicazione](./synapp-publish){: .btn } [Comandare una risorsa ▶](./command-redy.md){: .btn }

------------------

{% include table_of_content.html %}


# Visualizzazione dello stato di una risorsa

Nei progetti synapp abbiamo la necessità di visualizzare dati che appartengono a risorse e variabili definite nella parametrizzazione del REDY.

Di seguito è illustrato uno dei metodi per **ottenere e visualizzare lo stato di una risorsa**.  Tale metodo utilizza il collegamento di tipo *Fornitore di variabili*.

> 📌 **NOTA**<br>
Esistono altri modi per ottenere lo stato di una risorsa. Questi prevedono l'utilizzo di [**attori fornitori di dati**](../concepts/actor-types/redy-wos-variable-source.md). I dettagli sono disponibili nella sezione Concetti.

## Preparazione della risorsa

A titolo di esempio procediamo alla creazione di una risorsa di tipo **consegna analogica**. Aprire la parametrizzazione del REDY per la creazione della risorsa.

![Ressource](../assets/quick-start/display-redy-data/01.png)

Configurare la risorsa come in figura:

![Ressource](../assets/quick-start/display-redy-data/02.png)

- Descrizione: `Setpoint di temperatura`
- Numero di decimali: `0`
- Valori limite: tra `20` e `30`
- Unità personalizzate: `°C`


## Collegamento al *Fornitore di variabili*

Passare in Studio, nella progettazione della scena *Accueil*.

Creare un collegamento di tipo *Fornitore di variabili* per alimentare la proprietà *Contenuto* presente nella sezione *Specifico* dell'attore `text1`.

![Ressource](../assets/quick-start/display-redy-data/08.gif)

Il collegamento consente di legare i dati che ci interessano a un elemento synapp che funge da intermediario: *un fornitore di dati*.
Si tratta di un tipo speciale di attore: non viene visualizzato. Il suo scopo è fornire dati agli altri attori.

In ogni progetto è già presente un fornitore: il fornitore `global resources`. Lo vedremo più da vicino qui di seguito.

Nel frattempo selezionalo nel campo *Chiave padre*.

![Ressource](../assets/quick-start/display-redy-data/09.gif)

Nel campo **Cammino relativo** indicare quale risorsa deve andare a cercare nel REDY.

![Ressource](../assets/quick-start/display-redy-data/10.gif)

Si può notare che il percorso inserito è relativo al percorso definito in `resources`.

In realtà, stiamo semplicemente dicendo al fornitore di dati `resources` che, oltre alla variabile `:easy.RESS`, deve recuperare anche la variabile `:easy.RESS.R00001`.

In realtà, è lo stato della risorsa che ci interessa. È necessario precisarlo:

![Ressource](../assets/quick-start/display-redy-data/11.gif)


Non resta che convalidare l'impostazione per vedere il risultato direttamente nell'anteprima.

![Ressource](../assets/quick-start/display-redy-data/12.gif)

## Fornitore globale

Vediamo ora il fornitore globale `resources`. Passare alla sottosezione *Progetto/Fornitore dati*.

![Ressource](../assets/quick-start/display-redy-data/13.gif)

Qui è possibile gestire i fornitori di dati per l'intera synapp. Il fornitore globale `resources' si trova nell'arborescenza' degli attori.

Si noti che è impostato per aggiornare i dati richiesti ogni *60 secondi*.

> 📌 **NOTA**<br>La modalità di recupero dei dati è *relativa*, il che significa che finché nessuno fa richiesta di dati, il programma non recupera né aggiorna nulla.

Per saperne di più sui fornitori di dati globali, consultare la sezione [**Fornitori di dati**](../concepts/project/global-data-sources.md).

È possibile creare fornitori di dati direttamente in una scena. In questo contesto possono essere customizzati, le loro proprietà possono essere collegate e vi si può accedere tramite script, in modo da avere un controllo totale sul loro utilizzo.

Per ulteriori informazioni sui fornitori di dati globali, consultare la sezione [**Fornitori di dati**].(../concepts/actor-types/redy-wos-variable-source.md).

Molti altri campi sono accessibili tramite collegamento (il valore, il nome, ...). Per ulteriori informazioni, consultare la sezione [**Fornitori di variabili**](../concepts/actor-types/redy-wos-variable-source.md#champ-de-variable-redy).



# Prossima tappa
ora vediamo come [comandare una risorsa del REDY](./command-redy.md).

---------------------

[◀ Pubblicazione](./synapp-publish){: .btn } [Comandare una risorsa ▶](./command-redy.md){: .btn }
