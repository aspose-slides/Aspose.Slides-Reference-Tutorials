---
title: Grafico della mappa nelle diapositive Java
linktitle: Grafico della mappa nelle diapositive Java
second_title: Aspose.Slides API di elaborazione Java PowerPoint
description: Crea straordinari grafici a mappa nelle presentazioni PowerPoint con Aspose.Slides per Java. Guida passo passo e codice sorgente per gli sviluppatori Java.
type: docs
weight: 15
url: /it/java/chart-elements/map-chart-java-slides/
---

## Introduzione al grafico a mappe in Diapositive Java utilizzando Aspose.Slides per Java

In questo tutorial, ti guideremo attraverso il processo di creazione di un grafico a mappa in una presentazione di PowerPoint utilizzando Aspose.Slides per Java. I grafici a mappa sono un ottimo modo per visualizzare i dati geografici nelle tue presentazioni.

## Prerequisiti

 Prima di iniziare, assicurati di avere la libreria Aspose.Slides per Java integrata nel tuo progetto Java. Puoi scaricarlo da[Qui](https://releases.aspose.com/slides/java/).

## Passaggio 1: imposta il tuo progetto

Assicurati di aver impostato il tuo progetto Java e aggiunto la libreria Aspose.Slides per Java al classpath del tuo progetto.

## Passaggio 2: crea una presentazione PowerPoint

Innanzitutto, creiamo una nuova presentazione di PowerPoint.

```java
String resultPath = "MapChart_out.pptx";
Presentation presentation = new Presentation();
```

## Passaggio 3: aggiungi un grafico a mappa

Ora aggiungeremo un grafico a mappa alla presentazione.

```java
IChart chart = presentation.getSlides().get_Item(0).getShapes().addChart(ChartType.Map, 50, 50, 500, 400, false);
IChartDataWorkbook wb = chart.getChartData().getChartDataWorkbook();
```

## Passaggio 4: aggiungi dati al grafico della mappa

Aggiungiamo alcuni dati al grafico della mappa. Creeremo una serie e vi aggiungeremo punti dati.

```java
IChartSeries series = chart.getChartData().getSeries().add(ChartType.Map);
series.getDataPoints().addDataPointForMapSeries(wb.getCell(0, "B2", 5));
series.getDataPoints().addDataPointForMapSeries(wb.getCell(0, "B3", 1));
series.getDataPoints().addDataPointForMapSeries(wb.getCell(0, "B4", 10));
```

## Passaggio 5: aggiungi categorie

Dobbiamo aggiungere categorie al grafico della mappa, che rappresentano diverse regioni geografiche.

```java
chart.getChartData().getCategories().add(wb.getCell(0, "A2", "United States"));
chart.getChartData().getCategories().add(wb.getCell(0, "A3", "Mexico"));
chart.getChartData().getCategories().add(wb.getCell(0, "A4", "Brazil"));
```

## Passaggio 6: personalizzare i punti dati

È possibile personalizzare singoli punti dati. In questo esempio, modifichiamo il colore e il valore di un punto dati specifico.

```java
IChartDataPoint dataPoint = series.getDataPoints().get_Item(1);
dataPoint.getColorValue().getAsCell().setValue("15");
dataPoint.getFormat().getFill().setFillType(FillType.Solid);
dataPoint.getFormat().getFill().getSolidFillColor().setColor(Color.GREEN);
```

## Passaggio 7: salva la presentazione

Infine, salva la presentazione con il grafico della mappa.

```java
presentation.save(resultPath, SaveFormat.Pptx);
```

Questo è tutto! Hai creato un grafico a mappa in una presentazione di PowerPoint utilizzando Aspose.Slides per Java. Puoi personalizzare ulteriormente il grafico ed esplorare altre funzionalità offerte da Aspose.Slides per migliorare le tue presentazioni.

## Codice sorgente completo per il grafico della mappa nelle diapositive Java

```java
String resultPath = RunExamples.getOutPath() +  "MapChart_out.pptx";
Presentation presentation = new Presentation();
try {
	//creare un grafico vuoto
	IChart chart = presentation.getSlides().get_Item(0).getShapes().addChart(ChartType.Map, 50, 50, 500, 400, false);
	IChartDataWorkbook wb = chart.getChartData().getChartDataWorkbook();
	//Aggiungi serie e alcuni punti dati
	IChartSeries series = chart.getChartData().getSeries().add(ChartType.Map);
	series.getDataPoints().addDataPointForMapSeries(wb.getCell(0, "B2", 5));
	series.getDataPoints().addDataPointForMapSeries(wb.getCell(0, "B3", 1));
	series.getDataPoints().addDataPointForMapSeries(wb.getCell(0, "B4", 10));
	//aggiungere categorie
	chart.getChartData().getCategories().add(wb.getCell(0, "A2", "United States"));
	chart.getChartData().getCategories().add(wb.getCell(0, "A3", "Mexico"));
	chart.getChartData().getCategories().add(wb.getCell(0, "A4", "Brazil"));
	//modificare il valore del punto dati
	IChartDataPoint dataPoint = series.getDataPoints().get_Item(1);
	dataPoint.getColorValue().getAsCell().setValue("15");
	//impostare l'aspetto del punto dati
	dataPoint.getFormat().getFill().setFillType(FillType.Solid);
	dataPoint.getFormat().getFill().getSolidFillColor().setColor(Color.GREEN);
	presentation.save(resultPath, SaveFormat.Pptx);
} finally {
	if (presentation != null) presentation.dispose();
}
```

## Conclusione

In questo tutorial, abbiamo esaminato il processo di creazione di un grafico a mappa in una presentazione di PowerPoint utilizzando Aspose.Slides per Java. I grafici a mappa rappresentano un modo efficace per visualizzare i dati geografici, rendendo le tue presentazioni più coinvolgenti e informative. Riassumiamo i passaggi fondamentali:

## Domande frequenti

### Come posso modificare il tipo di grafico della mappa?

 È possibile modificare il tipo di grafico sostituendo`ChartType.Map` con il tipo di grafico desiderato durante la creazione del grafico al passaggio 3.

### Come posso personalizzare l'aspetto del grafico della mappa?

 È possibile personalizzare l'aspetto del grafico modificando le proprietà del file`dataPoint` oggetto nel passaggio 6. Puoi modificare colori, valori e altro.

### Posso aggiungere più punti dati e categorie?

 Sì, puoi aggiungere tutti i punti dati e le categorie necessari. Usa semplicemente il`series.getDataPoints().addDataPointForMapSeries()` E`chart.getChartData().getCategories().add()` metodi per aggiungerli.

### Come posso integrare Aspose.Slides per Java nel mio progetto?

 Scarica la libreria da[Qui](https://releases.aspose.com/slides/java/) e aggiungilo al classpath del tuo progetto.