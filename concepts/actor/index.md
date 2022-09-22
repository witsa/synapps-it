---
title: "L'attore"
parent: Concetti
has_children: true
nav_order: 4
---

> 🚧 n progress...

![SynApps](../../assets/under-progress.gif)

{% include table_of_content.html %}

# L'Attore

## Definizione

L'attore è l'elemento fondamentale dell'interfaccia. I numerosi tipi di attore e le loro caratteristiche permettono al realizzazione di qualsiasi tipo di interfaccia, dai moduli ai dashboard.

Gli attori sono organizzati in una struttura ad albero e vanno a caratterizzare quella che è definita come [scena](../scena.md).

![SynApps](../../assets/concepts/actor/01.png)

![SynApps](../../assets/concepts/actor/02.png)

## Chiave dell'attore

Un attore si identifica attraverso la sua Chiave. Si tratta di una stringa che deve essere unica nella scena o nel composito che contiene l'attore.

È possibile modificare questa chiave tramite Ispettore degli attori.

### Caratteri consentiti
 - Sono ammessi tutti i caratteri alfanumerici.
 - Tra i caratteri speciali è ammesso solo il trattino `-`.

> ✔️ **CONSIGLIO**<br>
Si consiglia di utilizzare la chiave degli attori per classificarli e descrivere al meglio il loro ruolo nella scena o nel composito.

### Categorie

Nell'ispettore, le proprietà sono organizzate per categorie:

- [**Specifico**](../actor-types/index.md)

Sono le proprietà specifiche del tipo di attore. Per i dettagli andare alla pagina [Tipi di attore] (../actor-types/index.md).

## Tipologia

Gli attori sono raggruppati secondo diverse tipologie in base alle caratteristiche che hanno in comune.

- vedere [Elenco attori](../actor-types/)

## Proprietà

Gli attori possiedono una serie di proprietà comuni. Inoltre ogni attore presenta delle proprietà specifiche alla categoria a cui appartiene.

Le proprietà caratterizzano lo stato dell'attore. Ne controllano l'aspetto e il comportamento.

Ogni proprietà ha un valore predefinito che è definito dallo [stile dell'attore](../actor-style.md).

Lo strumento *Ispettore delle proprietà* è la parte del *designer* che consente di impostare, programmare e collegare le proprietà di un attore.

![SynApps](../../assets/concepts/actor/03.png)

- [**Aspetto**](./category-aspect.md)

Proprietà relative all'aspetto dell'attore, come il colore di sfondo o la visibilità.

- [**Testo**](./category-text.md)

Proprietà relative al testo che sarà contenuto nell'attore o nei suoi figli. Alcune proprietà, come la dimensione o il colore dei caratteri, vengono trasmesse agli attori figli per *ereditarietà*.

-  [**Layout**](./category-disposition.md)

Proprietà che definiscono la posizione dell'attore rispetto all'attore che lo contiene. La natura di queste proprietà dipende dal tipo di disposizione a cui appartiene il genitore.

- [**Taglie**](./category-size.md)

Proprietà relative alle dimensioni dell'attore.

- [**Spazi**](./category-space.md)

Le proprietà relative alla distanza tra gli attori e gli angoli della scena..

- [**Bordi**](./category-border.md)

Le proprietà relative ai bordi dell'attore e all'arrotondamento degli angoli.

- [**Effetti**](./category-effect.md)

Proprietà relative alle trasformazioni geometriche (scala, traslazione, rotazione) o alle ombreggiature o alla visualizzazione dei suggerimenti.

### Valori ereditati

Alcune proprietà possono ereditare il loro valore dalla proprietà di un genitore dell'attore. È il caso, ad esempio, della dimensione dei caratteri. È quindi possibile definire i valori di queste proprietà una volta per tutte all'inizio dell'albero degli attori, in modo che tutti i figli possano beneficiarne.

## Eventi e ciclo di vita

Un attore genera degli eventi durante il suo intero ciclo di vita: dalla sua inizializzazione alla sua distruzione e inoltre dispone anche di eventi relativi al mouse, come il clic, il passaggio del mouse e così via. Infine, alcuni attori hanno eventi specifici relativi al loro modo di funzionare.
Tutti questi eventi possono essere intercettati ed utilizzati all'interno di script..

- Per saperne di più sul [ciclo di vita dell'attore](./actor-life-cycle)
-  Per saperne di più sugli [Script](../scripts/)

## Proprietà aggiuntive

È possibile definire proprietà aggiuntive per un attore. Una categoria dell'ispettore è dedicata alla loro gestione..

![SynApps](../../assets/concepts/actor/04.png)

Tipi di proprietà disponibili:

![SynApps](../../assets/concepts/actor/05.png)

> 🚧 in progress...


Ogni proprietà aggiuntiva è identificata attraverso la sua chiave che deve esser unica all'interno dell'attore.

Quando il valore di un componente aggiuntivo cambia, come tutte le altre proprietà, si attiva un evento di modifica. Per impostazione predefinita, viene attivato *Nessuno*.

## Link

> 🚧 in progress...

### Eventi di trasformazione

> Vedere [il ciclo di vita di un attore](../scripts/actor-life-cycle.md)

## Discesa dei contenuti
> 🚧 in progress...

## I fornitori di dati
> 🚧 in progress...
