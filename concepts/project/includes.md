---
title: "Inclusione"
parent: "Progetto"
grand_parent: Concetti
nav_order: 8
---

Le inclusioni offrono la possibilità di caricare i file all'apertura di un synapp.

{% include table_of_content.html %}

# Inclusioni all'esecuzione

È possibile includere file sorgenti in un synapp. Verranno caricati nell'ordine di definizione, uno dopo l'altro. Quindi viene visualizzata la [scena principale](../scene.md#scène-de-démarrage) s'affiche.

Questo permette di caricare le librerie `Javascript` o `CSS` che verranno utilizzate nelle scene.

I file inclusi possono essere *remoti* o *locali*. I file remoti vengono caricati dall'indirizzo fornito al momento della loro definizione. I file locali fanno parte della configurazione del synapp.

# Gestione delle inclusioni

È possibile gestire le inclusioni nella sezione *Progetto/Inclusione*.

Per il momento non esiste un designer per questa parte. È necessario modificare un file JSON di configurazione che contiene l'elenco delle inclusioni da caricare. Ogni inclusione è definita da un oggetto JSON,

- per un file JS remoto :


```json
   {
    "url": "https://example.com/script.js",
    "description": "Base 1view",
    "type": "js",
    "isRemote": true
  }
```

- pour un fichier JS local :

```json
   {
    "fileName": "nom-du-fichier.js",
    "description": "Base 1view",
    "type": "js",
    "isRemote": false
  }
```

In questo caso, il file `filename.js` deve trovarsi nella cartella `includes` del synapp.

Per i file CSS, basta specificare `"css"` per il campo `type`.

## Esempio di inclusione della libreria Leaflet

Ecco un esempio di configurazione che carica la libreria API di cartografia [Leaflet](https://leafletjs.com/reference.html) all'avvio di synapp:


```json
 [
  {
    "fileName": "https://unpkg.com/leaflet@1.8.0/dist/leaflet.js",
    "description": "ceci est un test",
    "type": "js",
    "isRemote": false
  },
  {
    "fileName": "https://unpkg.com/leaflet@1.8.0/dist/leaflet.css",
    "type": "css",
    "isRemote": false
  }
]
```
# Esempio di inclusione in 1view

Il codice sorgente che gestisce le scene operative nel modello di progetto **1view** è un esempio di inclusione di file `JavaScript`:

```json

[
  {
    "fileName": "oneview-base-comp.js",
    "description": "Base 1view",
    "type": "js",
    "isRemote": false
  },
  {
    "fileName": "oneview-desktop-comp.js",
    "description": "1view pour desktop",
    "type": "js",
    "isRemote": false
  },
  {
    "fileName": "oneview-smartphone-comp.js",
    "description": "1view pour smartphone",
    "type": "js",
    "isRemote": false
  }
]

```

Nella cartella `includes` del progetto si trovano i 3 file inclusi.
.
