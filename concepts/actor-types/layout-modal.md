---
title: "Disposizione | Modale"
parent: "Elenco attori"
grand_parent: Concetti
---


{% include links_actor.md apiClass="Actor.Layout.Modal" %}

# Modale

Attore che consente di visualizzare una finestra di dialogo o un menu.

![SynApps](../../assets/concepts/actor/modal/sample-01.gif)

{% include table_of_content.html %}

# Proprietà

## Mostra?

La proprietà *Mostra?* permette di visualizzare/nascondere la modale.

> 💡 **SUGGERIMENTO**<br>
> Attivare questa proprietà nel designer per visualizzare il contenuto della modale o per regolarne la posizione..


## Si chiude se si clicca altrove

Questa proprietà consente/impedisce la chiusura della finestra modale se l'utente fa clic al di fuori di essa.

> ⚠️ **ATTENZIONE**<br>
Se non si consente questo modo di procedere, è necessario definire un pulsante per chiudere la finestra modale.

## Sovrapposizione trasparente

Abilita/disabilita la presenza di uno sfondo opalescente trasparente dietro il modale.


## Ancoraggio della modale

Per impostazione predefinita, la finestra di dialogo viene visualizzata al centro dello schermo. È possibile definire un ancoraggio completamente diverso.

Per ancorare il modale, ci sono tre punti da osservare:
- *L'attore collegato:* per impostazione predefinita, nessun attore è collegato alla modale. Ma se se ne definisce uno, la finestra modale si posizionerà in relazione ad esso.
- *Ancoraggio orizzontale/verticale della modale:* queste due proprietà definiscono un punto della modale che sarà il suo ancoraggio. È questo punto che verrà agganciato a quello dell'attore collegato.
- *Ancoraggio orizzontale/verticale dell'attore collegato:* queste due proprietà definiscono un punto dell'attore collegato che sarà il suo ancoraggio. È questo punto che verrà ancorato a quello della modale.

Nell'esempio seguente, la <span style="color: red;">**modale**</span> è collegata a un <span style="color: green;">**pulsante**</span> e il suo ancoraggio è materializzato da un cerchio rosso, mentre l'ancoraggio sul pulsante è verde:

![SynApps](../../assets/concepts/actor/modal/sample-02.gif)



## Superamento dei contenuti

{% include property_overflow.md %}

Il valore predefinito è **Nascosto**.

> ✔️ **CONSIGLIO**<br>
> Se il contenuto non è visibile, è molto probabile che sia a causa delle dimensioni ridotte dell'attore padre.


# Eventi

{% include events_layout.md %}

# Uso

Il modale è un attore di layout che accetta solo **un figlio**. In generale, vi si colloca un attore impilamento che contiene l'interfaccia di dialogo.

> ✔️ **CONSIGLIO**<br>
> Collocare il più spesso possibile le modali in fondo all'albero degli attori. In questo modo si evita che il loro contenuto interferisca con la visualizzazione di altri attori del designer.

> ⚠️ **ATTENZIONE**<br>
> Non dimenticare di impostare una dimensione per la modale altrimenti non verrà visualizzata correttamente.
.

# Annullamento dell'ereditarietà delle proprietà

In un modale l'ereditarietà delle proprietà è interrotta. È necessario ridefinire queste proprietà internamente.

Ad esempio, se si imposta una dimensione del testo di 10px sull'attore principale di una scena, tale dimensione non verrà applicata alla finestra modale.

# Varianti

## Modale au clic

Questa variante di modale è preconfigurata per indicare l'attore che attiverà la sua visualizzazione quando si fa clic e l'attore che attiverà la sua chiusura.
