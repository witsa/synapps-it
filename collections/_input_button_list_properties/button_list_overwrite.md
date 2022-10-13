---
title: Superamento del testo
section: specifico
propName: textOverflow
propPath: properties.textOverflow
scriptApiClass: Actor.Input.ButtonListProperties

order: 6
---
La propriété spécifique `Dépassement de texte` permet de gérer l'affichage du texte dans le cas ou la taille du conteneur ne suffit pas à afficher l'entièreté du texte.


Esistono quindi tre opzioni per questa proprietà:

- Senza interruzione di linea.
- Ritorno alla linea.
- Troncato.

Ecco alcuni esempi per ciascuno di essi:

**Senza interruzione di linea**

![SynApps]( {{ site.baseurl }}/assets/concepts/actor/input_button/buttonClassic.PNG)

**Ritorno alla linea**

![SynApps]( {{ site.baseurl }}/assets/concepts/actor/input_button/buttonOverwrite.PNG)

>⚠️ **ATTENZIONE**<br>
La dimensione verticale dell'attore viene adattata automaticamente alla dimensione del testo, a meno che non sia fissa.

**Troncato**

![SynApps]( {{ site.baseurl }}/assets/concepts/actor/input_button/buttonTruncat.PNG)
