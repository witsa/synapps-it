---
title: "Acteur"
parent: Concepts
has_children: true
nav_order: 4
---

> 🚧 en cours de rédaction...

![SynApps](../../assets/under-progress.gif)

{% include table_of_content.html %}

# Attore

## Definizione

L'attore è l'elemento fondamentale dell'interfaccia. I numerosi tipi di attore e le loro specificità vi permetteranno di realizzare qualsiasi tipo di interfaccia, dai moduli ai dashboard..

Gli attori sono organizzati in una struttura ad albero che forma quella che è definita come [scena](../scena.md).

![SynApps](../../assets/concepts/actor/01.png)

![SynApps](../../assets/concepts/actor/02.png)

## Categoria

Un attore appartiene ad una categorie che ne determina il comportamento.

- voir [les types d'acteur](../actor-types/)

## Proprietà

Gli attori possiedono una serie di proprietà comuni. Inoltre ogni attore presenta delle proprietà specifiche alla categoria a cui appartiene.

Queste proprietà rappresentano lo stato dell'attore. Ne controllano l'aspetto e il comportamento.

Ogni proprietà ha un valore predefinito. Il valore è definito dallo [stile dell'attore](../actor-style.md).

Lo strumento *Ispettore dele proprietà* è la parte del *designer* che consente di impostare, programmare e collegare le proprietà di un attore.

![SynApps](../../assets/concepts/actor/03.png)

### Categorie

Nell'ispettore, le proprietà sono organizzate per categoria:

- [**Specifico**](../actor-types/index.md)

Sono le proprietà specifiche del tipo di attore. Per i dettagli andare alla pagina [Tipi di attore] (../actor-types/index.md).

- [**Aspetto**](./category-aspect.md)

Proprietà relative all'aspetto dell'attore, come il colore di sfondo o la visibilità.

- [**Testo**](./category-text.md)

Proprietà relative al testo che sarà contenuto nell'attore o nei suoi figli. Alcune proprietà, come la dimensione o il colore dei caratteri, vengono trasmesse agli attori figli per *ereditarietà*.

-  [**Layout**](./category-disposition.md)

Proprietà che definiscono la posizione dell'attore rispetto all'attore che lo contiene. La natura di queste proprietà dipende dal tipo di disposizione a cui appartiene il genitore.

- [**Taglie**](./category-size.md)

Proprietà relative alle dimensioni dell'attore.

- [**Spazi**](./category-space.md)

Les propriétés relatives à l'espacement entre les acteurs et les coins de la scène.

- [**Bordi**](./category-border.md)

Le proprietà relative ai bordi dell'attore e all'arrotondamento degli angoli.

- [**Effetti**](./category-effect.md)

Proprietà relative alle trasformazioni geometriche (scala, traslazione, rotazione) o alle ombreggiature o alla visualizzazione dei suggerimenti.

### Valori ereditati

Alcune proprietà possono ereditare il loro valore dalla proprietà di un genitore dell'attore. È il caso, ad esempio, della dimensione dei caratteri. È quindi possibile definire i valori di queste proprietà una volta per tutte all'inizio dell'albero degli attori, in modo che tutti i figli possano beneficiarne.

### Evento di modifica

Quando il suo valore cambia, ogni proprietà genera un evento di modifica. Esistono 4 tipi di modifica:
- **Aucune** Pas de modification particulière
- **Style** Modification qui entraîne un calcul des styles CSS de l'acteur.
- **Rendu** Modification qui entraîne un nouveau rendu de l'acteur.
- **Gabarit** Modification qui entraîne un nouveau calcul de gabarit et rendu de toute la hiérarchie de l'acteur.

Il est possible d'intervenir par script sur le déclenchement d'un évènement de changement de valeur.
- Voir la partie dédiées aux [Scripts](../scripts/)
- Voir la [documentation des scripts]({{ site.baseurl }}/script-api/){:target="_blank"}

## Clé d'acteur

Un acteur est identifiable par sa clé. C'est une chaîne de caractère qui doit être unique dans la scène ou le composite qui contient l'acteur.

Il est possible de changer cette clé dans l'inspecteur d'acteur.

### Caractères autorisés
 - Tous les caractères alphanumériques sont autorisés.
 - Seul le tiret `-` est autorisé parmi les caractères spéciaux.

> ✔️ **CONSEIL**<br>
Il est recommandé de profiter des clés d'acteur pour les qualifier et mieux comprendre le rôle de chaque acteur et la structure de votre scène ou composite.

## Les évènements et cycle de vie

Un acteur va déclencher des évènements pendant toute sa durée de vie : de son initialisation à sa destruction. Il aura aussi des évènements de souris comme le click, le survol... Enfin, certains acteurs possèdent des évènements spécifiques à leur comportement.
Tous ces évènements sont autant d'occasions d'intervenir et d'ajouter des comportements par script.

- En savoir plus sur le [cycle de vie d'un acteur](./actor-life-cycle)
- En savoir plus sur les [Scripts](../scripts/)

## Les additionnelles

Il est possible de définir des propriétés additionnelles sur un acteur. Une catégorie dans l'inspecteur est dédiée à leur gestion.

![SynApps](../../assets/concepts/actor/04.png)

Les types de propriétés disponibles :

![SynApps](../../assets/concepts/actor/05.png)

> 🚧 en cours de rédaction...


Chaque additionnelle est identifiée par sa clé qui doit être unique pour un acteur donné.

Lorsqu'une valeur d'additionnelle change, comme toute les autres propriétés, elle déclenche un type de d'évènement de modification. Par défaut c'est la *non modification* qui est lancé.

## Les liaisons

> 🚧 en cours de rédaction...

### Évènements de transformation

> voir [le cycle de vie d'un acteur](../scripts/actor-life-cycle.md)

## Le ruissellement de contexte
> 🚧 en cours de rédaction...

## Les fournisseurs de donnée
> 🚧 en cours de rédaction...
