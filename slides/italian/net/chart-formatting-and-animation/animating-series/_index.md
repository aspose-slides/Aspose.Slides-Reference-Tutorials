---
"description": "Scopri come animare serie di grafici con Aspose.Slides per .NET. Coinvolgi il tuo pubblico con presentazioni dinamiche. Inizia subito!"
"linktitle": "Serie animata in Chart"
"second_title": "API di elaborazione PowerPoint Aspose.Slides .NET"
"title": "Serie di grafici animati con Aspose.Slides per .NET"
"url": "/it/net/chart-formatting-and-animation/animating-series/"
"weight": 12
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Serie di grafici animati con Aspose.Slides per .NET


Vuoi dare un tocco di brio alle tue presentazioni con grafici animati? Aspose.Slides per .NET è qui per dare vita ai tuoi grafici. In questa guida passo passo, ti mostreremo come animare le serie in un grafico utilizzando Aspose.Slides per .NET. Ma prima di entrare nel vivo dell'azione, vediamo i prerequisiti.

## Prerequisiti

Per animare correttamente le serie in un grafico utilizzando Aspose.Slides per .NET, avrai bisogno di quanto segue:

### 1. Aspose.Slides per la libreria .NET

Assicurati di aver installato la libreria Aspose.Slides per .NET. Se non l'hai già fatto, puoi scaricarla da [Aspose.Slides per il sito web .NET](https://releases.aspose.com/slides/net/).

### 2. Presentazione esistente con un grafico

Preparare una presentazione PowerPoint (PPTX) con un grafico esistente che si desidera animare.

Ora che abbiamo chiarito i prerequisiti, scomponiamo il processo in una serie di passaggi per animare la serie di grafici.


## Passaggio 1: importare gli spazi dei nomi necessari

Per lavorare con Aspose.Slides per .NET, dovrai importare gli spazi dei nomi richiesti nel codice C#:

```csharp
﻿using Aspose.Slides.Charts;
using Aspose.Slides.Export;
using Aspose.Slides.Animation;
using Aspose.Slides;
```

## Passaggio 2: caricare la presentazione esistente

In questo passaggio, carica la presentazione PowerPoint esistente (PPTX) che contiene il grafico che desideri animare.

```csharp
// Percorso alla directory del documento
string dataDir = "Your Document Directory";

// Crea un'istanza della classe Presentazione che rappresenta un file di presentazione 
using (Presentation presentation = new Presentation(dataDir + "ExistingChart.pptx"))
{
    // Il tuo codice va qui
}
```

## Passaggio 3: ottenere il riferimento dell'oggetto grafico

Per lavorare con il grafico nella presentazione, è necessario ottenere un riferimento all'oggetto grafico:

```csharp
var slide = presentation.Slides[0] as Slide;
var shapes = slide.Shapes as ShapeCollection;
var chart = shapes[0] as IChart;
```

## Fase 4: Animare la serie

Ora è il momento di aggiungere effetti di animazione alla serie di grafici. Aggiungeremo un effetto di dissolvenza all'intero grafico e faremo apparire ogni serie una alla volta.

```csharp
// Animare il grafico
slide.Timeline.MainSequence.AddEffect(chart, EffectType.Fade, EffectSubtype.None, EffectTriggerType.AfterPrevious);

// Aggiungi animazione a ogni serie
((Sequence)slide.Timeline.MainSequence).AddEffect(chart, EffectChartMajorGroupingType.BySeries, 0, EffectType.Appear, EffectSubtype.None, EffectTriggerType.AfterPrevious);
((Sequence)slide.Timeline.MainSequence).AddEffect(chart, EffectChartMajorGroupingType.BySeries, 1, EffectType.Appear, EffectSubtype.None, EffectTriggerType.AfterPrevious);
((Sequence)slide.Timeline.MainSequence).AddEffect(chart, EffectChartMajorGroupingType.BySeries, 2, EffectType.Appear, EffectSubtype.None, EffectTriggerType.AfterPrevious);
((Sequence)slide.Timeline.MainSequence).AddEffect(chart, EffectChartMajorGroupingType.BySeries, 3, EffectType.Appear, EffectSubtype.None, EffectTriggerType.AfterPrevious);
```

## Passaggio 5: salvare la presentazione modificata

Dopo aver aggiunto gli effetti di animazione al grafico, salva la presentazione modificata sul disco.

```csharp
// Salva la presentazione modificata
presentation.Save(dataDir + "AnimatingSeries_out.pptx", SaveFormat.Pptx);
```

Ecco fatto! Hai animato con successo una serie in un grafico usando Aspose.Slides per .NET.

## Conclusione

In questo tutorial, ti abbiamo illustrato come animare una serie di grafici utilizzando Aspose.Slides per .NET. Con questa potente libreria, puoi creare presentazioni coinvolgenti e dinamiche che cattureranno l'attenzione del tuo pubblico.

Se hai domande o hai bisogno di ulteriore assistenza, non esitare a contattare la community di Aspose.Slides sul loro [forum di supporto](https://forum.aspose.com/).

## Domande frequenti

### Posso animare altri elementi del grafico oltre alle serie utilizzando Aspose.Slides per .NET?
Sì, puoi animare vari elementi del grafico, tra cui punti dati, assi e legende, utilizzando Aspose.Slides per .NET.

### Aspose.Slides per .NET è compatibile con le ultime versioni di PowerPoint?
Aspose.Slides per .NET supporta varie versioni di PowerPoint, tra cui PowerPoint 2007 e successive, garantendo la compatibilità con le versioni più recenti.

### Posso personalizzare individualmente gli effetti di animazione per ogni serie di grafici?
Sì, puoi personalizzare gli effetti di animazione per ogni serie di grafici per creare presentazioni uniche e coinvolgenti.

### Esiste una versione di prova disponibile per Aspose.Slides per .NET?
Sì, puoi provare la libreria con una prova gratuita da [Aspose.Slides per il sito web .NET](https://releases.aspose.com/).

### Dove posso acquistare una licenza per Aspose.Slides per .NET?
È possibile acquistare una licenza per Aspose.Slides per .NET dalla pagina di acquisto [Qui](https://purchase.aspose.com/buy).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}