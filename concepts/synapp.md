---
title: "Synapp"
parent: Concetti
nav_order: 2
---

Il synapp è l'applicazione HMI (Human-Machine Interface) vera e propria. Contiene le impostazioni essenziali per la sua esecuzione.

Il synapp possiede una propria identità, un nome e un'icona.

È questo oggetto si occupa degli aspetti necessari alla visualizzazione della scena corrente e contiene tutti gli elementi dell'applicazione, come le librerie, i fornitori di dati, i compositi, ecc.


![SynApps](../assets/scenes-nav.png)


## In studio

In Studio le proprietà del synapp sono gestite nella sezione [Progetto/Generale](./project.md#généralités).

## Progetto

### Il `GUID`
Il synapp porta con sé il `GUID` del progetto con cui è stato creato e pubblicato. Questo permette a un progetto di riconoscere il **suo** synapp all' interno di REDY.


> ⚠️ **ATTENZIONE**<br>
> **Non duplicare un progetto** perché il `guid` rimarrà invariato e ciò comporterà errori nella pubblicazione e nella gestione delle password per gli host. Se tuttavia è stato fatto, per ripristinare la situazione, modificate a mano il `guid` di uno dei due progetti nel file di configurazione, preferibilmente prima di aprirlo con Studio.
>
> Per duplicare correttamente un progetto, è sufficiente esportarlo come modello e creare il nuovo progetto a partire dal modello stesso.

## Identità Synapp

### Nome del synapp

Il nome del synapp è il titolo che appare nella scheda del browser o nell'elenco dei synapp in un REDY.

### Etichetta del synapp

È in questo modo che il REDY identifica il synapp. La configurazione del synapp nel REDY è effettivamente memorizzata nel percorso `:easy.SynApps.<etichetta>`.

