---
title: Creazione e personalizzazione di grafici in Aspose.Slides
linktitle: Creazione e personalizzazione di grafici in Aspose.Slides
second_title: API di elaborazione di PowerPoint .NET Aspose.Slides
description: Scopri come creare e personalizzare grafici straordinari utilizzando Aspose.Slides per .NET. Guida passo passo con esempi di codice.
type: docs
weight: 10
url: /it/net/chart-creation-and-customization/chart-creation-and-customization/
---

## Introduzione ad Aspose.Slides

Aspose.Slides è una solida libreria che fornisce API per lavorare con presentazioni PowerPoint in vari linguaggi di programmazione, incluso .NET. Consente agli sviluppatori di creare, manipolare e gestire diversi elementi di presentazioni, come diapositive, forme, testo e grafici.

## Impostazione del tuo progetto

Prima di iniziare, assicurati di avere la libreria Aspose.Slides installata nel tuo progetto .NET. È possibile scaricarlo dal sito Web Aspose o installarlo tramite il gestore pacchetti NuGet.

```csharp
// Installa Aspose.Slides tramite NuGet
Install-Package Aspose.Slides
```

## Creazione di un grafico

Per creare un grafico utilizzando Aspose.Slides, attenersi alla seguente procedura:

1. Importa gli spazi dei nomi necessari:
```csharp
using Aspose.Slides;
using Aspose.Slides.Charts;
```

2. Inizializza una presentazione:
```csharp
Presentation presentation = new Presentation();
ISlide slide = presentation.Slides.AddEmptySlide();
```

3. Aggiungi un grafico alla diapositiva:
```csharp
IChart chart = slide.Shapes.AddChart(ChartType.Column, 100, 100, 500, 300);
```

## Aggiunta di dati al grafico

Successivamente, aggiungiamo i dati al nostro grafico:

1. Accedi alla cartella di lavoro del grafico:
```csharp
IChartDataWorkbook workbook = chart.ChartData.ChartDataWorkbook;
```

2. Aggiungi categorie e serie:
```csharp
workbook.AddCell(0, 1, "Category 1");
workbook.AddCell(0, 2, "Category 2");

IChartSeries series = chart.ChartData.Series.Add(workbook.GetCell(0, 1), chart.Type);
```

3. Imposta i valori per la serie:
```csharp
series.DataPoints.AddDataPointForBarSeries(workbook.GetCell(0, 2));
```

## Personalizzazione degli elementi del grafico

Puoi personalizzare vari elementi del grafico:

1. Personalizza il titolo del grafico:
```csharp
chart.HasTitle = true;
chart.ChartTitle.Text.Text = "Sales Data";
```

2. Modifica le proprietà dell'asse:
```csharp
chart.Axes.HorizontalAxis.HasTitle = true;
chart.Axes.HorizontalAxis.Title.Text.Text = "Months";
```

3. Regola le griglie e i segni di spunta:
```csharp
chart.Axes.VerticalAxis.MajorGridLinesFormat.Line.FillFormat.FillType = FillType.Solid;
chart.Axes.VerticalAxis.MajorGridLinesFormat.Line.FillFormat.SolidFillColor.Color = Color.Gray;
```

## Applicazione di stili e colori

Migliora l'aspetto del tuo grafico:

1. Applica lo stile del grafico:
```csharp
chart.ChartStyle = 5; // Scegli lo stile desiderato
```

2. Imposta i colori della serie:
```csharp
series.Format.Fill.FillType = FillType.Solid;
series.Format.Fill.SolidFillColor.Color = Color.Blue;
```

## Formattazione di assi ed etichette

Controlla la formattazione e le etichette degli assi:

1. Formato valori dell'asse:
```csharp
chart.Axes.HorizontalAxis.NumberFormat.FormatCode = "mm/dd";
```

2. Ruota le etichette degli assi:
```csharp
chart.Axes.HorizontalAxis.TextFormat.RotationAngle = 45;
```

## Aggiunta di titoli e leggende

Aggiungi titoli e legende per migliorare la chiarezza:

1. Personalizza le proprietà della legenda:
```csharp
chart.Legend.Position = LegendPosition.Bottom;
chart.Legend.TextFormat.PortionFormat.FontBold = NullableBool.True;
```

2. Imposta i titoli degli assi:
```csharp
chart.Axes.VerticalAxis.Title.Text.Text = "Sales";
```

## Lavorare con più serie

Incorpora più serie per una rappresentazione completa dei dati:

1. Aggiungi serie aggiuntive:
```csharp
IChartSeries series2 = chart.ChartData.Series.Add(workbook.GetCell(0, 2), chart.Type);
```

2. Imposta i valori per la nuova serie:
```csharp
series2.DataPoints.AddDataPointForBarSeries(workbook.GetCell(0, 3));
```

## Salvare ed esportare la presentazione

Infine, salva ed esporta la tua presentazione:

```csharp
presentation.Save("ChartPresentation.pptx", SaveFormat.Pptx);
```
## Conclusione

In questo tutorial, abbiamo esplorato come creare, personalizzare e manipolare grafici utilizzando la libreria Aspose.Slides per .NET. Aspose.Slides fornisce un set completo di funzionalità che consentono agli sviluppatori di lavorare a livello di programmazione con presentazioni PowerPoint e gestire in modo efficiente le attività relative ai grafici.

## Domande frequenti

### Come posso modificare il tipo di grafico dopo averlo creato?

 È possibile modificare il tipo di grafico utilizzando il file`ChangeType` metodo sull'oggetto grafico e fornendo il metodo desiderato`ChartType` valore di enumerazione.

### Posso applicare effetti 3D al mio grafico?

 Sì, puoi aggiungere effetti 3D al tuo grafico configurando il file`Format.ThreeDFormat` proprietà della serie del grafico.

### È possibile incorporare grafici nelle applicazioni web?

Assolutamente! È possibile creare grafici utilizzando Aspose.Slides e quindi visualizzarli in applicazioni Web esportando le diapositive come immagini o HTML interattivo.

### Posso personalizzare l'aspetto dei singoli punti dati?

 Certamente! È possibile accedere ai singoli punti dati utilizzando il file`DataPoints`raccolta e applicarvi la formattazione.

### Dove posso trovare ulteriori informazioni su Aspose.Slides per .NET?

 Per documentazione dettagliata ed esempi, visitare il[Aspose.Slides per la documentazione .NET](https://reference.aspose.com/slides/net).