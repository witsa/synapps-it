---
title: "Disposizione | Box di visualizzazione"
parent: "Elenco attori"
grand_parent: Concetti
---

{% include links_actor.md apiClass="Actor.Layout.ViewBox" %}

# Box di visualizzazione

Attore che consente di disporre un attore figlio in modo da adattarlo alle sue dimensioni.

{% include table_of_content.html %}

# Proprietà

## Tipo di visualizzazione

Il riquadro di visualizzazione disporrà i suoi attori figli secondo la regola data dalla proprietà *Tipo di visualizzazione*:

- **Visibile** *(predefinito)*: il box di visualizzazione regolerà la dimensione del suo attore figlio in modo che sia completamente visibile al suo interno.
- **Piena**: il box di visualizzazione regolerà la dimensione del suo attore figlio in modo che riempia completamente lo spazio del riquadro.

Nell'esempio seguente, il box di visualizzazione presenta un attore immagine di dimensioni maggiori del box stesso.

![SynApps](../../assets/concepts/actor/view-box/sample-01.gif)


## Layout

Vedere le regole di layout con l'opzione [propriétés d'alignement vertical et horizontal](../actor/category-disposition.md#catégorie-disposition-flexible)


## Superamenti

{% include property_overflow.md %}

Il valore predefinito è **Nascosto**.

> ✔️ **CONSIGLIO**<br>
> Se il contenuto non è visibile, è molto probabile che sia a causa delle dimensioni ridotte dell'attore padre.

# Eventi

{% include events_layout.md %}

# Uso

Il box di visualizzazione è un attore molto utile per visualizzare contenuti di dimensioni fisse per garantire che siano visibili indipendentemente dalle dimensioni dello schermo.

Ad esempio, è possibile creare in un attore Canvas, una visualizzazione complessa con elementi posizionati con precisione all'interno dello spaziol. Successivamente, si colloca l'attore Canvas in una box di visualizzazione, in modo che sia visibile a qualsiasi dimensione dello schermo.

> ⚠️ **ATTENZIONE**<br>
> Non si devono definire dimensioni con [unità relative](../sizes.md) in attori che si trovano all'interno di un box di visualizzazione. .
>
> **Utilizzare sempre unità fisse: `px`, `cm` et `in`.**
