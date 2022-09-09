---
title: "REDY | Fornitore di variabili"
parent: "Elenco attori"
grand_parent: Concetti
---

{% include links_actor.md apiClass="REDY.Actor.WosVariableSource" %}

# Fornitore di variabili

L'attore Fornitore di variabili permette il collegamento con una variabile *WOS* in un REDY. Il fornitore si occupa di recuperare il valore della variabile definita dalla proprietà *Percorso* e lo inserisce nel campo informativo *Dati*. In alternativa, è possibile indicare un *Campo* specifico.

Inoltre, l'attore consente di definire il modo in cui si recupera e si aggiorna il valore della variabile e di attivare o meno la scrittura per permettere la modifica del valore nel REDY.

Il dato recuperato è disponibile per i collegamenti o per gli script..

L'attore serve come fornitore di base per qualsiasi [Fornitore di variabili relative](./redy-wos-relative-variable-source.md) o per i collegamenti di tipo [Fornitore di variabili](../binding.md#variable-provider) che puntano a lui..

{% include table_of_content.html %}

# Proprietà

## Percorso

Questa proprietà indica il *percorso* verso la variabile da interrogare. Si tratta di un percorso secondo il metodo REDY, ad esempio `:easy.RESS.R00001` o anche `:easy.RESS.R00001.Output`.

L'esploratore della parametrizzazione REDY aiuta nell'inserimento del percorso.

![SynApps](../../assets/concepts/actor/redy-variable-source/sample-01.gif)


## Campo delle Variabili REDY

Per impostazione predefinita, l'intera variabile viene recuperata e inserita nel campo *Data*. Se si desidera recuperare una parte della variabile, è possibile specificare il nome del campo da utilizzare scegliendo tra le seguenti possibilità:
- **Label** L'etichetta della variabile REDY. Ad esempio: `R00003` o `RunCount`.
- **Name** La descrisione della variabile REDY. Ad esempio: `Contatore 1`.
- **Valore** Il valore della variabile. Ad esempio: `true`, `"Testo"` o `23`, a seconda del tipo di variabile.
- **Stato** Lo stato se la variabile è una risorsa. Questo sarà il testo dello stato come definito in REDY. Ad esempio: ``ON'', ``Acceso''..
- **Percorso** L'intero percorso della variabile REDY. Ad esempio: `:easy.RESS.R00001` o anche `:easy.RESS.R00001.Output`.
- **ID** L'ID interno della variabile REDY.
- **Data** La data dell'ultimo aggiornamento della variabile REDY.
- **ID classe** Codice identificativo della classe a cui appartiene la variabile REDY.
- **URL dell'icona** L'URL dell'icona della variabile REDY. Utilizzabile direttamente, ad esempio, in un collegamento a un [Attore immagine](./display-image.md).
- **Lettura?** Indica se la variabile è accessibile dall'utente corrente in modalità lettura. Considerare il gruppo e il livello dell'utente.
- **Scrittura?** Indica se la variabile è modificabile dall'utente corrente. Tiene conto dei gruppi e del livello dell'utente.
- **Numero di figli** Il numero di figli presenti nella variabile REDY.
- **Figli** L'elenco dei figli della variabile REDY.

Se si desidera scrivere in questo campo, scegliere *Valore*. In questo modo, facendo una connessione con la scrittura abilitata ai dati dell'attore, si potrà scrivere sulla variabile REDY e inviare questo valore automaticamente se la proprietà *Scrittura su cambiamento* è attivata. Altrimenti, tramite script..

## Modalità

Cette propriété permet de définir le comportement de l'acteur à son arrivée dans la scène ou lorsque le *chemin* ou le *champ* de la variable cible sont modifiés.

- **Automatique** Si toutes les conditions sons réunis, l'acteur va récupérer automatiquement la variable et la placer elle ou le *champ* dans la *donnée*.
- **Manuel** L'acteur attend qu'on change de *mode* ou qu'un script le demande pour récupérer la variable et la placer elle ou le *champ* dans la *donnée*.
- **Relatif** L'acteur se comportera comme dans le mode automatique dès qu'il a des [fournisseurs de variable relative](./redy-wos-relative-variable-source.md) ou liaisons de type [fournisseur de variable](../binding.md#fournisseur-de-variable) qui pointent dessus.

Dans tous les cas, ceci est complètement indépendant du mode de rafraîchissement de l'acteur.

## Auto rafraîchissement?

Cette propriété active/désactive l'auto rafraîchissement de la variable ciblée.

## Délai de rafraîchissement

Cette propriété définit le délai de rafraîchissement (en seconde) de la variable ciblée lorsque l'auto rafraîchissement est activé.


> ✔️ **CONSEIL**<br>
> Évitez de définir des délais de rafraîchissement trop court. En dessous de 10 secondes, il faut vraiment s'interroger sur la pertinence d'un tel choix.

## Écriture au changement?

Cette propriété active/désactive l'enregistrement de la valeur d'une variable dans le REDY si la *donnée* est modifiée par liaison ou par script. Il bien entendu que le ce soit le *champ* ***Valeur*** qui soit inscrit dans la donnée.

# Événements

## `onRequestDone`

L'évènement `onRequestDone` est déclenché à chaque fois que l'acteur a réaliser une requête pour obtenir ou rafraîchir la variable et le champ souhaité.

> [⚡ `onRequestDone`]({{ site.baseurl }}/script-api/REDY.Actor.WosVariableSource.html#event:onRequestDone){:target="_blank"}

## `onWriteDone`

L'évènement `onWriteDone` est déclenché à chaque fois que l'acteur a réaliser une écriture vers le REDY.

> [⚡ `onWriteDone`]({{ site.baseurl }}/script-api/REDY.Actor.WosVariableSource.html#event:onWriteDone){:target="_blank"}

# Informations

## Donnée

Vous trouverez dans ce champ la variable ou le champ de variable désigné par l'acteur.

Une liaison avec l'écriture activée permet de modifier la valeur de la variable REDY si l'acteur la désigne.

## Requête en cours ?

Cette information permet de savoir si l'acteur est en train de réaliser une requête.

> 💡 **ASTUCE**<br>
Liez la visibilité d'une acteur sur cette information pour le visualiser lorsqu'il est en train de réaliser une requête.

## Première requête réalisée ?

Cette information sera vrai après avoir effectuer une première requête.

# Usage

Il est possible de créer des fournisseurs dans vos scènes ou composites. Vous pouvez également les créer de manière globale dans la sous-section [Projet / Fournisseurs de variable](../project/variable-source.md) pour en faire profiter toute votre synapp.


> ✔️ **CONSEIL**<br>
> Essayez de mutualiser les fournisseurs de variable dans vos scènes et composites. Rappelez-vous que des requêtes de données sont réalisées pour chaque fournisseur de variable. Ce qui est responsable d'un trafic de données qui pourrait être important pour l'équipement qui exécute votre synapp. Ceci est particulièrement sensible pour les équipements nomades comme les smartphones et tablettes.
