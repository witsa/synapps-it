---
title: "Taglie e dimensioni"
parent: Concetti
---

{% include table_of_content.html %}

# Taglie e dimensioni

Le proprietà di tipo Taglia possono assumere come valore le dimensoni CSS. In questa sezione troverete una panoramica delle diverse unità di misura e le istruzioni necessarie per il loro utilizzo all'interno di un progetto Synapp Studio.

## Grandezze e unità di misura

Una grandezza di tipo taglia ha sempre un'unità. L'unità più nota è il pixel `px`. Ma ce ne sono molti altri che Studio riconosce.

Innanzitutto, esistono unità di dimensioni fisse:
- il pixel `px`,
- il centimetro `cm`,
- il pollice `in`.

Poi ci sono le unità relative alle dimensioni del testo:
- la `em`,
- il `rem`,
- il `ch`.

E infine le unità di misura relative alle dimensioni del contenitore, dell'apparecchiatura o della finestra del browser:
- la percentuale `%`,
- `vw`,
- `vh`,
- `vmin`,
- `vmax`.

### Il pixel `px`

Il pixel è un'unità fissa, il che significa che per un determinato formato e scala, il pixel ha sempre la stessa dimensione. È un'unità facile da usare.

> 💡 **CONSIGLIO**<br>
> In genere si utilizza questa unità di misura all'interno di un attore [Canvas](./actor-types/layout-canvas.md) quando si gestiscono attori e/o immagini che si sovrappongono per creare uno sfondo o un disegno preciso . Una volta raggiunto l'obiettivo desiderato lasciate che sia un attore [Box di visualizzazione](./actor-types/layout-view-box.md) a gestire l'adattamento dell'insieme a qualsiasi dimensione di schermo.

Il pixel è definito come l'elemento più piccolo sullo schermo che è abbastanza grande da essere visibile.

### Centimetri `cm` e pollici `in`

Il centimetro e il pollice rappresentano unità di misura prossime alle dimensioni reali, a condizione che lo schermo sia sufficientemente grande.
Sono molto utili per definire le dimensioni *organiche*. Ad esempio, per garantire che un oggetto sia *toccabile*, è sufficiente attribuire ad esso una dimensione superiore a `1cm`.

> ⚠️ **ATTENZIONE**<br>
> Il `cm` di un piccolo schermo può risultare più piccolo di un centimetro reale.


### L'`em`

`1em` è la dimensione del testo dell'attore. Occorre ricordare che la dimensione del testo è una proprietà ereditata.
Quindi, se l'attore ha una dimensione del testo impostata a `15px`, `1em` rappresenta `15px`.
Se l'attore padre (di un Layout, o di un Composito, ...) ha impostato la dimensione del testo a `30px`, `1em` rappresenterà `30px` per tutti gli attori figli.

Cette unité est très pratique pour définir une taille de texte de référence tout en haut de votre arborescence d'acteurs et de définir des tailles relatives en dessous.
Exemple:

Supponiamo di avere la seguente struttura ad albero:
- Attore principale (dimensione del testo: `20px`)
  - Attore A
  - Attore B (dimensione del testo: `2em`)
    - Attore 1 (dimensione del testo: `0,5em`)
    - Attore 2
    - Attore 3 (dimensione del testo: `1.5em`)

In questo modo si otterranno le seguenti dimensioni:
- Attore principale (dimensione del testo: `20px`)
  - Attore A
  - Attore B (dimensione del testo *calcolata*: `40px`)
    - Attore 1 (dimensione del testo *calcolata*: `20px`)
    - Attore 2
    - Attore 3 (dimensione del testo *calcolata*: `60px`)

Se si modifica la taglia dell'attore radice, gli altri attori si adeguano automaticamente senza modificare le loro impostazioni.

![SynApps](../assets/concepts/sizes/sample-em.gif)


> 💡 **CONSIGLIO**<br>
> È molto utile definere delle grandezze nella radice della propria interfaccia per poi impostare le proprietà che ereditano in `em`. Si risparmia tempo prezioso quando si regolano le dimensioni e si apportano modifiche globali..

### Il `rem`

L'unità di misura `rem` è essenzialmente uguale a `em`. L'unica differenza è che la dimensione di riferimento è la dimensione del testo definita nel *corpo* della pagina `HTML. In Synapps, non si ha accesso diretto all'impostazione di questa dimensione, che è 12px. Ma è possibile modificarlo tramite script o CSS.

### La percentuale `%`

Questa unità è la percentuale della taglia del contenitore. Non è sempre facile da usare. Infatti, a volte è difficile sapere da quale taglia del contenitore viene preso il riferimento: dalla larghezza o dall'altezza. In generale, quando si tratta di una dimensione verticale, il riferimento è preso dall'altezza del contenitore. Quando si tratta di una dimensione orizzontale, il riferimento è la larghezza del contenitore. Questo vale per l'altezza, la larghezza e la dimensione del testo, ma non per i margini interni ed esterni.

### Il `vh` e il `vw`

Il valore `vh` è una percentuale dell'altezza della finestra o dello schermo del browser per un dispositivo mobile.
Il valore `vw` è una percentuale della larghezza della finestra o dello schermo del browser per un dispositivo mobile.

Quindi, un attore di `50vh` in altezza e `33vw` in larghezza è la metà della finestra in larghezza e un terzo in altezza.

Queste due unità ci permettono di iniziare a definire le dimensioni in relazione alle caratteristiche della finestra o dello schermo.

### Il `vmin` e il `vmax`

Il valore `vmin' è una percentuale della dimensione più piccola delle due dimensioni dello schermo. Cioè, per uno schermo più largo che alto, sarà una percentuale dell'altezza.

Il valore `vmax` è una percentuale della dimensione maggiore delle due dimensioni dello schermo. Cioè, per uno schermo più largo che alto, sarà una percentuale della larghezza.

Queste due unità sono ancora più funzionali delle precedenti, in particolare sui dispositivi mobili. Infatti, qualunque sia l'orientamento dello schermo, se si definisce una dimensione in `vmin` o `vmax`, questa rimarrà invariata!
È quindi possibile impostare le dimensioni del testo in `vmin` per garantire la leggibilità, indipendentemente dall'orientamento.

![SynApps](../assets/concepts/sizes/sample-vmin.gif)

## Impostazioni automatiche

Le proprietà di tipo *Taglia* possono assumere come valore anche delle impostazioni automatiche. Il comportamento è molto variabili a seconda dei casi.

- stringa vuota: in generale, si tratta di un valore predefinito che disattiva la proprietà.
- `auto`: indica che il comportamento deve essere automatico. Questo è il valore neutro per l'altezza minima, ad esempio.
- `none`: indica che il comportamento non deve tenere conto di questa dimensione. Questo è il valore predefinito per l'altezza massima, ad esempio.
- `inherit`: indica che la dimensione deve essere ereditata dal padre dell'attore.

Le seguenti impostazioni non sono ancora riconosciute da Studio, ma sono funzionanti in in un synapp sulle proprietà *altezza* e *larghezza*:

- `fit-content` : indica che l'attore deve adattarsi al suo contenuto.
- `min-content` : indica che l'attore deve adattarsi all'elemento più piccolo.
- `max-content` : indica che l'attore deve adattarsi all'elemento più grande.
