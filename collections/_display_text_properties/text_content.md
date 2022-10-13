---
title: Contenuto
section: specifico
propName: content
propPath: properties.content
scriptApiClass: Actor.Display.TextProperties
order: 1
---

Jolly
{: .label }


La proprietà specifica `contenuto` consente di specificare il testo che l'attore visualizzerà nella scena.


***Esempio:***

**Caso semplice**

Contenuto di base dell'attore:

![SynApps]( {{ site.baseurl }}/assets/concepts/actor/display_text/BaseC.PNG)

Risultato:

![SynApps]( {{ site.baseurl }}/assets/concepts/actor/display_text/BaseT.PNG){: width="450" }


**Jolly**
È possibile inserire dei caratteri jolly nel contenuto., Questi saranno sostituiti dal valore dell'addizionale che presenta la stessa chiave.

Contenuto con Jolly {% raw %}`{{chiave}}`{% endraw %} :

![SynApps]( {{ site.baseurl }}/assets/concepts/actor/display_text/AddiC.PNG)

Risultato nell'Ispettore con l'aggiunta automatica di unaddizionale che contiene un testo:

![SynApps]( {{ site.baseurl }}/assets/concepts/actor/display_text/AddiI.PNG)

Risultato del contenuto dell'attore di testo:

![SynApps]( {{ site.baseurl }}/assets/concepts/actor/display_text/AddiT.PNG){: width="450" }

**Suggerimento:**
La documentazione sui caratteri jolly e sul loro utilizzo è disponibile [a questo indirizzo].().
