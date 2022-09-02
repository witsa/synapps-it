---
title: Contenuto
section: specifici
propName: content
propPath: properties.content
scriptApiClass: Actor.Display.HtmlProperties
order: 7
---

Stringa Jolly
{: .label }

Questa proprietà consente di definire il contenuto HTML dell'attore..

**Esempio:**

```html
<div style="background-color: red;">
    <p>
        Ceci est <i>un</i> <b>paragraphe</b>.
    </p>
</div>
```
Résultat :
<div style="background-color: red;">
    <p>
        Questo è <i>un</i> <b>paragrafo</b>.
    </p>
</div>

**Jokerable**

È possibile inserire stringhe Jolly (ex.: {% raw %}`{{jokerKey}}`{% endraw %}) nel codice. La stringa verrà sostituita dal valore del parametro aggiuntico con chiave identica.

Esempio:

{% raw %}
```html
<div style="background-color: {{theColor}};">
    <p>
        Questo è un paragrafo.
    </p>
</div>
```
{% endraw %}
Il valore del parametro addizionale con chiave `theColor` di tipo *colore* si sostituirà alla stringa jolly.

> 💡 **CONSIGLIO**<br>
> Mentre è possibile aggiungere uno stile CSS con un tag HTML `<style>`,non è possibile aggiungere codice Javascript.
> A tale scopo, è necessario utilizzare gli eventi dell'attore.

