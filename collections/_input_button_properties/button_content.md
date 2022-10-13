---
title: Contenuto
section: specifico
propName: content
propPath: properties.content
scriptApiClass: Actor.input.ButtonProperties
order: 1
---

Jolly
{: .label }

Questa proprietà è utilizzata per definire il contenuto HTML dell'attore.

**Esempio**

<div class="code-example" markdown="1">

![SynApps]( {{ site.baseurl }}/assets/concepts/actor/input_button/button01.png)

</div>


```html
Questo è <i>un</i> <b style="background-color: red;">bottone</b>
```


**Caratteri Jolly**

È possibile inserire dei caratteri jolly (ad esempio, {% raw %}`{{jokerKey}}`{% endraw %}) nel contenuto. Questi saranno sostituiti dal valore dell'addizionale con chiave identica.

Esempio:

{% raw %}
```html
Questo è <i>un</i> <b style="background-color: {{theColor}};">bottone</b>.

```
{% endraw %}
Il valore del parametro addizionale `theColor` di tipo *colore* andrà a sostituire la stringa jolly.



> 💡 **Consiglio**<br>
> Mentre è possibile aggiungere uno stile CSS con un tag HTML `<style>`, non è possibile aggiungere codice Javascript.
> Per farlo, è necessario utilizzare gli eventi dell'attore..

