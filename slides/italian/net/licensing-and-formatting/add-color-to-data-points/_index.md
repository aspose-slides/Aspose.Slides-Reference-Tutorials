---
title: Colorazione del grafico con Aspose.Slides per .NET
linktitle: Aggiungi colore ai punti dati nel grafico
second_title: API di elaborazione di PowerPoint .NET Aspose.Slides
description: Scopri come aggiungere colore ai punti dati in un grafico con Aspose.Slides per .NET. Migliora visivamente le tue presentazioni e coinvolgi il tuo pubblico in modo efficace.
weight: 12
url: /it/net/licensing-and-formatting/add-color-to-data-points/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Colorazione del grafico con Aspose.Slides per .NET


In questa guida passo passo, ti guideremo attraverso il processo di aggiunta di colore ai punti dati in un grafico utilizzando Aspose.Slides per .NET. Aspose.Slides è una potente libreria per lavorare con presentazioni PowerPoint in applicazioni .NET. L'aggiunta di colore ai punti dati in un grafico può rendere le tue presentazioni visivamente più accattivanti e più facili da comprendere.

## Prerequisiti

Prima di iniziare, assicurati di disporre dei seguenti prerequisiti:

1. Visual Studio: è necessario che Visual Studio sia installato sul computer.

2.  Aspose.Slides per .NET: scarica e installa Aspose.Slides per .NET da[Link per scaricare](https://releases.aspose.com/slides/net/).

3. Una conoscenza di base di C#: dovresti avere una conoscenza di base della programmazione C#.

4. La tua directory dei documenti: sostituisci "La tua directory dei documenti" nel codice con il percorso effettivo della directory dei documenti.

## Importazione di spazi dei nomi

Prima di poter lavorare con Aspose.Slides per .NET, è necessario importare gli spazi dei nomi necessari. 

```csharp
﻿using Aspose.Slides.Charts;
using Aspose.Slides.Export;
using Aspose.Slides;
```


In questo esempio, aggiungeremo colore ai punti dati in un grafico utilizzando il tipo di grafico Sunburst.

```csharp
using (Presentation pres = new Presentation())
{
    // Il percorso della directory dei documenti.
    string dataDir = "Your Document Directory";

    IChart chart = pres.Slides[0].Shapes.AddChart(ChartType.Sunburst, 100, 100, 450, 400);
    
    // Il resto del codice verrà aggiunto nei passaggi seguenti.
}
```

## Passaggio 1: accesso ai punti dati

Per aggiungere colore a punti dati specifici in un grafico, devi accedere a tali punti dati. In questo esempio, prenderemo di mira il punto dati 3.

```csharp
IChartDataPointCollection dataPoints = chart.ChartData.Series[0].DataPoints;
dataPoints[3].DataPointLevels[0].Label.DataLabelFormat.ShowValue = true;
```

## Passaggio 2: personalizzazione delle etichette dati

Ora personalizziamo le etichette dati per il punto dati 0. Nasconderemo il nome della categoria e mostreremo il nome della serie.

```csharp
IDataLabel branch1Label = dataPoints[0].DataPointLevels[2].Label;
branch1Label.DataLabelFormat.ShowCategoryName = false;
branch1Label.DataLabelFormat.ShowSeriesName = true;
```

## Passaggio 3: impostazione del formato del testo e del colore di riempimento

Possiamo migliorare ulteriormente l'aspetto delle etichette dati impostando il formato del testo e il colore di riempimento. In questo passaggio, imposteremo il colore del testo su giallo per il punto dati 0.

```csharp
branch1Label.DataLabelFormat.TextFormat.PortionFormat.FillFormat.FillType = FillType.Solid;
branch1Label.DataLabelFormat.TextFormat.PortionFormat.FillFormat.SolidFillColor.Color = Color.Yellow;
```

## Passaggio 4: personalizzazione del colore di riempimento del punto dati

Ora cambiamo il colore di riempimento del punto dati 9. Lo imposteremo su un colore specifico.

```csharp
IFormat steam4Format = dataPoints[9].Format;
steam4Format.Fill.FillType = FillType.Solid;
steam4Format.Fill.SolidFillColor.Color = Color.FromArgb(0, 176, 240, 255);
```

## Passaggio 5: salvataggio della presentazione

Dopo aver personalizzato il grafico, puoi salvare la presentazione con le modifiche.

```csharp
pres.Save(dataDir + "AddColorToDataPoints.pptx", SaveFormat.Pptx);
```

Congratulazioni! Hai aggiunto con successo colore ai punti dati in un grafico utilizzando Aspose.Slides per .NET. Ciò può migliorare notevolmente l'attrattiva visiva e la chiarezza delle tue presentazioni.

## Conclusione

Aggiungere colore ai punti dati in un grafico è un modo efficace per rendere le tue presentazioni più coinvolgenti e informative. Con Aspose.Slides per .NET, hai gli strumenti per creare grafici visivamente accattivanti che trasmettono i tuoi dati in modo efficace.

## Domande frequenti (FAQ)

### Cos'è Aspose.Slides per .NET?
   Aspose.Slides per .NET è una libreria che consente agli sviluppatori .NET di lavorare con presentazioni PowerPoint a livello di codice.

### Posso personalizzare altre proprietà del grafico utilizzando Aspose.Slides?
   Sì, puoi personalizzare vari aspetti dei grafici, come etichette dati, caratteri, colori e altro, utilizzando Aspose.Slides per .NET.

### Dove posso trovare la documentazione per Aspose.Slides per .NET?
    Puoi trovare la documentazione dettagliata su[collegamento alla documentazione](https://reference.aspose.com/slides/net/).

### È disponibile una prova gratuita per Aspose.Slides per .NET?
    Sì, puoi scaricare una versione di prova gratuita da[Qui](https://releases.aspose.com/).

### Come posso ottenere supporto per Aspose.Slides per .NET?
    Per supporto e discussioni, visitare il[Forum Aspose.Slides](https://forum.aspose.com/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
