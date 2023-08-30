---
title: Recupera la cartella di lavoro dal grafico
linktitle: Recupera la cartella di lavoro dal grafico
second_title: API di elaborazione di PowerPoint .NET Aspose.Slides
description: Scopri come recuperare una cartella di lavoro da un grafico utilizzando Aspose.Slides per .NET. Estrai i dati dei grafici e crea cartelle di lavoro Excel a livello di codice.
type: docs
weight: 12
url: /it/net/additional-chart-features/chart-recover-workbook/
---

## introduzione

Possono verificarsi incidenti e potresti trovarti a dover recuperare una cartella di lavoro da un grafico. Aspose.Slides per .NET viene in soccorso in tali situazioni. Questa potente libreria ti consente di estrarre dati dai grafici nelle presentazioni e convertirli in una nuova cartella di lavoro. In questa guida passo passo, ti guideremo attraverso il processo di recupero di una cartella di lavoro da un grafico utilizzando Aspose.Slides per .NET.

## Prerequisiti

Prima di iniziare, assicurati di avere a disposizione quanto segue:

- Visual Studio: scarica e installa Visual Studio, essenziale per lo sviluppo .NET.
-  Aspose.Slides per .NET: è possibile scaricare la libreria da[Qui](https://downloads.aspose.com/slides/net).

## Passaggio 1: installare Aspose.Slides per .NET

Se non lo hai già fatto, scarica e installa Aspose.Slides per .NET. Questa libreria fornisce funzionalità complete per lavorare con le presentazioni di PowerPoint a livello di codice.

## Passaggio 2: carica la presentazione

Per iniziare, crea un nuovo progetto C# in Visual Studio. Aggiungere riferimenti agli assembly Aspose.Slides necessari. Carica la presentazione di PowerPoint che contiene il grafico da cui desideri recuperare i dati.

```csharp
// Carica la presentazione
Presentation presentation = new Presentation("your-presentation.pptx");
```

## Passaggio 3: identificare il grafico

 Identifica la diapositiva e il grafico da cui desideri recuperare i dati. È possibile accedere alle diapositive utilizzando il file`presentation.Slides` raccolta e grafici utilizzando il file`slide.Shapes` collezione.

```csharp
// Ottieni la diapositiva contenente il grafico
ISlide slide = presentation.Slides[0];

// Prendi il grafico
IChart chart = null;
foreach (IShape shape in slide.Shapes)
{
    if (shape is IChart)
    {
        chart = (IChart)shape;
        break;
    }
}
```

## Passaggio 4: estrai i dati dal grafico

Estrai i dati dal grafico utilizzando l'API di Aspose.Slides. È possibile recuperare valori dalle serie e dalle categorie di grafici.

```csharp
// Estrai i dati del grafico
IChartData chartData = chart.ChartData;
```

## Passaggio 5: crea una nuova cartella di lavoro

Crea una nuova cartella di lavoro Excel utilizzando una libreria come EPPlus o ClosedXML.

```csharp
// Crea una nuova cartella di lavoro di Excel
using (var excelPackage = new ExcelPackage())
{
    var worksheet = excelPackage.Workbook.Worksheets.Add("Chart Data");
    // Aggiungi qui il codice per popolare le intestazioni del foglio di lavoro
}
```

## Passaggio 6: popolare la cartella di lavoro con i dati del grafico

Compila il foglio di lavoro Excel con i dati estratti dal grafico.

```csharp
//Popolare il foglio di lavoro Excel con i dati del grafico
int rowIndex = 2;
foreach (var series in chartData.Series)
{
    worksheet.Cells[rowIndex, 1].Value = series.Name;
    // Aggiungi qui il codice per popolare il foglio di lavoro con i dati della serie
    rowIndex++;
}
```

## Passaggio 7: salvare la cartella di lavoro

Salva la cartella di lavoro di Excel con i dati del grafico recuperati.

```csharp
// Salva la cartella di lavoro di Excel
excelPackage.SaveAs(new FileInfo("recovered-workbook.xlsx"));
```

## Conclusione

Il recupero di una cartella di lavoro da un grafico è semplificato con Aspose.Slides per .NET. Seguendo questi passaggi, è possibile estrarre a livello di codice i dati da un grafico in una presentazione di PowerPoint e creare una nuova cartella di lavoro di Excel con i dati recuperati. Questo processo può essere un vero toccasana quando si verificano incidenti e i dati devono essere recuperati.

## Domande frequenti

### Come installo Aspose.Slides per .NET?

 È possibile scaricare Aspose.Slides per .NET da[Qui](https://downloads.aspose.com/slides/net).

### Posso recuperare dati da diversi tipi di grafici?

Sì, Aspose.Slides per .NET supporta vari tipi di grafici, inclusi grafici a barre, grafici a linee, grafici a torta e altro.

### Aspose.Slides per .NET è adatto all'uso professionale?

Assolutamente! Aspose.Slides per .NET è una solida libreria utilizzata dagli sviluppatori per lavorare in modo efficiente con le presentazioni PowerPoint.

### Esistono requisiti di licenza per l'utilizzo di Aspose.Slides per .NET?

 Sì, Aspose.Slides per .NET richiede una licenza valida per uso commerciale. Puoi trovare i dettagli della licenza su[Sito web Aspose](https://purchase.aspose.com).

### Posso personalizzare l'aspetto della cartella di lavoro Excel recuperata?

Sì, puoi personalizzare l'aspetto e la formattazione della cartella di lavoro Excel utilizzando librerie come EPPlus o ClosedXML.