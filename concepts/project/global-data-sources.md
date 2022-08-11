---
title: "Fornitore di dati"
parent: "progetto"
grand_parent: concetti
nav_order: 8
---

# Fornitore globale di dati

Questa parte è dedicata alla definizione degli attori [firnitori di risorsa,](../actor-types/redy-resource-source.md), [variabile](../actor-types/redy-wos-variable-source.md) e [variabile relativa](../actor-types/redy-wos-relative-variable-source.md) che possono essere utilizzati nel progetto.

Sono disponibili attraverso un collegamento di tipo *fornitore di variabili* o nel campo 'chiave padre'' di attori di tipo Fornitore variabile relativa.

Un attore Fornitore di variabili è sempre predefinito al momento della creazione del progetto e punta a `easy.RESS`. Viene utilizzato per facilitare la definizione di collegamenti di tipo *Fornitore variabile*..

>⚠️ **ATTENZIONE**<br>
A meno che non si abbia una buona ragione, *non cancellare questo attore*..

# Designer

Questi attori non appaiono nell'anteprima del Designer.

# Particularité

Le mode de récupération des acteurs fournisseurs sont par défaut *Relatif*. C'est à dire qu'ils attendent d'être consommées, d'une manière ou d'une autre, pour commencer à réaliser des requêtes.

Si vous désirez que les requêtes soient réalisée dès le chargement de la scène de départ, vous pouvez utiliser le mode *Automatique*.
