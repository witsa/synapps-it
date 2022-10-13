---
title: "Grafici | Indicatore"
parent: "Elenco attori"
grand_parent: Concetti
---

{% include links_actor.md apiClass="Actor.Charting.GaugeDemo" %}

# Indicatore di valore

![SynApps](../../assets/concepts/actor/charting_gauge/gauge.png)

L'attore Indicatore viene utilizzato per rappresentare graficamente un valore in un intervallo mediante un arco colorato.

{% include table_of_content.html %}

## Personalizzazione

E' possibile personalizzare la propria immagine cambiando i colori
- dell'ago
- dell'arco prima dell'ago
- dell'arco dopo l'ago.
La personalizzazione va oltre, consentendo di definire lo spessore dell'arco e la sua estensione angolare.

## Alcune raccomandazioni

- Non uscire dall'intervallo definito dai limiti, altrimenti l'indicatore non funzionerà correttamente.
- Fissare la larghezza e l'altezza per evitare problemi di ridimensionamento. Se necessario, posizionarlo successivamente in un [Box di visualizzazione](./layout-view-box.md).

## Qualche esempio

### Indicatore spesso senza agoe

<div class="code-example" markdown="1">

![SynApps](../../assets/concepts/actor/charting_gauge/gauge01.png)

</div>
```
SYNAPPS-STUDIO-ACTOR|{"type":"charting/gauge-demo","key":"gauge-demo1","properties":{"height":"200px","width":"350px","gaugeColor":"rgba(224, 224, 224, 0)","gaugeStartColor":"rgba(4, 207, 4, 1)","gaugeWidth":10}}
```

### Indicatore ad anello fine senza ago

<div class="code-example" markdown="1">

![SynApps](../../assets/concepts/actor/charting_gauge/gauge02.png)

</div>
```
SYNAPPS-STUDIO-ACTOR|{"type":"charting/gauge-demo","key":"gauge-demo2","properties":{"height":"200px","width":"350px","gaugeColor":"rgba(224, 224, 224, 0)","gaugeStartColor":"rgba(207, 92, 4, 1)","gaugeWidth":1,"gaugeBackgroundColor":"rgba(194, 194, 194, 0)","gaugeAngle":360,"gaugeValue":80}}
```

### Indicatore ad anello fine senza ago con testo all'interno

<div class="code-example" markdown="1">

![SynApps](../../assets/concepts/actor/charting_gauge/gauge03.gif)

Si noterà che il testo rimane ben centrato e contenuto nell'indicatore grazie a un riquadro di visualizzazione con margini interni.
</div>

```
SYNAPPS-STUDIO-ACTOR|{"type":"layout/stack","key":"stack2","children":[{"type":"layout/canvas","key":"canvas1","properties":{"height":"200px","width":"350px"},"children":[{"type":"charting/gauge-demo","key":"gauge-demo3","properties":{"height":"100%","width":"100%","gaugeColor":"rgba(224, 224, 224, 0)","gaugeStartColor":"rgba(4, 112, 207, 1)","gaugeWidth":1,"gaugeBackgroundColor":"rgba(194, 194, 194, 0)","gaugeAngle":360,"gaugeValue":820,"gaugeMaxValue":1000}},{"type":"layout/view-box","key":"view-box1","properties":{"height":"100%","width":"100%","paddingTop":"35px","paddingBottom":"27px","paddingRight":"115px","paddingLeft":"115px"},"children":[{"type":"layout/stack","key":"stack3","children":[{"type":"display/text","key":"text1","properties":{"lineHeight":"0.9em"},"bindings":{"properties.content":{"sourceType":"actor","sourceKey":"gauge-demo3","path":"properties.gaugeValue"},"properties.color":{"sourceType":"actor","sourceKey":"gauge-demo3","path":"properties.gaugeStartColor"}}},{"type":"display/text","key":"text2","properties":{"content":"kWh","horizontalAlignment":"middle","fontSize":"0.3em"},"bindings":{"properties.color":{"sourceType":"actor","sourceKey":"gauge-demo3","path":"properties.gaugeStartColor"}}}]}]}]},{"type":"input/text-box","key":"text-box1","properties":{"width":"350px","inputType":"range","min":0,"max":1000,"step":5},"bindings":{"properties.value":{"sourceType":"actor","sourceKey":"gauge-demo3","path":"properties.gaugeValue","canWrite":true}}}]}
```
