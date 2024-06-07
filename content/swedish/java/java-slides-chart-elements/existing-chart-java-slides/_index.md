---
title: Befintligt diagram i Java Slides
linktitle: Befintligt diagram i Java Slides
second_title: Aspose.Slides Java PowerPoint Processing API
description: Förbättra dina PowerPoint-presentationer med Aspose.Slides för Java. Lär dig att ändra befintliga diagram programmatiskt. Steg-för-steg guide med källkod för diagramanpassning.
type: docs
weight: 12
url: /sv/java/chart-elements/existing-chart-java-slides/
---

## Introduktion till befintliga diagram i Java Slides med Aspose.Slides för Java

I den här handledningen kommer vi att visa hur man ändrar ett befintligt diagram i en PowerPoint-presentation med Aspose.Slides för Java. Vi går igenom stegen för att ändra diagramdata, kategorinamn, serienamn och lägga till en ny serie i diagrammet. Se till att du har konfigurerat Aspose.Slides för Java i ditt projekt.

## Förutsättningar

Innan vi börjar, se till att du har följande förutsättningar på plats:

1. Aspose.Slides för Java-bibliotek som ingår i ditt projekt.
2. En befintlig PowerPoint-presentation med ett diagram som du vill ändra.
3. Java utvecklingsmiljö inrättad.

## Steg 1: Ladda presentationen

```java
// Sökvägen till dokumentkatalogen.
String dataDir = "Your Document Directory";

// Instantiate Presentation-klass som representerar PPTX-fil
Presentation pres = new Presentation(dataDir + "ExistingChart.pptx");
```

## Steg 2: Gå till bild och diagram

```java
// Gå till den första bilden
ISlide sld = pres.getSlides().get_Item(0);

// Gå till diagrammet på bilden
IChart chart = (IChart) sld.getShapes().get_Item(0);
```

## Steg 3: Ändra diagramdata och kategorinamn

```java
// Ställa in index för diagramdatabladet
int defaultWorksheetIndex = 0;

// Hämta arbetsbladet för diagramdata
IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();

// Ändra namn på diagramkategorier
fact.getCell(defaultWorksheetIndex, 1, 0, "Modified Category 1");
fact.getCell(defaultWorksheetIndex, 2, 0, "Modified Category 2");
```

## Steg 4: Uppdatera First Chart Series

```java
// Ta den första diagramserien
IChartSeries series = chart.getChartData().getSeries().get_Item(0);

// Uppdatera serienamn
fact.getCell(defaultWorksheetIndex, 0, 1, "New_Series1");

// Uppdatera seriedata
series.getDataPoints().get_Item(0).getValue().setData(90);
series.getDataPoints().get_Item(1).getValue().setData(123);
series.getDataPoints().get_Item(2).getValue().setData(44);
```

## Steg 5: Uppdatera Second Chart Series

```java
// Ta den andra diagramserien
series = chart.getChartData().getSeries().get_Item(1);

// Uppdatera serienamn
fact.getCell(defaultWorksheetIndex, 0, 2, "New_Series2");

// Uppdatera seriedata
series.getDataPoints().get_Item(0).getValue().setData(23);
series.getDataPoints().get_Item(1).getValue().setData(67);
series.getDataPoints().get_Item(2).getValue().setData(99);
```

## Steg 6: Lägg till en ny serie i diagrammet

```java
// Lägger till en ny serie
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 3, "Series 3"), chart.getType());

// Ta den tredje diagramserien
series = chart.getChartData().getSeries().get_Item(2);

// Fyll i seriedata
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 3, 20));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 3, 50));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 3, 30));
```

## Steg 7: Ändra diagramtyp

```java
//Ändra diagramtypen till Clustered Cylinder
chart.setType(ChartType.ClusteredCylinder);
```

## Steg 8: Spara den ändrade presentationen

```java
// Spara presentationen med det modifierade diagrammet
pres.save(dataDir + "AsposeChartModified_out.pptx", SaveFormat.Pptx);
```

Grattis! Du har framgångsrikt modifierat ett befintligt diagram i en PowerPoint-presentation med Aspose.Slides för Java. Du kan nu använda den här koden för att anpassa diagram i dina PowerPoint-presentationer programmatiskt.

## Komplett källkod för befintligt diagram i Java Slides

```java
// Sökvägen till dokumentkatalogen.
String dataDir = "Your Document Directory";
// Instantiate Presentation class that represents PPTX file// Instantiate Presentation class that represents PPTX file
Presentation pres = new Presentation(dataDir + "ExistingChart.pptx");
// Öppna första slideMarker
ISlide sld = pres.getSlides().get_Item(0);
// Lägg till diagram med standarddata
IChart chart = (IChart) sld.getShapes().get_Item(0);
// Ställa in index för diagramdatabladet
int defaultWorksheetIndex = 0;
// Hämta arbetsbladet för diagramdata
IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
// Ändra diagramkategorinamn
fact.getCell(defaultWorksheetIndex, 1, 0, "Modified Category 1");
fact.getCell(defaultWorksheetIndex, 2, 0, "Modified Category 2");
// Ta första diagramserien
IChartSeries series = chart.getChartData().getSeries().get_Item(0);
// Uppdaterar nu seriedata
fact.getCell(defaultWorksheetIndex, 0, 1, "New_Series1");// Ändra serienamn
series.getDataPoints().get_Item(0).getValue().setData(90);
series.getDataPoints().get_Item(1).getValue().setData(123);
series.getDataPoints().get_Item(2).getValue().setData(44);
// Ta andra diagramserien
series = chart.getChartData().getSeries().get_Item(1);
// Uppdaterar nu seriedata
fact.getCell(defaultWorksheetIndex, 0, 2, "New_Series2");// Ändra serienamn
series.getDataPoints().get_Item(0).getValue().setData(23);
series.getDataPoints().get_Item(1).getValue().setData(67);
series.getDataPoints().get_Item(2).getValue().setData(99);
// Nu lägger vi till en ny serie
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 3, "Series 3"), chart.getType());
// Ta 3:e diagramserien
series = chart.getChartData().getSeries().get_Item(2);
//Fyller nu på seriedata
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 3, 20));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 3, 50));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 3, 30));
chart.setType(ChartType.ClusteredCylinder);
// Spara presentationen med diagram
pres.save(dataDir + "AsposeChartModified_out.pptx", SaveFormat.Pptx);
```
## Slutsats

den här omfattande självstudien har vi lärt oss hur man ändrar ett befintligt diagram i en PowerPoint-presentation med Aspose.Slides för Java. Genom att följa den steg-för-steg-guiden och använda källkodsexempel kan du enkelt anpassa och uppdatera diagram för att möta dina specifika krav. Här är en sammanfattning av vad vi tog upp:

## FAQ's

### Hur kan jag ändra diagramtypen?

 Du kan ändra diagramtypen genom att använda`chart.setType(ChartType.ChartTypeHere)` metod. Byta ut`ChartTypeHere` med önskad diagramtyp, som t.ex`ChartType.ClusteredCylinder` i vårt exempel.

### Kan jag lägga till fler datapunkter i en serie?

 Ja, du kan lägga till fler datapunkter i en serie med hjälp av`series.getDataPoints().addDataPointForBarSeries(cell)` metod. Se till att tillhandahålla lämplig celldata.

### Hur uppdaterar jag kategorinamnen?

 Du kan uppdatera kategorinamn genom att använda`fact.getCell(worksheetIndex, columnIndex, rowIndex, newValue)` för att ställa in de nya kategorinamnen.

### Hur ändrar jag serienamn?

 För att ändra serienamn, använd`fact.getCell(worksheetIndex, columnIndex, rowIndex, newValue)` för att ställa in de nya serienamnen.

### Finns det något sätt att ta bort en serie från diagrammet?

 Ja, du kan ta bort en serie från diagrammet genom att använda`chart.getChartData().getSeries().removeAt(index)` metod, var`index`är indexet för serien du vill ta bort.