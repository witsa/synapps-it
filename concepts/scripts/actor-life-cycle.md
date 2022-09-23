---
title: "Ciclo di vita di un attore"
parent: Scripts
grand_parent: Concetti
---

{% include table_of_content.html %}

# Ciclo di vita di un attore

Tutti gli attori hanno un ciclo di vita in cui vengono visualizzati e poi eliminati da una scena (questo vale anche per un composito).

In ogni fase del ciclo di vita, l'attore subisce trasformazioni che talvolta si traducono in eventi. Questi forniscono l'opportunità di eseguire azioni prestabilite mediante l'uso di script `Javascript`.

Per sapere quando e come intervenire al momento giusto su un attore, è importante capire il suo ciclo di vita in una scena/composizione.

# Visualizzazione di una scena o di un composito

Quando una scena o un composito viene visualizzato, il *Runtime* ne interpreta le caratteristiche a partire dall'attore principale che contiene la struttura degli attori che compongono la scena o il composito. Questo attore contiene anche tutte le definizioni degli script.

Il *Runtime* attraverserà l'albero degli attori partendo dall'attore principale. Si occuperà quindi di ogni figlio, di ogni figlio di un attore figlio, ecc.

La visualizzazione della struttura ad albero avviene in 3 fasi:

- Inizializzazione
- La post-inizializzazione
- il primo rendering.

Ogni passaggio ha un ruolo particolare durante il quale vengono attivati gli eventi.

## Inizializzazione

Durante la fase di inizializzazione, la struttura ad albero viene percorsa, dall'alto verso il basso, in modo da identificare gli attori che la compongono.

![SynApps](../../assets/concepts/life-cycle//init.gif)

In questa fase, ogni attore inizializza le sue proprietà, valorizza le proprietà definite nei suoi parametri, crea eventuali proprietà aggiuntive e attribuisce loro un valore.

A questo punto viene generato un evento: [`onInit`]({{ site.baseurl }}/script-api/Actor.BaseActor.html#event:onInit){:target="_blank"}.

In questo momento, potrebbe succedere che non tutti gli attori definiti nella scena o nel composito siano presenti o disponibili.
I [collegamenti](../binding.md) non sono ancora stati completati.

> ✔️ **CONSIGLIO**<br>
> Si tratta quindi di una fase preferenziale per completare l'inizializzazione dell'attore. Ad esempio, la modifica dei valori delle proprietà tramite script. Infatti, non esiste il rischio di perdere prestazioni a causa dell'esecuzione dei collegamenti e delle loro possibili implicazioni, in quanto non sono ancora operativi.

> Questo è anche il momento migliore per definire la logica operativa da collegare all'attore o alla scena/composito.

Per contro, non è il momento giusto per cercare di accedere ad altri attori, poiché questi non sono ancora stati tutti creati.

Non è nemmeno il momento di agire sull'elemento DOM corrispondente all'attore: non è ancora stato creato!

## Post-inizializzazione

Una volta inizializzato l'intero albero, il *Runtime* eseguirà la fase di post-inizializzazione, questa volta risalendo l'albero.

![SynApps](../../assets/concepts/life-cycle//post-init.gif)

In questa fase, l'attore inserisce l'elemento DOM nel flusso HTML, crea i suoi collegamenti, determina le fonti di questi collegamenti e li esegue.

Viene quindi generato un evento: [`onPostInit`]({{ site.baseurl }}/script-api/Actor.BaseActor.html#event:onPostInit){:target="_blank"}.

> ✔️ **CONSIGLIO**<br>
> Questo è il momento giusto per agire nell'elemento DOM. Ma attenzione, lo stile CSS dell'attore non è ancora definito, né lo sono le sue classi CSS. Non è il momento di agire su questi elementi.

Tutti gli attori sono presenti e disponibili, ma alcuni non sono ancora post-inizializzati.

## Primo rendering

Dopo che l'attore principale è stato post-inizializzato, il *Runtime* eseguirà la prima fase di rendering.

Questa operazione consiste nello ripercorrere la struttura ad albero degli attori, verso il basso

![SynApps](../../assets/concepts/life-cycle//first-render.gif)

Sono previste diverse azioni:

Ogni attore ha un elemento DOM corrispondente nel flusso HTML. Le classi CSS sono definite in base al tipo di attore e allo [stile dell'attore](../actor-style.md) che utilizza. Una [classe unica]({{ site.baseurl }}/script-api/Actor.BaseActor.html#uniqClass){:target="_blank"} è definita anche in base alla chiave e alla posizione dell'attore. È molto utile per identificare l'attore nel DOM. Infine, vengono aggiunte le classi definite nella proprietà *Classe* dell'attore.

Lo stile CSS dell'elemento viene compilato grazie alle proprietà dell'attore e allo [Stile dell'attore](../actor-style.md) che utilizza.
È in questa fase che lo stile CSS viene costruito e inserito nell'elemento DOM..

Viene generato l'evento [`onCssStyling`]({{ site.baseurl }}/script-api/Actor.BaseActor.html#event:onCssStyling){:target="_blank"}.

> ✔️ **CONSIGLIO**<br>
> Questo è il momento di modificare lo stile CSS dell'elemento DOM o di aggiungervi classi CSS tramite script.

Successivamente, viene eseguito un primo calcolo della sagoma sull'attore. Alcuni attori necessitano di questo passaggio per essere visualizzati correttamente, come ad esempio la [Box di visualizzazione](../actor-types/layout-view-box.md).

Infine, viene generato l'evento [`onRender`]({{ site.baseurl }}/script-api/Actor.BaseActor.html#event:onRender){:target="_blank"}. Nel contesto dell'evento, il campo `isFirstRender` è vero. Questo perché l'evento viene attivato ogni volta che l'attore passa attraverso la fase di rendering, quindi è interessante sapere se si tratta del primo rendering o meno.


> ✔️ **CONSIGLIO**<br>
> Questo evento è il momento giusto per agire sull'elemento DOM o al suo interno.


## RIASSUNTO

<style>
.table-wrapper td, .table-wrapper th {
  font-size: 0.8em !important;
  padding: 0.4em;
  min-width: auto;
}

}
</style>

| Phase | Description | Parcourt | Évènements | Liaisons | Présence du DOM | Style et Classes CSS | Gabarit calculé |
|:----:|:-----------|:-------:|:----------------------|:--------:|:--------:|:--------:|:-----------------:|
| Initialisation | Création des acteurs et Initialisation des propriétés et additionnelles | Descendant | `onInit` | | | | |
| Post-initialisation | Placement de l'élément DOM dans le flux HTML et création des liaisons | Montant | `onPostInit` | Création | Création | | |
| Premier rendu | Création des classes CSS, du style CSS et du gabarit | Descendant | `onCssStyling`<br>`onRender(isFirstRender=true)` | Oui<br>Oui | Oui<br>Oui | Création<br>Oui | Non<br>Oui |


# Aggiunta dinamica di un attore
Quando un attore viene aggiunto dopo la visualizzazione di una scena o di un composito, tutto si svolge come se fosse un attore principale. Il rendering di questo attore e dei suoi figli passa attraverso le stesse fasi:
- Inizializzazione
- Post-inizializzazione
- Primo rendering

Una volta che l'attore è stato visualizzato, la struttura ad albero subirà una successione di cambiamenti di dimensioni. Quindi ci si aspetta che l'evento `onComputeLayout` venga eseguito su gran parte dell'ascendenza dell'attore aggiunto.

> ✔️ **CONSIGLIO**<br>
> A causa di questo fenomeno di ricalcolo delle taglie dovuto all'inserimento di un attore in modo dinamico, nel caso di aggiunte multiple, è necessario tenere conto di questo tempo e ridurlo al minimo (aggiunta in un canvas, dimensioni fisse del contenitore, ritardo tra ogni aggiunta, aggiunta di attori in una volta sola).

# Eliminazione di un attore

Quando un attore viene cancellato, ad esempio quando si cambia una scena, i collegamenti vengono rimossi e anche l'elemento DOM viene rimosso dal flusso HTML. L'evento [`onDestroy`]({{ site.baseurl }}/script-api/Actor.BaseActor.html#event:onDestroy){:target="_blank"} viene generato.

> ✔️ **CONSEIL**<br>
> Questo è un buon momento per rimuovere gli eventi sull'elemento DOM che sono stati aggiunti manualmente.

![SynApps](../../assets/concepts/life-cycle/destroy.gif)


È importante notare che l'eliminazione di un albero di attori viene eseguita dal basso verso l'alto.

| Fase | Descrizione | Percorso guidato | Eventi | Collegamenti | Presenza di DOM | Classi di stile e CSS | Modello calcolato |
|:----:|:-----------|:-------:|:----------------------|:--------:|:--------:|:--------:|:-----------------:|
| Eliminazione | Eliminazionee |Eliminazione di attori e disattivazione di collegamenti | Importo | `onDestroy` | Sì | Sì | Sì | Sì | Sì |


# Variazione del valore della proprietà di un attore

Quando il valore della proprietà di un attore cambia o viene aggiunto, vengono attivati due eventi:

 - `onValueChanged` che viene attivato per una determinata proprietà dell'attore. Il nuovo `newValue` e il vecchio `oldValue` sono presenti nel contesto dell'evento.
 - L'evento `onPropertyChanged` viene attivato per qualsiasi proprietà o componente aggiuntivo dell'attore. Oltre ai valori vecchi e nuovi, i campi `name` e `propertyPath` sono presenti nel contesto per identificare la proprietà o il complemento che è cambiato.

Prima che questi due eventi vengano generati, una variazione di valore può innescare quello che viene definito una modifica.
Sono possibili 4 modifiche:
- Nessuna modifica: in questo caso non succede nulla. Questa è la modifica predefinita per i componenti aggiuntivi.
- **Stile CSS**: in questo caso, lo stile CSS dell'elemento DOM viene ricalcolato. L'evento [`onCssStyling`]({{ site.baseurl }}/script-api/Actor.BaseActor.html#event:onCssStyling){:target="_blank"} viene nuovamente attivato.
- **Rendering**: in questo caso, viene eseguito un nuovo rendering globale. Gli eventi [`onCssStyling`]({{ site.baseurl }}/script-api/Actor.BaseActor.html#event:onCssStyling){:target="_blank"}, [`onComputeLayout`]({{ site.baseurl }}/script-api/Actor. BaseActor.html#event:onComputeLayout){:target="_blank"} e [`onRender`]({{ site.baseurl }}/script-api/Actor.BaseActor.html#event:onRender){:target="_blank"} vengono generati.
- **Gabarit** : in quest'ultimo caso, viene ricalcolata l'intera sagoma della struttura di attori. Questo causerà l'esecuzione di una serie di eventi [`onComputeLayout`]({{ site.baseurl }}/script-api/Actor.BaseActor.html#event:onComputeLayout){:target="_blank"}.

Le proprietà specifiche di un attore prevedono ciascuna un proprio tipo di modifica. Spetta a voi definire la modifica che comporta la variazione di valore di una proprietà aggiuntiva.

# Transformations de liaison
È possibile intervenire sul valore che verrà scritto nella proprietà target di un [collegameto](../binding.md). L'evento [`onReadTransform`]({{ site.baseurl }}/script-api/Actor.BaseActor.html#event:additionals/[additionalName]/binding/onReadTransform){:target="_blank"} viene generato quando il valore sorgente di un vincolo è letto perché è cambiato o la sorgente è cambiata. Questo valore viene passato nel campo `value` del contesto dell'evento e, per impostazione predefinita, viene restituito direttamente dall'evento. È possibile trasformare questo valore per scrivere qualcos'altro nella proprietà di destinazione.

> ✔️ **CONSIGLIO**<br>
> Molto utile, ad esempio, per cambiare il tipo di valore: da un valore booleano a un colore.

Allo stesso modo, se la scrittura è abilitata sul collegamento, una modifica del valore di destinazione attiverà la scrittura sul valore di origine. L'evento [`onWriteTransform`]({{ site.baseurl }}/script-api/Actor.BaseActor.html#event:additionals/[additionalName]/binding/onWriteTransform){:target="_blank"} iene generato e consente di intervenire sul valore trasmesso.

>⚠️ **ATTENZIONE**<br>
> Se si esegue una trasformazione in lettura su un collegamento abilitato alla scrittura, assicurarsi di eseguire la trasformazione inversa. In caso contrario, l'interfaccia si troverebbe in un ciclo infinito in cui la scrittura annulla ciò che la lettura ha fatto.
