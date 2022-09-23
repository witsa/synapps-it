---
title: "Scripts"
parent: Concetti
has_children: true
---

# Scripts

Synapps Studio offre un ambiente di sviluppo completamente programmabile.

Il linguaggio utilizzato è `Javascript`. Viene fornita un'API per manipolare e accedere a tutti gli oggetti del synapp

Vedere la [documentazione scripts]({{ site.baseurl }}/script-api/){:target="_blank"}

## Script negli eventi

Synapps è un framework di sviluppo guidato dagli eventi. Cioè, gli attori e le proprietà scatenano eventi (`onClick`, `onPropertyChange`, ecc.) che consentono l'esecuzione di script.
Il [ciclo di vita](./actor-life-cycle.md) di un attore genera eventi. Ma ogni attore può anche avere eventi specifici.

## Gli script nelle inclusioni

È possibile includere un file `JavaScript` tramite un'[inclusione](../project/includes.md).
