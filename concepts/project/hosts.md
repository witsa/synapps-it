---
title: "Host"
parent: "Progetto"
grand_parent: Concetti
nav_order: 6
---

{% include table_of_content.html %}

# Nel Runtime

Per Synapps, l'host è il sistema che ospita ed esegue il synapp una volta terminato e pubblicato. Contiene gli elementi necessari in temmini di dati e parametrizzazione.

L'host può essere:

- un REDY
- un REDY-PC
<!-- - *prossimamente* un server HighWay -->

L'oggetto host è accessibile tramite collegamento e script.

Contiene la [sessione](../session.md) e ne consente la gestione, tramite script.

> L'host è un oggetto essenziale per l'esecuzione di un synapp.

# In Studio

In un progetto, gli host sono gestiti nella sezione *Progetto/Host*.

![Hôtes](../../assets/hosts.png)

È possibile definire più host, ma uno solo di essi sarà attivo nel progetto e verrà utilizzato per la visualizzazione nel designer o per l'esecuzione del synapp nel browser.

Passando da un host ad un'altro, è possibile visualizzare un synapp su REDY diversi o simulare il funzionamento cambiando tipo di utente sullo stesso REDY.

È in questa scheda che è possibile pubblicare il synapp in un host.

![Hôtes](../../assets/concepts/host-01.png)

## Creazione di un host

Quando si crea un host, è necessario inserire il dominio e le informazioni necessaro per l'accesso. Studio sarà poi in grado di usare l'host attivo per scopi di runtime e di anteprima, se lo si desidera.

## Informazioni

Le informazioni su un host vengono recuperate alla prima connessione. Le informazioni fornite riguardano la natura dell'host, le sue opzioni e il profilo dell'utente.

## Pubblicazione

Il synapp deve essere pubblicato nell'host per essere fruibile dagli utenti.

Studio si occupa di trasformare il progetto e i suoi contenuti in un componente della parametrizzazione nell'host.

![Hôtes](../../assets/concepts/host-02.png)

Se nel progetto si definiscono più host, si potrà gestire la pubblicazione dello stesso synapp su tutti gli host.

> ⚠️ **ATTENZIONE**<br> Ricorda che per pubblicare (o gestire) un synapp su un *REDY* è necessari un profilo minimo di *Installatore* e l'*ADD Intravision*.

Scegliere un host.

![Hôtes](../../assets/quick-start/synapp-publish/02.png)

Una volta fatto il login le informazioni sull'host sono riportate nella colonna centrale.

Nella colonna di destra, si trova l'area dedicata alla gestione dei synapp presenti nell'host.

![Hôtes](../../assets/quick-start/synapp-publish/03.png)

> ⚠️ **ATTENZIONE**<br> Studio identifica ogni synapp attraverso il GUID del progetto. Nel REDY è la *label* che identifica i synapp. È quindi necessario fare attenzione affinché non si sovrascriva un synapp già pubblicato col medesimo *label*.

Per ogni pubblicazione, viene inserito un numero di *build*. Di fatto, questa numero è formato dalla la data in cui è avvenuta la pubblicazione.

![Hôtes](../../assets/quick-start/synapp-publish/05.png)

È possibile vedere come effettuare la pubblicazione nella [Guida introduttiva](../../quick-start/synapp-publish.md).

### Il synapp nella parametrizzazione

Il synapp in un REDY corrisponde a un nodo della *parametrizzazione*:

![Hôtes](../../assets/quick-start/synapp-publish/06.png)

Contiene l'intera struttura ad albero che il runtime Synapps è in grado di interpretare.

![Hôtes](../../assets/quick-start/synapp-publish/07.png)


> ⚠️ **ATTENZIONE**<br> La struttura ad albero non deve essere modificata. Lasciare che Synapps Studio gestisca questa parte della parametrizzazione.

> 📌 **NOTA**<br> Si raccomanda di salvare le impostazioni dopo aver pubblicato il synapp.
