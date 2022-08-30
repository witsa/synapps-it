---
title: "Aggiuntivo"
parent: Concetti
nav_order: 7
---

{% include table_of_content.html %}

# Parametro aggiuntivo

I parametri aggiuntivi sono proprietà come quelle che associate agli attori, ma che è possibile aggiungere anche ad altri oggetti Synapps.

Il vantaggio è che, una volta creata, questa nuova proprietà è visibile nell'inspettore dell'oggetto a cui appartiene.

Gli attori, le scene e i compositi possono ospitare parametri aggiuntivi. È così che si creano i parametri della scena e le proprietà specifiche di un composito.

Un Parametro Aggiuntivo può essere la sede o la fonte di un [collegamento](./binding.md). Può essere utilizzato in uno script. Dà anche origine a [eventi di cambio di valore delle proprietà](./scripts/actor-life-cycle.md#property-value-change-of-actor).

## Parametri comuni

### Chiave
Un aggiuntivo è identificato attraverso la sua chiave, che deve essere unica e specifica all'oggetto al quale appartiene.

### Nome
Nell'ispettore è possibile definire il nome che apparirà davanti alla proprietà creata. Se non viene impostato, la sua chiave verrà utilizzata come nome.

### Descrizione

È possibile descrivere la proprietà aggiuntiva per aiutare a capirne la funzione. La descrizione vene visualizzata al passaggio del mouse sul nome della proprietà.

### Aiuto
Si può definire un testo di aiuto che viene visualizzato sotto la proprietà.

### Vuoto accettato?

Questa opzione consente di indicare se l'aggiuntivo può essere vuoto o meno.

### Sola lettura?

In alcuni casi è richiesto che la proprietà aggiuntiva non sia modificbile. Questa opzione consente di disabilitare la modifica.

### Modifica

Nel caso di proprietà aggiuntive di tipo attore e composito, è possibile specificare il tipo di modifica che il componente aggiuntivo causa nel suo ciclo di vita. Vedere la sezione che spiega le [modifiche]](./scripts/actor-life-cycle.md#changement-de-valeur-de-propriété-dun-acteur)

### Presente nell'URL ?

Nel caso di un parametro di Scena, è possibile stabilire se questo deve apparire nell'URL. Vedi la sezione che spiega i [parametri di una scena](./scene.md#paramètres-de-scène)

## Tipo di aggiuntivo

Esistono diversi tipi di parametri aggiuntivi:

- Testo

Permette di creare una proprietà per l'inserimento di un testo.

- Numero

Permette di creare una proprietà per l'inserimento di un numero.

È possibile anche definire un massimo e un minimo, nonché il passo quando si cambia il valore trascinandolo. È possibile aggiungere un'unità.

- Taglia

Consente di definire una proprietà per inserire una dimensione. Assomiglia alla proprietà *numero*.

È possibile impostare il valore neutro.

Consultare [la sezione che descrive le unità delle taglie](./sizes.md)

- Booleano

Consente di ottenere una proprietà con un pulsante.

- Immagine

Consente definire un parametro per aggiungere un'immagine.

- Colore 

Consente definire un parametro per inserire un colore.

- Icona
- 
Crea una proprietà che permette di ottenere la chiave di un'icona dalla libreria Synapps.

<!-- ![image](https://user-images.githubusercontent.com/35595723/124151000-646ede80-da92-11eb-8003-4235f467aaa1.png) -->

- Data

Fornisce una parametro per inserire una data con una data minima e massima opzionale.

- Selezione semplice **ALPHA**

Nel prossimo futuro sarà possibile selezionare un'opzione da un elenco.

- Selezione multipla **ALPHA**

Nel prossimo futuro sarà possibile effettuare una scelta multipla da un elenco.

- Attore

Permette la scelta della chiave di un attore tra quelle presenti nella scena o nel composito corrente. Un'opzione consente di attivare o meno la possibilità di scegliere l'attore corrente. È possibile filtrare gli attori disponibili in base al loro tipo.

- Scena

Permette la selezione della chiave di una scena tra quelle del synapp. Un'opzione consente di attivare o meno la possibilità di scegliere la scena corrente.

- Composito

Permette la scelta della chiave di un composito tra quelle del synapp. Un'opzione consente di attivare o meno la possibilità di scegliere il composito corrente.

- Percorso variabile

Consente di scegliere il percorso di una variabile REDY. Diverse opzioni consentono di affinare le possibilità visualizzate dall'esploratore di variabili.

### Parametri aggiuntivi complementari

In alcuni tipi di attori,  parametri aggiuntivi possono essere utilizzati per completare le definizioni delle proprietà. Questo è il caso, ad esempio, di attori di contenuto come [Pulsante](./actor-types/input-button.md), dove è possibile completare dei caratteri jolly con parametri aggiuntivi.

I parametri delle scene vengono inoltre aggiunti agli attori dello schermo per impostare la scena prescelta.
