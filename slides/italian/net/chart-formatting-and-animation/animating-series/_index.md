---
title: Animare le serie di grafici con Aspose.Slides per .NET
linktitle: Serie animate nel grafico
second_title: API di elaborazione di PowerPoint .NET Aspose.Slides
description: Scopri come animare le serie di grafici con Aspose.Slides per .NET. Coinvolgi il tuo pubblico con presentazioni dinamiche. Inizia ora!
weight: 12
url: /it/net/chart-formatting-and-animation/animating-series/
---

{< blocks/products/pf/main-wrap-class >}
{< blocks/products/pf/main-container >}
{< blocks/products/pf/tutorial-page-section >}


Stai cercando di aggiungere un po' di brio alle tue presentazioni con grafici animati? Aspose.Slides per .NET è qui per dare vita ai tuoi grafici. In questa guida passo passo, ti mostreremo come animare le serie in un grafico utilizzando Aspose.Slides per .NET. Ma prima di tuffarci nell'azione, esaminiamo i prerequisiti.

## Prerequisiti

Per animare con successo le serie in un grafico utilizzando Aspose.Slides per .NET, avrai bisogno di quanto segue:

### 1. Aspose.Slides per la libreria .NET

 Assicurati di avere la libreria Aspose.Slides per .NET installata. Se non lo hai già fatto, puoi scaricarlo dal[Aspose.Slides per il sito Web .NET](https://releases.aspose.com/slides/net/).

### 2. Presentazione esistente con un grafico

Prepara una presentazione PowerPoint (PPTX) con un grafico esistente che desideri animare.

Ora che abbiamo coperto i prerequisiti, suddividiamo il processo in una serie di passaggi per animare la serie di grafici.


## Passaggio 1: importa gli spazi dei nomi necessari

Dovrai importare gli spazi dei nomi richiesti nel codice C# per lavorare con Aspose.Slides per .NET:

```csharp
﻿using Aspose.Slides.Charts;
using Aspose.Slides.Export;
using Aspose.Slides.Animation;
using Aspose.Slides;
```

## Passaggio 2: carica la presentazione esistente

In questo passaggio, carica la presentazione PowerPoint esistente (PPTX) che contiene il grafico che desideri animare.

```csharp
// Percorso della directory dei documenti
string dataDir = "Your Document Directory";

// Crea un'istanza della classe Presentation che rappresenta un file di presentazione
using (Presentation presentation = new Presentation(dataDir + "ExistingChart.pptx"))
{
    // Il tuo codice va qui
}
```

## Passaggio 3: ottenere il riferimento dell'oggetto grafico

Per lavorare con il grafico nella tua presentazione, dovrai ottenere un riferimento all'oggetto grafico:

```csharp
var slide = presentation.Slides[0] as Slide;
var shapes = slide.Shapes as ShapeCollection;
var chart = shapes[0] as IChart;
```

## Passaggio 4: animare la serie

Ora è il momento di aggiungere effetti di animazione alle serie di grafici. Aggiungeremo un effetto di dissolvenza all'intero grafico e faremo apparire ogni serie una per una.

```csharp
// Animare il grafico
slide.Timeline.MainSequence.AddEffect(chart, EffectType.Fade, EffectSubtype.None, EffectTriggerType.AfterPrevious);

// Aggiungi animazione a ciascuna serie
((Sequence)slide.Timeline.MainSequence).AddEffect(chart, EffectChartMajorGroupingType.BySeries, 0, EffectType.Appear, EffectSubtype.None, EffectTriggerType.AfterPrevious);
((Sequence)slide.Timeline.MainSequence).AddEffect(chart, EffectChartMajorGroupingType.BySeries, 1, EffectType.Appear, EffectSubtype.None, EffectTriggerType.AfterPrevious);
((Sequence)slide.Timeline.MainSequence).AddEffect(chart, EffectChartMajorGroupingType.BySeries, 2, EffectType.Appear, EffectSubtype.None, EffectTriggerType.AfterPrevious);
((Sequence)slide.Timeline.MainSequence).AddEffect(chart, EffectChartMajorGroupingType.BySeries, 3, EffectType.Appear, EffectSubtype.None, EffectTriggerType.AfterPrevious);
```

## Passaggio 5: salva la presentazione modificata

Dopo aver aggiunto gli effetti di animazione al grafico, salva la presentazione modificata su disco.

```csharp
//Salva la presentazione modificata
presentation.Save(dataDir + "AnimatingSeries_out.pptx", SaveFormat.Pptx);
```

Questo è tutto! Hai animato con successo le serie in un grafico utilizzando Aspose.Slides per .NET.

## Conclusione

In questo tutorial, ti abbiamo guidato attraverso il processo di animazione delle serie in un grafico utilizzando Aspose.Slides per .NET. Con questa potente libreria puoi creare presentazioni coinvolgenti e dinamiche che affascinano il tuo pubblico.

 Se hai domande o hai bisogno di ulteriore assistenza, non esitare a contattare la community di Aspose.Slides sul loro[Forum di assistenza](https://forum.aspose.com/).

## Domande frequenti

### Posso animare altri elementi del grafico oltre alle serie utilizzando Aspose.Slides per .NET?
Sì, puoi animare vari elementi del grafico, inclusi punti dati, assi e legende, utilizzando Aspose.Slides per .NET.

### Aspose.Slides per .NET è compatibile con le ultime versioni di PowerPoint?
Aspose.Slides per .NET supporta varie versioni di PowerPoint, incluso PowerPoint 2007 e successive, garantendo la compatibilità con le versioni più recenti.

### Posso personalizzare gli effetti di animazione per ciascuna serie di grafici individualmente?
Sì, puoi personalizzare gli effetti di animazione per ciascuna serie di grafici per creare presentazioni uniche e accattivanti.

### È disponibile una versione di prova per Aspose.Slides per .NET?
 Sì, puoi provare la libreria con una prova gratuita da[Aspose.Slides per il sito Web .NET](https://releases.aspose.com/).

### Dove posso acquistare una licenza per Aspose.Slides per .NET?
 È possibile acquistare una licenza per Aspose.Slides per .NET dalla pagina di acquisto[Qui](https://purchase.aspose.com/buy).
{< /blocks/products/pf/tutorial-page-section >}

{< /blocks/products/pf/main-container >}
{< /blocks/products/pf/main-wrap-class >}

{< blocks/products/products-backtop-button >}
