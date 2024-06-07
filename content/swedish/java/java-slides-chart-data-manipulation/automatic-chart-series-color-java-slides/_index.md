---
title: Automatisk diagramseriefärg i Java Slides
linktitle: Automatisk diagramseriefärg i Java Slides
second_title: Aspose.Slides Java PowerPoint Processing API
description: Lär dig hur du skapar dynamiska diagram med automatisk seriefärg i PowerPoint-presentationer med Aspose.Slides för Java. Förbättra dina datavisualiseringar utan ansträngning.
type: docs
weight: 14
url: /sv/java/chart-data-manipulation/automatic-chart-series-color-java-slides/
---

## Introduktion till Automatic Chart Series Color i Aspose.Slides för Java

I den här handledningen kommer vi att utforska hur man skapar en PowerPoint-presentation med ett diagram med Aspose.Slides för Java och ställer in automatiska fyllningsfärger för diagramserier. Automatiska fyllningsfärger kan göra dina diagram mer visuellt tilltalande och spara tid genom att låta biblioteket välja färger åt dig.

## Förutsättningar

 Innan du börjar, se till att du har Aspose.Slides för Java-biblioteket installerat i ditt projekt. Du kan ladda ner den från[här](https://releases.aspose.com/slides/java/).

## Steg 1: Skapa en ny presentation

Först skapar vi en ny PowerPoint-presentation och lägger till en bild till den.

```java
// Sökvägen till dokumentkatalogen.
String dataDir = "Your Document Directory";
// Skapa en instans av presentationsklassen
Presentation presentation = new Presentation();
```

## Steg 2: Lägg till ett diagram till bilden

Därefter lägger vi till ett klustrat kolumndiagram till bilden. Vi kommer också att ställa in den första serien för att visa värden.

```java
// Få tillgång till första bilden
ISlide slide = presentation.getSlides().get_Item(0);
// Lägg till diagram med standarddata
IChart chart = slide.getShapes().addChart(ChartType.ClusteredColumn, 0, 0, 500, 500);
// Ställ in första serien på Visa värden
chart.getChartData().getSeries().get_Item(0).getLabels().getDefaultDataLabelFormat().setShowValue(true);
```

## Steg 3: Fyll i diagramdata

Nu kommer vi att fylla i diagrammet med data. Vi börjar med att ta bort de standardgenererade serierna och kategorierna och lägger sedan till nya serier och kategorier.

```java
// Ställa in index för diagramdatabladet
int defaultWorksheetIndex = 0;
// Hämta arbetsbladet för diagramdata
IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
// Ta bort standardgenererade serier och kategorier
chart.getChartData().getSeries().clear();
chart.getChartData().getCategories().clear();

// Lägger till ny serie
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 1, "Series 1"), chart.getType());
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 2, "Series 2"), chart.getType());

// Lägger till nya kategorier
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 1, 0, "Category 1"));
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 2, 0, "Category 2"));
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 3, 0, "Category 3"));
```

## Steg 4: Fyll i seriedata

Vi kommer att fylla i seriedata för både serie 1 och serie 2.

```java
// Ta första diagramserien
IChartSeries series = chart.getChartData().getSeries().get_Item(0);
//Fyller nu på seriedata
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 1, 20));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 50));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 30));

// Ta den andra diagramserien
series = chart.getChartData().getSeries().get_Item(1);
//Fyller nu på seriedata
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 2, 30));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 2, 10));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 2, 60));
```

## Steg 5: Ställ in automatisk fyllningsfärg för serier

Låt oss nu ställa in automatiska fyllningsfärger för diagramserien. Detta kommer att få biblioteket att välja färger åt oss.

```java
// Ställa in automatisk fyllningsfärg för serier
series.getFormat().getFill().setFillType(FillType.NotDefined);
```

## Steg 6: Spara presentationen

Slutligen sparar vi presentationen med diagrammet till en PowerPoint-fil.

```java
// Spara presentationen med diagram
presentation.save(dataDir + "AutomaticColor_out.pptx", SaveFormat.Pptx);
```

## Komplett källkod för automatisk diagramseriefärg i Java Slides

```java
// Sökvägen till dokumentkatalogen.
String dataDir = "Your Document Directory";
// Skapa en instans av presentationsklassen
Presentation presentation = new Presentation();
try
{
	// Få tillgång till första bilden
	ISlide slide = presentation.getSlides().get_Item(0);
	// Lägg till diagram med standarddata
	IChart chart = slide.getShapes().addChart(ChartType.ClusteredColumn, 0, 0, 500, 500);
	// Ställ in första serien på Visa värden
	chart.getChartData().getSeries().get_Item(0).getLabels().getDefaultDataLabelFormat().setShowValue(true);
	// Ställa in index för diagramdatabladet
	int defaultWorksheetIndex = 0;
	// Hämta arbetsbladet för diagramdata
	IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
	// Ta bort standardgenererade serier och kategorier
	chart.getChartData().getSeries().clear();
	chart.getChartData().getCategories().clear();
	int s = chart.getChartData().getSeries().size();
	s = chart.getChartData().getCategories().size();
	// Lägger till ny serie
	chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 1, "Series 1"), chart.getType());
	chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 2, "Series 2"), chart.getType());
	// Lägger till nya kategorier
	chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 1, 0, "Caetegoty 1"));
	chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 2, 0, "Caetegoty 2"));
	chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 3, 0, "Caetegoty 3"));
	// Ta första diagramserien
	IChartSeries series = chart.getChartData().getSeries().get_Item(0);
	//Fyller nu på seriedata
	series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 1, 20));
	series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 50));
	series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 30));
	// Ställa in automatisk fyllningsfärg för serier
	series.getFormat().getFill().setFillType(FillType.NotDefined);
	// Ta den andra diagramserien
	series = chart.getChartData().getSeries().get_Item(1);
	//Fyller nu på seriedata
	series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 2, 30));
	series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 2, 10));
	series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 2, 60));
	//Ställa in fyllnadsfärg för serier
	series.getFormat().getFill().setFillType(FillType.Solid);
	series.getFormat().getFill().getSolidFillColor().setColor(Color.GRAY);
	// Spara presentationen med diagram
	presentation.save(dataDir + "AutomaticColor_out.pptx", SaveFormat.Pptx);
}
finally
{
	if (presentation != null) presentation.dispose();
}
```

## Slutsats

I den här handledningen har vi lärt oss hur man skapar en PowerPoint-presentation med ett diagram med Aspose.Slides för Java och ställer in automatiska fyllningsfärger för diagramserier. Automatiska färger kan förstärka dina diagrams visuella tilltalande och göra dina presentationer mer engagerande. Du kan ytterligare anpassa diagrammet efter behov för dina specifika krav.

## FAQ's

### Hur ställer jag in automatiska fyllningsfärger för diagramserier i Aspose.Slides för Java?

För att ställa in automatiska fyllningsfärger för diagramserier i Aspose.Slides för Java, använd följande kod:

```java
// Ställa in automatisk fyllningsfärg för serier
series.getFormat().getFill().setFillType(FillType.NotDefined);
```

Denna kod låter biblioteket välja färger automatiskt för diagramserien.

### Kan jag anpassa diagramfärgerna om det behövs?

 Ja, du kan anpassa diagramfärgerna efter behov. I exemplet använde vi automatiska fyllningsfärger, men du kan ställa in specifika färger genom att ändra`FillType` och`SolidFillColor` egenskaperna hos seriens format.

### Hur kan jag lägga till ytterligare serier eller kategorier i diagrammet?

För att lägga till ytterligare serier eller kategorier till diagrammet, använd`getSeries()` och`getCategories()` diagrammets metoder`ChartData` objekt. Du kan lägga till nya serier och kategorier genom att ange deras data och etiketter.

### Är det möjligt att ytterligare formatera diagrammet och etiketterna?

Ja, du kan formatera diagrammet, serierna och etiketterna ytterligare efter behov. Aspose.Slides för Java tillhandahåller omfattande formateringsalternativ för diagram, inklusive teckensnitt, färger, stilar och mer. Du kan utforska dokumentationen för mer information om formateringsalternativ.

### Var kan jag hitta mer information om att arbeta med Aspose.Slides för Java?

 För mer information och detaljerad dokumentation om Aspose.Slides för Java, kan du besöka referensdokumentationen[här](https://reference.aspose.com/slides/java/).