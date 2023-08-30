---
title: Aggiungi barre di errore personalizzate al grafico
linktitle: Aggiungi barre di errore personalizzate al grafico
second_title: API di elaborazione di PowerPoint .NET Aspose.Slides
description: Scopri come aggiungere barre di errore personalizzate ai grafici utilizzando Aspose.Slides per .NET. Crea, stili e personalizza le barre di errore per una visualizzazione accurata dei dati.
type: docs
weight: 13
url: /it/net/licensing-and-formatting/add-custom-error/
---

## Introduzione alle barre di errore personalizzate

Le barre di errore sono rappresentazioni grafiche utilizzate per indicare la variabilità o l'incertezza dei punti dati in un grafico. Possono aiutare a rappresentare l'intervallo entro il quale è probabile che rientri il valore reale del punto dati. Le barre di errore personalizzate ti consentono di definire valori di errore specifici per ciascun punto dati, fornendo un maggiore controllo sul modo in cui l'incertezza viene visualizzata nel grafico.

## Impostazione dell'ambiente di sviluppo

 Prima di iniziare, assicurati di aver installato la libreria Aspose.Slides per .NET. Puoi scaricarlo da[Qui](https://releases.aspose.com/slides/net). Seguire le istruzioni di installazione fornite nella documentazione.

## Creazione di un grafico di esempio

Iniziamo creando un grafico di esempio utilizzando Aspose.Slides per .NET. Creeremo un grafico a barre di base a scopo dimostrativo. Assicurati di aver fatto riferimento alla libreria nel tuo progetto.

```csharp
using Aspose.Slides;
using Aspose.Slides.Charts;

// Istanziare l'oggetto Presentazione
using Presentation presentation = new Presentation();

// Aggiungi una diapositiva
ISlide slide = presentation.Slides.AddSlide(0, presentation.SlideSize.Size);

// Aggiungi un grafico
IChart chart = slide.Shapes.AddChart(ChartType.ClusteredBar, 100, 100, 500, 300);

// Aggiungi dati di esempio
IChartDataWorkbook workbook = chart.ChartData.ChartDataWorkbook;
IChartSeries series = chart.ChartData.Series.Add(workbook.GetCell(0, "A1"), chart.Type);
series.Values.Add(workbook.GetCell(0, "B1"));
series.Values.Add(workbook.GetCell(0, "B2"));

// Imposta le etichette delle categorie
chart.ChartData.Categories.Add(workbook.GetCell(0, "A2"));
chart.ChartData.Categories.Add(workbook.GetCell(0, "A3"));

// Imposta il titolo del grafico
chart.ChartTitle.AddTextFrameForOverriding("Sample Chart");
chart.ChartTitle.TextFrameForOverriding.Text = "Sample Chart";

// Salva la presentazione
presentation.Save("SampleChart.pptx", SaveFormat.Pptx);
```

Questo codice crea una presentazione di PowerPoint con un grafico a barre di esempio.

## Aggiunta di barre di errore al grafico

Ora aggiungiamo le barre di errore al grafico. Le barre di errore vengono aggiunte a punti dati specifici in una serie. Aggiungeremo barre di errore al primo punto dati nel nostro grafico di esempio.

```csharp
// Accedi alla prima serie
IChartSeries firstSeries = chart.ChartData.Series[0];

// Aggiungi barre di errore
IErrorBarsFormat errorBarsFormat = firstSeries.ErrorBarsFormat.Add();
errorBarsFormat.Type = ErrorBarType.FixedValue;

// Imposta il valore della barra di errore
errorBarsFormat.Value = 5; // È possibile modificare il valore in base ai dati

// Salva la presentazione aggiornata
presentation.Save("ChartWithErrorBars.pptx", SaveFormat.Pptx);
```

Questo codice aggiunge barre di errore a valore fisso al primo punto dati del grafico.

## Personalizzazione dei valori della barra di errore

È possibile personalizzare i valori della barra di errore per ciascun punto dati individualmente. Modifichiamo il codice per impostare valori di errore diversi per ciascun punto dati.

```csharp
// Imposta valori di errore personalizzati per ciascun punto
double[] errorValues = { 3, 6 }; // Valori di errore per i due punti dati

for (int i = 0; i < firstSeries.DataPoints.Count; i++)
{
    firstSeries.ErrorBarsFormat[i].Value = errorValues[i];
}

// Salva la presentazione aggiornata
presentation.Save("CustomErrorValuesChart.pptx", SaveFormat.Pptx);
```

Questo codice imposta valori di errore personalizzati per ciascun punto dati della serie.

## Barre di errore di stile

Puoi definire uno stile per le barre di errore per migliorarne la visibilità e adattarle all'estetica del grafico. Personalizziamo l'aspetto delle barre di errore.

```csharp
// Personalizza l'aspetto della barra di errore
errorBarsFormat.LineFormat.Width = 2; // Imposta la larghezza della linea
errorBarsFormat.LineFormat.SolidFillColor.Color = Color.Red; //Imposta il colore della linea

// Salva la presentazione aggiornata
presentation.Save("StyledErrorBarsChart.pptx", SaveFormat.Pptx);
```

Questo codice regola la larghezza della linea e il colore delle barre di errore.

## Aggiornamento dei dati del grafico

Se hai bisogno di aggiornare i dati del grafico, puoi farlo facilmente utilizzando Aspose.Slides per .NET. Sostituiamo i dati con nuovi valori.

```csharp
// Aggiorna i dati del grafico
series.Values[0].Value = 15;
series.Values[1].Value = 20;

// Salva la presentazione aggiornata
presentation.Save("UpdatedChartData.pptx", SaveFormat.Pptx);
```

Questo codice aggiorna i valori dei dati del grafico.

## Barre di errore per serie multiple

Puoi aggiungere barre di errore a più serie in un grafico. Aggiungiamo le barre di errore alla seconda serie nel nostro grafico di esempio.

```csharp
// Accedi alla seconda serie
IChartSeries secondSeries = chart.ChartData.Series[1];

// Aggiungi barre di errore alla seconda serie
IErrorBarsFormat secondSeriesErrorBars = secondSeries.ErrorBarsFormat.Add();
secondSeriesErrorBars.Type = ErrorBarType.Percent;

// Imposta il valore della barra di errore per la seconda serie
secondSeriesErrorBars.Value = 10; // È possibile regolare il valore

// Salva la presentazione aggiornata
presentation.Save("MultiSeriesChartWithErrorBars.pptx", SaveFormat.Pptx);
```

Questo codice aggiunge barre di errore alla seconda serie nel grafico.

## Gestire gli errori negativi e positivi

Le barre di errore possono rappresentare errori sia positivi che negativi. Modifichiamo il codice per aggiungere entrambi i tipi di barre di errore.

```csharp
// Aggiungi barre di errore positive e negative
errorBarsFormat.Type = ErrorBarType.Custom;
errorBarsFormat.PlusValue = 4; // Valore di errore positivo
errorBarsFormat.MinusValue = 2; // Valore di errore negativo

// Salva la presentazione aggiornata
presentation.Save("PositiveNegativeErrorBars.pptx", SaveFormat.Pptx);
```

Questo codice aggiunge barre di errore positive e negative personalizzate al grafico.

## Salvataggio ed esportazione del grafico

Dopo aver aggiunto le barre di errore e personalizzato il grafico, puoi salvarlo ed esportarlo per un ulteriore utilizzo.

```csharp
// Salva il grafico finale
presentation.Save("FinalChart.pptx", SaveFormat.Pptx);
```

Questo codice salva il grafico finale con le barre di errore.

## Conclusione

In questo tutorial, abbiamo esplorato come aggiungere barre di errore personalizzate a un grafico utilizzando Aspose.Slides per .NET. Abbiamo trattato la creazione di un grafico di esempio, l'aggiunta di barre di errore, la personalizzazione dei valori di errore, lo stile delle barre di errore, l'aggiornamento dei dati del grafico, l'aggiunta di barre di errore a più serie e la gestione degli errori positivi e negativi. Con Aspose.Slides per .NET, hai la flessibilità di creare grafici informativi e visivamente accattivanti con barre di errore personalizzate che comunicano efficacemente la variabilità dei tuoi dati.

## Domande frequenti

### Come posso regolare lo spessore delle barre di errore?

 È possibile regolare lo spessore delle barre di errore modificando il file`LineFormat.Width` proprietà del`ErrorBarsFormat`.

### Posso utilizzare valori di errore diversi per ciascun punto dati?

Sì, puoi impostare valori di errore personalizzati per ciascun punto dati individualmente utilizzando un loop e il file`Value` proprietà di`ErrorBarsFormat`.

### È possibile aggiungere barre di errore a più serie in un unico grafico?

Assolutamente, puoi aggiungere barre di errore a più serie nello stesso grafico. Basta accedere alla serie desiderata e applicare le barre di errore come dimostrato nell'articolo.

### Posso rimuovere le barre di errore dopo averle aggiunte?

 Sì, puoi rimuovere le barre di errore chiamando il file`Clear` metodo sul`ErrorBarsFormat` oggetto.

### Dove posso trovare ulteriori informazioni su Aspose.Slides per .NET?

 È possibile trovare documentazione dettagliata ed esempi per Aspose.Slides per .NET su[Sito web della documentazione di Aspose](https://reference.aspose.com/slides/net/).