---
title: Grafico a scatola nelle diapositive Java
linktitle: Grafico a scatola nelle diapositive Java
second_title: Aspose.Slides API di elaborazione Java PowerPoint
description: Scopri come creare grafici a scatola nelle presentazioni Java con Aspose.Slides. Guida passo passo e codice sorgente inclusi per una visualizzazione efficace dei dati.
type: docs
weight: 10
url: /it/java/chart-elements/box-chart-java-slides/
---

## Introduzione al grafico a scatola in Aspose.Slides per Java

In questo tutorial ti guideremo attraverso il processo di creazione di un grafico a scatola utilizzando Aspose.Slides per Java. I grafici a scatola sono utili per visualizzare i dati statistici con vari quartili e valori anomali. Forniremo istruzioni dettagliate insieme al codice sorgente per aiutarti a iniziare.

## Prerequisiti

Prima di iniziare, assicurati di avere quanto segue:

- Aspose.Slides per la libreria Java installata e configurata.
- Predisposizione di un ambiente di sviluppo Java.

## Passaggio 1: inizializzare la presentazione

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "test.pptx");
```

In questo passaggio inizializziamo un oggetto di presentazione utilizzando il percorso di un file PowerPoint esistente ("test.pptx" in questo esempio).

## Passaggio 2: crea il grafico a scatola

```java
try {
    IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.BoxAndWhisker, 50, 50, 500, 400);
    chart.getChartData().getCategories().clear();
    chart.getChartData().getSeries().clear();
```

In questo passaggio creiamo una forma di diagramma a scatola nella prima diapositiva della presentazione. Cancelliamo anche tutte le categorie e le serie esistenti dal grafico.

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

 In questo passaggio definiamo le categorie per il Box Chart. Noi usiamo il`IChartDataWorkbook` per aggiungere categorie ed etichettarle di conseguenza.

## Passaggio 4: crea la serie

```java
    IChartSeries series = chart.getChartData().getSeries().add(ChartType.BoxAndWhisker);
    series.setQuartileMethod(QuartileMethodType.Exclusive);
    series.setShowMeanLine(true);
    series.setShowMeanMarkers(true);
    series.setShowInnerPoints(true);
    series.setShowOutlierPoints(true);
```

Qui creiamo una serie BoxAndWhisker per il grafico e configuriamo varie opzioni come il metodo quartile, la linea media, gli indicatori medi, i punti interni e i punti anomali.

## Passaggio 5: aggiungi punti dati

```java
    series.getDataPoints().addDataPointForBoxAndWhiskerSeries(wb.getCell(0, "B1", 15));
    series.getDataPoints().addDataPointForBoxAndWhiskerSeries(wb.getCell(0, "B2", 41));
    series.getDataPoints().addDataPointForBoxAndWhiskerSeries(wb.getCell(0, "B3", 16));
    series.getDataPoints().addDataPointForBoxAndWhiskerSeries(wb.getCell(0, "B4", 10));
    series.getDataPoints().addDataPointForBoxAndWhiskerSeries(wb.getCell(0, "B5", 23));
    series.getDataPoints().addDataPointForBoxAndWhiskerSeries(wb.getCell(0, "B6", 16));
```

In questo passaggio aggiungiamo punti dati alla serie BoxAndWhisker. Questi punti dati rappresentano i dati statistici per il grafico.

## Passaggio 6: salva la presentazione

```java
    pres.save("BoxAndWhisker.pptx", SaveFormat.Pptx);
} finally {
    if (pres != null) pres.dispose();
}
```

Infine, salviamo la presentazione con il Box Chart in un nuovo file PowerPoint denominato "BoxAndWhisker.pptx".

Congratulazioni! Hai creato con successo un grafico a scatola utilizzando Aspose.Slides per Java. Puoi personalizzare ulteriormente il grafico regolando varie proprietà e aggiungendo più punti dati secondo necessità.

## Codice sorgente completo per il grafico a scatola nelle diapositive Java

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

In questo tutorial, abbiamo imparato come creare un grafico a scatola utilizzando Aspose.Slides per Java. I box chart sono strumenti preziosi per visualizzare i dati statistici, inclusi quartili e valori anomali. Abbiamo fornito una guida passo passo insieme al codice sorgente per aiutarti a iniziare a creare grafici a scatola nelle tue applicazioni Java.

## Domande frequenti

### Come posso modificare l'aspetto del grafico a scatola?

È possibile personalizzare l'aspetto del grafico a scatola modificando proprietà quali stili di linea, colori e caratteri. Fare riferimento alla documentazione Aspose.Slides per Java per i dettagli sulla personalizzazione del grafico.

### Posso aggiungere ulteriori serie di dati al Box Chart?

 Sì, puoi aggiungere più serie di dati al grafico a scatola creandone altre`IChartSeries` oggetti e aggiungendovi punti dati.

### Cosa significa QuartileMethodType.Exclusive?

 IL`QuartileMethodType.Exclusive` L'impostazione specifica che i calcoli del quartile devono essere eseguiti utilizzando il metodo esclusivo. Puoi scegliere diversi metodi di calcolo del quartile a seconda dei tuoi dati e requisiti.