---
"description": "Impara ad animare gli elementi dei grafici in PowerPoint con Aspose.Slides per .NET. Guida passo passo per presentazioni straordinarie."
"linktitle": "Animazione degli elementi delle categorie nel grafico"
"second_title": "API di elaborazione PowerPoint Aspose.Slides .NET"
"title": "Animazioni di grafici potenti con Aspose.Slides per .NET"
"url": "/it/net/chart-formatting-and-animation/animating-categories-elements/"
"weight": 11
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Animazioni di grafici potenti con Aspose.Slides per .NET


Nel mondo delle presentazioni, le animazioni possono dare vita ai contenuti, soprattutto quando si tratta di grafici. Aspose.Slides per .NET offre una serie di potenti funzionalità che consentono di creare animazioni straordinarie per i grafici. In questa guida passo passo, vi guideremo attraverso il processo di animazione degli elementi di categoria in un grafico utilizzando Aspose.Slides per .NET.

## Prerequisiti

Prima di immergerci nel tutorial, è necessario soddisfare i seguenti prerequisiti:

- Aspose.Slides per .NET: assicurati di aver installato Aspose.Slides per .NET nel tuo ambiente di sviluppo. Se non l'hai già fatto, puoi scaricarlo da [Qui](https://releases.aspose.com/slides/net/).

- Presentazione esistente: dovresti avere una presentazione PowerPoint con un grafico che desideri animare. In caso contrario, crea una presentazione di esempio con un grafico a scopo di test.

Ora che hai tutto a posto, iniziamo ad animare gli elementi del grafico!

## Importa spazi dei nomi

Il primo passo è importare gli spazi dei nomi necessari per accedere alle funzionalità di Aspose.Slides. Aggiungi i seguenti spazi dei nomi al tuo progetto:

```csharp
using Aspose.Slides;
using Aspose.Slides.Charts;
```

## Passaggio 1: caricare la presentazione

```csharp
// Percorso alla directory dei documenti
string dataDir = "Your Document Directory";

using (Presentation presentation = new Presentation(dataDir + "ExistingChart.pptx"))
{
    // Ottieni il riferimento dell'oggetto grafico
    var slide = presentation.Slides[0] as Slide;
    var shapes = slide.Shapes as ShapeCollection;
    var chart = shapes[0] as IChart;
```

In questa fase, carichiamo la presentazione PowerPoint esistente contenente il grafico da animare. Quindi accediamo all'oggetto grafico nella prima diapositiva.

## Passaggio 2: animare gli elementi delle categorie

```csharp
// Animare gli elementi delle categorie
slide.Timeline.MainSequence.AddEffect(chart, EffectType.Fade, EffectSubtype.None, EffectTriggerType.AfterPrevious);
```

Questo passaggio aggiunge un effetto di animazione "Dissolvenza" all'intero grafico, facendolo apparire dopo l'animazione precedente.

Successivamente, aggiungeremo animazioni ai singoli elementi all'interno di ogni categoria del grafico. È qui che avviene la vera magia.

## Fase 3: Animare i singoli elementi

Suddivideremo l'animazione dei singoli elementi all'interno di ciascuna categoria nei seguenti passaggi:

### Fase 3.1: Animazione degli elementi nella categoria 0

```csharp
((Sequence)slide.Timeline.MainSequence).AddEffect(chart, EffectChartMinorGroupingType.ByElementInCategory, 0, 0, EffectType.Appear, EffectSubtype.None, EffectTriggerType.AfterPrevious);
((Sequence)slide.Timeline.MainSequence).AddEffect(chart, EffectChartMinorGroupingType.ByElementInCategory, 0, 1, EffectType.Appear, EffectSubtype.None, EffectTriggerType.AfterPrevious);
((Sequence)slide.Timeline.MainSequence).AddEffect(chart, EffectChartMinorGroupingType.ByElementInCategory, 0, 2, EffectType.Appear, EffectSubtype.None, EffectTriggerType.AfterPrevious);
((Sequence)slide.Timeline.MainSequence).AddEffect(chart, EffectChartMinorGroupingType.ByElementInCategory, 0, 3, EffectType.Appear, EffectSubtype.None, EffectTriggerType.AfterPrevious);
```

Qui stiamo animando singoli elementi all'interno della categoria 0 del grafico, facendoli apparire uno dopo l'altro. Per questa animazione viene utilizzato l'effetto "Apparizione".

### Fase 3.2: Animazione degli elementi nella categoria 1

```csharp
((Sequence)slide.Timeline.MainSequence).AddEffect(chart, EffectChartMinorGroupingType.ByElementInCategory, 1, 0, EffectType.Appear, EffectSubtype.None, EffectTriggerType.AfterPrevious);
((Sequence)slide.Timeline.MainSequence).AddEffect(chart, EffectChartMinorGroupingType.ByElementInCategory, 1, 1, EffectType.Appear, EffectSubtype.None, EffectTriggerType.AfterPrevious);
((Sequence)slide.Timeline.MainSequence).AddEffect(chart, EffectChartMinorGroupingType.ByElementInCategory, 1, 2, EffectType.Appear, EffectSubtype.None, EffectTriggerType.AfterPrevious);
((Sequence)slide.Timeline.MainSequence).AddEffect(chart, EffectChartMinorGroupingType.ByElementInCategory, 1, 3, EffectType.Appear, EffectSubtype.None, EffectTriggerType.AfterPrevious);
```

Il processo viene ripetuto per la categoria 1, animandone i singoli elementi mediante l'effetto "Appari".

### Fase 3.3: Animazione degli elementi nella categoria 2

```csharp
((Sequence)slide.Timeline.MainSequence).AddEffect(chart, EffectChartMinorGroupingType.ByElementInCategory, 2, 0, EffectType.Appear, EffectSubtype.None, EffectTriggerType.AfterPrevious);
((Sequence)slide.Timeline.MainSequence).AddEffect(chart, EffectChartMinorGroupingType.ByElementInCategory, 2, 1, EffectType.Appear, EffectSubtype.None, EffectTriggerType.AfterPrevious);
((Sequence)slide.Timeline.MainSequence).AddEffect(chart, EffectChartMinorGroupingType.ByElementInCategory, 2, 2, EffectType.Appear, EffectSubtype.None, EffectTriggerType.AfterPrevious);
((Sequence)slide.Timeline.MainSequence).AddEffect(chart, EffectChartMinorGroupingType.ByElementInCategory, 2, 3, EffectType.Appear, EffectSubtype.None, EffectTriggerType.AfterPrevious);
```

Lo stesso processo continua per la categoria 2, animandone gli elementi singolarmente.

## Passaggio 4: salva la presentazione

```csharp
// Scrivi il file di presentazione sul disco
presentation.Save(dataDir + "AnimatingCategoriesElements_out.pptx", SaveFormat.Pptx);
}
```

Nell'ultimo passaggio, salviamo la presentazione con le animazioni appena aggiunte. Ora, gli elementi del grafico saranno animati splendidamente durante l'esecuzione della presentazione.

## Conclusione

L'animazione degli elementi di categoria in un grafico può migliorare l'aspetto visivo delle tue presentazioni. Con Aspose.Slides per .NET, questo processo diventa semplice ed efficiente. Hai imparato come importare namespace, caricare una presentazione e aggiungere animazioni sia all'intero grafico che ai suoi singoli elementi. Scatena la tua creatività e rendi le tue presentazioni più accattivanti con Aspose.Slides per .NET.

## Domande frequenti

### 1. Come posso scaricare Aspose.Slides per .NET?
Puoi scaricare Aspose.Slides per .NET da [questo collegamento](https://releases.aspose.com/slides/net/).

### 2. È necessaria esperienza di programmazione per utilizzare Aspose.Slides per .NET?
Sebbene l'esperienza di programmazione sia utile, Aspose.Slides per .NET fornisce un'ampia documentazione ed esempi per assistere gli utenti di tutti i livelli di competenza.

### 3. Posso usare Aspose.Slides per .NET con qualsiasi versione di PowerPoint?
Aspose.Slides per .NET è progettato per funzionare con varie versioni di PowerPoint, garantendone la compatibilità.

### 4. Come posso ottenere una licenza temporanea per Aspose.Slides per .NET?
È possibile ottenere una licenza temporanea per Aspose.Slides per .NET [Qui](https://purchase.aspose.com/temporary-license/).

### 5. Esiste un forum della community per il supporto di Aspose.Slides per .NET?
Sì, puoi trovare un forum della community di supporto per Aspose.Slides per .NET [Qui](https://forum.aspose.com/).


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}