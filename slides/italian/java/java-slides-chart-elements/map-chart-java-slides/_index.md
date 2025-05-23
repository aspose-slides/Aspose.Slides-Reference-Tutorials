---
"description": "Crea mappe spettacolari nelle presentazioni PowerPoint con Aspose.Slides per Java. Guida passo passo e codice sorgente per sviluppatori Java."
"linktitle": "Grafico a mappa in Java Slides"
"second_title": "API di elaborazione Java PowerPoint di Aspose.Slides"
"title": "Grafico a mappa in Java Slides"
"url": "/it/java/chart-elements/map-chart-java-slides/"
"weight": 15
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Grafico a mappa in Java Slides


## Introduzione al grafico a mappa in Java Slides utilizzando Aspose.Slides per Java

In questo tutorial, ti guideremo attraverso il processo di creazione di un grafico a mappa in una presentazione PowerPoint utilizzando Aspose.Slides per Java. I grafici a mappa sono un ottimo modo per visualizzare dati geografici nelle tue presentazioni.

## Prerequisiti

Prima di iniziare, assicurati di aver integrato la libreria Aspose.Slides per Java nel tuo progetto Java. Puoi scaricarla da [Qui](https://releases.aspose.com/slides/java/).

## Passaggio 1: imposta il tuo progetto

Assicurati di aver impostato il tuo progetto Java e di aver aggiunto la libreria Aspose.Slides per Java al classpath del tuo progetto.

## Passaggio 2: creare una presentazione PowerPoint

Per prima cosa, creiamo una nuova presentazione PowerPoint.

```java
String resultPath = "MapChart_out.pptx";
Presentation presentation = new Presentation();
```

## Passaggio 3: aggiungere un grafico della mappa

Adesso aggiungeremo una mappa alla presentazione.

```java
IChart chart = presentation.getSlides().get_Item(0).getShapes().addChart(ChartType.Map, 50, 50, 500, 400, false);
IChartDataWorkbook wb = chart.getChartData().getChartDataWorkbook();
```

## Passaggio 4: aggiungere dati al grafico della mappa

Aggiungiamo alcuni dati al grafico della mappa. Creeremo una serie e vi aggiungeremo punti dati.

```java
IChartSeries series = chart.getChartData().getSeries().add(ChartType.Map);
series.getDataPoints().addDataPointForMapSeries(wb.getCell(0, "B2", 5));
series.getDataPoints().addDataPointForMapSeries(wb.getCell(0, "B3", 1));
series.getDataPoints().addDataPointForMapSeries(wb.getCell(0, "B4", 10));
```

## Passaggio 5: aggiungere categorie

Dobbiamo aggiungere categorie alla mappa, che rappresentino diverse regioni geografiche.

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

## Passaggio 7: Salva la presentazione

Infine, salva la presentazione con la mappa.

```java
presentation.save(resultPath, SaveFormat.Pptx);
```

Ecco fatto! Hai creato un grafico a mappa in una presentazione PowerPoint utilizzando Aspose.Slides per Java. Puoi personalizzare ulteriormente il grafico ed esplorare altre funzionalità offerte da Aspose.Slides per migliorare le tue presentazioni.

## Codice sorgente completo per il grafico della mappa in Java Slides

```java
String resultPath = "Your Output Directory" +  "MapChart_out.pptx";
Presentation presentation = new Presentation();
try {
	//crea un grafico vuoto
	IChart chart = presentation.getSlides().get_Item(0).getShapes().addChart(ChartType.Map, 50, 50, 500, 400, false);
	IChartDataWorkbook wb = chart.getChartData().getChartDataWorkbook();
	//Aggiungi serie e pochi punti dati
	IChartSeries series = chart.getChartData().getSeries().add(ChartType.Map);
	series.getDataPoints().addDataPointForMapSeries(wb.getCell(0, "B2", 5));
	series.getDataPoints().addDataPointForMapSeries(wb.getCell(0, "B3", 1));
	series.getDataPoints().addDataPointForMapSeries(wb.getCell(0, "B4", 10));
	//aggiungere categorie
	chart.getChartData().getCategories().add(wb.getCell(0, "A2", "United States"));
	chart.getChartData().getCategories().add(wb.getCell(0, "A3", "Mexico"));
	chart.getChartData().getCategories().add(wb.getCell(0, "A4", "Brazil"));
	//modifica il valore del punto dati
	IChartDataPoint dataPoint = series.getDataPoints().get_Item(1);
	dataPoint.getColorValue().getAsCell().setValue("15");
	//imposta l'aspetto del punto dati
	dataPoint.getFormat().getFill().setFillType(FillType.Solid);
	dataPoint.getFormat().getFill().getSolidFillColor().setColor(Color.GREEN);
	presentation.save(resultPath, SaveFormat.Pptx);
} finally {
	if (presentation != null) presentation.dispose();
}
```

## Conclusione

In questo tutorial, abbiamo illustrato il processo di creazione di un grafico a mappa in una presentazione PowerPoint utilizzando Aspose.Slides per Java. I grafici a mappa sono un modo efficace per visualizzare dati geografici, rendendo le presentazioni più coinvolgenti e informative. Riassumiamo i passaggi chiave:

## Domande frequenti

### Come posso cambiare il tipo di grafico della mappa?

È possibile modificare il tipo di grafico sostituendolo `ChartType.Map` con il tipo di grafico desiderato durante la creazione del grafico nel passaggio 3.

### Come posso personalizzare l'aspetto del grafico della mappa?

È possibile personalizzare l'aspetto del grafico modificandone le proprietà `dataPoint` oggetto nel passaggio 6. È possibile modificare colori, valori e altro ancora.

### Posso aggiungere altri punti dati e categorie?

Sì, puoi aggiungere tutti i punti dati e le categorie di cui hai bisogno. Usa semplicemente il `series.getDataPoints().addDataPointForMapSeries()` E `chart.getChartData().getCategories().add()` metodi per aggiungerli.

### Come posso integrare Aspose.Slides per Java nel mio progetto?

Scarica la libreria da [Qui](https://releases.aspose.com/slides/java/) e aggiungilo al classpath del tuo progetto.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}