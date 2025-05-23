---
"description": "Scopri come creare grafici a scatola nelle presentazioni Java con Aspose.Slides. Guida dettagliata e codice sorgente inclusi per una visualizzazione efficace dei dati."
"linktitle": "Grafico a scatola in Java Slides"
"second_title": "API di elaborazione Java PowerPoint di Aspose.Slides"
"title": "Grafico a scatola in Java Slides"
"url": "/it/java/chart-elements/box-chart-java-slides/"
"weight": 10
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Grafico a scatola in Java Slides


## Introduzione al grafico a scatola in Aspose.Slides per Java

In questo tutorial, ti guideremo attraverso il processo di creazione di un grafico a scatola utilizzando Aspose.Slides per Java. I grafici a scatola sono utili per visualizzare dati statistici con diversi quartili e valori anomali. Forniremo istruzioni dettagliate e il codice sorgente per aiutarti a iniziare.

## Prerequisiti

Prima di iniziare, assicurati di avere quanto segue:

- Libreria Aspose.Slides per Java installata e configurata.
- È stato configurato un ambiente di sviluppo Java.

## Passaggio 1: inizializzare la presentazione

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "test.pptx");
```

In questo passaggio inizializziamo un oggetto presentazione utilizzando il percorso verso un file PowerPoint esistente ("test.pptx" in questo esempio).

## Passaggio 2: creare il grafico a scatola

```java
try {
    IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.BoxAndWhisker, 50, 50, 500, 400);
    chart.getChartData().getCategories().clear();
    chart.getChartData().getSeries().clear();
```

In questa fase, creiamo un grafico a scatola nella prima diapositiva della presentazione. Eliminiamo anche eventuali categorie e serie esistenti dal grafico.

## Passaggio 3: definire le categorie

```java
    IChartDataWorkbook wb = chart.getChartData().getChartDataWorkbook();
    wb.clear(0);
    chart.getChartData().getCategories().add(wb.getCell(0, "A1", "Category 1"));
    chart.getChartData().getCategories().add(wb.getCell(0, "A2", "Category 1"));
    chart.getChartData().getCategories().add(wb.getCell(0, "A3", "Category 1"));
    chart.getChartData().getCategories().add(wb.getCell(0, "A4", "Category 1"));
    chart.getChartData().getCategories().add(wb.getCell(0, "A5", "Category 1"));
    chart.getChartData().getCategories().add(wb.getCell(0, "A6", "Category 1"));
```

In questo passaggio, definiamo le categorie per il grafico a scatola. Utilizziamo il `IChartDataWorkbook` per aggiungere categorie ed etichettarle di conseguenza.

## Passaggio 4: creare la serie

```java
    IChartSeries series = chart.getChartData().getSeries().add(ChartType.BoxAndWhisker);
    series.setQuartileMethod(QuartileMethodType.Exclusive);
    series.setShowMeanLine(true);
    series.setShowMeanMarkers(true);
    series.setShowInnerPoints(true);
    series.setShowOutlierPoints(true);
```

Qui creiamo una serie BoxAndWhisker per il grafico e configuriamo varie opzioni, come il metodo dei quartili, la linea media, i marcatori della media, i punti interni e i punti anomali.

## Passaggio 5: aggiungere punti dati

```java
    series.getDataPoints().addDataPointForBoxAndWhiskerSeries(wb.getCell(0, "B1", 15));
    series.getDataPoints().addDataPointForBoxAndWhiskerSeries(wb.getCell(0, "B2", 41));
    series.getDataPoints().addDataPointForBoxAndWhiskerSeries(wb.getCell(0, "B3", 16));
    series.getDataPoints().addDataPointForBoxAndWhiskerSeries(wb.getCell(0, "B4", 10));
    series.getDataPoints().addDataPointForBoxAndWhiskerSeries(wb.getCell(0, "B5", 23));
    series.getDataPoints().addDataPointForBoxAndWhiskerSeries(wb.getCell(0, "B6", 16));
```

In questa fase, aggiungiamo punti dati alla serie BoxAndWhisker. Questi punti dati rappresentano i dati statistici per il grafico.

## Passaggio 6: Salva la presentazione

```java
    pres.save("BoxAndWhisker.pptx", SaveFormat.Pptx);
} finally {
    if (pres != null) pres.dispose();
}
```

Infine, salviamo la presentazione con il grafico a scatola in un nuovo file PowerPoint denominato "BoxAndWhisker.pptx".

Congratulazioni! Hai creato con successo un grafico a scatola utilizzando Aspose.Slides per Java. Puoi personalizzare ulteriormente il grafico modificando diverse proprietà e aggiungendo altri punti dati, se necessario.

## Codice sorgente completo per il grafico a scatola in Java Slides

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "test.pptx");
try
{
	IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.BoxAndWhisker, 50, 50, 500, 400);
	chart.getChartData().getCategories().clear();
	chart.getChartData().getSeries().clear();
	IChartDataWorkbook wb = chart.getChartData().getChartDataWorkbook();
	wb.clear(0);
	chart.getChartData().getCategories().add(wb.getCell(0, "A1", "Category 1"));
	chart.getChartData().getCategories().add(wb.getCell(0, "A2", "Category 1"));
	chart.getChartData().getCategories().add(wb.getCell(0, "A3", "Category 1"));
	chart.getChartData().getCategories().add(wb.getCell(0, "A4", "Category 1"));
	chart.getChartData().getCategories().add(wb.getCell(0, "A5", "Category 1"));
	chart.getChartData().getCategories().add(wb.getCell(0, "A6", "Category 1"));
	IChartSeries series = chart.getChartData().getSeries().add(ChartType.BoxAndWhisker);
	series.setQuartileMethod(QuartileMethodType.Exclusive);
	series.setShowMeanLine(true);
	series.setShowMeanMarkers(true);
	series.setShowInnerPoints(true);
	series.setShowOutlierPoints(true);
	series.getDataPoints().addDataPointForBoxAndWhiskerSeries(wb.getCell(0, "B1", 15));
	series.getDataPoints().addDataPointForBoxAndWhiskerSeries(wb.getCell(0, "B2", 41));
	series.getDataPoints().addDataPointForBoxAndWhiskerSeries(wb.getCell(0, "B3", 16));
	series.getDataPoints().addDataPointForBoxAndWhiskerSeries(wb.getCell(0, "B4", 10));
	series.getDataPoints().addDataPointForBoxAndWhiskerSeries(wb.getCell(0, "B5", 23));
	series.getDataPoints().addDataPointForBoxAndWhiskerSeries(wb.getCell(0, "B6", 16));
	pres.save("BoxAndWhisker.pptx", SaveFormat.Pptx);
}
finally
{
	if (pres != null) pres.dispose();
}
```

## Conclusione

In questo tutorial abbiamo imparato a creare un grafico a scatola utilizzando Aspose.Slides per Java. I grafici a scatola sono strumenti preziosi per visualizzare dati statistici, inclusi quartili e valori anomali. Abbiamo fornito una guida passo passo e il codice sorgente per aiutarti a iniziare a creare grafici a scatola nelle tue applicazioni Java.

## Domande frequenti

### Come posso modificare l'aspetto del grafico a scatola?

È possibile personalizzare l'aspetto del grafico a scatola modificando proprietà come stili di linea, colori e font. Per informazioni dettagliate sulla personalizzazione dei grafici, consultare la documentazione di Aspose.Slides per Java.

### Posso aggiungere ulteriori serie di dati al grafico a scatola?

Sì, puoi aggiungere più serie di dati al grafico a scatola creandone altre `IChartSeries` oggetti e aggiungendovi punti dati.

### Cosa significa QuartileMethodType.Exclusive?

IL `QuartileMethodType.Exclusive` L'impostazione specifica che i calcoli dei quartili devono essere eseguiti utilizzando il metodo esclusivo. È possibile scegliere diversi metodi di calcolo dei quartili a seconda dei dati e delle esigenze.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}