---
title: Valore unico
section: specifico
propName: isSingleValue
propPath: properties.isSingleValue
scriptApiClass: Actor.input.CursorProperties
order: 2
---
La proprietà specifica Valore unico` consente di attivare/disattivare un secondo cursore sull'attore.

Per attivare un secondo cursore sull'attore occorre disabilitare questa proprietà.

In questo modo si aggiungerà all'attore una proprietà `Valore 2`, che funziona come la proprietà specifica `Valore` e consente di impostare un intervallo.

Si un second curseur est présent, la propriété spécifique `Valeur` devient la borne inférieure et la propriété spécifique `Valeur 2` devient la borne supérieure.

Il est à noter que la borne inférieure ne peut pas dépasser la borne supérieure et inversement.

Vengono visualizzate anche due nuove proprietà specifiche: :
<br>
`Differenza minima`: imposta una differenza minima tra il `valore` e il `valore 2.`
<br>
`Differenza massima`: imposta una differenza massima tra `Valore' e `Valore 2`


>⚠️ **ATTENZIONE**<br>
È possibile impostare il `Valore` al di sopra del limite superiore e il `Valore 2` al di sotto del limite inferiore, tuttavia è consigliabile impostare i valori entro i limiti definiti.

Allo stesso modo, i valori `Valore` e `Valore 2` possono non rispettare le differenze `Minimo` e `Massimo` quando vengono impostati manualmente; tuttavia, è consigliabile impostare valori con un intervallo che rispetti le differenze definite..
