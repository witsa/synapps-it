---
title: "Aggiuntivo"
parent: Concetti
nav_order: 7
---

{% include table_of_content.html %}

# Proprietà aggiuntive

Le proprietà aggiuntive  sono proprietà come quelle che si trovano sugli attori, ma che è possibile aggiungere anche ad altri oggetti Synapps.

Il vantaggio è che, una volta creata, questa nuova proprietà è disponibile nell'inspettore dell'oggetto a cui appartiene.

Gli attori, le scene e i compositi possono ospitare proprietà aggiuntive. È così che si creano i parametri della scena e le proprietà specifiche di un composito.

Un Aggiuntivo può essere la sede o la fonte di un [binding](./binding.md). Può essere utilizzato in uno script. Dà anche origine a [eventi di cambio di valore delle proprietà](./scripts/actor-life-cycle.md#property-value-change-of-actor).

## Parametri comuni

### Chiave
Un aggiuntivo è identificato attraverso la sua chiave, che deve essere unica e specifica all'oggetto al quale appartiene.

### Nome
Nell'ispettore è possibile definire il nome che apparirà davanti alla proprietà creata. Se non viene impostato, la sua chiave verrà utilizzata come nome.

### Descrizione

È possibile descrivere la proprietà aggiuntiva per aiutare a capirne la funzione. La descrizione vene visualizzata al passaggio del mouse sul nome della proprietà.

### Aiuto
Si può definire un testo di aiuto che viene visualizzato sotto la proprietà.

### Vuoto accettato?

Questa opzione consente di indicare se l'aggiuntivo può essere vuoto o meno.

### Sola lettura?

In alcuni casi è richiesto che la proprietà aggiuntiva non sia modificbile. Questa opzione consente di disabilitare la modifica.

### Modifica

Nel caso di proprietà aggiuntive di tipo attore e composito, è possibile specificare il tipo di modifica che il componente aggiuntivo causa nel suo ciclo di vita. Vedere la sezione che spiega le [modifiche]](./scripts/actor-life-cycle.md#changement-de-valeur-de-propriété-dun-acteur)

### Presente nell'URL ?

Nel caso di un parametro di Scena, è possibile stabilire se questo deve apparire nell'URL. Vedi la sezione che spiega i [parametri di una scena](./scene.md#paramètres-de-scène)

## Tipo si aggiuntivo

Esistono diversi tipi di parametri aggiuntivi:

- Testo

Permette di creare una proprietà per l'inserimento di un testo.

- Numero

Permette di creare una proprietà per l'inserimento di un numero.

È possibile anche definire un massimo e un minimo, nonché il passo quando si cambia il valore trascinandolo. È possibile aggiungere un'unità.

- Taglia

Permet d'obtenir une propriété pour saisir une taille. Ressemble à la propriété *Nombre* mais permet en plus de gérer les unités de type taille.

Il est possible de définir la valeur neutre.

Voir [la section qui explique les unités de taille](./sizes.md)

- Booléen

Permet d'obtenir une propriété avec un bouton à bascule.

- Image

Permet d'obtenir une propriété pour ajouter une image.

- Couleur

Permet d'obtenir une propriété pour saisir une couleur.

- Icône
Permet d'obtenir une propriété pour obtenir la clé d'une icône de la bibliothèque de Synapps.

<!-- ![image](https://user-images.githubusercontent.com/35595723/124151000-646ede80-da92-11eb-8003-4235f467aaa1.png) -->

- Date

Permet d'obtenir une propriété pour saisir une date avec en option une date minimum et une date maximum.

- Sélection simple **ALPHA**

Permettra dans un avenir proche la saisie d'un option parmi une liste.

- Sélection multiple **ALPHA**

Permettra dans un avenir proche la saisie de plusieurs options parmi une liste.

- Acteur

Permet de choisir la clé d'un acteur parmi ceux de la scène ou du composite courant. Une option permet d'activer ou pas la possibilité de choisir l'acteur actuel. Il est possible de filtrer les acteurs disponibles par leur type.

- Scène

Permet de choisir la clé d'une scène parmi celles de la synapp. Une option permet d'activer ou pas la possibilité de choisir la scène actuelle.

- Composite

Permet de choisir la clé d'un composite parmi ceux de la synapp. Une option permet d'activer ou pas la possibilité de choisir le composite actuel.


- Chemin de variable

Permet de choisir un chemin de variable REDY. Plusieurs options permettent d'affiner les possibilités affichée par l'explorateur de variable.

### Additionnelles de complément

Dans certains types d'acteur, des additionnelles peuvent être utilisées pour compléter des définitions de propriétés. C'est le cas pas exemple des acteurs à contenu comme le [bouton](./actor-types/input-button.md) ou il est possible de compléter des jokers par les valeurs d'additionnelle.

Les paramètres de scènes sont renseignés par des addtionnelles également dans les acteur écran pour paramétrer la scène choisie.
