---
title: Animazione
section: effetti
propName: animation
propPath: properties.animation
scriptApiClass: Actor.BaseActorProperties
order: 8
---

Questa proprietà consente di definire animazioni CSS sull'attore.

Per dichiarare un'animazione su un attore, è necessario prima definire l'animazione CSS da utilizzare

A tal fine, è possibile : 
- utilizzare un'animazione incorporata nel CSS del runtime Synapps ([vedi Strumenti CSS]())
- definire l'animazione in un'inclusione CSS ([vedi inclusioni]())
- o creare un `Attore HTML` che conterrà la definizione dell'animazione.

Esempio di `Attore HTML`.

Il contenuto di questo `Attore HTML` deve essere il seguente:
```html
<style>

  @keyframes myAnimationName {
    introduzione all'animazione
  }

</style>
```

Definisce un'animazione con il nome `myAnimationName` (da modificare).

Tale animazione può essere utilizzata da qualsiasi altro attore, attraverso il suo nome, nel seguente modo:

![SynApps]( {{ site.baseurl }}/assets/concepts/actor/base_properties/animation/Animation.PNG)



**Suggerimento:**
La documentazione sulle animazioni CSS è disponibile [a questo indirizzo](https://developer.mozilla.org/fr/docs/Web/CSS/animation).
