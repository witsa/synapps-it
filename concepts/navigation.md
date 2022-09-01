---
title: "Navigazione"
parent: Concetti
---

# La navigazione in un synapp

## Navigazione semplice

Quando eseguita, la synapp visualizza la scena principale.

Se il synapp contiene diverse scene, si può navigare tra di esse semplicemente usando l'[attore Pulsante di navigazione](./actor-types/input-nav-button.md).

![SynApps](../assets/scenes-nav.png)

> 📌 **NOTA**<br>
E' possibile navigare grazie ad uno script. [⚡ `synapp.navigate(sceneKey,sceneParams)`]({{ site.baseurl }}/script-api/Synapps.Synapp.html#navigate){:target="_blank"}

## Navigazione in un attore Schermo

Se la scena contiene un [attore schermo](./actor-types/display-screen.md), è possibile fargli visualizzare un'altra scena grazie a un [attore Pulsante di navicazione](./actor-types/input-nav-button.md) specificando il nome dell'attore Schermo in questione.

> 📌 **NOTA**<br>
Il campo [scène](./actor-types/display-screen.md#scene) dell'attore Schermo può essere definito manualmente tramite collegamento o tramite script.

## Navigation paramétrée

Il pulsante di navigazione può essere utilizzato anche per impostare una scena. A tal fine, il Designer vi aiuterà: Selezionare la scena da visualizzare e se questa presenta dei parametri, il designer invita ad aggiungerli effettuare l'impostazione.

### In un attore di scherm0

È possibile parametrare una scena visualizzata in un attore Schermo. [vedi qui](./actor-types/display-screen.md#scene)
