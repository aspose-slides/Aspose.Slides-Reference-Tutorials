---
title: Formattazione e animazione del grafico in Aspose.Slides
linktitle: Formattazione e animazione del grafico in Aspose.Slides
second_title: API di elaborazione di PowerPoint .NET Aspose.Slides
description: Scopri come formattare e animare i grafici in Aspose.Slides per .NET, migliorando le tue presentazioni con immagini accattivanti.
type: docs
weight: 10
url: /it/net/chart-formatting-and-animation/chart-formatting-and-animation/
---

La creazione di presentazioni accattivanti con grafici e animazioni dinamici può migliorare notevolmente l'impatto del tuo messaggio. Aspose.Slides per .NET ti consente di raggiungere proprio questo. In questo tutorial ti guideremo attraverso il processo di animazione e formattazione dei grafici utilizzando Aspose.Slides per .NET. Suddivideremo i passaggi in sezioni gestibili per assicurarti di comprendere a fondo il concetto.

## Prerequisiti

Prima di immergerti nella formattazione e nell'animazione dei grafici con Aspose.Slides, avrai bisogno di quanto segue:

1.  Aspose.Slides per .NET: assicurati di aver installato Aspose.Slides per .NET. Se non l'hai già fatto, puoi[scaricalo qui](https://releases.aspose.com/slides/net/).

2. Presentazione esistente: disponi di una presentazione esistente che contiene un grafico che desideri formattare e animare.

3. Conoscenza di base di C#: la familiarità con C# sarà utile per implementare i passaggi.

Ora cominciamo.

## Importa spazi dei nomi

Per iniziare, dovrai importare gli spazi dei nomi necessari per accedere alle funzionalità Aspose.Slides. Nel tuo progetto C#, aggiungi quanto segue:

```csharp
﻿using Aspose.Slides.Charts;
using Aspose.Slides.Export;
using Aspose.Slides.Animation;
using Aspose.Slides;
```

## Animazione degli elementi delle categorie nel grafico

### Passaggio 1: carica la presentazione e accedi al grafico

Innanzitutto, carica la presentazione esistente e accedi al grafico che desideri animare. Questo esempio presuppone che il grafico si trovi sulla prima diapositiva della presentazione.

```csharp
using (Presentation presentation = new Presentation("Your Document Directory\\ExistingChart.pptx"))
{
    var slide = presentation.Slides[0] as Slide;
    var shapes = slide.Shapes as ShapeCollection;
    var chart = shapes[0] as IChart;
}
```

### Passaggio 2: aggiungi l'animazione agli elementi delle categorie

Ora aggiungiamo l'animazione agli elementi delle categorie. In questo esempio, stiamo utilizzando un effetto di dissolvenza in apertura.

```csharp
slide.Timeline.MainSequence.AddEffect(chart, EffectType.Fade, EffectSubtype.None, EffectTriggerType.AfterPrevious);

for (int i = 0; i < chart.ChartData.Categories.Count; i++)
{
    ((Sequence)slide.Timeline.MainSequence).AddEffect(chart, EffectChartMinorGroupingType.ByElementInCategory, 0, i, EffectType.Appear, EffectSubtype.None, EffectTriggerType.AfterPrevious);
}
```

### Passaggio 3: salva la presentazione

Infine, salva la presentazione modificata su disco.

```csharp
presentation.Save("Your Document Directory\\AnimatingCategoriesElements_out.pptx", SaveFormat.Pptx);
```

## Serie animate nel grafico

### Passaggio 1: carica la presentazione e accedi al grafico

Similmente all'esempio precedente, caricherai la presentazione e accederai al grafico.

```csharp
using (Presentation presentation = new Presentation("Your Document Directory\\ExistingChart.pptx"))
{
    var slide = presentation.Slides[0] as Slide;
    var shapes = slide.Shapes as ShapeCollection;
    var chart = shapes[0] as IChart;
}
```

### Passaggio 2: aggiungi l'animazione alla serie

Ora aggiungiamo l'animazione alla serie di grafici. Anche qui stiamo usando un effetto di dissolvenza.

```csharp
slide.Timeline.MainSequence.AddEffect(chart, EffectType.Fade, EffectSubtype.None, EffectTriggerType.AfterPrevious);

for (int i = 0; i < chart.ChartData.Series.Count; i++)
{
    ((Sequence)slide.Timeline.MainSequence).AddEffect(chart, EffectChartMajorGroupingType.BySeries, i, EffectType.Appear, EffectSubtype.None, EffectTriggerType.AfterPrevious);
}
```

### Passaggio 3: salva la presentazione

Salva la presentazione modificata con la serie animata.

```csharp
presentation.Save("Your Document Directory\\AnimatingSeries_out.pptx", SaveFormat.Pptx);
```

## Animazione degli elementi della serie nel grafico

### Passaggio 1: carica la presentazione e accedi al grafico

Come prima, carica la presentazione e accedi al grafico.

```csharp
using (Presentation presentation = new Presentation("Your Document Directory\\ExistingChart.pptx"))
{
    var slide = presentation.Slides[0] as Slide;
    var shapes = slide.Shapes as ShapeCollection;
    var chart = shapes[0] as IChart;
}
```

### Passaggio 2: aggiungi l'animazione agli elementi della serie

In questo passaggio aggiungerai l'animazione agli elementi della serie, creando un effetto visivo impressionante.

```csharp
slide.Timeline.MainSequence.AddEffect(chart, EffectType.Fade, EffectSubtype.None, EffectTriggerType.AfterPrevious);

for (int seriesIndex = 0; seriesIndex < chart.ChartData.Series.Count; seriesIndex++)
{
    for (int elementIndex = 0; elementIndex < chart.ChartData.Categories.Count; elementIndex++)
    {
        ((Sequence)slide.Timeline.MainSequence).AddEffect(chart, EffectChartMinorGroupingType.ByElementInSeries, seriesIndex, elementIndex, EffectType.Appear, EffectSubtype.None, EffectTriggerType.AfterPrevious);
    }
}
```

### Passaggio 3: salva la presentazione

Non dimenticare di salvare la presentazione con gli elementi della serie animata.

```csharp
presentation.Save("Your Document Directory\\AnimatingSeriesElements_out.pptx", SaveFormat.Pptx);
```

Congratulazioni! Ora hai imparato come formattare e animare i grafici in Aspose.Slides per .NET. Queste tecniche possono rendere le tue presentazioni più coinvolgenti e informative.

## Conclusione

Aspose.Slides per .NET fornisce potenti strumenti per la formattazione e l'animazione dei grafici, consentendoti di creare presentazioni visivamente accattivanti che affascinano il tuo pubblico. Seguendo questa guida passo passo, potrai padroneggiare l'arte dell'animazione dei grafici e migliorare le tue presentazioni.

## Domande frequenti

### 1. Dove posso trovare la documentazione per Aspose.Slides per .NET?

 È possibile accedere alla documentazione su[https://reference.aspose.com/slides/net/](https://reference.aspose.com/slides/net/).

### 2. Come posso scaricare Aspose.Slides per .NET?

 È possibile scaricare Aspose.Slides per .NET da[https://releases.aspose.com/slides/net/](https://releases.aspose.com/slides/net/).

### 3. È disponibile una prova gratuita?

 Sì, puoi ottenere una prova gratuita di Aspose.Slides per .NET su[https://releases.aspose.com/](https://releases.aspose.com/).

### 4. Posso acquistare una licenza temporanea per Aspose.Slides per .NET?

 Sì, puoi acquistare una licenza temporanea su[https://purchase.aspose.com/temporary-license/](https://purchase.aspose.com/temporary-license/).

### 5. Dove posso ottenere supporto o porre domande su Aspose.Slides per .NET?

 Per supporto e domande, visitare il forum Aspose.Slides all'indirizzo[https://forum.aspose.com/](https://forum.aspose.com/).

