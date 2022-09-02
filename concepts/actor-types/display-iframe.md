---
title: "Visualizzazione | IFrame"
parent: "Tipologie di attori"
grand_parent: Concetti
---

{% include links_actor.md apiClass="Actor.Display.Iframe" %}

# IFrame

L'attore Iframe consente di incorporare una pagina web nella scena.

{% include table_of_content.html %}

# Proprietà specifiche

{% assign sorted = site.display_iframe_properties | sort: 'order' %}

{% for property in sorted %}

{% include actor_property.md property=property %}

{% endfor %}

## Autorizzare gli script

Questa proprietà consente di attivare o disattivare il JavaScript del sito web caricato dall'iFrame.

## Traiter comme même origine

Questa proprietà permette di autorizzare come tali i siti web visualizzati della stessa origine.

Se questa proprietà è disabilitata, le risorse del sito di origine saranno inaccessibili all'iFrame, anche se questo si trova sulla stessa origine. Inoltre, il sito all'interno dell'iFrame avrà un'origine "nulla" che potrebbe impedire alcune richieste e limitare alcuni accessi.

*Per saperne di più sulle origini e sul loro funzionamento:*
La documentazione MDN è disponibile [a questo indirizzo](https://developer.mozilla.org/fr/docs/Web/Security/Same-origin_policy).

## Autorizza i modali

Questa proprietà consente di attivare/disattivare tutti gli avvisi di sistema che possono verificarsi in seguito a un'azione nell'iFrame.

## Autorizza i popup

Questa proprietà consente di abilitare/disabilitare i popup durante la navigazione nel sito web dell'iFrame.

> 📌 **NOTA**<br>
> Questo potrebbe comportare la disattivazione di alcuni moduli di accesso.

## Autorizzare i formes

Questa proprietà consente di abilitare/disabilitare i formulari durante la navigazione nel Synapp.


>⚠️ **ATTENZIONE**<br>
> Se si disattiva questa opzione, non sarà possibile utilizzare i moduli di login, di contatto, ecc...


# Campi d'informazione

## Contenuto completato

{% include field_completed_content.md %}

# Alcuni esempi

## iframe verso REDY

<div class="code-example" markdown="1">

Ecco un esempio di iFrame che mostra una pagina di un REDY.

![SynApps](../../assets/concepts/actor/display_iframe/iframe01.png)

Il campo aggiuntivo *Chemin REDY* permette di definire il path verso la pagina, dalla radice del REDY (in questo caso viene visualizzato il Dashboard).

</div>

```text
SYNAPPS-STUDIO-ACTOR|{"type":"display/iframe","key":"iframe1","properties":{"verticalAlignment":"expand"},"additionalDefs":{"redyPath":{"type":"text","label":"Chemin REDY"}},"additionals":{"redyPath":"/easy/dashboard"},"bindings":{"properties.url":{"sourceType":"relative","sourcePath":"self","path":"additionals.redyPath"}},"events":{"properties/url/binding/onReadTransform":["return  `${this.dataStores.redy.host.domain}/WSID${this.dataStores.redy.host.session.sid}${context.value}`;"]}}
```
