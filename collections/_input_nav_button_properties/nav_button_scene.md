---
title: Scena
section: specifico
propName: displaySceneKey
propPath: properties.displaySceneKey
scriptApiClass: Actor.Input.NavButtonProperties
order: 1
---
La proprietà specifica `Chiave di Scena` consente di definire la scena a cui il pulsante reindirizzerà l'utente.

Nell' ispettore, viene fatto riferimento a tutte le scene del progetto a cui è possibile essere reindirizzati.

Esistono due possibilità quando si seleziona una scena.

- Il campo Chiave dell'attore `Schermo` è lasciato vuoto:
<br>
Il pulsante permette di passare alla scena selezionata..

- Il campo `Chiave dell' attore schermo` viene valorizzato con la chiave di un attore schermo:
<br>
Il pulsante consente di modificare la visualizzazione dell'attore Schermo in base alla scena specificata nella proprietà `Chiave di Scena`.

**Modifica dei parametri di una scena con il tasto di navigazione**

Quando si seleziona la proprietà `Scena`, se la scena selezionata contiene uno o più parametri, viene visualizzata una guida sotto la selezione.

Questa guida permetterà di impostare un valore diverso a un parametro della scena.

Se il valore di questo parametro della scena è collegato a un altro elemento di un attore, anche quest'ultimo cambierà.

Si noti che questa operazione può essere eseguita sulla scena in cui si trova il pulsante di navigazione, quindi è possibile modificare i parametri della scena corrente utilizzando il pulsante..

**Esempio**

Di seguito è riportato un esempio di scena con due pulsanti che modificano un parametro della scena il cui valore è collegato a quello di un attore di testo.

{% raw %}
```
SYNAPPS-STUDIO-SCENE|{"config":{"key":"scene1","name":"Scène 1","additionalDefs":{"prop1":{"type":"text"}},"additionals":{"prop1":"TEST"}},"leadActor":{"type":"layout/stack","key":"stack1","children":[{"type":"input/nav-button","key":"nav-button1","properties":{"content":"Bouton de navigation","displaySceneKey":"scene1"},"additionals":{"prop1":"Hello world !"},"additionalDefs":{"prop1":{"type":"text"}}},{"type":"input/nav-button","key":"nav-button2","properties":{"content":"Bouton de navigation","displaySceneKey":"scene1"},"additionals":{"prop1":"Lorem Ipsum"},"additionalDefs":{"prop1":{"type":"text"}}},{"type":"display/text","key":"text1","properties":{"content":"Voici du texte !"},"bindings":{"properties.content":"stage@additionals.prop1"}}]}}
```
{% endraw %}

>⚠️ **ATTENZIONE**<br>
> Se si vogliono controllare i parametri di una scena attraverso un attore schermo, non bisogna dimenticare di creare i parametri aggiuntivi corrispondenti anche su questo, altrimenti non verrà trasmessa alcuna azione.
