---
title: Animazione di elementi della serie in diapositive Java
linktitle: Animazione di elementi della serie in diapositive Java
second_title: Aspose.Slides API di elaborazione Java PowerPoint
description: Scopri come animare gli elementi della serie nelle diapositive di PowerPoint utilizzando Aspose.Slides per Java. Segui questa guida passo passo completa con il codice sorgente per migliorare le tue presentazioni.
weight: 12
url: /it/java/animation-and-layout/animating-series-elements-java-slides/
---

{< blocks/products/pf/main-wrap-class >}
{< blocks/products/pf/main-container >}
{< blocks/products/pf/tutorial-page-section >}


## Introduzione all'animazione degli elementi della serie nelle diapositive Java

In questo tutorial, ti guideremo attraverso l'animazione degli elementi della serie nelle diapositive di PowerPoint utilizzando Aspose.Slides per Java. Le animazioni possono rendere le tue presentazioni più coinvolgenti e informative. In questo esempio ci concentreremo sull'animazione di un grafico in una diapositiva di PowerPoint.

## Prerequisiti

Prima di iniziare, assicurati di avere quanto segue:

- Aspose.Slides per la libreria Java installata.
- Una presentazione PowerPoint esistente con un grafico che desideri animare.
- Configurazione dell'ambiente di sviluppo Java.

## Passaggio 1: caricare la presentazione

 Per prima cosa devi caricare la presentazione di PowerPoint che contiene il grafico che desideri animare. Sostituire`"Your Document Directory"` con il percorso effettivo della directory dei documenti.

```java
String dataDir = "Your Document Directory";
Presentation presentation = new Presentation(dataDir + "ExistingChart.pptx");
```

## Passaggio 2: ottieni un riferimento al grafico

Una volta caricata la presentazione, ottieni un riferimento al grafico che desideri animare. In questo esempio presupponiamo che il grafico si trovi nella prima diapositiva.

```java
ISlide slide = presentation.getSlides().get_Item(0);
IShapeCollection shapes = slide.getShapes();
IChart chart = (IChart) shapes.get_Item(0);
```

## Passaggio 3: aggiungi effetti di animazione

 Ora aggiungiamo effetti di animazione agli elementi del grafico. Utilizzeremo il`slide.getTimeline().getMainSequence().addEffect()` metodo per specificare come deve animarsi il grafico.

```java
// Anima l'intero grafico
slide.getTimeline().getMainSequence().addEffect(chart, EffectType.Fade, EffectSubtype.None, EffectTriggerType.AfterPrevious);

// Anima i singoli elementi della serie (puoi personalizzare questa parte)
for (int seriesIndex = 0; seriesIndex < chart.getChartData().getSeries().size(); seriesIndex++) {
    for (int pointIndex = 0; pointIndex < chart.getChartData().getSeries().get_Item(seriesIndex).getPoints().size(); pointIndex++) {
        ((Sequence) slide.getTimeline().getMainSequence()).addEffect(chart, EffectChartMinorGroupingType.ByElementInSeries, seriesIndex, pointIndex, EffectType.Appear, EffectSubtype.None, EffectTriggerType.AfterPrevious);
    }
}
```

Nel codice sopra, animiamo prima l'intero grafico con un effetto "Dissolvenza". Quindi, passiamo in rassegna le serie e i punti all'interno del grafico e applichiamo un effetto "Appare" a ciascun elemento. È possibile personalizzare il tipo di animazione e attivarla secondo necessità.

## Passaggio 4: salva la presentazione

Infine, salva la presentazione modificata con le animazioni in un nuovo file.

```java
presentation.save(dataDir + "AnimatingSeriesElements_out.pptx", SaveFormat.Pptx);
```

## Codice sorgente completo per l'animazione di elementi della serie nelle diapositive Java

```java
// Il percorso della directory dei documenti.
String dataDir = "Your Document Directory";
// Carica una presentazione
Presentation presentation = new Presentation(dataDir + "ExistingChart.pptx");
try
{
	// Ottieni il riferimento dell'oggetto grafico
	ISlide slide = presentation.getSlides().get_Item(0);
	IShapeCollection shapes = slide.getShapes();
	IChart chart = (IChart) shapes.get_Item(0);
	// Animare gli elementi della serie
	slide.getTimeline().getMainSequence().addEffect(chart, EffectType.Fade, EffectSubtype.None, EffectTriggerType.AfterPrevious);
	((Sequence) slide.getTimeline().getMainSequence()).addEffect(chart, EffectChartMinorGroupingType.ByElementInSeries, 0, 0, EffectType.Appear, EffectSubtype.None, EffectTriggerType.AfterPrevious);
	((Sequence) slide.getTimeline().getMainSequence()).addEffect(chart, EffectChartMinorGroupingType.ByElementInSeries, 0, 1, EffectType.Appear, EffectSubtype.None, EffectTriggerType.AfterPrevious);
	((Sequence) slide.getTimeline().getMainSequence()).addEffect(chart, EffectChartMinorGroupingType.ByElementInSeries, 0, 2, EffectType.Appear, EffectSubtype.None, EffectTriggerType.AfterPrevious);
	((Sequence) slide.getTimeline().getMainSequence()).addEffect(chart, EffectChartMinorGroupingType.ByElementInSeries, 0, 3, EffectType.Appear, EffectSubtype.None, EffectTriggerType.AfterPrevious);
	((Sequence) slide.getTimeline().getMainSequence()).addEffect(chart, EffectChartMinorGroupingType.ByElementInSeries, 1, 0, EffectType.Appear, EffectSubtype.None, EffectTriggerType.AfterPrevious);
	((Sequence) slide.getTimeline().getMainSequence()).addEffect(chart, EffectChartMinorGroupingType.ByElementInSeries, 1, 1, EffectType.Appear, EffectSubtype.None, EffectTriggerType.AfterPrevious);
	((Sequence) slide.getTimeline().getMainSequence()).addEffect(chart, EffectChartMinorGroupingType.ByElementInSeries, 1, 2, EffectType.Appear, EffectSubtype.None, EffectTriggerType.AfterPrevious);
	((Sequence) slide.getTimeline().getMainSequence()).addEffect(chart, EffectChartMinorGroupingType.ByElementInSeries, 1, 3, EffectType.Appear, EffectSubtype.None, EffectTriggerType.AfterPrevious);
	((Sequence) slide.getTimeline().getMainSequence()).addEffect(chart, EffectChartMinorGroupingType.ByElementInSeries, 2, 0, EffectType.Appear, EffectSubtype.None, EffectTriggerType.AfterPrevious);
	((Sequence) slide.getTimeline().getMainSequence()).addEffect(chart, EffectChartMinorGroupingType.ByElementInSeries, 2, 1, EffectType.Appear, EffectSubtype.None, EffectTriggerType.AfterPrevious);
	((Sequence) slide.getTimeline().getMainSequence()).addEffect(chart, EffectChartMinorGroupingType.ByElementInSeries, 2, 2, EffectType.Appear, EffectSubtype.None, EffectTriggerType.AfterPrevious);
	((Sequence) slide.getTimeline().getMainSequence()).addEffect(chart, EffectChartMinorGroupingType.ByElementInSeries, 2, 3, EffectType.Appear, EffectSubtype.None, EffectTriggerType.AfterPrevious);
	// Scrivere il file di presentazione su disco
	presentation.save(dataDir + "AnimatingSeriesElements_out.pptx", SaveFormat.Pptx);
}
finally
{
	if (presentation != null) presentation.dispose();
}
```

## Conclusione

Hai imparato come animare gli elementi della serie nelle diapositive di PowerPoint utilizzando Aspose.Slides per Java. Le animazioni possono migliorare le tue presentazioni e renderle più coinvolgenti. Personalizza gli effetti di animazione e i trigger in base alle tue esigenze specifiche.

## Domande frequenti

### Come posso personalizzare l'animazione per i singoli elementi del grafico?

È possibile personalizzare l'animazione per i singoli elementi del grafico modificando il tipo di animazione e l'attivazione nel codice. Nel nostro esempio, abbiamo utilizzato l'effetto "Appare", ma puoi scegliere tra vari tipi di animazione come "Dissolvenza", "Vola in entrata" ecc. e specificare diversi attivatori come "Al clic", "Dopo precedente" o "Con precedente."

### Posso applicare animazioni ad altri oggetti in una diapositiva di PowerPoint?

 Sì, puoi applicare animazioni a vari oggetti in una diapositiva di PowerPoint, non solo ai grafici. Usa il`addEffect` metodo per specificare l'oggetto che si desidera animare e le proprietà di animazione desiderate.

### Come posso integrare Aspose.Slides per Java nel mio progetto?

Per integrare Aspose.Slides per Java nel tuo progetto, devi includere la libreria nel tuo percorso di creazione o utilizzare strumenti di gestione delle dipendenze come Maven o Gradle. Fare riferimento alla documentazione di Aspose.Slides per istruzioni dettagliate sull'integrazione.

### C'è un modo per visualizzare in anteprima le animazioni nell'applicazione PowerPoint?

Sì, dopo aver salvato la presentazione, puoi aprirla nell'applicazione PowerPoint per visualizzare in anteprima le animazioni e apportare ulteriori modifiche, se necessario. PowerPoint fornisce una modalità di anteprima a questo scopo.

### Sono disponibili opzioni di animazione più avanzate in Aspose.Slides per Java?

Sì, Aspose.Slides per Java offre un'ampia gamma di opzioni di animazione avanzate, inclusi percorsi di movimento, tempistica e animazioni interattive. Puoi esplorare la documentazione e gli esempi forniti da Aspose.Slides per implementare animazioni avanzate nelle tue presentazioni.
{< /blocks/products/pf/tutorial-page-section >}

{< /blocks/products/pf/main-container >}
{< /blocks/products/pf/main-wrap-class >}

{< blocks/products/products-backtop-button >}
