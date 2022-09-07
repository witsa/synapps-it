---
title: "Disposizione | Impilamento"
parent: "Elenco attori"
grand_parent: Concetti
---


{% include links_actor.md apiClass="Actor.Layout.Stack" %}

# Impilamento

Attore che consente di disporre gli attori figli in una pila, in verticale o in orizzontale.

{% include table_of_content.html %}

# Proprietà

## Orientamento

Lo stack disporrà i suoi attori figli secondo la regola data dalla proprietà *Orientamento*:

- **Verticale** *(predefinito)* : Gli attori figli sono impilati uno sotto l'altro, dall'alto verso il basso.
- **Orizzontale** : Gli attori figli sono impilati l'uno accanto all'altro, da sinistra a destra.

## Layout

Vedere le regole di layout con le proprietà [allineamento verticale e orizzontale](../actor/category-disposition.md#catégorie-disposition-flexible)

## Superamento dei contenuti

{% include property_overflow.md %}

Il valore predefinito è **Nascosto**.

> ✔️ **CONSIGLIO**<br>
> Se il contenuto non è visibile, è molto probabile che sia a causa delle dimensioni ridotte dell'attore padre.

# Eventi

{% include events_layout.md %}

# Uso

Le regole di impilamento con [layout flessibile](./actor/category-disposition.md#category-flexible-disposition) sono la base per costruire interfacce che si adattino a qualsiasi dimensione dello schermo.
Combinati con il layout [Canvas](./layout-canvas.md) e con [Box di visualizzazione](./layout-view-box.md), questi attori possono essere usati per costruire qualsiasi tipo di schema.
