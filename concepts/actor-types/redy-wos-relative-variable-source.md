---
title: "REDY | Fornitore varaibili relative"
parent: "Elenco attori"
grand_parent: Concetti
---

{% include links_actor.md apiClass="REDY.Actor.WosRelativeVariableSource" %}

# Fornitore varaibili relative

Questo attore fornitore di dati è usato a complemento degli attori [Fornitore variavili](./redy-wos-variable-source.md) o [Fornitore risorse](./redy-resource-source.md) per comunicare con una variabile *WOS* figlia di un REDY.

Permette il recupero di una variabile figlia o anche la scrittura di un valore di una variabile figlia utilizzando solo il *sub-path* relativo a un'altra variabile (definita in un altro fornitore).

La variabile o il campo di variabile che richiama è memorizzato nelle sue informazioni `Dati`, come per gli altri fornitori di dati.

Si noti che non contiene un parametro di query. Questo perché la responsabilità è del fornitore genitore che effettua la query.

I dati recuperati sono disponibili tramite collegamento o script.

{% include table_of_content.html %}

# Proprietà

## Chiave del padre

Questa proprietà permette di definire il fornitore padre dell'attore attraverso la sua chiave. È possibile scegliere tra tutti i provider della stessa scena o dello stesso composito e tra quelli definiti tra i provider di dati globali.

È ovviamente possibile scegliere anche un altro fornitore di variabili relative.

> 📌 **NOTA**<br>
In ogni caso, un fornitore normale viene trovato andando a ritroso nell'ascendenza dei relativi attori.


## Percorso relativo

Questa proprietà contiene un *percorso relativo* alla variabile da recuperare. È un percorso di tipo REDY, ma legato a un altro percorso, ad esempio : `R00001` o `R00001.Output`.

Il percorso di riferimento è una costruzione di tutti i percorsi rimontando i genitori dell'attore.

Esempio:campo

- **Fornitore 1** :
  - Cammino : `easy.RESS.R00001`

Questo fornitore punta alla risorsa `R00001`. Esegue le interrogazioni.

- **Fonitore relativo 1** :
  - Genitore: **Fornitore 1**
  - Cammino relativo: `Output`

Questo fornitore è correlato al primo. Indica che è interessato alla variabile figlia `Output` di ciò che è definito nel provider padre, in questo caso la risorsa `R00001`. Il percorso completo è `easy.RESS.R00001.Output`

- **Fornitore relativo 2** :
  - Parent : **Fonitore relativo 1**
  - champ : *Value*

Il Fornitore relativo 2 è correlato al *fornitore relativo 1*. A sua volta indica che è interessato al campo *Value* di ciò che deriva dal provider padre, in questo caso la variabile `easy.RESS.R00001.Output`. Il percorso completo risulta dunque: `easy.RESS.R00001.Output`, ma è questo *Value* che verrà scritto nei *dati* dell'attore.

Come per i normali provider, l'esploratore dei parametri REDY aiuta ad individuare il percorso.

## Campo REDY
Per impostazione predefinita, l'intera variabile viene recuperata e inserita nel campo *Data*. Se si vuole recuperare una parte della variabile, si può indicare il nome del campo da recuperare tra le possibilità che si trovano [qui](./redy-wos-variable-source.md#champ-de-variable-redy).

## Modalità di lettura

La proprietà è utilizzata per definire come il fornitore principale deve procedere per ottenere il dato. Ricordiamo infatti che è il fornitore padre a eseguire le richieste. Sono possibili due modalità di lettura:

- **Solo una volta** Il dato viene letto una sola volta
- **Ad ogni aggiornamento** L'attore aggiorna il dato ogni volta che il provider padre effettua una richiesta.

## Scrittura su cambiamento?

Questa proprietà abilita/disabilita la registrazione del valore di una variabile nel REDY se i *dati* vengono modificati dal collegamento o da script. Deve essere il *campo* ***Valore*** quello scritto nei dati.

Aussi, pour déclencher l'enregistrement de la donnée changée dans le REDY, il faudra appeler la méthode [⚡ `write()`]({{ site.baseurl }}/script-api/REDY.Actor.WosRelativeVariableSource.html#method:write){:target="_blank"} de l'acteur.

# Événements

## `onDidDataStore`

L'évènement `onDidDataStore` est déclenché à chaque fois que le fournisseur parent a réaliser une requête et que la donnée cible est écrite dans l'information *Donnée*.

> [⚡ `onDidDataStore`]({{ site.baseurl }}/script-api/REDY.Actor.WosRelativeVariableSource.html#event:onDidDataStore){:target="_blank"}

## `onWriteDone`

L'évènement `onWriteDone` est déclenché à chaque fois que l'acteur a réaliser une écriture vers le REDY.

> [⚡ `onWriteDone`]({{ site.baseurl }}/script-api/REDY.Actor.WosRelativeVariableSource.html#event:onWriteDone){:target="_blank"}

# Informations

## Donnée

Vous trouverez dans ce champ la variable ou le champ de variable désigné par l'acteur.

Une liaison avec l'écriture activée permet de modifier la valeur de la variable REDY si l'acteur la désigne.

## Requête en cours ?

Cette information permet de savoir si l'acteur parent est en train de réaliser une requête.

> 💡 **ASTUCE**<br>
Liez la visibilité d'une acteur sur cette information pour le visualiser lorsqu'il est en train de réaliser une requête.


# Usage

Il est possible de créer des fournisseurs dans vos scènes ou composites. Vous pouvez également les créer de manière globale dans la sous-section [Projet / Fournisseurs de variable](../project/variable-source.md) pour en faire profiter toute votre synapp.


## Grouper des requêtes.

Utiliser les fournisseurs relatifs est une bonne manière de mutualiser les fournisseurs de variable dans vos scènes et composites. Si vous attachez plusieurs relatifs à un même fournisseur de variable, il récupérera en même temps toutes les variables désignées.

Par exemple vous pouvez grouper la requête des sous variables d'une ressource :

- **Fournisseur 1 :** *pour accéder à une ressource*
  - chemin : `easy.RESS.R00001`

- **Fournisseur relatif 1 :** *pour accéder à son état*
  - parent : **Fournisseur 1**
  - champ : *État*

  ▶️ Champ *État* de `easy.RESS.R00001`

- **Fournisseur relatif 2 :** *pour accéder à sa valeur brute*
  - parent : **Fournisseur relatif 1**
  - chemin relatif : `Output`
  - champ : *Valeur*

  ▶️ Champ *Valeur* de `easy.RESS.R00001.Output`


- **Fournisseur relatif 2 :** *pour accéder à son unité*
  - parent : **Fournisseur relatif 2**
  - chemin relatif : `Unit`
  - champ : *Valeur*

  ▶️ Champ *Valeur* de `easy.RESS.R00001.Unit`

Le *Fournisseur 1* réalise en une seule requête la récupération de toutes les variables désignées.

## Chemin dynamique
Avec les fournisseurs relatifs, il est possible de construire un chemin cible dont les segments sont dynamiques :

- **Fournisseur 1 :**
  - chemin : `easy.RESS`

- **Fournisseur relatif 1 :**
  - parent : **Fournisseur 1**
  - chemin relatif : <span style="color: green;">*le sous chemin que vous souhaitez, renseigné par liaison par exemple.*</span>

- **Fournisseur relatif 2 :**
  - parent : **Fournisseur relatif 1**
  - chemin relatif : `Output`
  - champ : *Valeur*
