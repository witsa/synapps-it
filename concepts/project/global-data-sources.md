---
title: "Fornitore di dati"
parent: "progetto"
grand_parent: concetti
nav_order: 8
---

# Fornitore globale di dati

Questa parte è dedicata alla definizione degli attori [fornitore di risorsa,](../actor-types/redy-resource-source.md), [variabile](../actor-types/redy-wos-variable-source.md) e [variabile relativa](../actor-types/redy-wos-relative-variable-source.md) che possono essere utilizzati nel progetto.

Sono disponibili attraverso un collegamento di tipo *fornitore di variabili* o nel campo 'chiave padre'' di attori di tipo Fornitore variabile relativa.

Alla creazione di un nuovo progetto viene creato un attore Fornitore di variabili che punta a `easy.RESS`. Viene utilizzato per facilitare la definizione di collegamenti di tipo *Fornitore variabile*.

>⚠️ **ATTENZIONE**<br>
A meno che non si abbia una buona ragione, *non cancellare questo attore*.

# Designer

Questi attori non appaiono nell'anteprima del Designer.

# Caratteristitica specifica

La modalità di recupero degli attori fornitori è per default *Relativa*. Ciò significa che aspettano di essere utilizzati, in un modo o nell'altro, prima di iniziare a effettuare richieste.

Se si desidera che le query vengano eseguite non appena viene caricata la scena iniziale, è possibile utilizzare la modalità *Automatica*.
