---
title: Andra plotalternativ för diagram i Java Slides
linktitle: Andra plotalternativ för diagram i Java Slides
second_title: Aspose.Slides Java PowerPoint Processing API
description: Lär dig hur du anpassar diagram i Java Slides med Aspose.Slides för Java. Utforska andra plotalternativ och förbättra dina presentationer.
type: docs
weight: 12
url: /sv/java/chart-creation/second-plot-options-charts-java-slides/
---

## Introduktion till andra plotalternativ för diagram i Java Slides

I den här handledningen kommer vi att utforska hur man lägger till andra plotalternativ till diagram med Aspose.Slides för Java. Andra plotalternativ låter dig anpassa utseendet och beteendet hos diagram, särskilt i scenarier som cirkeldiagram. Vi kommer att tillhandahålla steg-för-steg-instruktioner och källkodsexempel för att uppnå detta. 

## Förutsättningar
Innan vi börjar, se till att du har Aspose.Slides för Java installerat och konfigurerat i ditt Java-projekt.

## Steg 1: Skapa en presentation
Låt oss börja med att skapa en ny presentation:

```java
// Sökvägen till dokumentkatalogen.
String dataDir = "Your Document Directory";
// Skapa en instans av presentationsklassen
Presentation presentation = new Presentation();
```

## Steg 2: Lägg till ett diagram till en bild
Därefter lägger vi till ett diagram till en bild. I det här exemplet skapar vi ett cirkeldiagram:

```java
// Lägg till diagram på bilden
IChart chart = presentation.getSlides().get_Item(0).getShapes().addChart(ChartType.PieOfPie, 50, 50, 500, 400);
```

## Steg 3: Anpassa diagramegenskaper
Låt oss nu ställa in olika egenskaper för diagrammet, inklusive andra plotalternativ:

```java
// Visa dataetiketter för den första serien
chart.getChartData().getSeries().get_Item(0).getLabels().getDefaultDataLabelFormat().setShowValue(true);

// Ställ in storleken på den andra pajen (i procent)
chart.getChartData().getSeries().get_Item(0).getParentSeriesGroup().setSecondPieSize(149);

// Dela pajen i procent
chart.getChartData().getSeries().get_Item(0).getParentSeriesGroup().setPieSplitBy(PieSplitType.ByPercentage);

// Ställ in läget för splittringen
chart.getChartData().getSeries().get_Item(0).getParentSeriesGroup().setPieSplitPosition(53);
```

## Steg 4: Spara presentationen
Slutligen, spara presentationen med diagrammet och andra plotalternativ:

```java
// Skriv presentation till disk
presentation.save(dataDir + "SecondPlotOptionsforCharts_out.pptx", SaveFormat.Pptx);
```

## Komplett källkod för andra plotalternativ

```java
// Sökvägen till dokumentkatalogen.
String dataDir = "Your Document Directory";
// Skapa en instans av presentationsklassen
Presentation presentation = new Presentation();
// Lägg till diagram på bilden
IChart chart = presentation.getSlides().get_Item(0).getShapes().addChart(ChartType.PieOfPie, 50, 50, 500, 400);
// Ställ in olika egenskaper
chart.getChartData().getSeries().get_Item(0).getLabels().getDefaultDataLabelFormat().setShowValue(true);
chart.getChartData().getSeries().get_Item(0).getParentSeriesGroup().setSecondPieSize(149);
chart.getChartData().getSeries().get_Item(0).getParentSeriesGroup().setPieSplitBy(PieSplitType.ByPercentage);
chart.getChartData().getSeries().get_Item(0).getParentSeriesGroup().setPieSplitPosition(53);
// Skriv presentation till disk
presentation.save(dataDir + "SecondPlotOptionsforCharts_out.pptx", SaveFormat.Pptx);
```

## Slutsats

I den här handledningen har vi lärt oss hur man lägger till andra plotalternativ till diagram i Java Slides med Aspose.Slides för Java. Du kan anpassa olika egenskaper för att förbättra utseendet och funktionaliteten på dina diagram, vilket gör dina presentationer mer informativa och visuellt tilltalande.

## FAQ's

### Hur kan jag ändra storleken på den andra cirkeln i ett cirkeldiagram?

 För att ändra storleken på den andra cirkeln i ett cirkeldiagram, använd`setSecondPieSize` metod som visas i kodexemplet ovan. Justera värdet för att ange storleken i procent.

###  Vad gör`PieSplitBy` control in a Pie of Pie chart?

 De`PieSplitBy`egenskapen styr hur cirkeldiagrammet delas. Du kan ställa in den på antingen`PieSplitType.ByPercentage` eller`PieSplitType.ByValue` för att dela upp diagrammet efter procent eller efter ett specifikt värde.

### Hur ställer jag in positionen för delingen i ett cirkeldiagram?

 Du kan ställa in positionen för delingen i ett cirkeldiagram med hjälp av`setPieSplitPosition` metod. Justera värdet för att ange önskad position.