---
title: Flerkategoridiagram i Java Slides
linktitle: Flerkategoridiagram i Java Slides
second_title: Aspose.Slides Java PowerPoint Processing API
description: Skapa flerkategoridiagram i Java Slides med Aspose.Slides för Java. Steg-för-steg-guide med källkod för imponerande datavisualisering i presentationer.
type: docs
weight: 20
url: /sv/java/chart-data-manipulation/multi-category-chart-java-slides/
---

## Introduktion till flerkategoridiagram i Java Slides med Aspose.Slides

I den här handledningen kommer vi att lära oss hur man skapar ett flerkategoridiagram i Java-bilder med Aspose.Slides for Java API. Den här guiden kommer att ge steg-för-steg-instruktioner tillsammans med källkod för att hjälpa dig att skapa ett klustrat kolumndiagram med flera kategorier och serier.

## Förutsättningar
Innan vi börjar, se till att du har Aspose.Slides för Java-biblioteket installerat och konfigurerat i din Java-utvecklingsmiljö.

## Steg 1: Konfigurera miljön
Importera först de nödvändiga klasserna och skapa ett nytt presentationsobjekt för att arbeta med bilder.

```java
// Sökvägen till dokumentkatalogen.
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
```

## Steg 2: Lägga till en bild och ett diagram
Skapa sedan en bild och lägg till ett klustrat kolumndiagram till den.

```java
ISlide slide = pres.getSlides().get_Item(0);
IChart ch = slide.getShapes().addChart(ChartType.ClusteredColumn, 100, 100, 600, 450);
```

## Steg 3: Rensa befintliga data
Rensa alla befintliga data från diagrammet.

```java
ch.getChartData().getSeries().clear();
ch.getChartData().getCategories().clear();
```

## Steg 4: Ställa in datakategorier
Låt oss nu ställa in datakategorier för diagrammet. Vi kommer att skapa flera kategorier och gruppera dem.

```java
IChartDataWorkbook fact = ch.getChartData().getChartDataWorkbook();
fact.clear(0);

int defaultWorksheetIndex = 0;

// Lägg till kategorier och gruppera dem
IChartCategory category = ch.getChartData().getCategories().add(fact.getCell(0, "c2", "A"));
category.getGroupingLevels().setGroupingItem(1, "Group1");

category = ch.getChartData().getCategories().add(fact.getCell(0, "c3", "B"));

category = ch.getChartData().getCategories().add(fact.getCell(0, "c4", "C"));
category.getGroupingLevels().setGroupingItem(1, "Group2");

category = ch.getChartData().getCategories().add(fact.getCell(0, "c5", "D"));

category = ch.getChartData().getCategories().add(fact.getCell(0, "c6", "E"));
category.getGroupingLevels().setGroupingItem(1, "Group3");

category = ch.getChartData().getCategories().add(fact.getCell(0, "c7", "F"));

category = ch.getChartData().getCategories().add(fact.getCell(0, "c8", "G"));
category.getGroupingLevels().setGroupingItem(1, "Group4");

category = ch.getChartData().getCategories().add(fact.getCell(0, "c9", "H"));
```

## Steg 5: Lägga till serier
Låt oss nu lägga till en serie till diagrammet tillsammans med datapunkter.

```java
IChartSeries series = ch.getChartData().getSeries().add(fact.getCell(0, "D1", "Series 1"), ChartType.ClusteredColumn);

series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, "D2", 10));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, "D3", 20));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, "D4", 30));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, "D5", 40));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, "D6", 50));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, "D7", 60));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, "D8", 70));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, "D9", 80));
```

## Steg 6: Spara presentationen
Spara slutligen presentationen med diagrammet.

```java
pres.save(dataDir + "AsposeChart_out.pptx", SaveFormat.Pptx);
```

Det är allt! Du har framgångsrikt skapat ett flerkategoridiagram i en Java-bild med Aspose.Slides. Du kan anpassa detta diagram ytterligare för att passa dina specifika krav.

## Komplett källkod för flerkategoridiagram i Java Slides

```java
// Sökvägen till dokumentkatalogen.
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
ISlide slide = pres.getSlides().get_Item(0);
IChart ch = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 100, 100, 600, 450);
ch.getChartData().getSeries().clear();
ch.getChartData().getCategories().clear();
IChartDataWorkbook fact = ch.getChartData().getChartDataWorkbook();
fact.clear(0);
int defaultWorksheetIndex = 0;
IChartCategory category = ch.getChartData().getCategories().add(fact.getCell(0, "c2", "A"));
category.getGroupingLevels().setGroupingItem(1, "Group1");
category = ch.getChartData().getCategories().add(fact.getCell(0, "c3", "B"));
category = ch.getChartData().getCategories().add(fact.getCell(0, "c4", "C"));
category.getGroupingLevels().setGroupingItem(1, "Group2");
category = ch.getChartData().getCategories().add(fact.getCell(0, "c5", "D"));
category = ch.getChartData().getCategories().add(fact.getCell(0, "c6", "E"));
category.getGroupingLevels().setGroupingItem(1, "Group3");
category = ch.getChartData().getCategories().add(fact.getCell(0, "c7", "F"));
category = ch.getChartData().getCategories().add(fact.getCell(0, "c8", "G"));
category.getGroupingLevels().setGroupingItem(1, "Group4");
category = ch.getChartData().getCategories().add(fact.getCell(0, "c9", "H"));
// Lägger till serie
IChartSeries series = ch.getChartData().getSeries().add(fact.getCell(0, "D1", "Series 1"),
		ChartType.ClusteredColumn);
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, "D2", 10));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, "D3", 20));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, "D4", 30));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, "D5", 40));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, "D6", 50));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, "D7", 60));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, "D8", 70));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, "D9", 80));
// Spara presentationen med diagram
pres.save(dataDir + "AsposeChart_out.pptx", SaveFormat.Pptx);
```

## Slutsats

den här handledningen har vi lärt oss hur man skapar ett flerkategoridiagram i Java-bilder med Aspose.Slides för Java API. Vi gick igenom en steg-för-steg-guide med källkod för att skapa ett klustrat kolumndiagram med flera kategorier och serier.

## FAQ's

### Hur kan jag anpassa diagrammets utseende?

Du kan anpassa diagrammets utseende genom att ändra egenskaper som färger, teckensnitt och stilar. Se Aspose.Slides-dokumentationen för detaljerade anpassningsalternativ.

### Kan jag lägga till fler serier i diagrammet?

Ja, du kan lägga till ytterligare serier i diagrammet genom att följa en liknande process som visas i steg 5.

### Hur ändrar jag diagramtypen?

 För att ändra diagramtypen, byt ut`ChartType.ClusteredColumn` med önskad diagramtyp när du lägger till diagrammet i steg 2.

### Hur kan jag lägga till en titel i diagrammet?

 Du kan lägga till en titel till diagrammet genom att använda`ch.getChartTitle().getTextFrame().setText("Chart Title");` metod.