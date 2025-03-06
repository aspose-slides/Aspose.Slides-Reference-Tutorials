---
title: Indicatori predefiniti nel grafico nelle diapositive Java
linktitle: Indicatori predefiniti nel grafico nelle diapositive Java
second_title: Aspose.Slides API di elaborazione Java PowerPoint
description: Scopri come creare diapositive Java con indicatori predefiniti nei grafici utilizzando Aspose.Slides per Java. Guida passo passo con il codice sorgente.
weight: 16
url: /it/java/chart-data-manipulation/default-markers-in-chart-java-slides/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Indicatori predefiniti nel grafico nelle diapositive Java


## Introduzione agli indicatori predefiniti nel grafico nelle diapositive Java

In questo tutorial esploreremo come creare un grafico con indicatori predefiniti utilizzando Aspose.Slides per Java. Gli indicatori predefiniti sono simboli o forme aggiunti ai punti dati in un grafico per evidenziarli. Creeremo un grafico a linee con indicatori per visualizzare i dati.

## Prerequisiti

Prima di iniziare, assicurati di avere la libreria Aspose.Slides per Java installata e configurata nel tuo progetto Java.

## Passaggio 1: crea una presentazione

Innanzitutto, creiamo una presentazione e aggiungiamo una diapositiva. Aggiungeremo quindi un grafico alla diapositiva.

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
ISlide slide = pres.getSlides().get_Item(0);
```

## Passaggio 2: aggiungi un grafico a linee con indicatori

Ora aggiungiamo un grafico a linee con indicatori alla diapositiva. Cancelleremo anche tutti i dati predefiniti dal grafico.

```java
IChart chart = slide.getShapes().addChart(ChartType.LineWithMarkers, 10, 10, 400, 400);
chart.getChartData().getSeries().clear();
chart.getChartData().getCategories().clear();
```

## Passaggio 3: popolare i dati del grafico

Popoleremo il grafico con dati di esempio. In questo esempio creeremo due serie con punti dati e categorie.

```java
IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();

// Serie 1
chart.getChartData().getSeries().add(fact.getCell(0, 0, 1, "Series 1"));
IChartSeries series = chart.getChartData().getSeries().get_Item(0);
chart.getChartData().getCategories().add(fact.getCell(0, 1, 0, "C1"));
series.getDataPoints().addDataPointForLineSeries(fact.getCell(0, 1, 1, 24));
chart.getChartData().getCategories().add(fact.getCell(0, 2, 0, "C2"));
series.getDataPoints().addDataPointForLineSeries(fact.getCell(0, 2, 1, 23));
chart.getChartData().getCategories().add(fact.getCell(0, 3, 0, "C3"));
series.getDataPoints().addDataPointForLineSeries(fact.getCell(0, 3, 1, -10));
chart.getChartData().getCategories().add(fact.getCell(0, 4, 0, "C4"));
series.getDataPoints().addDataPointForLineSeries(fact.getCell(0, 4, 1, null));

// Serie 2
chart.getChartData().getSeries().add(fact.getCell(0, 0, 2, "Series 2"));
IChartSeries series2 = chart.getChartData().getSeries().get_Item(1);

// Popolamento dei dati delle serie
series2.getDataPoints().addDataPointForLineSeries(fact.getCell(0, 1, 2, 30));
series2.getDataPoints().addDataPointForLineSeries(fact.getCell(0, 2, 2, 10));
series2.getDataPoints().addDataPointForLineSeries(fact.getCell(0, 3, 2, 60));
series2.getDataPoints().addDataPointForLineSeries(fact.getCell(0, 4, 2, 40));
```

## Passaggio 4: personalizza il grafico

Puoi personalizzare ulteriormente il grafico, ad esempio aggiungendo una legenda e modificandone l'aspetto.

```java
chart.setLegend(true);
chart.getLegend().setOverlay(false);
```

## Passaggio 5: salva la presentazione

Infine, salva la presentazione con il grafico nella posizione desiderata.

```java
pres.save(dataDir + "DefaultMarkersInChart.pptx", SaveFormat.Pptx);
```

Questo è tutto! Hai creato un grafico a linee con indicatori predefiniti utilizzando Aspose.Slides per Java.

## Codice sorgente completo per i marcatori predefiniti nel grafico nelle diapositive Java

```java
        // Il percorso della directory dei documenti.
        String dataDir = "Your Document Directory";
        Presentation pres = new Presentation();
        try
        {
            ISlide slide = pres.getSlides().get_Item(0);
            IChart chart = slide.getShapes().addChart(ChartType.LineWithMarkers, 10, 10, 400, 400);
            chart.getChartData().getSeries().clear();
            chart.getChartData().getCategories().clear();
            IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
            chart.getChartData().getSeries().add(fact.getCell(0, 0, 1, "Series 1"), chart.getType());
            IChartSeries series = chart.getChartData().getSeries().get_Item(0);
            chart.getChartData().getCategories().add(fact.getCell(0, 1, 0, "C1"));
            series.getDataPoints().addDataPointForLineSeries(fact.getCell(0, 1, 1, 24));
            chart.getChartData().getCategories().add(fact.getCell(0, 2, 0, "C2"));
            series.getDataPoints().addDataPointForLineSeries(fact.getCell(0, 2, 1, 23));
            chart.getChartData().getCategories().add(fact.getCell(0, 3, 0, "C3"));
            series.getDataPoints().addDataPointForLineSeries(fact.getCell(0, 3, 1, -10));
            chart.getChartData().getCategories().add(fact.getCell(0, 4, 0, "C4"));
            series.getDataPoints().addDataPointForLineSeries(fact.getCell(0, 4, 1, null));
            chart.getChartData().getSeries().add(fact.getCell(0, 0, 2, "Series 2"), chart.getType());
            //Prendi la seconda serie di grafici
            IChartSeries series2 = chart.getChartData().getSeries().get_Item(1);
            //Ora popolano i dati delle serie
            series2.getDataPoints().addDataPointForLineSeries(fact.getCell(0, 1, 2, 30));
            series2.getDataPoints().addDataPointForLineSeries(fact.getCell(0, 2, 2, 10));
            series2.getDataPoints().addDataPointForLineSeries(fact.getCell(0, 3, 2, 60));
            series2.getDataPoints().addDataPointForLineSeries(fact.getCell(0, 4, 2, 40));
            chart.setLegend(true);
            chart.getLegend().setOverlay(false);
            pres.save(dataDir + "DefaultMarkersInChart.pptx", SaveFormat.Pptx);
        }
        finally
        {
            if (pres != null) pres.dispose();
        }
```
## Conclusione

In questo tutorial completo, hai imparato come creare diapositive Java con indicatori predefiniti nei grafici utilizzando Aspose.Slides per Java. Abbiamo coperto l'intero processo, dall'impostazione di una presentazione alla personalizzazione dell'aspetto del grafico e al salvataggio del risultato.

## Domande frequenti

### Come posso cambiare i simboli dei marcatori?

È possibile personalizzare i simboli dei marcatori impostando lo stile del marcatore per ciascun punto dati. Utilizzo`IDataPoint.setMarkerStyle()` per modificare il simbolo del marcatore.

### Come posso regolare i colori del grafico?

 Per modificare i colori del grafico, puoi utilizzare il file`IChartSeriesFormat` E`IShapeFillFormat` interfacce per impostare le proprietà di riempimento e linea.

### Posso aggiungere etichette ai punti dati?

 Sì, puoi aggiungere etichette ai punti dati utilizzando il file`IDataPoint.getLabel()` metodo e personalizzarli secondo necessità.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
