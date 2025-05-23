---
"description": "Leer hoe je Java-dia's maakt met standaardmarkeringen in diagrammen met Aspose.Slides voor Java. Stapsgewijze handleiding met broncode."
"linktitle": "Standaardmarkeringen in diagrammen in Java-dia's"
"second_title": "Aspose.Slides Java PowerPoint-verwerkings-API"
"title": "Standaardmarkeringen in diagrammen in Java-dia's"
"url": "/nl/java/chart-data-manipulation/default-markers-in-chart-java-slides/"
"weight": 16
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Standaardmarkeringen in diagrammen in Java-dia's


## Inleiding tot standaardmarkeringen in grafieken in Java-dia's

In deze tutorial laten we zien hoe je een grafiek met standaardmarkeringen maakt met Aspose.Slides voor Java. Standaardmarkeringen zijn symbolen of vormen die aan datapunten in een grafiek worden toegevoegd om ze te markeren. We maken een lijndiagram met markeringen om gegevens te visualiseren.

## Vereisten

Voordat u begint, moet u ervoor zorgen dat u de Aspose.Slides voor Java-bibliotheek hebt geïnstalleerd en ingesteld in uw Java-project.

## Stap 1: Een presentatie maken

Laten we eerst een presentatie maken en er een dia aan toevoegen. Vervolgens voegen we een grafiek toe aan de dia.

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
ISlide slide = pres.getSlides().get_Item(0);
```

## Stap 2: Voeg een lijndiagram met markeringen toe

Laten we nu een lijndiagram met markeringen aan de dia toevoegen. We wissen ook alle standaardgegevens uit het diagram.

```java
IChart chart = slide.getShapes().addChart(ChartType.LineWithMarkers, 10, 10, 400, 400);
chart.getChartData().getSeries().clear();
chart.getChartData().getCategories().clear();
```

## Stap 3: Grafiekgegevens invullen

We vullen de grafiek met voorbeeldgegevens. In dit voorbeeld maken we twee reeksen met datapunten en categorieën.

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

// Het vullen van reeksgegevens
series2.getDataPoints().addDataPointForLineSeries(fact.getCell(0, 1, 2, 30));
series2.getDataPoints().addDataPointForLineSeries(fact.getCell(0, 2, 2, 10));
series2.getDataPoints().addDataPointForLineSeries(fact.getCell(0, 3, 2, 60));
series2.getDataPoints().addDataPointForLineSeries(fact.getCell(0, 4, 2, 40));
```

## Stap 4: Pas de grafiek aan

U kunt de grafiek verder aanpassen, bijvoorbeeld door een legenda toe te voegen en het uiterlijk aan te passen.

```java
chart.setLegend(true);
chart.getLegend().setOverlay(false);
```

## Stap 5: Sla de presentatie op

Sla ten slotte de presentatie met de grafiek op de gewenste locatie op.

```java
pres.save(dataDir + "DefaultMarkersInChart.pptx", SaveFormat.Pptx);
```

Dat is alles! Je hebt een lijndiagram met standaardmarkeringen gemaakt met Aspose.Slides voor Java.

## Volledige broncode voor standaardmarkeringen in grafieken in Java-dia's

```java
        // Het pad naar de documentenmap.
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
            //Neem de tweede grafiekserie
            IChartSeries series2 = chart.getChartData().getSeries().get_Item(1);
            //Nu worden reeksgegevens ingevuld
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
## Conclusie

In deze uitgebreide tutorial heb je geleerd hoe je Java Slides met standaardmarkeringen in grafieken maakt met Aspose.Slides voor Java. We hebben het hele proces behandeld, van het opzetten van een presentatie tot het aanpassen van de weergave van de grafiek en het opslaan van het resultaat.

## Veelgestelde vragen

### Hoe kan ik de markeringssymbolen wijzigen?

U kunt de markeringssymbolen aanpassen door de markeringsstijl voor elk gegevenspunt in te stellen. Gebruik `IDataPoint.setMarkerStyle()` om het markeringssymbool te wijzigen.

### Hoe pas ik de kleuren van het diagram aan?

Om de kleuren van het diagram te wijzigen, kunt u de `IChartSeriesFormat` En `IShapeFillFormat` interfaces om vulling- en lijneigenschappen in te stellen.

### Kan ik labels aan de datapunten toevoegen?

Ja, u kunt labels toevoegen aan datapunten met behulp van de `IDataPoint.getLabel()` en pas ze indien nodig aan.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}