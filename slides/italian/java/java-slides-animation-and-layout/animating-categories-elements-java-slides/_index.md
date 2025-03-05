---
title: Animazione degli elementi delle categorie nelle diapositive Java
linktitle: Animazione degli elementi delle categorie nelle diapositive Java
second_title: Aspose.Slides API di elaborazione Java PowerPoint
description: Ottimizza le tue presentazioni Java con Aspose.Slides per Java. Scopri passo dopo passo come animare gli elementi delle categorie nelle diapositive di PowerPoint.
type: docs
weight: 10
url: /it/java/animation-and-layout/animating-categories-elements-java-slides/
---

## Introduzione all'animazione degli elementi delle categorie nelle diapositive Java

In questo tutorial, ti guideremo attraverso il processo di animazione degli elementi di categoria nelle diapositive Java utilizzando Aspose.Slides per Java. Questa guida passo passo ti fornirà il codice sorgente e le spiegazioni per aiutarti a ottenere questo effetto di animazione.

## Prerequisiti

Prima di iniziare, assicurati di avere quanto segue:

- Aspose.Slides per API Java installata.
- Una presentazione PowerPoint esistente contenente un grafico. Animerai gli elementi della categoria di questo grafico.

## Passaggio 1: importa la libreria Aspose.Slides

Per iniziare, importa la libreria Aspose.Slides nel tuo progetto Java. Puoi scaricare e aggiungere la libreria al classpath del tuo progetto. Assicurati di aver configurato le dipendenze necessarie.

## Passaggio 2: carica la presentazione

```java
// Il percorso della directory dei documenti.
String dataDir = "Your Document Directory";
Presentation presentation = new Presentation(dataDir + "ExistingChart.pptx");
```

 In questo codice carichiamo una presentazione PowerPoint esistente che contiene il grafico che desideri animare. Sostituire`"Your Document Directory"` con il percorso effettivo della directory dei documenti.

## Passaggio 3: ottieni un riferimento all'oggetto grafico

```java
ISlide slide = presentation.getSlides().get_Item(0);
IShapeCollection shapes = slide.getShapes();
IChart chart = (IChart) shapes.get_Item(0);
```

Otteniamo un riferimento all'oggetto grafico nella prima diapositiva della presentazione. Regolare l'indice della diapositiva (`get_Item(0)`) e indice di forma (`get_Item(0)`) secondo necessità per accedere al grafico specifico.

## Passaggio 4: animare gli elementi delle categorie

```java
slide.getTimeline().getMainSequence().addEffect(chart, EffectType.Fade, EffectSubtype.None, EffectTriggerType.AfterPrevious);

for (int i = 0; i < chart.getChartData().getCategories().size(); i++) {
    for (int j = 0; j < chart.getChartData().getSeries().size(); j++) {
        ((Sequence) slide.getTimeline().getMainSequence()).addEffect(chart, EffectChartMinorGroupingType.ByElementInCategory, i, j, EffectType.Appear, EffectSubtype.None, EffectTriggerType.AfterPrevious);
    }
}
```

Animiamo gli elementi delle categorie all'interno del grafico. Questo codice aggiunge un effetto di dissolvenza all'intero grafico e quindi aggiunge un effetto "Appare" a ciascun elemento all'interno di ciascuna categoria. Regola il tipo e il sottotipo dell'effetto secondo necessità.

## Passaggio 5: salva la presentazione

```java
presentation.save(dataDir + "AnimatingCategoriesElements_out.pptx", SaveFormat.Pptx);
```

 Infine, salva la presentazione modificata con il grafico animato in un nuovo file. Sostituire`"AnimatingCategoriesElements_out.pptx"` con il nome del file di output desiderato.


## Codice sorgente completo per animare gli elementi delle categorie nelle diapositive Java
```java
// Il percorso della directory dei documenti.
String dataDir = "Your Document Directory";
Presentation presentation = new Presentation(dataDir + "ExistingChart.pptx");
try
{
	// Ottieni il riferimento dell'oggetto grafico
	ISlide slide = presentation.getSlides().get_Item(0);
	IShapeCollection shapes = slide.getShapes();
	IChart chart = (IChart) shapes.get_Item(0);
	// Animare gli elementi delle categorie
	slide.getTimeline().getMainSequence().addEffect(chart, EffectType.Fade, EffectSubtype.None, EffectTriggerType.AfterPrevious);
	((Sequence) slide.getTimeline().getMainSequence()).addEffect(chart, EffectChartMinorGroupingType.ByElementInCategory, 0, 0, EffectType.Appear, EffectSubtype.None, EffectTriggerType.AfterPrevious);
	((Sequence) slide.getTimeline().getMainSequence()).addEffect(chart, EffectChartMinorGroupingType.ByElementInCategory, 0, 1, EffectType.Appear, EffectSubtype.None, EffectTriggerType.AfterPrevious);
	((Sequence) slide.getTimeline().getMainSequence()).addEffect(chart, EffectChartMinorGroupingType.ByElementInCategory, 0, 2, EffectType.Appear, EffectSubtype.None, EffectTriggerType.AfterPrevious);
	((Sequence) slide.getTimeline().getMainSequence()).addEffect(chart, EffectChartMinorGroupingType.ByElementInCategory, 0, 3, EffectType.Appear, EffectSubtype.None, EffectTriggerType.AfterPrevious);
	((Sequence) slide.getTimeline().getMainSequence()).addEffect(chart, EffectChartMinorGroupingType.ByElementInCategory, 1, 0, EffectType.Appear, EffectSubtype.None, EffectTriggerType.AfterPrevious);
	((Sequence) slide.getTimeline().getMainSequence()).addEffect(chart, EffectChartMinorGroupingType.ByElementInCategory, 1, 1, EffectType.Appear, EffectSubtype.None, EffectTriggerType.AfterPrevious);
	((Sequence) slide.getTimeline().getMainSequence()).addEffect(chart, EffectChartMinorGroupingType.ByElementInCategory, 1, 2, EffectType.Appear, EffectSubtype.None, EffectTriggerType.AfterPrevious);
	((Sequence) slide.getTimeline().getMainSequence()).addEffect(chart, EffectChartMinorGroupingType.ByElementInCategory, 1, 3, EffectType.Appear, EffectSubtype.None, EffectTriggerType.AfterPrevious);
	((Sequence) slide.getTimeline().getMainSequence()).addEffect(chart, EffectChartMinorGroupingType.ByElementInCategory, 2, 0, EffectType.Appear, EffectSubtype.None, EffectTriggerType.AfterPrevious);
	((Sequence) slide.getTimeline().getMainSequence()).addEffect(chart, EffectChartMinorGroupingType.ByElementInCategory, 2, 1, EffectType.Appear, EffectSubtype.None, EffectTriggerType.AfterPrevious);
	((Sequence) slide.getTimeline().getMainSequence()).addEffect(chart, EffectChartMinorGroupingType.ByElementInCategory, 2, 2, EffectType.Appear, EffectSubtype.None, EffectTriggerType.AfterPrevious);
	((Sequence) slide.getTimeline().getMainSequence()).addEffect(chart, EffectChartMinorGroupingType.ByElementInCategory, 2, 3, EffectType.Appear, EffectSubtype.None, EffectTriggerType.AfterPrevious);
	// Scrivere il file di presentazione su disco
	presentation.save(dataDir + "AnimatingCategoriesElements_out.pptx", SaveFormat.Pptx);
}
finally
{
	if (presentation != null) presentation.dispose();
}
```

## Conclusione

Hai animato con successo gli elementi della categoria in una diapositiva Java utilizzando Aspose.Slides per Java. Questa guida passo passo ti ha fornito il codice sorgente e le spiegazioni necessari per ottenere questo effetto di animazione nelle tue presentazioni PowerPoint. Sperimenta diversi effetti e impostazioni per personalizzare ulteriormente le tue animazioni.

## Domande frequenti

### Come posso personalizzare gli effetti di animazione?

 Puoi personalizzare gli effetti di animazione modificando il file`EffectType` E`EffectSubtype` parametri quando si aggiungono effetti agli elementi del grafico. Fare riferimento alla documentazione Aspose.Slides per Java per maggiori dettagli sugli effetti di animazione disponibili.

### Posso applicare queste animazioni ad altri tipi di grafici?

Sì, puoi applicare animazioni simili ad altri tipi di grafici modificando il codice per indirizzare gli elementi specifici del grafico che desideri animare. Regolare di conseguenza la struttura del loop e i parametri.

### Come posso saperne di più su Aspose.Slides per Java?

 Per documentazione completa e risorse aggiuntive, visitare il[Aspose.Slides per riferimento API Java](https://reference.aspose.com/slides/java/) . Puoi anche scaricare la libreria da[Qui](https://releases.aspose.com/slides/java/).
