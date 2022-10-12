---
title: Scala
section: effetti
propName: scaling
propPath: properties.scaling
scriptApiClass: Actor.BaseActorProperties
order: 3
---
Questa proprietà consente di modificare le dimensioni dell'attore.

Il valore atteso è un numero positivo o negativo.
Con un valore compreso nell'intervallo [-1,1], l'elemento viene ridotto.
Quando il valore è negativo, l'elemento è invertito per simmetria centrale.

Nell'Inspector, il campo di immissione funge anche da cursore, consentendo di modificare il valore trascinando il mouse verso destra per aumentarlo e verso sinistra per diminuirlo..

**Suggerimento:**
La proprietà definisce il valore della funzione 'scale()' in CSS, la cui documentazione è disponibile [a questo indirizzo](https://developer.mozilla.org/fr/docs/Web/CSS/transform-function/scale()).

>⚠️ **ATTENZIONE**<br>
Non è possibile impostare due valori come indicato nella documentazione CSS.
