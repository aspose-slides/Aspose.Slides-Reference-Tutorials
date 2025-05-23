---
"description": "Ottimizza le tue presentazioni Java con Aspose.Slides per Java. Scopri come animare gli elementi delle categorie nelle diapositive di PowerPoint passo dopo passo."
"linktitle": "Animazione degli elementi delle categorie nelle diapositive Java"
"second_title": "API di elaborazione Java PowerPoint di Aspose.Slides"
"title": "Animazione degli elementi delle categorie nelle diapositive Java"
"url": "/it/java/animation-and-layout/animating-categories-elements-java-slides/"
"weight": 10
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Animazione degli elementi delle categorie nelle diapositive Java


## Introduzione all'animazione degli elementi di categoria in Java Slides

In questo tutorial, ti guideremo attraverso il processo di animazione degli elementi di categoria nelle diapositive Java utilizzando Aspose.Slides per Java. Questa guida passo passo ti fornirà il codice sorgente e le spiegazioni necessarie per ottenere questo effetto di animazione.

## Prerequisiti

Prima di iniziare, assicurati di avere quanto segue:

- Installata l'API Aspose.Slides per Java.
- Una presentazione PowerPoint esistente contenente un grafico. Animare gli elementi delle categorie di questo grafico.

## Passaggio 1: importare la libreria Aspose.Slides

Per iniziare, importa la libreria Aspose.Slides nel tuo progetto Java. Puoi scaricare e aggiungere la libreria al classpath del tuo progetto. Assicurati di aver configurato le dipendenze necessarie.

## Passaggio 2: caricare la presentazione

```java
// Percorso verso la directory dei documenti.
String dataDir = "Your Document Directory";
Presentation presentation = new Presentation(dataDir + "ExistingChart.pptx");
```

In questo codice, carichiamo una presentazione PowerPoint esistente che contiene il grafico che desideri animare. Sostituisci `"Your Document Directory"` con il percorso effettivo verso la directory dei documenti.

## Passaggio 3: ottenere un riferimento all'oggetto grafico

```java
ISlide slide = presentation.getSlides().get_Item(0);
IShapeCollection shapes = slide.getShapes();
IChart chart = (IChart) shapes.get_Item(0);
```

Otteniamo un riferimento all'oggetto grafico nella prima diapositiva della presentazione. Regola l'indice della diapositiva (`get_Item(0)`) e indice di forma (`get_Item(0)`) secondo necessità per accedere al tuo grafico specifico.

## Passaggio 4: animare gli elementi delle categorie

```java
slide.getTimeline().getMainSequence().addEffect(chart, EffectType.Fade, EffectSubtype.None, EffectTriggerType.AfterPrevious);

for (int i = 0; i < chart.getChartData().getCategories().size(); i++) {
    for (int j = 0; j < chart.getChartData().getSeries().size(); j++) {
        ((Sequence) slide.getTimeline().getMainSequence()).addEffect(chart, EffectChartMinorGroupingType.ByElementInCategory, i, j, EffectType.Appear, EffectSubtype.None, EffectTriggerType.AfterPrevious);
    }
}
```

Animiamo gli elementi delle categorie all'interno del grafico. Questo codice aggiunge un effetto di dissolvenza all'intero grafico e poi aggiunge un effetto "Apparizione" a ciascun elemento di ogni categoria. Regola il tipo e il sottotipo di effetto secondo necessità.

## Passaggio 5: Salva la presentazione

```java
presentation.save(dataDir + "AnimatingCategoriesElements_out.pptx", SaveFormat.Pptx);
```

Infine, salva la presentazione modificata con il grafico animato in un nuovo file. Sostituisci `"AnimatingCategoriesElements_out.pptx"` con il nome del file di output desiderato.


## Codice sorgente completo per animare gli elementi delle categorie nelle diapositive Java
```java
// Percorso verso la directory dei documenti.
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
	// Scrivi il file di presentazione sul disco
	presentation.save(dataDir + "AnimatingCategoriesElements_out.pptx", SaveFormat.Pptx);
}
finally
{
	if (presentation != null) presentation.dispose();
}
```

## Conclusione

Hai animato con successo gli elementi di categoria in una diapositiva Java utilizzando Aspose.Slides per Java. Questa guida passo passo ti ha fornito il codice sorgente e le spiegazioni necessarie per ottenere questo effetto di animazione nelle tue presentazioni PowerPoint. Sperimenta diversi effetti e impostazioni per personalizzare ulteriormente le tue animazioni.

## Domande frequenti

### Come posso personalizzare gli effetti di animazione?

È possibile personalizzare gli effetti di animazione modificando il `EffectType` E `EffectSubtype` parametri quando si aggiungono effetti agli elementi del grafico. Consultare la documentazione di Aspose.Slides per Java per maggiori dettagli sugli effetti di animazione disponibili.

### Posso applicare queste animazioni ad altri tipi di grafici?

Sì, puoi applicare animazioni simili ad altri tipi di grafici modificando il codice per adattarlo agli elementi specifici del grafico che desideri animare. Adatta la struttura del ciclo e i parametri di conseguenza.

### Come posso saperne di più su Aspose.Slides per Java?

Per una documentazione completa e risorse aggiuntive, visitare il sito [Riferimento API Aspose.Slides per Java](https://reference.aspose.com/slides/java/)Puoi anche scaricare la libreria da [Qui](https://releases.aspose.com/slides/java/).


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}