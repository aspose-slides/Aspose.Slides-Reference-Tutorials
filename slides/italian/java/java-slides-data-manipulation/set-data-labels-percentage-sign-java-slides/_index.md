---
title: Imposta il segno percentuale delle etichette dati nelle diapositive Java
linktitle: Imposta il segno percentuale delle etichette dati nelle diapositive Java
second_title: Aspose.Slides API di elaborazione Java PowerPoint
description: Scopri come impostare le etichette dei dati con segni di percentuale nelle presentazioni di PowerPoint utilizzando Aspose.Slides per Java. Crea grafici accattivanti con guida passo passo e codice sorgente.
weight: 17
url: /it/java/data-manipulation/set-data-labels-percentage-sign-java-slides/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}


## Introduzione all'impostazione delle etichette dei dati Segno percentuale in Aspose.Slides per Java

In questa guida ti guideremo attraverso il processo di impostazione delle etichette dei dati con un segno di percentuale utilizzando Aspose.Slides per Java. Creeremo una presentazione PowerPoint con un istogramma in pila e configureremo le etichette dei dati per visualizzare le percentuali.

## Prerequisiti

 Prima di iniziare, assicurati di aver aggiunto la libreria Aspose.Slides per Java al tuo progetto. Puoi scaricarlo da[Qui](https://releases.aspose.com/slides/java/).

## Passaggio 1: crea una nuova presentazione

Innanzitutto, creiamo una nuova presentazione di PowerPoint utilizzando Aspose.Slides.

```java
// Il percorso della directory dei documenti.
String dataDir = "Your Document Directory";
// Crea un'istanza della classe Presentation
Presentation presentation = new Presentation();
```

## Passaggio 2: aggiungi una diapositiva e un grafico

Successivamente, aggiungiamo una diapositiva e un istogramma in pila alla presentazione.

```java
// Ottieni il riferimento della diapositiva
ISlide slide = presentation.getSlides().get_Item(0);

// Aggiungi il grafico PercentsStackedColumn a una diapositiva
IChart chart = slide.getShapes().addChart(ChartType.PercentsStackedColumn, 20, 20, 500, 400);
```

## Passaggio 3: configurare il formato del numero dell'asse

Per visualizzare le percentuali, dobbiamo configurare il formato numerico per l'asse verticale del grafico.

```java
// Imposta NumberFormatLinkedToSource su false
chart.getAxes().getVerticalAxis().setNumberFormatLinkedToSource(false);
chart.getAxes().getVerticalAxis().setNumberFormat("0.00%");
```

## Passaggio 4: aggiungi i dati del grafico

Aggiungiamo dati al grafico creando serie e punti dati. In questo esempio, aggiungiamo due serie con i rispettivi punti dati.

```java
// Ottenere il foglio di lavoro con i dati del grafico
IChartDataWorkbook workbook = chart.getChartData().getChartDataWorkbook();

// Aggiungi nuova serie
IChartSeries series = chart.getChartData().getSeries().add(workbook.getCell(defaultWorksheetIndex, 0, 1, "Reds"), chart.getType());
series.getDataPoints().addDataPointForBarSeries(workbook.getCell(defaultWorksheetIndex, 1, 1, 0.30));
series.getDataPoints().addDataPointForBarSeries(workbook.getCell(defaultWorksheetIndex, 2, 1, 0.50));
series.getDataPoints().addDataPointForBarSeries(workbook.getCell(defaultWorksheetIndex, 3, 1, 0.80));
series.getDataPoints().addDataPointForBarSeries(workbook.getCell(defaultWorksheetIndex, 4, 1, 0.65));

// Aggiungi nuova serie
IChartSeries series2 = chart.getChartData().getSeries().add(workbook.getCell(defaultWorksheetIndex, 0, 2, "Blues"), chart.getType());
series2.getDataPoints().addDataPointForBarSeries(workbook.getCell(defaultWorksheetIndex, 1, 2, 0.70));
series2.getDataPoints().addDataPointForBarSeries(workbook.getCell(defaultWorksheetIndex, 2, 2, 0.50));
series2.getDataPoints().addDataPointForBarSeries(workbook.getCell(defaultWorksheetIndex, 3, 2, 0.20));
series2.getDataPoints().addDataPointForBarSeries(workbook.getCell(defaultWorksheetIndex, 4, 2, 0.35));
```

## Passaggio 5: personalizzare le etichette dati

Ora personalizziamo l'aspetto delle etichette dati.

```java
// Impostazione delle proprietà LabelFormat
series.getLabels().getDefaultDataLabelFormat().setShowValue(true);
series.getLabels().getDefaultDataLabelFormat().setNumberFormatLinkedToSource(false);
series.getLabels().getDefaultDataLabelFormat().setNumberFormat("0.0%");
series.getLabels().getDefaultDataLabelFormat().getTextFormat().getPortionFormat().setFontHeight(10);
series.getLabels().getDefaultDataLabelFormat().getTextFormat().getPortionFormat().getFillFormat().setFillType(FillType.Solid);
series.getLabels().getDefaultDataLabelFormat().getTextFormat().getPortionFormat().getFillFormat().getSolidFillColor().setColor(Color.WHITE);
series.getLabels().getDefaultDataLabelFormat().setShowValue(true);

series2.getLabels().getDefaultDataLabelFormat().setShowValue(true);
series2.getLabels().getDefaultDataLabelFormat().setNumberFormatLinkedToSource(false);
series2.getLabels().getDefaultDataLabelFormat().setNumberFormat("0.0%");
series2.getLabels().getDefaultDataLabelFormat().getTextFormat().getPortionFormat().setFontHeight(10);
series2.getLabels().getDefaultDataLabelFormat().getTextFormat().getPortionFormat().getFillFormat().setFillType(FillType.Solid);
series2.getLabels().getDefaultDataLabelFormat().getTextFormat().getPortionFormat().getFillFormat().getSolidFillColor().setColor(Color.WHITE);
```

## Passaggio 6: salva la presentazione

Infine, salviamo la presentazione in un file PowerPoint.

```java
// Scrivi la presentazione su disco
presentation.save(dataDir + "SetDataLabelsPercentageSign_out.pptx", SaveFormat.Pptx);
```

Questo è tutto! Hai creato con successo una presentazione di PowerPoint con un istogramma in pila e configurato etichette dati per visualizzare le percentuali utilizzando Aspose.Slides per Java.

## Codice sorgente completo per l'accesso percentuale delle etichette dei dati impostati nelle diapositive Java

```java
// Il percorso della directory dei documenti.
String dataDir = "Your Document Directory";
// Crea un'istanza della classe Presentation
Presentation presentation = new Presentation();
// Ottieni il riferimento della diapositiva
ISlide slide = presentation.getSlides().get_Item(0);
// Aggiungi il grafico PercentsStackedColumn a una diapositiva
IChart chart = slide.getShapes().addChart(ChartType.PercentsStackedColumn, 20, 20, 500, 400);
// Imposta NumberFormatLinkedToSource su false
chart.getAxes().getVerticalAxis().setNumberFormatLinkedToSource(false);
chart.getAxes().getVerticalAxis().setNumberFormat("0.00%");
chart.getChartData().getSeries().clear();
int defaultWorksheetIndex = 0;
// Ottenere il foglio di lavoro con i dati del grafico
IChartDataWorkbook workbook = chart.getChartData().getChartDataWorkbook();
// Aggiungi nuova serie
IChartSeries series = chart.getChartData().getSeries().add(workbook.getCell(defaultWorksheetIndex, 0, 1, "Reds"), chart.getType());
series.getDataPoints().addDataPointForBarSeries(workbook.getCell(defaultWorksheetIndex, 1, 1, 0.30));
series.getDataPoints().addDataPointForBarSeries(workbook.getCell(defaultWorksheetIndex, 2, 1, 0.50));
series.getDataPoints().addDataPointForBarSeries(workbook.getCell(defaultWorksheetIndex, 3, 1, 0.80));
series.getDataPoints().addDataPointForBarSeries(workbook.getCell(defaultWorksheetIndex, 4, 1, 0.65));
// Impostazione del colore di riempimento delle serie
series.getFormat().getFill().setFillType(FillType.Solid);
series.getFormat().getFill().getSolidFillColor().setColor(Color.RED);
// Impostazione delle proprietà LabelFormat
series.getLabels().getDefaultDataLabelFormat().setShowValue(true);
series.getLabels().getDefaultDataLabelFormat().setNumberFormatLinkedToSource(false);
series.getLabels().getDefaultDataLabelFormat().setNumberFormat("0.0%");
series.getLabels().getDefaultDataLabelFormat().getTextFormat().getPortionFormat().setFontHeight(10);
series.getLabels().getDefaultDataLabelFormat().getTextFormat().getPortionFormat().getFillFormat().setFillType(FillType.Solid);
series.getLabels().getDefaultDataLabelFormat().getTextFormat().getPortionFormat().getFillFormat().getSolidFillColor().setColor(Color.WHITE);
series.getLabels().getDefaultDataLabelFormat().setShowValue(true);
// Aggiungi nuova serie
IChartSeries series2 = chart.getChartData().getSeries().add(workbook.getCell(defaultWorksheetIndex, 0, 2, "Blues"), chart.getType());
series2.getDataPoints().addDataPointForBarSeries(workbook.getCell(defaultWorksheetIndex, 1, 2, 0.70));
series2.getDataPoints().addDataPointForBarSeries(workbook.getCell(defaultWorksheetIndex, 2, 2, 0.50));
series2.getDataPoints().addDataPointForBarSeries(workbook.getCell(defaultWorksheetIndex, 3, 2, 0.20));
series2.getDataPoints().addDataPointForBarSeries(workbook.getCell(defaultWorksheetIndex, 4, 2, 0.35));
// Impostazione del tipo e del colore di riempimento
series2.getFormat().getFill().setFillType(FillType.Solid);
series2.getFormat().getFill().getSolidFillColor().setColor(Color.BLUE);
series2.getLabels().getDefaultDataLabelFormat().setShowValue(true);
series2.getLabels().getDefaultDataLabelFormat().setNumberFormatLinkedToSource(false);
series2.getLabels().getDefaultDataLabelFormat().setNumberFormat("0.0%");
series2.getLabels().getDefaultDataLabelFormat().getTextFormat().getPortionFormat().setFontHeight(10);
series2.getLabels().getDefaultDataLabelFormat().getTextFormat().getPortionFormat().getFillFormat().setFillType(FillType.Solid);
series2.getLabels().getDefaultDataLabelFormat().getTextFormat().getPortionFormat().getFillFormat().getSolidFillColor().setColor(Color.WHITE);
// Scrivi la presentazione su disco
presentation.save(dataDir + "SetDataLabelsPercentageSign_out.pptx", SaveFormat.Pptx);
```

## Conclusione

Seguendo questa guida, hai imparato come creare presentazioni accattivanti con etichette di dati basate su percentuali, che possono essere particolarmente utili per trasmettere informazioni in modo efficace in report aziendali, materiali didattici e altro ancora.

## Domande frequenti

### Come posso cambiare i colori delle serie di grafici?

 Puoi modificare il colore di riempimento delle serie di grafici utilizzando`setFill` metodo come mostrato nell'esempio.

### Posso personalizzare la dimensione del carattere delle etichette dati?

Sì, puoi personalizzare la dimensione del carattere delle etichette dati impostando il file`setFontHeight` proprietà come dimostrato nel codice.

### Come posso aggiungere più serie al grafico?

 È possibile aggiungere ulteriori serie al grafico utilizzando il comando`add` metodo sul`IChartSeriesCollection` oggetto.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
