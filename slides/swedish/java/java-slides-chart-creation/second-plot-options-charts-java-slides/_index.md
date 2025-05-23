---
"description": "Lär dig hur du anpassar diagram i Java Slides med Aspose.Slides för Java. Utforska alternativ för andra plottar och förbättra dina presentationer."
"linktitle": "Andra plottalternativ för diagram i Java Slides"
"second_title": "Aspose.Slides Java PowerPoint-bearbetnings-API"
"title": "Andra plottalternativ för diagram i Java Slides"
"url": "/sv/java/chart-creation/second-plot-options-charts-java-slides/"
"weight": 12
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Andra plottalternativ för diagram i Java Slides


## Introduktion till andra plottalternativ för diagram i Java Slides

den här handledningen ska vi utforska hur man lägger till andra plottalternativ till diagram med hjälp av Aspose.Slides för Java. Med andra plottalternativ kan du anpassa diagrammens utseende och beteende, särskilt i scenarier som Pie of Pie-diagram. Vi kommer att ge steg-för-steg-instruktioner och källkodsexempel för att uppnå detta. 

## Förkunskapskrav
Innan vi börjar, se till att du har Aspose.Slides för Java installerat och konfigurerat i ditt Java-projekt.

## Steg 1: Skapa en presentation
Låt oss börja med att skapa en ny presentation:

```java
// Sökvägen till dokumentkatalogen.
String dataDir = "Your Document Directory";
// Skapa en instans av Presentation-klassen
Presentation presentation = new Presentation();
```

## Steg 2: Lägg till ett diagram i en bild
Härnäst lägger vi till ett diagram i en bild. I det här exemplet skapar vi ett cirkeldiagram:

```java
// Lägg till diagram på bilden
IChart chart = presentation.getSlides().get_Item(0).getShapes().addChart(ChartType.PieOfPie, 50, 50, 500, 400);
```

## Steg 3: Anpassa diagramegenskaper
Nu ska vi ställa in olika egenskaper för diagrammet, inklusive alternativ för andra plott:

```java
// Visa dataetiketter för den första serien
chart.getChartData().getSeries().get_Item(0).getLabels().getDefaultDataLabelFormat().setShowValue(true);

// Ange storleken på den andra cirkeln (i procent)
chart.getChartData().getSeries().get_Item(0).getParentSeriesGroup().setSecondPieSize(149);

// Dela kakan i procent
chart.getChartData().getSeries().get_Item(0).getParentSeriesGroup().setPieSplitBy(PieSplitType.ByPercentage);

// Ställ in delningens position
chart.getChartData().getSeries().get_Item(0).getParentSeriesGroup().setPieSplitPosition(53);
```

## Steg 4: Spara presentationen
Slutligen, spara presentationen med alternativen för diagram och andra plott:

```java
// Skriv presentation till disk
presentation.save(dataDir + "SecondPlotOptionsforCharts_out.pptx", SaveFormat.Pptx);
```

## Komplett källkod för andra plottalternativ

```java
// Sökvägen till dokumentkatalogen.
String dataDir = "Your Document Directory";
// Skapa en instans av Presentation-klassen
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

I den här handledningen har vi lärt oss hur man lägger till alternativ för andra plottar i diagram i Java Slides med hjälp av Aspose.Slides för Java. Du kan anpassa olika egenskaper för att förbättra utseendet och funktionaliteten hos dina diagram, vilket gör dina presentationer mer informativa och visuellt tilltalande.

## Vanliga frågor

### Hur kan jag ändra storleken på det andra cirkeldiagrammet i ett cirkeldiagram?

För att ändra storleken på det andra cirkeldiagrammet i ett cirkeldiagram, använd `setSecondPieSize` metoden som visas i kodexemplet ovan. Justera värdet för att ange storleken i procent.

### Vad gör `PieSplitBy` kontroll i ett cirkeldiagram?

De `PieSplitBy` egenskapen styr hur cirkeldiagrammet delas. Du kan ställa in det på antingen `PieSplitType.ByPercentage` eller `PieSplitType.ByValue` för att dela diagrammet efter procentandel respektive efter ett specifikt värde.

### Hur ställer jag in positionen för delningen i ett cirkeldiagram?

Du kan ange positionen för delningen i ett cirkeldiagram med hjälp av `setPieSplitPosition` metod. Justera värdet för att ange önskad position.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}