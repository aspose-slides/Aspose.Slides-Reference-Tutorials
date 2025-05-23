---
"description": "Lär dig hur du skapar Java-bilder med standardmarkörer i diagram med Aspose.Slides för Java. Steg-för-steg-guide med källkod."
"linktitle": "Standardmarkörer i diagram i Java-bilder"
"second_title": "Aspose.Slides Java PowerPoint-bearbetnings-API"
"title": "Standardmarkörer i diagram i Java-bilder"
"url": "/sv/java/chart-data-manipulation/default-markers-in-chart-java-slides/"
"weight": 16
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Standardmarkörer i diagram i Java-bilder


## Introduktion till standardmarkörer i diagram i Java-presentationer

I den här handledningen ska vi utforska hur man skapar ett diagram med standardmarkörer med hjälp av Aspose.Slides för Java. Standardmarkörer är symboler eller former som läggs till datapunkter i ett diagram för att markera dem. Vi ska skapa ett linjediagram med markörer för att visualisera data.

## Förkunskapskrav

Innan du börjar, se till att du har Aspose.Slides för Java-biblioteket installerat och konfigurerat i ditt Java-projekt.

## Steg 1: Skapa en presentation

Först skapar vi en presentation och lägger till en bild i den. Sedan lägger vi till ett diagram i bilden.

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
ISlide slide = pres.getSlides().get_Item(0);
```

## Steg 2: Lägg till ett linjediagram med markörer

Nu ska vi lägga till ett linjediagram med markörer på bilden. Vi rensar även all standarddata från diagrammet.

```java
IChart chart = slide.getShapes().addChart(ChartType.LineWithMarkers, 10, 10, 400, 400);
chart.getChartData().getSeries().clear();
chart.getChartData().getCategories().clear();
```

## Steg 3: Fyll i diagramdata

Vi fyller diagrammet med exempeldata. I det här exemplet skapar vi två serier med datapunkter och kategorier.

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

// Ifyllning av seriedata
series2.getDataPoints().addDataPointForLineSeries(fact.getCell(0, 1, 2, 30));
series2.getDataPoints().addDataPointForLineSeries(fact.getCell(0, 2, 2, 10));
series2.getDataPoints().addDataPointForLineSeries(fact.getCell(0, 3, 2, 60));
series2.getDataPoints().addDataPointForLineSeries(fact.getCell(0, 4, 2, 40));
```

## Steg 4: Anpassa diagrammet

Du kan anpassa diagrammet ytterligare, till exempel genom att lägga till en förklaring och justera dess utseende.

```java
chart.setLegend(true);
chart.getLegend().setOverlay(false);
```

## Steg 5: Spara presentationen

Spara slutligen presentationen med diagrammet på önskad plats.

```java
pres.save(dataDir + "DefaultMarkersInChart.pptx", SaveFormat.Pptx);
```

Det var allt! Du har skapat ett linjediagram med standardmarkörer med Aspose.Slides för Java.

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
            //Ta den andra diagramserien
            IChartSeries series2 = chart.getChartData().getSeries().get_Item(1);
            //Nu fyller seriedata
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

den här omfattande handledningen har du lärt dig hur du skapar Java-presentationer med standardmarkörer i diagram med hjälp av Aspose.Slides för Java. Vi gick igenom hela processen, från att skapa en presentation till att anpassa diagrammets utseende och spara resultatet.

## Vanliga frågor

### Hur kan jag ändra markörsymbolerna?

Du kan anpassa markörsymbolerna genom att ställa in markörstilen för varje datapunkt. `IDataPoint.setMarkerStyle()` för att ändra markörsymbolen.

### Hur justerar jag diagrammets färger?

För att ändra diagrammets färger kan du använda `IChartSeriesFormat` och `IShapeFillFormat` gränssnitt för att ställa in fyllnings- och linjeegenskaper.

### Kan jag lägga till etiketter till datapunkterna?

Ja, du kan lägga till etiketter till datapunkter med hjälp av `IDataPoint.getLabel()` metod och anpassa dem efter behov.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}