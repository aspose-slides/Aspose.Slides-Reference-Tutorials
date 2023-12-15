---
title: Utilizzo delle opzioni degli indicatori di grafico sul punto dati in Aspose.Slides .NET
linktitle: Opzioni contrassegno grafico sul punto dati
second_title: API di elaborazione di PowerPoint .NET Aspose.Slides
description: Scopri come migliorare i tuoi grafici PowerPoint utilizzando Aspose.Slides per .NET. Personalizza gli indicatori di punti dati con immagini. Crea presentazioni accattivanti.
type: docs
weight: 11
url: /it/net/advanced-chart-customization/chart-marker-options-on-data-point/
---

Quando si lavora con presentazioni e visualizzazione di dati, Aspose.Slides per .NET offre un'ampia gamma di potenti funzionalità per creare, personalizzare e manipolare grafici. In questo tutorial esploreremo come utilizzare le opzioni degli indicatori del grafico sui punti dati per migliorare le presentazioni dei grafici. Questa guida passo passo ti guiderà attraverso il processo, partendo dai prerequisiti e dall'importazione degli spazi dei nomi, fino alla suddivisione di ogni esempio in più passaggi.

## Prerequisiti

Prima di approfondire l'utilizzo delle opzioni degli indicatori del grafico sui punti dati, assicurati di disporre dei seguenti prerequisiti:

-  Aspose.Slides per .NET: assicurati di avere Aspose.Slides per .NET installato. Puoi scaricarlo da[sito web](https://releases.aspose.com/slides/net/).

- Presentazione di esempio: per questo tutorial utilizzeremo una presentazione di esempio denominata "Test.pptx". Dovresti avere questa presentazione nella directory dei documenti.

Ora iniziamo importando gli spazi dei nomi necessari.

## Importa spazi dei nomi

```csharp
﻿using Aspose.Slides;
using Aspose.Slides.Charts;
using Aspose.Slides.Export;
```

Abbiamo importato gli spazi dei nomi richiesti e inizializzato la nostra presentazione. Ora procediamo a utilizzare le opzioni degli indicatori del grafico sui punti dati.

## Passaggio 1: creazione del grafico predefinito

```csharp

// Il percorso della directory dei documenti.
string dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "Test.pptx");

ISlide slide = pres.Slides[0];

// Creazione del grafico predefinito
IChart chart = slide.Shapes.AddChart(ChartType.LineWithMarkers, 0, 0, 400, 400);
```

Creiamo un grafico predefinito di tipo "LineWithMarkers" sulla diapositiva in una posizione e dimensione specificate.

## Passaggio 2: ottenere l'indice del foglio di lavoro dei dati del grafico predefinito

```csharp
// Ottenere l'indice del foglio di lavoro dei dati del grafico predefinito
int defaultWorksheetIndex = 0;
```

Qui otteniamo l'indice del foglio di lavoro dei dati del grafico predefinito.

## Passaggio 3: ottenere il foglio di lavoro dei dati del grafico

```csharp
//Ottenere il foglio di lavoro con i dati del grafico
IChartDataWorkbook fact = chart.ChartData.ChartDataWorkbook;
```

Recuperiamo la cartella di lavoro dei dati del grafico per lavorare con i dati del grafico.

## Passaggio 4: modifica della serie di grafici

```csharp
// Elimina la serie demo
chart.ChartData.Series.Clear();

// Aggiungi nuova serie
chart.ChartData.Series.Add(fact.GetCell(defaultWorksheetIndex, 1, 1, "Series 1"), chart.Type);
```

In questo passaggio rimuoviamo tutte le serie demo esistenti e aggiungiamo una nuova serie denominata "Serie 1" al grafico.

## Passaggio 5: impostazione del riempimento immagine per i punti dati

```csharp
// Imposta l'immagine per i marcatori
System.Drawing.Image img1 = (System.Drawing.Image)new Bitmap(dataDir + "aspose-logo.jpg");
IPPImage imgx1 = pres.Images.AddImage(img1);

System.Drawing.Image img2 = (System.Drawing.Image)new Bitmap(dataDir + "Tulips.jpg");
IPPImage imgx2 = pres.Images.AddImage(img2);

// Prendi la prima serie di grafici
IChartSeries series = chart.ChartData.Series[0];

// Aggiungi nuovi punti dati con riempimento immagine
IChartDataPoint point = series.DataPoints.AddDataPointForLineSeries(fact.GetCell(defaultWorksheetIndex, 1, 1, (double)4.5));
point.Marker.Format.Fill.FillType = FillType.Picture;
point.Marker.Format.Fill.PictureFillFormat.Picture.Image = imgx1;

point = series.DataPoints.AddDataPointForLineSeries(fact.GetCell(defaultWorksheetIndex, 2, 1, (double)2.5));
point.Marker.Format.Fill.FillType = FillType.Picture;
point.Marker.Format.Fill.PictureFillFormat.Picture.Image = imgx2;

point = series.DataPoints.AddDataPointForLineSeries(fact.GetCell(defaultWorksheetIndex, 3, 1, (double)3.5));
point.Marker.Format.Fill.FillType = FillType.Picture;
point.Marker.Format.Fill.PictureFillFormat.Picture.Image = imgx1;

point = series.DataPoints.AddDataPointForLineSeries(fact.GetCell(defaultWorksheetIndex, 4, 1, (double)4.5));
point.Marker.Format.Fill.FillType = FillType.Picture;
point.Marker.Format.Fill.PictureFillFormat.Picture.Image = imgx2;
```

Impostiamo indicatori di immagine per i punti dati, consentendoti di personalizzare il modo in cui ciascun punto dati appare sul grafico.

## Passaggio 6: modifica della dimensione dell'indicatore della serie di grafici

```csharp
//Modifica delle dimensioni dell'indicatore delle serie di grafici
series.Marker.Size = 15;
```

Qui regoliamo la dimensione dell'indicatore della serie di grafici per renderlo visivamente accattivante.

## Passaggio 7: salvataggio della presentazione

```csharp
pres.Save(dataDir + "AsposeScatterChart.pptx", SaveFormat.Pptx);
```

Infine, salviamo la presentazione con le nuove impostazioni del grafico.

## Conclusione

Aspose.Slides per .NET ti consente di creare straordinarie presentazioni di grafici con varie opzioni di personalizzazione. In questo tutorial ci siamo concentrati sull'utilizzo delle opzioni degli indicatori del grafico sui punti dati per migliorare la rappresentazione visiva dei dati. Con Aspose.Slides per .NET, puoi portare le tue presentazioni al livello successivo, rendendole più coinvolgenti e informative.

 Se hai domande o hai bisogno di assistenza con Aspose.Slides per .NET, non esitare a visitare il[Documentazione Aspose.Slides](https://reference.aspose.com/slides/net/) o contattare il[Chiedi comunità](https://forum.aspose.com/) per supporto.

## Domande frequenti (FAQ)

### Posso utilizzare immagini personalizzate come marcatori per punti dati in Aspose.Slides per .NET?
Sì, puoi utilizzare immagini personalizzate come marcatori per punti dati in Aspose.Slides per .NET, come dimostrato in questo tutorial.

### Come posso modificare il tipo di grafico in Aspose.Slides per .NET?
È possibile modificare il tipo di grafico specificandone uno diverso`ChartType` durante la creazione del grafico, ad esempio "Bar", "Torta" o "Area".

### Aspose.Slides per .NET è compatibile con le ultime versioni di PowerPoint?
Aspose.Slides per .NET è progettato per funzionare con vari formati di PowerPoint e viene regolarmente aggiornato per mantenere la compatibilità con le ultime versioni di PowerPoint.

### Dove posso trovare ulteriori tutorial e risorse per Aspose.Slides per .NET?
 Puoi esplorare tutorial e risorse aggiuntivi nel file[Documentazione Aspose.Slides](https://reference.aspose.com/slides/net/).

### È disponibile una versione di prova di Aspose.Slides per .NET?
 Sì, puoi provare Aspose.Slides per .NET scaricando una versione di prova gratuita da[Qui](https://releases.aspose.com/).