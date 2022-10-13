---
title: Opzioni
section: specifico
propName: options
propPath: properties.options
scriptApiClass: Actor.Input.ButtonListProperties
order: 4
---
La proprietà specifica `Opzioni` consente di popolare i pulsanti tramite il formato JSON.

Per creare un nuovo pulsante tramite il formato JSON, è necessario specificare tre parametri:
- value (obbligatorio):
<br>
Immettere il valore del pulsante.
<br>
Il valore atteso è una stringa.

- text (obbligatorio):
<br>
Inserire il testo che verrà visualizzato sul pulsante.
<br>
Il valore atteso è una stringa.

- disabled (opzionale):
<br>
Attiva/disattiva il bottone.
<br>
Il valore atteso è un booleano (true/false).
<br>
Se questa opzione non viene specificata, il valore predefinito è `False`.

**Esempio**
Ecco un elenco di 3 pulsanti, l'ultimo dei quali è disabilitato:
```
[
  {
    "value": "bouton1",
    "text": "Button 1"
  },
  {
    "value": "bouton2",
    "text": "Button 2"
  },
  {
    "value": "bouton3",
    "text": "Button 3",
    "disabled": true
  }
]
```
