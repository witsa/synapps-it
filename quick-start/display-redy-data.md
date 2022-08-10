---
title: Visualizzare uno stato
parent: Guida introduttiva
nav_order: 6
---

[◀ Pubblicazione](./synapp-publish){: .btn } [Comandare una risorsa ▶](./command-redy.md){: .btn }

------------------

{% include table_of_content.html %}


# Visualizzazione dello stato di una risorsa

Nei progetti synapp abbiamo la necessità di visualizzare dati che appartengono a risorse e variabili definite nella parametrizzazione del REDY.

Di seguito è illustrato uno dei metodi per **ottenere e visualizzare lo stato di una risorsa**.  Tale metodo utilizza il collegamento di tipo *Fornitore di variabili*.

> 📌 **NOTA**<br>
Esistono altri modi per ottenere lo stato di una risorsa. Questi prevedono l'utilizzo di [**attori fornitori di dati**](../concepts/actor-types/redy-wos-variable-source.md). I dettagli sono disponibili nella sezione Concetti.

## Preparazione della risorsa

A titolo di esempio procediamo alla creazione di una risorsa di tipo **consegna analogica**. Aprire la parametrizzazione del REDY per la creazione della risorsa.

![Ressource](../assets/quick-start/display-redy-data/01.png)

Configurare la risorsa come in figura:

![Ressource](../assets/quick-start/display-redy-data/02.png)

- Descriozione: `Setpoint di temperatura`
- Numero di decimali: `0`
- Valori limite: tra `20` e `30`
- Unità personalizzate: `°C`


## Collegamento di tipo *Fornitore di variabili*

Passare in Studio, nella progettazione della scena *Accueil*.

Creare un collegamento di tipo *Fornitore di variabili* per alimentare la proprietà *Contenuto* presente nella sezione *Specifico* dell'attore `text1`.

![Ressource](../assets/quick-start/display-redy-data/08.gif)

Cette liaison permet d'indiquer la donnée qui nous intéresse à un élément de synapp qui joue le role d'intermédiaire : *un fournisseur de donnée*.
C'est un acteur d'un type spécial : il n'est pas afficher. Son objectif est de fournir les données aux autres acteurs.

Dans chaque projet, un fournisseur est déjà présent : le fournisseur global `resources`. Nous allons le regarder de plus prés un peu plus bas.

En attendant, choisissez le dans le champ *Clé parent*.

![Ressource](../assets/quick-start/display-redy-data/09.gif)

Maintenant, vous allez lui indiquer la ressource qu'il doit aller chercher dans le champ **Chemin relatif**.

![Ressource](../assets/quick-start/display-redy-data/10.gif)

Vous pouvez observer que le chemin saisi est relatif au chemin défini dans `resources`.

En réalité, nous indiquons simplement au fournisseur de données `resources` qu'en plus de la variable `:easy.RESS`, il devra aller chercher la variable `:easy.RESS.R00001`.

Mais plus précisément, c'est l'état de la ressource qui nous intéresse. Il faut dont l'indiquer :

![Ressource](../assets/quick-start/display-redy-data/11.gif)


Voila qui est fait. Il ne reste plus qu'à valider votre réglage pour voir directement le résultat dans l'aperçu.

![Ressource](../assets/quick-start/display-redy-data/12.gif)

## Fournisseur global

Intéressons nous maintenant au fournisseur global `resources`. Rendez-vous dans la sous-section *Projet/Fournisseurs de données*.

![Ressource](../assets/quick-start/display-redy-data/13.gif)

Vous trouverez ici un designer qui permet de gérer les fournisseurs de données pour toute votre synapp. Vous retrouvez le fournisseur global `resources` dans le plan des acteurs.

Observez qu'il est paramétré pour rafraîchir les données qu'on lui demande toutes les *60 secondes*.

> 📌 **REMARQUE**<br> Vous apprendrez que son mode de récupération de données est *Relatif*, c'est à dire que tant personne ne lui demande de données, il ne récupère ni ne rafraîchit rien.

Pour en savoir plus sur les fournisseurs de données globaux, rendez-vous dans la section [**Fournisseurs de données**](../concepts/project/global-data-sources.md).

Il est tout à fait possible de créer des fournisseurs de données directement dans une scène. Dans ce cas, il sont paramétrable, leur propriétés liable et accessible par script. ce qui donne un contrôle total sur leur utilisation.

Pour en savoir plus, rendez-vous dans la section [**Fournisseurs de variable**](../concepts/actor-types/redy-wos-variable-source.md).

Bien d'autre champ sont accessibles par liaison (la valeur, le nom, ...). Pour en savoir plus, rendez-vous encore dans la section [**Fournisseurs de variable**](../concepts/actor-types/redy-wos-variable-source.md#champ-de-variable-redy).



# Prochaine étape
Maintenant, vous allez [commander une ressource dans le REDY](./command-redy.md).

---------------------

[◀ Publication](./synapp-publish){: .btn } [Commander une ressource ▶](./command-redy.md){: .btn }
