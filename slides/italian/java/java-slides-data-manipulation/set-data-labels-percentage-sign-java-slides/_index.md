---
"description": "Scopri come impostare etichette dati con simboli di percentuale nelle presentazioni PowerPoint utilizzando Aspose.Slides per Java. Crea grafici accattivanti con istruzioni dettagliate e codice sorgente."
"linktitle": "Imposta il segno percentuale delle etichette dati in Java Slides"
"second_title": "API di elaborazione Java PowerPoint di Aspose.Slides"
"title": "Imposta il segno percentuale delle etichette dati in Java Slides"
"url": "/it/java/data-manipulation/set-data-labels-percentage-sign-java-slides/"
"weight": 17
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Imposta il segno percentuale delle etichette dati in Java Slides


## Introduzione al segno percentuale delle etichette dati in Aspose.Slides per Java

In questa guida, ti guideremo attraverso il processo di impostazione delle etichette dati con il simbolo di percentuale utilizzando Aspose.Slides per Java. Creeremo una presentazione PowerPoint con un grafico a colonne impilate e configureremo le etichette dati per visualizzare le percentuali.

## Prerequisiti

Prima di iniziare, assicurati di aver aggiunto la libreria Aspose.Slides per Java al tuo progetto. Puoi scaricarla da [Qui](https://releases.aspose.com/slides/java/).

## Passaggio 1: creare una nuova presentazione

Per prima cosa, creiamo una nuova presentazione PowerPoint utilizzando Aspose.Slides.

```java
// Percorso verso la directory dei documenti.
String dataDir = "Your Document Directory";
// Crea un'istanza della classe Presentazione
Presentation presentation = new Presentation();
```

## Passaggio 2: aggiungere una diapositiva e un grafico

Successivamente aggiungiamo alla presentazione una diapositiva e un grafico a colonne impilate.

```java
// Ottieni il riferimento della diapositiva
ISlide slide = presentation.getSlides().get_Item(0);

// Aggiungi un grafico a colonne in pila con percentuali su una diapositiva
IChart chart = slide.getShapes().addChart(ChartType.PercentsStackedColumn, 20, 20, 500, 400);
```

## Passaggio 3: configurare il formato del numero dell'asse

Per visualizzare le percentuali, dobbiamo configurare il formato numerico per l'asse verticale del grafico.

```java
// Imposta NumberFormatLinkedToSource su falso
chart.getAxes().getVerticalAxis().setNumberFormatLinkedToSource(false);
chart.getAxes().getVerticalAxis().setNumberFormat("0.00%");
```

## Passaggio 4: aggiungere i dati del grafico

Aggiungiamo dati al grafico creando serie e punti dati. In questo esempio, aggiungiamo due serie con i rispettivi punti dati.

```java
// Ottenere il foglio di lavoro dei dati del grafico
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

Adesso personalizziamo l'aspetto delle etichette dati.

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

## Passaggio 6: Salva la presentazione

Infine, salviamo la presentazione in un file PowerPoint.

```java
// Scrivi la presentazione su disco
presentation.save(dataDir + "SetDataLabelsPercentageSign_out.pptx", SaveFormat.Pptx);
```

Ecco fatto! Hai creato con successo una presentazione PowerPoint con un grafico a colonne impilate e configurato le etichette dati per visualizzare le percentuali utilizzando Aspose.Slides per Java.

## Codice sorgente completo per impostare il segno percentuale delle etichette dati in Java Slides

```java
// Percorso verso la directory dei documenti.
String dataDir = "Your Document Directory";
// Crea un'istanza della classe Presentazione
Presentation presentation = new Presentation();
// Ottieni il riferimento della diapositiva
ISlide slide = presentation.getSlides().get_Item(0);
// Aggiungi un grafico a colonne in pila con percentuali su una diapositiva
IChart chart = slide.getShapes().addChart(ChartType.PercentsStackedColumn, 20, 20, 500, 400);
// Imposta NumberFormatLinkedToSource su falso
chart.getAxes().getVerticalAxis().setNumberFormatLinkedToSource(false);
chart.getAxes().getVerticalAxis().setNumberFormat("0.00%");
chart.getChartData().getSeries().clear();
int defaultWorksheetIndex = 0;
// Ottenere il foglio di lavoro dei dati del grafico
IChartDataWorkbook workbook = chart.getChartData().getChartDataWorkbook();
// Aggiungi nuova serie
IChartSeries series = chart.getChartData().getSeries().add(workbook.getCell(defaultWorksheetIndex, 0, 1, "Reds"), chart.getType());
series.getDataPoints().addDataPointForBarSeries(workbook.getCell(defaultWorksheetIndex, 1, 1, 0.30));
series.getDataPoints().addDataPointForBarSeries(workbook.getCell(defaultWorksheetIndex, 2, 1, 0.50));
series.getDataPoints().addDataPointForBarSeries(workbook.getCell(defaultWorksheetIndex, 3, 1, 0.80));
series.getDataPoints().addDataPointForBarSeries(workbook.getCell(defaultWorksheetIndex, 4, 1, 0.65));
// Impostazione del colore di riempimento della serie
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

Seguendo questa guida, hai imparato a creare presentazioni accattivanti con etichette dati basate su percentuali, che possono rivelarsi particolarmente utili per trasmettere informazioni in modo efficace in report aziendali, materiali didattici e altro ancora.

## Domande frequenti

### Come posso cambiare i colori delle serie di grafici?

È possibile modificare il colore di riempimento delle serie di grafici utilizzando `setFill` metodo come mostrato nell'esempio.

### Posso personalizzare la dimensione del carattere delle etichette dati?

Sì, puoi personalizzare la dimensione del carattere delle etichette dati impostando `setFontHeight` proprietà come dimostrato nel codice.

### Come posso aggiungere altre serie al grafico?

È possibile aggiungere ulteriori serie al grafico utilizzando `add` metodo sul `IChartSeriesCollection` oggetto.


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}