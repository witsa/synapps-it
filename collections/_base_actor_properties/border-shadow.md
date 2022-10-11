---
title: Ombre de la bordure
section: border
propName: borderShadow
propPath: properties.borderShadow
scriptApiClass: Actor.BaseActorProperties
order: 5
---
Questa proprietà viene utilizzata per aggiungere un'ombra al bordo dell'attore.

Questa proprietà prevede due valori obbligatori e diversi valori opzionali.

Esempio: ` box-shadow: A B C D E; `.

n questo esempio :
- A (obbligatorio): è la posizione X dell'ombra proiettata.
- B (richiesto): è la posizione Y dell'ombra proiettata.
- C (opzionale) : Permette di controllare la sfocatura applicata all'ombra (più alto è il valore, più sfocata sarà l'ombra).
- D (opzionale): Permette di controllare le dimensioni dell'ombra (i valori negativi diminuiscono le dimensioni, mentre i valori positivi le aumentano).
- E (opzionale): Permette di impostare il colore dell'ombra proiettata (l'impostazione predefinita è nero).

I valori attesi per i parametri A, B, D sono numeri positivi o negativi seguiti dal loro suffisso unitario (`px, em`, ecc...).
Il valore atteso per il parametro C è un numero positivo seguito dal suo suffisso unitario (`px,em`, ecc...).
Il valore atteso per il parametro E è un colore o un codice RGB. La guida per l'elenco dei colori CSS nativi si trova [a questo indirizzo](https://developer.mozilla.org/fr/docs/Web/CSS/color_value).


**Consiglio:**
La documentazione dell'attributo CSS Bos-Shadow è disponibile [a questo indirizzo](https://developer.mozilla.org/fr/docs/Web/CSS/box-shadow).
