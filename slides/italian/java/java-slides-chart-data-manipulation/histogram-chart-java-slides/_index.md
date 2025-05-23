---
"description": "Scopri come creare grafici a istogramma nelle presentazioni PowerPoint utilizzando Aspose.Slides per Java. Guida passo passo con codice sorgente per la visualizzazione dei dati."
"linktitle": "Grafico a istogramma in Java Slides"
"second_title": "API di elaborazione Java PowerPoint di Aspose.Slides"
"title": "Grafico a istogramma in Java Slides"
"url": "/it/java/chart-data-manipulation/histogram-chart-java-slides/"
"weight": 19
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Grafico a istogramma in Java Slides


## Introduzione al grafico a istogramma in Java Slides utilizzando Aspose.Slides

In questo tutorial, ti guideremo attraverso il processo di creazione di un grafico a istogramma in una presentazione PowerPoint utilizzando l'API Aspose.Slides per Java. Un grafico a istogramma viene utilizzato per rappresentare la distribuzione dei dati su un intervallo continuo.

## Prerequisiti

Prima di iniziare, assicurati di aver installato la libreria Aspose.Slides per Java. Puoi scaricarla da [Sito web di Aspose](https://releases.aspose.com/slides/java/).

## Passaggio 1: inizializza il tuo progetto

Crea un progetto Java e includi la libreria Aspose.Slides nelle dipendenze del progetto.

## Passaggio 2: importare le librerie necessarie

```java
import com.aspose.slides.*;
```

## Passaggio 3: caricare una presentazione esistente

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "test.pptx");
```

Assicurati di sostituire `"Your Document Directory"` con il percorso effettivo del documento PowerPoint.

## Passaggio 4: creare un grafico a istogramma

Ora creiamo un grafico a istogramma su una diapositiva della presentazione.

```java
try {
    IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.Histogram, 50, 50, 500, 400);
    chart.getChartData().getCategories().clear();
    chart.getChartData().getSeries().clear();
    IChartDataWorkbook wb = chart.getChartData().getChartDataWorkbook();
    
    // Aggiungere punti dati alla serie
    IChartSeries series = chart.getChartData().getSeries().add(ChartType.Histogram);
    series.getDataPoints().addDataPointForHistogramSeries(wb.getCell(0, "A1", 15));
    series.getDataPoints().addDataPointForHistogramSeries(wb.getCell(0, "A2", -41));
    series.getDataPoints().addDataPointForHistogramSeries(wb.getCell(0, "A3", 16));
    series.getDataPoints().addDataPointForHistogramSeries(wb.getCell(0, "A4", 10));
    series.getDataPoints().addDataPointForHistogramSeries(wb.getCell(0, "A5", -23));
    series.getDataPoints().addDataPointForHistogramSeries(wb.getCell(0, "A6", 16));
    
    // Imposta il tipo di aggregazione dell'asse orizzontale su Automatico
    chart.getAxes().getHorizontalAxis().setAggregationType(AxisAggregationType.Automatic);
    
    // Salva la presentazione
    pres.save(dataDir + "Histogram.pptx", SaveFormat.Pptx);
} finally {
    if (pres != null) pres.dispose();
}
```

In questo codice, prima eliminiamo tutte le categorie e le serie esistenti dal grafico. Quindi, aggiungiamo punti dati alla serie utilizzando `getDataPoints().addDataPointForHistogramSeries` metodo. Infine, impostiamo il tipo di aggregazione dell'asse orizzontale su Automatico e salviamo la presentazione.

## Codice sorgente completo per il grafico a istogramma in Java Slides

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "test.pptx");
try
{
	IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.Histogram, 50, 50, 500, 400);
	chart.getChartData().getCategories().clear();
	chart.getChartData().getSeries().clear();
	IChartDataWorkbook wb = chart.getChartData().getChartDataWorkbook();
	wb.clear(0);
	IChartSeries series = chart.getChartData().getSeries().add(ChartType.Histogram);
	series.getDataPoints().addDataPointForHistogramSeries(wb.getCell(0, "A1", 15));
	series.getDataPoints().addDataPointForHistogramSeries(wb.getCell(0, "A2", -41));
	series.getDataPoints().addDataPointForHistogramSeries(wb.getCell(0, "A3", 16));
	series.getDataPoints().addDataPointForHistogramSeries(wb.getCell(0, "A4", 10));
	series.getDataPoints().addDataPointForHistogramSeries(wb.getCell(0, "A5", -23));
	series.getDataPoints().addDataPointForHistogramSeries(wb.getCell(0, "A6", 16));
	chart.getAxes().getHorizontalAxis().setAggregationType(AxisAggregationType.Automatic);
	pres.save(dataDir + "Histogram.pptx", SaveFormat.Pptx);
}
finally
{
	if (pres != null) pres.dispose();
}
```

## Conclusione

In questo tutorial, abbiamo esplorato come creare un grafico a istogramma in una presentazione di PowerPoint utilizzando l'API Aspose.Slides per Java. I grafici a istogramma sono strumenti preziosi per visualizzare la distribuzione dei dati su un intervallo continuo e possono rappresentare un'aggiunta preziosa alle vostre presentazioni, soprattutto quando si tratta di contenuti statistici o analitici.

## Domande frequenti

### Come faccio a installare Aspose.Slides per Java?

È possibile scaricare la libreria Aspose.Slides per Java da [Qui](https://releases.aspose.com/slides/java/)Seguire le istruzioni di installazione fornite sul loro sito web.

### A cosa serve un grafico a istogramma?

Un grafico a istogramma viene utilizzato per visualizzare la distribuzione dei dati su un intervallo continuo. È comunemente utilizzato in statistica per rappresentare le distribuzioni di frequenza.

### Posso personalizzare l'aspetto del grafico istogramma?

Sì, puoi personalizzare l'aspetto del grafico, inclusi i suoi colori, le etichette e gli assi, utilizzando l'API Aspose.Slides.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}