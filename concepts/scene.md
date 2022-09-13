---
title: "La Scena"
parent: Concetti
nav_order: 3
---
{% include table_of_content.html %}


La scena è l'oggetto di synapp che contiene gli altri oggetti del progetto e definisce il layout dell'interfaccia visualizzata.

# Scena di avvio

Quando si avvia il synapp, viene visualizzata una prima scena, la **scena di avvio**. È definita nell'elenco delle scene di Studio ed è materializzata dalla presenza dell' icona ![scène de démarrage](../assets/start-scene-icon.png).

![SynApps]( {{ site.baseurl }}/assets/concepts/scene/scene-start.png)

# Visualizzazione della scena

Gli attori [pulsanti di navigazione](./actor-types/input-nav-button.md) permettono di cambiare la scena presentata dal synapp.

L'attore [Schermo](./actor-types/display-screen.md) permette di visualizzare un'altra scena all'interno di una scena.

Naturalmente, è possibile controllare la visualizzazione delle scene tramite collegamenti o script.

# Campi in una scena

## Chiave

Una scena è identificata dalla sua chiave. LA chiave deve essere univoca all'interno di un synapp.

> ✔️ **CONSGLIO**<br>
Si raccomanda di nominare la chiave di una scena in modo che corrisponda a ciò che verrà visualizzato.

## Nome

Normalmente, in Studio, una scena è caratterizzata dal suo nome. Occorre sceglierlo bene per illustrare ciò che verrà visualizzato.

## Esclusione

Una scena può essere esclusa dalla pubblicazione in una ULI. Questa scena sarà presente solo nel progetto. Può essere utile per definire scene di prova che non appariranno nel synapp finale.

## Impostazioni della scena

È possibile definire componenti aggiuntivi per configurare una scena. [vedi parametri aggiuntivi](./additionals.md)
Questi componenti aggiuntivi sono ovviamente accessibili tramite collegamento e script

In questo caso dispongono di un'opzione supplementare: la possibilità di visualizzare il parametro nell'`URL` del browser. In questo modo, è possibile impostare una scena direttamente dal suo indirizzo di accesso.

## Attori

Gli [Attori](./actor/index.md) sono gli elementi che definiscono l'interfaccia di una scena. Vengono presentati come una struttura ad albero che parte dall' **attore principale**.

![SynApps](../assets/scene-actors.png)

# Elenco delle scene

L'elenco delle scene in Studio consiste in una struttura ad albero composta da cartelle in cui sono memorizzate le scene del progetto.

![SynApps]( {{ site.baseurl }}/assets/concepts/scene/scene-start.png)

La gestione delle cartelle e delle scene si effettua attraverso le azioni contenute nel menu contestuale di ciascun elemento.

## Aggiunta di una scena

Per aggiungere una scena, fare clic con il tasto destro del mouse su una cartella. Il menu contestuale consente di selezionare la scena di base da aggiungere tra le opzioni disponibili.
Attualmente esistono solo due scene di base: una scena vuota e il modello di scena predefinito.

![SynApps]( {{ site.baseurl }}/assets/concepts/scene/new-scene.png)

### Copia/Incolla della scena

È possibile copiare una scena negli appunti utilizzando il menu contestuale.

È possibile incollare ovunque questa scena, sempre utilizzando il menu:
- in una cartella del progetto (verrà duplicata)
- in un altro progetto
- in un'e-mail per condividerla.
- in un file da archiviare
- o, come in questo caso, come esempio.

> ⚠️ **ATTENZIONE**<br>
> Viene copiata solo la scena, non gli elementi della libreria che potrebbe utilizzare.

## Aggiunta di una cartella

Come per le scene, è possibile aggiungere una nuova cartella visualizzando il menu della cartella a cui si desidera aggiungerla.
L'azione che consente di modificare il nome di una cartella si trova nel suo menu contestuale.

# Designer di scena

In Studio, quando si fa clic su una scena nell'elenco, viene visualizzato il **Designer** della scena. Questa interfaccia consente di realizzare integralmente la scena.

Nel Designer è possibile gestire i campi della scena e l'albero degli attori che la scena presenta.

![SynApps](../assets/quick-start/designer-first-steps/02.png)

- Al centro viene visualizzata la **struttura** della scena <span style="color: red;">**A**</span>.
- Sotto l'elenco delle scene, a sinistra, si trova la **mappa degli attori**  <span style="color: red;">**B**</span>.
- A destra si trova l'**ispettore** dell'oggetto selezionato nel pannello di sinistra.  <span style="color: red;">**C**</span>.

# Esempi di Scene

Di seguito si trovano una serie di scene che potranno essere copiare e incollare liberamente nelle vostre creazioni.

## Hub scelta del formato
Ecco una scena che, una volta impostata come scena d'avvio, naviga automaticamente nel progetto verso una scena realizzata per il modello Desktop/Tablet o verso una scena realizzata per il modello Smartphone. La scena corretta viene scelta in base alla risoluzione del display e alla presenza di funzioni touch.

Le scene di destinazione devono essere definite nei parametri della scena.


{% raw %}
```text
SYNAPPS-STUDIO-SCENE|{"config":{"key":"hub","name":"Hub","additionalDefs":{"desktopMaster":{"type":"scene","label":"Gabarit Desktop","helperTxt":"Scène de Gabarit pour PC et tablette"},"smartphoneMaster":{"type":"scene","label":"Gabarit Smartphone","helperTxt":"Scène de Gabarit pour Smartphone"},"size":{"type":"number","label":"Taille limite","unit":"px"}},"additionals":{"size":760}},"leadActor":{"key":"stack1","type":"layout/stack","properties":{"verticalAlignment":"expand"},"events":{"onInit":["const smartphoneMaster = this.scene.additionals.smartphoneMaster;","const desktopMaster = this.scene.additionals.desktopMaster;","const size = this.scene.additionals.size || 760;","const isEmpty = context.utils.isEmpty;","if (isEmpty(smartphoneMaster) || isEmpty(smartphoneMaster)) return;","this._navTimeout = setTimeout(() => {","  if (this.isDestroyed || this.isDestroying) return;","  if (this.synapp.isInDesigner) return;","  var isSmallScreen = window.matchMedia(`only screen and (max-width: ${size}px), only screen and (max-height: ${size}px)`);","  var isTouchEnabled = 'ontouchstart' in window || navigator.maxTouchPoints > 0 || navigator.msMaxTouchPoints > 0;","  var hasMouse = Boolean(window.matchMedia('(hover: hover) and (pointer: fine)').matches);","  if (isSmallScreen.matches && isTouchEnabled && !hasMouse) {","    this.synapp.navigate(this.scene.additionals.smartphoneMaster);","  } else {","    this.synapp.navigate(this.scene.additionals.desktopMaster);","  }","}, 500);"],"onDestroy":["if (this._navTimeout) clearTimeout(this._navTimeout);"]}}}
```
{% endraw %}
