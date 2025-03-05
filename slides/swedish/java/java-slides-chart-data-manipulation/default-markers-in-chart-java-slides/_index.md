---
title: Standardmarkörer i diagram i Java Slides
linktitle: Standardmarkörer i diagram i Java Slides
second_title: Aspose.Slides Java PowerPoint Processing API
description: Lär dig hur du skapar Java Slides med standardmarkörer i diagram med Aspose.Slides för Java. Steg-för-steg guide med källkod.
type: docs
weight: 16
url: /sv/java/chart-data-manipulation/default-markers-in-chart-java-slides/
---

## Introduktion till standardmarkörer i diagram i Java Slides

I den här handledningen kommer vi att utforska hur man skapar ett diagram med standardmarkörer med Aspose.Slides för Java. Standardmarkörer är symboler eller former som läggs till datapunkter i ett diagram för att markera dem. Vi skapar ett linjediagram med markörer för att visualisera data.

## Förutsättningar

Innan du börjar, se till att du har Aspose.Slides för Java-biblioteket installerat och konfigurerat i ditt Java-projekt.

## Steg 1: Skapa en presentation

Låt oss först skapa en presentation och lägga till en bild till den. Vi lägger sedan till ett diagram på bilden.

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
ISlide slide = pres.getSlides().get_Item(0);
```

## Steg 2: Lägg till ett linjediagram med markörer

Låt oss nu lägga till ett linjediagram med markörer på bilden. Vi tar också bort alla standarddata från diagrammet.

```java
IChart chart = slide.getShapes().addChart(ChartType.LineWithMarkers, 10, 10, 400, 400);
chart.getChartData().getSeries().clear();
chart.getChartData().getCategories().clear();
```

## Steg 3: Fyll i diagramdata

Vi fyller i diagrammet med exempeldata. I det här exemplet skapar vi två serier med datapunkter och kategorier.

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

// Fyller på seriedata
series2.getDataPoints().addDataPointForLineSeries(fact.getCell(0, 1, 2, 30));
series2.getDataPoints().addDataPointForLineSeries(fact.getCell(0, 2, 2, 10));
series2.getDataPoints().addDataPointForLineSeries(fact.getCell(0, 3, 2, 60));
series2.getDataPoints().addDataPointForLineSeries(fact.getCell(0, 4, 2, 40));
```

## Steg 4: Anpassa diagrammet

Du kan anpassa diagrammet ytterligare, som att lägga till en förklaring och justera dess utseende.

```java
chart.setLegend(true);
chart.getLegend().setOverlay(false);
```

## Steg 5: Spara presentationen

Slutligen sparar du presentationen med diagrammet på önskad plats.

```java
pres.save(dataDir + "DefaultMarkersInChart.pptx", SaveFormat.Pptx);
```

Det är allt! Du har skapat ett linjediagram med standardmarkörer med Aspose.Slides för Java.

## Komplett källkod för standardmarkörer i diagram i Java Slides

```java
        // Sökvägen till dokumentkatalogen.
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
            //Ta andra diagramserien
            IChartSeries series2 = chart.getChartData().getSeries().get_Item(1);
            //Fyller nu på seriedata
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
## Slutsats

I den här omfattande handledningen har du lärt dig hur du skapar Java Slides med standardmarkörer i diagram med Aspose.Slides för Java. Vi täckte hela processen, från att sätta upp en presentation till att anpassa diagrammets utseende och spara resultatet.

## FAQ's

### Hur kan jag ändra markörsymbolerna?

Du kan anpassa markörsymbolerna genom att ställa in markörstilen för varje datapunkt. Använda sig av`IDataPoint.setMarkerStyle()` för att ändra markörsymbolen.

### Hur justerar jag diagrammets färger?

 För att ändra diagrammets färger kan du använda`IChartSeriesFormat` och`IShapeFillFormat` gränssnitt för att ställa in fyllnings- och linjeegenskaper.

### Kan jag lägga till etiketter till datapunkterna?

 Ja, du kan lägga till etiketter till datapunkter med hjälp av`IDataPoint.getLabel()` metod och anpassa dem efter behov.