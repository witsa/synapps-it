---
title: "Inclusione"
parent: "Progetto"
grand_parent: Concetti
nav_order: 8
---

Le inclusioni offrono la possibilità di caricare i file all'apertura di un synapp.

{% include table_of_content.html %}

# Inclusioni all'esecuzione

Synapps Studio permette di includere file sorgente in un synapp. I file definiti verranno caricati in modo sequenziale nell'ordine con cui sono stati definiti. In seguito a questa operazione viene visualizzata la [scena principale](../scene.md#scène-de-démarrage) s'affiche.

Questa funzionalità permette di caricare ad esempio le librerie `Javascript` o `CSS` che saranno poi utilizzate nelle scene.

I file inclusi possono essere *remoti* o *locali*. I file remoti vengono caricati a partire dall'indirizzo fornito al momento della loro definizione. I file locali fanno parte della configurazione del synapp.

# Gestione delle inclusioni

È possibile gestire le inclusioni nella sezione *Progetto/Inclusione*.

Per il momento non esiste un designer dedicato a queste funzioni. È necessario modificare un file JSON di configurazione che contiene l'elenco delle inclusioni da caricare. Ogni inclusione è definita da un oggetto JSON,

- per un file JS remoto:


```json
   {
    "url": "https://example.com/script.js",
    "description": "Base 1view",
    "type": "js",
    "isRemote": true
  }
```

- per un file JS locale:

```json
   {
    "fileName": "NomeFile.js",
    "description": "Base 1view",
    "type": "js",
    "isRemote": false
  }
```

In questo caso, il file `NomeFile.js` deve trovarsi nella cartella `includes` del synapp.

Per i file CSS, basta specificare `"css"` per il campo `type`.

## Esempio di inclusione della libreria Leaflet

Di seguito è riportato un esempio di configurazione che carica la libreria API della cartografia [Leaflet](https://leafletjs.com/reference.html) all'avvio di synapp:

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

I 3 file inclusi devono trovarsi nella cartella `includes` contenuta nella cartella definita al momento della creazione del progetto in Synapps Studio.
.
