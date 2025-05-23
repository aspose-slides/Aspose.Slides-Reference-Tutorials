---
"description": "Skapa flerkategoridiagram i Java Slides med Aspose.Slides för Java. Steg-för-steg-guide med källkod för imponerande datavisualisering i presentationer."
"linktitle": "Flerkategoridiagram i Java Slides"
"second_title": "Aspose.Slides Java PowerPoint-bearbetnings-API"
"title": "Flerkategoridiagram i Java Slides"
"url": "/sv/java/chart-data-manipulation/multi-category-chart-java-slides/"
"weight": 20
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Flerkategoridiagram i Java Slides


## Introduktion till flerkategoridiagram i Java Slides med Aspose.Slides

I den här handledningen lär vi oss hur man skapar ett flerkategorisdiagram i Java-bilder med hjälp av Aspose.Slides för Java API. Den här guiden ger steg-för-steg-instruktioner tillsammans med källkod som hjälper dig att skapa ett klustrat kolumndiagram med flera kategorier och serier.

## Förkunskapskrav
Innan vi börjar, se till att du har Aspose.Slides för Java-biblioteket installerat och konfigurerat i din Java-utvecklingsmiljö.

## Steg 1: Konfigurera miljön
Importera först nödvändiga klasser och skapa ett nytt presentationsobjekt för att arbeta med bilder.

```java
// Sökvägen till dokumentkatalogen.
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
```

## Steg 2: Lägga till en bild och ett diagram
Skapa sedan en bild och lägg till ett klustrat stapeldiagram i den.

```java
ISlide slide = pres.getSlides().get_Item(0);
IChart ch = slide.getShapes().addChart(ChartType.ClusteredColumn, 100, 100, 600, 450);
```

## Steg 3: Rensa befintliga data
Rensa all befintlig data från diagrammet.

```java
ch.getChartData().getSeries().clear();
ch.getChartData().getCategories().clear();
```

## Steg 4: Konfigurera datakategorier
Nu ska vi ställa in datakategorier för diagrammet. Vi ska skapa flera kategorier och gruppera dem.

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
Nu lägger vi till en serie i diagrammet tillsammans med datapunkter.

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

Det var allt! Du har skapat ett flerkategorisdiagram i en Java-bild med hjälp av Aspose.Slides. Du kan anpassa diagrammet ytterligare för att passa dina specifika behov.

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
//            Lägga till serier
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
// Spara presentation med diagram
pres.save(dataDir + "AsposeChart_out.pptx", SaveFormat.Pptx);
```

## Slutsats

den här handledningen har vi lärt oss hur man skapar ett flerkategorisdiagram i Java-slides med hjälp av Aspose.Slides för Java API. Vi gick igenom en steg-för-steg-guide med källkod för att skapa ett klustrat kolumndiagram med flera kategorier och serier.

## Vanliga frågor

### Hur kan jag anpassa diagrammets utseende?

Du kan anpassa diagrammets utseende genom att ändra egenskaper som färger, teckensnitt och stilar. Se dokumentationen för Aspose.Slides för detaljerade anpassningsalternativ.

### Kan jag lägga till fler serier i diagrammet?

Ja, du kan lägga till ytterligare serier i diagrammet genom att följa en liknande process som visas i steg 5.

### Hur ändrar jag diagramtypen?

För att ändra diagramtypen, ersätt `ChartType.ClusteredColumn` med önskad diagramtyp när du lägger till diagrammet i steg 2.

### Hur kan jag lägga till en titel i diagrammet?

Du kan lägga till en titel i diagrammet med hjälp av `ch.getChartTitle().getTextFrame().setText("Chart Title");` metod.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}