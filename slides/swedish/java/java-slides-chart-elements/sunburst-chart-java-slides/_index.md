---
title: Sunburst-diagram i Java Slides
linktitle: Sunburst-diagram i Java Slides
second_title: Aspose.Slides Java PowerPoint Processing API
description: Skapa fantastiska Sunburst-diagram i Java Slides med Aspose.Slides. Lär dig steg-för-steg-diagramskapande och datamanipulation.
weight: 16
url: /sv/java/chart-elements/sunburst-chart-java-slides/
---

{< blocks/products/pf/main-wrap-class >}
{< blocks/products/pf/main-container >}
{< blocks/products/pf/tutorial-page-section >}


## Introduktion till Sunburst Chart i Java Slides med Aspose.Slides

I den här handledningen kommer du att lära dig hur du skapar ett Sunburst-diagram i en PowerPoint-presentation med Aspose.Slides för Java API. Ett Sunburst-diagram är ett radiellt diagram som används för att representera hierarkiska data. Vi kommer att tillhandahålla steg-för-steg-instruktioner tillsammans med källkoden.

## Förutsättningar

 Innan du börjar, se till att du har Aspose.Slides for Java-biblioteket installerat och konfigurerat i ditt Java-projekt. Du kan ladda ner biblioteket från[här](https://releases.aspose.com/slides/java/).

## Steg 1: Importera nödvändiga bibliotek

Importera först de nödvändiga biblioteken för att arbeta med Aspose.Slides och skapa ett Sunburst-diagram i din Java-applikation.

```java
import com.aspose.slides.*;
```

## Steg 2: Initiera presentationen

Initiera en PowerPoint-presentation och ange katalogen där din presentationsfil ska sparas.

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "test.pptx");
```

## Steg 3: Skapa Sunburst-diagrammet

Skapa ett Sunburst-diagram på en bild. Vi anger position (X, Y) och dimensioner (bredd, höjd) för diagrammet.

```java
IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.Sunburst, 50, 50, 500, 400);
```

## Steg 4: Förbered diagramdata

Rensa alla befintliga kategorier och seriedata från diagrammet och skapa en dataarbetsbok för diagrammet.

```java
chart.getChartData().getCategories().clear();
chart.getChartData().getSeries().clear();
IChartDataWorkbook wb = chart.getChartData().getChartDataWorkbook();
wb.clear(0);
```

## Steg 5: Definiera diagramhierarki

Definiera den hierarkiska strukturen för Sunburst-diagrammet. Du kan lägga till grenar, stjälkar och löv som kategorier.

```java
// Gren 1
IChartCategory leaf = chart.getChartData().getCategories().add(wb.getCell(0, "C1", "Leaf1"));
leaf.getGroupingLevels().setGroupingItem(1, "Stem1");
leaf.getGroupingLevels().setGroupingItem(2, "Branch1");
chart.getChartData().getCategories().add(wb.getCell(0, "C2", "Leaf2"));
leaf = chart.getChartData().getCategories().add(wb.getCell(0, "C3", "Leaf3"));
leaf.getGroupingLevels().setGroupingItem(1, "Stem2");
chart.getChartData().getCategories().add(wb.getCell(0, "C4", "Leaf4"));

// Gren 2
leaf = chart.getChartData().getCategories().add(wb.getCell(0, "C5", "Leaf5"));
leaf.getGroupingLevels().setGroupingItem(1, "Stem3");
leaf.getGroupingLevels().setGroupingItem(2, "Branch2");
chart.getChartData().getCategories().add(wb.getCell(0, "C6", "Leaf6"));
leaf = chart.getChartData().getCategories().add(wb.getCell(0, "C7", "Leaf7"));
leaf.getGroupingLevels().setGroupingItem(1, "Stem4");
chart.getChartData().getCategories().add(wb.getCell(0, "C8", "Leaf8"));
```

## Steg 6: Lägg till data i diagrammet

Lägg till datapunkter i Sunburst-diagramserien.

```java
IChartSeries series = chart.getChartData().getSeries().add(ChartType.Sunburst);
series.getLabels().getDefaultDataLabelFormat().setShowCategoryName(true);
series.getDataPoints().addDataPointForSunburstSeries(wb.getCell(0, "D1", 4));
series.getDataPoints().addDataPointForSunburstSeries(wb.getCell(0, "D2", 5));
series.getDataPoints().addDataPointForSunburstSeries(wb.getCell(0, "D3", 3));
series.getDataPoints().addDataPointForSunburstSeries(wb.getCell(0, "D4", 6));
series.getDataPoints().addDataPointForSunburstSeries(wb.getCell(0, "D5", 9));
series.getDataPoints().addDataPointForSunburstSeries(wb.getCell(0, "D6", 9));
series.getDataPoints().addDataPointForSunburstSeries(wb.getCell(0, "D7", 4));
series.getDataPoints().addDataPointForSunburstSeries(wb.getCell(0, "D8", 3));
```

## Steg 7: Spara presentationen

Spara slutligen presentationen med Sunburst-diagrammet.

```java
pres.save("Sunburst.pptx", SaveFormat.Pptx);
```

## Komplett källkod för Sunburst-diagram i Java Slides

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "test.pptx");
try
{
	IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.Sunburst, 50, 50, 500, 400);
	chart.getChartData().getCategories().clear();
	chart.getChartData().getSeries().clear();
	IChartDataWorkbook wb = chart.getChartData().getChartDataWorkbook();
	wb.clear(0);
	//gren 1
	IChartCategory leaf = chart.getChartData().getCategories().add(wb.getCell(0, "C1", "Leaf1"));
	leaf.getGroupingLevels().setGroupingItem(1, "Stem1");
	leaf.getGroupingLevels().setGroupingItem(2, "Branch1");
	chart.getChartData().getCategories().add(wb.getCell(0, "C2", "Leaf2"));
	leaf = chart.getChartData().getCategories().add(wb.getCell(0, "C3", "Leaf3"));
	leaf.getGroupingLevels().setGroupingItem(1, "Stem2");
	chart.getChartData().getCategories().add(wb.getCell(0, "C4", "Leaf4"));
	//gren 2
	leaf = chart.getChartData().getCategories().add(wb.getCell(0, "C5", "Leaf5"));
	leaf.getGroupingLevels().setGroupingItem(1, "Stem3");
	leaf.getGroupingLevels().setGroupingItem(2, "Branch2");
	chart.getChartData().getCategories().add(wb.getCell(0, "C6", "Leaf6"));
	leaf = chart.getChartData().getCategories().add(wb.getCell(0, "C7", "Leaf7"));
	leaf.getGroupingLevels().setGroupingItem(1, "Stem4");
	chart.getChartData().getCategories().add(wb.getCell(0, "C8", "Leaf8"));
	IChartSeries series = chart.getChartData().getSeries().add(ChartType.Sunburst);
	series.getLabels().getDefaultDataLabelFormat().setShowCategoryName(true);
	series.getDataPoints().addDataPointForSunburstSeries(wb.getCell(0, "D1", 4));
	series.getDataPoints().addDataPointForSunburstSeries(wb.getCell(0, "D2", 5));
	series.getDataPoints().addDataPointForSunburstSeries(wb.getCell(0, "D3", 3));
	series.getDataPoints().addDataPointForSunburstSeries(wb.getCell(0, "D4", 6));
	series.getDataPoints().addDataPointForSunburstSeries(wb.getCell(0, "D5", 9));
	series.getDataPoints().addDataPointForSunburstSeries(wb.getCell(0, "D6", 9));
	series.getDataPoints().addDataPointForSunburstSeries(wb.getCell(0, "D7", 4));
	series.getDataPoints().addDataPointForSunburstSeries(wb.getCell(0, "D8", 3));
	pres.save("Sunburst.pptx", SaveFormat.Pptx);
}
finally
{
	if (pres != null) pres.dispose();
}
```

## Slutsats

den här handledningen har du lärt dig hur du skapar ett Sunburst-diagram i en PowerPoint-presentation med Aspose.Slides för Java API. Du har sett hur du initierar presentationen, skapar diagrammet, definierar diagramhierarki, lägger till datapunkter och sparar presentationen. Du kan nu använda denna kunskap för att skapa interaktiva och informativa Sunburst-diagram i dina Java-applikationer.

## FAQ's

### Hur anpassar jag utseendet på Sunburst-diagrammet?

Du kan anpassa utseendet på Sunburst-diagrammet genom att ändra egenskaper som färger, etiketter och stilar. Se Aspose.Slides-dokumentationen för detaljerade anpassningsalternativ.

### Kan jag lägga till fler datapunkter i diagrammet?

 Ja, du kan lägga till fler datapunkter i diagrammet genom att använda`series.getDataPoints().addDataPointForSunburstSeries()` metod för varje datapunkt du vill inkludera.

### Hur kan jag lägga till verktygstips till Sunburst-diagrammet?

För att lägga till verktygstips till Sunburst-diagrammet kan du ställa in dataetikettformatet för att visa ytterligare information, såsom värden eller beskrivningar, när du håller muspekaren över diagramsegment.

### Är det möjligt att skapa interaktiva Sunburst-diagram med hyperlänkar?

Ja, du kan skapa interaktiva Sunburst-diagram med hyperlänkar genom att lägga till hyperlänkar till specifika diagramelement eller segment. Se Aspose.Slides-dokumentationen för detaljer om hur du lägger till hyperlänkar.
{< /blocks/products/pf/tutorial-page-section >}

{< /blocks/products/pf/main-container >}
{< /blocks/products/pf/main-wrap-class >}

{< blocks/products/products-backtop-button >}
