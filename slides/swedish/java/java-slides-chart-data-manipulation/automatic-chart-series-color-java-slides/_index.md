---
"description": "Lär dig hur du skapar dynamiska diagram med automatisk seriefärg i PowerPoint-presentationer med Aspose.Slides för Java. Förbättra dina datavisualiseringar utan ansträngning."
"linktitle": "Automatisk färgläggning av diagramserier i Java-presentationer"
"second_title": "Aspose.Slides Java PowerPoint-bearbetnings-API"
"title": "Automatisk färgläggning av diagramserier i Java-presentationer"
"url": "/sv/java/chart-data-manipulation/automatic-chart-series-color-java-slides/"
"weight": 14
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Automatisk färgläggning av diagramserier i Java-presentationer


## Introduktion till automatisk färgläggning av diagramserier i Aspose.Slides för Java

I den här handledningen ska vi utforska hur man skapar en PowerPoint-presentation med ett diagram med hjälp av Aspose.Slides för Java och ställer in automatiska fyllningsfärger för diagramserier. Automatiska fyllningsfärger kan göra dina diagram mer visuellt tilltalande och spara tid genom att låta biblioteket välja färger åt dig.

## Förkunskapskrav

Innan du börjar, se till att du har Aspose.Slides för Java-biblioteket installerat i ditt projekt. Du kan ladda ner det från [här](https://releases.aspose.com/slides/java/).

## Steg 1: Skapa en ny presentation

Först skapar vi en ny PowerPoint-presentation och lägger till en bild i den.

```java
// Sökvägen till dokumentkatalogen.
String dataDir = "Your Document Directory";
// Skapa en instans av Presentation-klassen
Presentation presentation = new Presentation();
```

## Steg 2: Lägg till ett diagram i bilden

Nästa steg är att lägga till ett klustrat stapeldiagram i bilden. Vi ställer också in den första serien så att värden visas.

```java
// Åtkomst till första bilden
ISlide slide = presentation.getSlides().get_Item(0);
// Lägg till diagram med standarddata
IChart chart = slide.getShapes().addChart(ChartType.ClusteredColumn, 0, 0, 500, 500);
// Ställ in första serien på Visa värden
chart.getChartData().getSeries().get_Item(0).getLabels().getDefaultDataLabelFormat().setShowValue(true);
```

## Steg 3: Fyll i diagramdata

Nu fyller vi diagrammet med data. Vi börjar med att ta bort de standardgenererade serierna och kategorierna och lägger sedan till nya serier och kategorier.

```java
// Ställa in index för diagramdatablad
int defaultWorksheetIndex = 0;
// Hämta diagramdataarbetsbladet
IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
// Ta bort standardgenererade serier och kategorier
chart.getChartData().getSeries().clear();
chart.getChartData().getCategories().clear();

// Lägger till nya serier
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
// Nu fyller seriedata
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 1, 20));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 50));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 30));

// Ta den andra diagramserien
series = chart.getChartData().getSeries().get_Item(1);
// Nu fyller seriedata
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 2, 30));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 2, 10));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 2, 60));
```

## Steg 5: Ställ in automatisk fyllningsfärg för serier

Nu ska vi ställa in automatiska fyllningsfärger för diagramserien. Detta gör att biblioteket väljer färger åt oss.

```java
// Ställa in automatisk fyllningsfärg för serier
series.getFormat().getFill().setFillType(FillType.NotDefined);
```

## Steg 6: Spara presentationen

Slutligen sparar vi presentationen med diagrammet till en PowerPoint-fil.

```java
// Spara presentation med diagram
presentation.save(dataDir + "AutomaticColor_out.pptx", SaveFormat.Pptx);
```

## Komplett källkod för automatisk färgning av diagramserier i Java Slides

```java
// Sökvägen till dokumentkatalogen.
String dataDir = "Your Document Directory";
// Skapa en instans av Presentation-klassen
Presentation presentation = new Presentation();
try
{
	// Åtkomst till första bilden
	ISlide slide = presentation.getSlides().get_Item(0);
	// Lägg till diagram med standarddata
	IChart chart = slide.getShapes().addChart(ChartType.ClusteredColumn, 0, 0, 500, 500);
	// Ställ in första serien på Visa värden
	chart.getChartData().getSeries().get_Item(0).getLabels().getDefaultDataLabelFormat().setShowValue(true);
	// Ställa in index för diagramdatablad
	int defaultWorksheetIndex = 0;
	// Hämta diagramdataarbetsbladet
	IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
	// Ta bort standardgenererade serier och kategorier
	chart.getChartData().getSeries().clear();
	chart.getChartData().getCategories().clear();
	int s = chart.getChartData().getSeries().size();
	s = chart.getChartData().getCategories().size();
	// Lägger till nya serier
	chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 1, "Series 1"), chart.getType());
	chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 2, "Series 2"), chart.getType());
	// Lägger till nya kategorier
	chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 1, 0, "Caetegoty 1"));
	chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 2, 0, "Caetegoty 2"));
	chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 3, 0, "Caetegoty 3"));
	// Ta första diagramserien
	IChartSeries series = chart.getChartData().getSeries().get_Item(0);
	// Nu fyller seriedata
	series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 1, 20));
	series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 50));
	series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 30));
	// Ställa in automatisk fyllningsfärg för serier
	series.getFormat().getFill().setFillType(FillType.NotDefined);
	// Ta den andra diagramserien
	series = chart.getChartData().getSeries().get_Item(1);
	// Nu fyller seriedata
	series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 2, 30));
	series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 2, 10));
	series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 2, 60));
	// Ställa in fyllningsfärg för serier
	series.getFormat().getFill().setFillType(FillType.Solid);
	series.getFormat().getFill().getSolidFillColor().setColor(Color.GRAY);
	// Spara presentation med diagram
	presentation.save(dataDir + "AutomaticColor_out.pptx", SaveFormat.Pptx);
}
finally
{
	if (presentation != null) presentation.dispose();
}
```

## Slutsats

den här handledningen har vi lärt oss hur man skapar en PowerPoint-presentation med ett diagram med hjälp av Aspose.Slides för Java och ställer in automatiska fyllningsfärger för diagramserier. Automatiska färger kan förbättra dina diagrams visuella attraktionskraft och göra dina presentationer mer engagerande. Du kan ytterligare anpassa diagrammet efter behov för dina specifika behov.

## Vanliga frågor

### Hur ställer jag in automatiska fyllningsfärger för diagramserier i Aspose.Slides för Java?

För att ställa in automatiska fyllningsfärger för diagramserier i Aspose.Slides för Java, använd följande kod:

```java
// Ställa in automatisk fyllningsfärg för serier
series.getFormat().getFill().setFillType(FillType.NotDefined);
```

Den här koden låter biblioteket välja färger automatiskt för diagramserien.

### Kan jag anpassa diagrammets färger om det behövs?

Ja, du kan anpassa diagrammets färger efter behov. I exemplet som visas använde vi automatiska fyllningsfärger, men du kan ange specifika färger genom att ändra `FillType` och `SolidFillColor` egenskaper hos seriens format.

### Hur kan jag lägga till ytterligare serier eller kategorier i diagrammet?

För att lägga till ytterligare serier eller kategorier i diagrammet, använd `getSeries()` och `getCategories()` metoder för diagrammets `ChartData` objekt. Du kan lägga till nya serier och kategorier genom att ange deras data och etiketter.

### Är det möjligt att formatera diagrammet och etiketterna ytterligare?

Ja, du kan formatera diagrammet, serierna och etiketterna ytterligare efter behov. Aspose.Slides för Java erbjuder omfattande formateringsalternativ för diagram, inklusive teckensnitt, färger, stilar med mera. Du kan utforska dokumentationen för mer information om formateringsalternativ.

### Var kan jag hitta mer information om att arbeta med Aspose.Slides för Java?

För mer information och detaljerad dokumentation om Aspose.Slides för Java kan du besöka referensdokumentationen. [här](https://reference.aspose.com/slides/java/).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}