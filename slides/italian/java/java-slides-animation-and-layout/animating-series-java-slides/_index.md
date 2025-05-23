---
"description": "Ottimizza le tue presentazioni con le animazioni in serie in Aspose.Slides per Java. Segui la nostra guida passo passo con esempi di codice sorgente per creare coinvolgenti animazioni PowerPoint."
"linktitle": "Animazione di serie in Java Slides"
"second_title": "API di elaborazione Java PowerPoint di Aspose.Slides"
"title": "Animazione di serie in Java Slides"
"url": "/it/java/animation-and-layout/animating-series-java-slides/"
"weight": 11
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Animazione di serie in Java Slides


## Introduzione all'animazione di serie in Aspose.Slides per Java

In questa guida, ti guideremo attraverso il processo di animazione di serie in diapositive Java utilizzando l'API Aspose.Slides per Java. Questa libreria ti permette di lavorare con le presentazioni PowerPoint a livello di codice.

## Prerequisiti

Prima di iniziare, assicurati di avere i seguenti prerequisiti:

- Libreria Aspose.Slides per Java.
- Configurazione dell'ambiente di sviluppo Java.

## Passaggio 1: caricare la presentazione

Per prima cosa, dobbiamo caricare una presentazione PowerPoint esistente che contenga un grafico. Sostituisci `"Your Document Directory"` con il percorso effettivo del file della presentazione.

```java
// Percorso verso la directory dei documenti.
String dataDir = "Your Document Directory";
// Crea un'istanza della classe Presentazione che rappresenta un file di presentazione 
Presentation presentation = new Presentation(dataDir + "ExistingChart.pptx");
```

## Passaggio 2: accedi al grafico

Successivamente, accederemo al grafico all'interno della presentazione. In questo esempio, supponiamo che il grafico si trovi nella prima diapositiva e che sia la prima forma di quella diapositiva.

```java
// Ottieni il riferimento all'oggetto grafico
ISlide slide = presentation.getSlides().get_Item(0);
IShapeCollection shapes = slide.getShapes();
IChart chart = (IChart) shapes.get_Item(0);
```

## Passaggio 3: aggiungere animazioni

Ora aggiungiamo animazioni alle serie all'interno del grafico. Useremo un effetto dissolvenza in entrata e faremo apparire ogni serie una dopo l'altra.

```java
// Animare l'intero grafico
slide.getTimeline().getMainSequence().addEffect(chart, EffectType.Fade, EffectSubtype.None, EffectTriggerType.AfterPrevious);

// Aggiungere animazioni a ciascuna serie (supponendo che ci siano 4 serie)
for (int i = 0; i < 4; i++) {
    ((Sequence) slide.getTimeline().getMainSequence()).addEffect(chart,
            EffectChartMajorGroupingType.BySeries, i,
            EffectType.Appear, EffectSubtype.None, EffectTriggerType.AfterPrevious);
}
```

Nel codice sopra, utilizziamo un effetto dissolvenza in entrata per l'intero grafico e poi utilizziamo un ciclo per aggiungere un effetto "Apparizione" a ciascuna serie, una dopo l'altra.

## Passaggio 4: salva la presentazione

Infine, salva la presentazione modificata sul disco.

```java
presentation.save(dataDir + "AnimatingSeries_out.pptx", SaveFormat.Pptx);
```

## Codice sorgente completo per l'animazione di serie in Aspose.Slides per Java

```java
// Percorso verso la directory dei documenti.
String dataDir = "Your Document Directory";
// Crea un'istanza della classe Presentazione che rappresenta un file di presentazione 
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
	// Scrivi la presentazione modificata sul disco 
	presentation.save(dataDir + "AnimatingSeries_out.pptx", SaveFormat.Pptx);
}
finally
{
	if (presentation != null) presentation.dispose();
}
```

## Conclusione

Hai animato con successo una serie di immagini in un grafico di PowerPoint utilizzando Aspose.Slides per Java. Questo può rendere le tue presentazioni più coinvolgenti e visivamente accattivanti. Esplora altre opzioni di animazione e perfeziona le tue presentazioni secondo necessità.

## Domande frequenti

### Come posso controllare l'ordine delle animazioni delle serie?

Per controllare l'ordine delle animazioni della serie, utilizzare `EffectTriggerType.AfterPrevious` parametro quando si aggiungono gli effetti. Questo farà sì che ogni serie di animazioni inizi dopo la fine della precedente.

### Posso applicare animazioni diverse a ogni serie?

Sì, puoi applicare animazioni diverse a ciascuna serie specificando diverse `EffectType` E `EffectSubtype` valori quando si aggiungono effetti.

### Cosa succede se la mia presentazione è composta da più di quattro serie?

Puoi estendere il ciclo nel passaggio 3 per aggiungere animazioni a tutte le serie del grafico. Basta regolare le condizioni del ciclo di conseguenza.

### Come posso personalizzare la durata e il ritardo dell'animazione?

È possibile personalizzare la durata e il ritardo dell'animazione impostando le proprietà degli effetti di animazione. Consultare la documentazione di Aspose.Slides per Java per dettagli sulle opzioni di personalizzazione disponibili.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}