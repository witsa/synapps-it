---
title: "Esecuzione di uno script alla visualizione"
parent: Scripts
grand_parent: Concetti
---

# Esecuzione di uno script sul displayalla visualizzazione

## Come eseguire uno script alla visualizzazione di una scena o di un composito

Sia per una scena che per un composito, è possibile eseguire uno script nel momento della sua visualizzazione.

Per farlo, basta definire questo script nell'evento `onPostInit` dell'attore principale della scena o del composito.

Di fatto, quando una scena o un composito deve essere visualizzato, la costruzione avviene percorrendo l'albero degli attori. Durante questa costruzione, gli script `onInit` vengono eseguiti attraversando l'albero degli attori dall'alto verso il basso. Quindi l'evento `onPostInit` viene eseguito su ogni attore, risalendo l'albero. Così, quando arriva il turno dell'attore principale, tutti gli attori sono stati dichiarati, tutti i collegamenti creati.

## Collegamento connessi

- [Cycle de vie d'un acteur](../actor/actor-life-cycle.md)
