---
title: Hantera egenskapsdiagram i Java Slides
linktitle: Hantera egenskapsdiagram i Java Slides
second_title: Aspose.Slides Java PowerPoint Processing API
description: Lär dig att skapa fantastiska diagram och hantera egenskaper i Java-bilder med Aspose.Slides. Steg-för-steg-guide med källkod för kraftfulla presentationer.
type: docs
weight: 13
url: /sv/java/data-manipulation/manage-properties-charts-java-slides/
---

## Introduktion till hantering av egenskaper och diagram i Java Slides med Aspose.Slides

I den här handledningen kommer vi att utforska hur man hanterar egenskaper och skapar diagram i Java-bilder med Aspose.Slides. Aspose.Slides är ett kraftfullt Java API för att arbeta med PowerPoint-presentationer. Vi kommer att gå igenom steg-för-steg-processen, inklusive källkodsexempel.

## Förutsättningar

 Innan vi börjar, se till att du har Aspose.Slides-biblioteket för Java installerat och konfigurerat i ditt projekt. Du kan ladda ner den från[här](https://releases.aspose.com/slides/java/).

## Lägga till ett diagram till en bild

För att lägga till ett diagram till en bild, följ dessa steg:

1. Importera de nödvändiga klasserna och skapa en instans av klassen Presentation.

```java
// Skapa en instans av presentationsklassen
Presentation presentation = new Presentation();
```

2. Öppna bilden där du vill lägga till diagrammet. I det här exemplet kommer vi åt den första bilden.

```java
// Få tillgång till första bilden
ISlide slide = presentation.getSlides().get_Item(0);
```

3. Lägg till ett diagram med standarddata. I det här fallet lägger vi till ett StackedColumn3D-diagram.

```java
// Lägg till diagram med standarddata
IChart chart = slide.getShapes().addChart(ChartType.StackedColumn3D, 0, 0, 500, 500);
```

## Ställa in diagramdata

För att ställa in diagramdata måste vi skapa en diagramdataarbetsbok och lägga till serier och kategorier. Följ dessa steg:

4. Ställ in index för diagramdatabladet.

```java
// Ställa in index för diagramdatabladet
int defaultWorksheetIndex = 0;
```

5. Skaffa arbetsboken för diagramdata.

```java
//Hämta arbetsbladet för diagramdata
IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
```

6. Lägg till serier i diagrammet. I det här exemplet lägger vi till två serier som heter "Serie 1" och "Serie 2".

```java
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 1, "Series 1"), chart.getType());
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 2, "Series 2"), chart.getType());
```

7. Lägg till kategorier i diagrammet. Här lägger vi till tre kategorier.

```java
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 1, 0, "Category 1"));
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 2, 0, "Category 2"));
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 3, 0, "Category 3"));
```

## Ställa in 3D-rotationsegenskaper

Låt oss nu ställa in 3D-rotationsegenskaper för diagrammet:

8. Ställ in de räta vinkelaxlarna.

```java
chart.getRotation3D().setRightAngleAxes(true);
```

9. Ställ in rotationsvinklarna för X- och Y-axlarna. I det här exemplet roterar vi X med 40 grader och Y med 270 grader.

```java
chart.getRotation3D().setRotationX((byte) 40);
chart.getRotation3D().setRotationY(270);
```

10. Ställ in djupprocenten till 150.

```java
chart.getRotation3D().setDepthPercents(150);
```

## Fylla på seriedata

11. Ta den andra diagramserien och fyll den med datapunkter.

```java
IChartSeries series = chart.getChartData().getSeries().get_Item(1);

// Fyll i seriedata
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 1, 20));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 50));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 30));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 2, 30));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 2, 10));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 2, 60));
```

## Justera överlappning

12. Ställ in överlappningsvärdet för serier. Du kan till exempel ställa in den till 100 för ingen överlappning.

```java
series.getParentSeriesGroup().setOverlap((byte) 100);
```

## Sparar presentationen

Slutligen, spara presentationen på disk.

```java
presentation.save(dataDir + "Rotation3D_out.pptx", SaveFormat.Pptx);
```

Det är allt! Du har framgångsrikt skapat ett 3D-staplat kolumndiagram med anpassade egenskaper med Aspose.Slides i Java.

## Komplett källkod för hantering av egenskapsdiagram i Java Slides

```java
// Sökvägen till dokumentkatalogen.
String dataDir = "Your Document Directory";
// Skapa en instans av presentationsklassen
Presentation presentation = new Presentation();
// Få tillgång till första bilden
ISlide slide = presentation.getSlides().get_Item(0);
// Lägg till diagram med standarddata
IChart chart = slide.getShapes().addChart(ChartType.StackedColumn3D, 0, 0, 500, 500);
// Ställa in index för diagramdatabladet
int defaultWorksheetIndex = 0;
//Hämta arbetsbladet för diagramdata
IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
// Lägg till serier
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 1, "Series 1"), chart.getType());
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 2, "Series 2"), chart.getType());
// Lägg till Catrgories
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 1, 0, "Caetegoty 1"));
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 2, 0, "Caetegoty 2"));
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 3, 0, "Caetegoty 3"));
// Ställ in egenskaper för Rotation3D
chart.getRotation3D().setRightAngleAxes(true);
chart.getRotation3D().setRotationX((byte) 40);
chart.getRotation3D().setRotationY(270);
chart.getRotation3D().setDepthPercents(150);
// Ta andra diagramserien
IChartSeries series = chart.getChartData().getSeries().get_Item(1);
// Fyller nu på seriedata
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 1, 20));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 50));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 30));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 2, 30));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 2, 10));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 2, 60));
// Ställ in överlappningsvärde
series.getParentSeriesGroup().setOverlap((byte) 100);
// Skriv presentation till disk
presentation.save(dataDir + "Rotation3D_out.pptx", SaveFormat.Pptx);
```

## Slutsats

I den här handledningen grävde vi in i världen av att hantera egenskaper och skapa diagram i Java-bilder med Aspose.Slides. Aspose.Slides är ett robust Java API som gör det möjligt för utvecklare att arbeta med PowerPoint-presentationer effektivt. Vi täckte de väsentliga stegen och gav källkodsexempel för att guida dig genom processen.

## FAQ's

### Hur kan jag ändra diagramtypen?

 Du kan ändra diagramtypen genom att ändra`ChartType`parameter när du lägger till diagrammet. Se Aspose.Slides-dokumentationen för tillgängliga diagramtyper.

### Kan jag anpassa diagramfärgerna?

Ja, du kan anpassa diagramfärgerna genom att ställa in fyllningsegenskaperna för seriedatapunkter eller kategorier.

### Hur lägger jag till fler datapunkter i en serie?

 Du kan lägga till fler datapunkter till en serie genom att använda`series.getDataPoints().addDataPointForBarSeries()` metod och ange cellen som innehåller datavärdet.

### Hur kan jag ställa in en annan rotationsvinkel?

 För att ställa in en annan rotationsvinkel för X- och Y-axlarna, använd`chart.getRotation3D().setRotationX()` och`chart.getRotation3D().setRotationY()` med önskade vinkelvärden.

### Vilka andra 3D-egenskaper kan jag anpassa?

Du kan utforska andra 3D-egenskaper i diagrammet, såsom djup, perspektiv och belysning, genom att hänvisa till Aspose.Slides-dokumentationen.