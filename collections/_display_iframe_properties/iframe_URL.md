---
title: URL
section: specifico
propName: url
propPath: properties.url
scriptApiClass: Actor.Display.IframeProperties
order: 1
---

Jolly
{: .label }

Questa proprietà consente di inserire l'URL di un elemento da visualizzare nell'attore.

Questo elemento deve essere un indirizzo che rimanda a una risorsa WEB o, più frequentemente, a una pagina WEB di un sito WEB accessibile.

> ⚠️ **ATTENZIONE**<br>
> Si noti che alcuni siti web vietano l'accesso attraverso un iFrame.

**Accetta caratteri Jolly**

È possibile inserire dei caratteri jolly (ad esempio, {% raw %}`{{jokerKey}}`{% endraw %}) nella definizione dell'URL, che saranno sostituiti dal valore di addizionali con la stessa chiave.

Esempio:

{% raw %}
```URL
https://www.wit-italia.com/{{section}}/
```
{% endraw %}
Une additionnelle de clé `section` de type *texte* remplacera le joker par sa valeur.
