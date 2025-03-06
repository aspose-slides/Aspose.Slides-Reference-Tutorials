---
title: Serie animate in diapositive Java
linktitle: Serie animate in diapositive Java
second_title: Aspose.Slides API di elaborazione Java PowerPoint
description: Ottimizza le tue presentazioni con animazioni di serie in Aspose.Slides per Java. Segui la nostra guida passo passo con esempi di codice sorgente per creare coinvolgenti animazioni PowerPoint.
weight: 11
url: /it/java/animation-and-layout/animating-series-java-slides/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}


## Introduzione all'animazione delle serie in Aspose.Slides per Java

In questa guida ti guideremo attraverso il processo di animazione delle serie in diapositive Java utilizzando Aspose.Slides per l'API Java. Questa libreria ti consente di lavorare con le presentazioni di PowerPoint a livello di codice.

## Prerequisiti

Prima di iniziare, assicurati di disporre dei seguenti prerequisiti:

- Aspose.Slides per la libreria Java.
- Configurazione dell'ambiente di sviluppo Java.

## Passaggio 1: caricare la presentazione

 Innanzitutto, dobbiamo caricare una presentazione PowerPoint esistente che contenga un grafico. Sostituire`"Your Document Directory"` con il percorso effettivo del file di presentazione.

```java
// Il percorso della directory dei documenti.
String dataDir = "Your Document Directory";
// Crea un'istanza della classe Presentation che rappresenta un file di presentazione
Presentation presentation = new Presentation(dataDir + "ExistingChart.pptx");
```

## Passaggio 2: accedi al grafico

Successivamente, accederemo al grafico all'interno della presentazione. In questo esempio presupponiamo che il grafico si trovi sulla prima diapositiva e che sia la prima forma su tale diapositiva.

```java
// Ottieni riferimento all'oggetto grafico
ISlide slide = presentation.getSlides().get_Item(0);
IShapeCollection shapes = slide.getShapes();
IChart chart = (IChart) shapes.get_Item(0);
```

## Passaggio 3: aggiungi animazioni

Ora aggiungiamo animazioni alla serie all'interno del grafico. Utilizzeremo un effetto di dissolvenza in apertura e faremo apparire ogni serie una dopo l'altra.

```java
// Anima l'intero grafico
slide.getTimeline().getMainSequence().addEffect(chart, EffectType.Fade, EffectSubtype.None, EffectTriggerType.AfterPrevious);

// Aggiungi animazioni a ciascuna serie (supponendo che ci siano 4 serie)
for (int i = 0; i < 4; i++) {
    ((Sequence) slide.getTimeline().getMainSequence()).addEffect(chart,
            EffectChartMajorGroupingType.BySeries, i,
            EffectType.Appear, EffectSubtype.None, EffectTriggerType.AfterPrevious);
}
```

Nel codice sopra, utilizziamo un effetto di dissolvenza in apertura per l'intero grafico e quindi utilizziamo un loop per aggiungere un effetto "Appare" a ciascuna serie una dopo l'altra.

## Passaggio 4: salva la presentazione

Infine, salva la presentazione modificata su disco.

```java
presentation.save(dataDir + "AnimatingSeries_out.pptx", SaveFormat.Pptx);
```

## Codice sorgente completo per l'animazione di serie in Aspose.Slides per Java

```java
// Il percorso della directory dei documenti.
String dataDir = "Your Document Directory";
// Crea un'istanza della classe Presentation che rappresenta un file di presentazione
Presentation presentation = new Presentation(dataDir + "ExistingChart.pptx");
try
{
	// Ottieni il riferimento dell'oggetto grafico
	ISlide slide = presentation.getSlides().get_Item(0);
	IShapeCollection shapes = slide.getShapes();
	IChart chart = (IChart) shapes.get_Item(0);
	// Animare la serie
	slide.getTimeline().getMainSequence().addEffect(chart, EffectType.Fade, EffectSubtype.None,
			EffectTriggerType.AfterPrevious);
	((Sequence) slide.getTimeline().getMainSequence()).addEffect(chart,
			EffectChartMajorGroupingType.BySeries, 0,
			EffectType.Appear, EffectSubtype.None, EffectTriggerType.AfterPrevious);
	((Sequence) slide.getTimeline().getMainSequence()).addEffect(chart,
			EffectChartMajorGroupingType.BySeries, 1,
			EffectType.Appear, EffectSubtype.None, EffectTriggerType.AfterPrevious);
	((Sequence) slide.getTimeline().getMainSequence()).addEffect(chart,
			EffectChartMajorGroupingType.BySeries, 2,
			EffectType.Appear, EffectSubtype.None, EffectTriggerType.AfterPrevious);
	((Sequence) slide.getTimeline().getMainSequence()).addEffect(chart,
			EffectChartMajorGroupingType.BySeries, 3,
			EffectType.Appear, EffectSubtype.None, EffectTriggerType.AfterPrevious);
	// Scrivere la presentazione modificata su disco
	presentation.save(dataDir + "AnimatingSeries_out.pptx", SaveFormat.Pptx);
}
finally
{
	if (presentation != null) presentation.dispose();
}
```

## Conclusione

Hai animato con successo serie in un grafico di PowerPoint utilizzando Aspose.Slides per Java. Ciò può rendere le tue presentazioni più coinvolgenti e visivamente accattivanti. Esplora più opzioni di animazione e perfeziona le tue presentazioni secondo necessità.

## Domande frequenti

### Come posso controllare l'ordine delle animazioni delle serie?

 Per controllare l'ordine delle animazioni della serie, utilizzare il comando`EffectTriggerType.AfterPrevious` parametro quando si aggiungono gli effetti. Ciò farà sì che ogni animazione della serie inizi dopo il termine della precedente.

### Posso applicare animazioni diverse a ciascuna serie?

 Sì, puoi applicare animazioni diverse a ciascuna serie specificandone diverse`EffectType` E`EffectSubtype` valori quando si aggiungono effetti.

### Cosa succede se la mia presentazione ha più di quattro serie?

Puoi estendere il ciclo nel passaggio 3 per aggiungere animazioni per tutte le serie nel grafico. Basta regolare di conseguenza le condizioni del loop.

### Come posso personalizzare la durata e il ritardo dell'animazione?

È possibile personalizzare la durata e il ritardo dell'animazione impostando le proprietà sugli effetti di animazione. Controlla la documentazione di Aspose.Slides per Java per i dettagli sulle opzioni di personalizzazione disponibili.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
