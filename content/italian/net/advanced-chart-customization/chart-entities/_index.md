---
title: Entità del grafico e formattazione
linktitle: Entità del grafico e formattazione
second_title: API di elaborazione di PowerPoint .NET Aspose.Slides
description: Impara a creare e formattare grafici dinamici in PowerPoint utilizzando Aspose.Slides per .NET. Guida passo passo con il codice sorgente.
type: docs
weight: 13
url: /it/net/advanced-chart-customization/chart-entities/
---

## Introduzione ad Aspose.Slides e alla manipolazione dei grafici

Aspose.Slides per .NET è una libreria completa che consente agli sviluppatori di creare, modificare e manipolare presentazioni PowerPoint a livello di codice. Quando si tratta di grafici, Aspose.Slides offre un'ampia gamma di funzionalità per aggiungere, modificare e formattare grafici all'interno delle diapositive della presentazione.

## Configurazione dell'ambiente di sviluppo

 Per iniziare, assicurati di avere un ambiente di sviluppo funzionante con Aspose.Slides per .NET installato. È possibile scaricare la libreria da[Qui](https://releases.aspose.com/slides/net/).

## Aggiunta di un grafico a una diapositiva

Iniziamo aggiungendo un grafico a una diapositiva. Il codice seguente mostra come creare una nuova presentazione, aggiungere una diapositiva e inserirvi un grafico:

```csharp
// Istanziare l'oggetto Presentazione
Presentation presentation = new Presentation();

// Aggiungi una diapositiva
ISlide slide = presentation.Slides.AddEmptySlide();

// Aggiungi un grafico alla diapositiva
IChart chart = slide.Shapes.AddChart(ChartType.ClusteredColumn, 100, 100, 500, 300);
```

## Modifica dei dati del grafico

grafici non sono nulla senza dati. Aspose.Slides ti consente di popolare facilmente i grafici con i dati. Ecco come puoi modificare i dati del grafico:

```csharp
// Accedi alla cartella di lavoro del grafico
IChartDataWorkbook workbook = chart.ChartData.ChartDataWorkbook;

// Accedi al foglio di lavoro del grafico
IChartDataWorksheet worksheet = workbook.Worksheets[0];

// Compila i dati del grafico
worksheet.Cells["A1"].Value = "Category";
worksheet.Cells["A2"].Value = "Apple";
worksheet.Cells["A3"].Value = "Banana";
// ...

worksheet.Cells["B1"].Value = "Value";
worksheet.Cells["B2"].Value = 25;
worksheet.Cells["B3"].Value = 40;
// ...
```

## Personalizzazione dell'aspetto del grafico

La formattazione di un grafico ne migliora l'attrattiva visiva. Esploriamo come formattare i vari aspetti di un grafico:

## Formattazione del titolo e degli assi del grafico

Puoi formattare il titolo e gli assi del grafico utilizzando il seguente codice:

```csharp
chart.HasTitle = true;
chart.ChartTitle.TextFrame.Text = "Sales Report";

chart.Axes.HorizontalAxis.Title.TextFrame.Text = "Fruits";
chart.Axes.VerticalAxis.Title.TextFrame.Text = "Quantity";
```

## Applicazione degli stili di grafico

Applica stili di grafico predefiniti per rendere il tuo grafico più accattivante:

```csharp
chart.ChartStyle = ChartStylePreset.Style2;
```

## Regolazione delle etichette dati

Le etichette dati forniscono il contesto al grafico. Modificateli in questo modo:

```csharp
IDataLabel label = chart.Series[0].DataPoints[0].Label;
label.ShowValue = true;
label.DataLabelFormat.TextFormat.PortionFormat.FontBold = NullableBool.True;
```

## Lavorare con gli elementi del grafico

La gestione degli elementi del grafico migliora il controllo sulla rappresentazione visiva del grafico. Esploriamo alcune tecniche:

## Gestione delle serie di dati

Puoi aggiungere, rimuovere e manipolare serie di dati in questo modo:

```csharp
IChartSeries series = chart.ChartData.Series.Add(worksheet.Cells, "A2:A3", "B2:B3");
```

## Gestione delle legende dei grafici

Le legende forniscono informazioni essenziali sui componenti del grafico:

```csharp
chart.Legend.Position = LegendPosition.Bottom;
```

## Manipolazione dei punti dati

Regola i punti dati individualmente per enfatizzarli:

```csharp
chart.Series[0].DataPoints[0].Format.Fill.FillType = FillType.Solid;
chart.Series[0].DataPoints[0].Format.Fill.SolidFillColor.Color = Color.Red;
```

## Esportazione e salvataggio della presentazione modificata

Dopo aver apportato le modifiche desiderate al grafico, puoi salvare la presentazione:

```csharp
presentation.Save("ModifiedPresentation.pptx", SaveFormat.Pptx);
```

## Conclusione

In questa guida, abbiamo esplorato l'affascinante mondo delle entità grafiche e della formattazione utilizzando Aspose.Slides per .NET. Abbiamo iniziato con le nozioni di base sull'aggiunta e la modifica dei grafici, abbiamo approfondito la personalizzazione del loro aspetto e abbiamo persino gestito vari elementi del grafico. Aspose.Slides fornisce agli sviluppatori un potente toolkit per creare grafici visivamente accattivanti e informativi a livello di programmazione.

## Domande frequenti

### Come installo Aspose.Slides per .NET?

 È possibile scaricare Aspose.Slides per .NET da[Qui](https://releases.aspose.com/slides/net/).

### Posso applicare stili personalizzati ai grafici?

Sì, puoi applicare stili personalizzati ai grafici manipolando varie proprietà del grafico.

### Come faccio ad aggiungere etichette dati ai punti dati del grafico?

 Puoi aggiungere etichette dati ai punti dati del grafico utilizzando`DataLabel` proprietà di un punto dati.

### Aspose.Slides è adatto solo agli sviluppatori avanzati?

No, Aspose.Slides è progettato per soddisfare gli sviluppatori di tutti i livelli, dai principianti agli esperti.

### Posso esportare grafici in diversi formati utilizzando Aspose.Slides?

Assolutamente! Aspose.Slides supporta l'esportazione di presentazioni in vari formati, inclusi PowerPoint e PDF.