---
"description": "Förbättra dina PowerPoint-presentationer med Aspose.Slides för Java. Lär dig att modifiera befintliga diagram programmatiskt. Steg-för-steg-guide med källkod för anpassning av diagram."
"linktitle": "Befintligt diagram i Java-presentationer"
"second_title": "Aspose.Slides Java PowerPoint-bearbetnings-API"
"title": "Befintligt diagram i Java-presentationer"
"url": "/sv/java/chart-elements/existing-chart-java-slides/"
"weight": 12
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Befintligt diagram i Java-presentationer


## Introduktion till befintliga diagram i Java-presentationer med Aspose.Slides för Java

den här handledningen visar vi hur man ändrar ett befintligt diagram i en PowerPoint-presentation med hjälp av Aspose.Slides för Java. Vi går igenom stegen för att ändra diagramdata, kategorinamn, serienamn och lägga till en ny serie i diagrammet. Se till att du har Aspose.Slides för Java konfigurerat i ditt projekt.

## Förkunskapskrav

Innan vi börjar, se till att du har följande förutsättningar på plats:

1. Aspose.Slides för Java-biblioteket ingår i ditt projekt.
2. En befintlig PowerPoint-presentation med ett diagram som du vill ändra.
3. Java-utvecklingsmiljö konfigurerad.

## Steg 1: Ladda presentationen

```java
// Sökvägen till dokumentkatalogen.
String dataDir = "Your Document Directory";

// Instansiera presentationsklassen som representerar en PPTX-fil
Presentation pres = new Presentation(dataDir + "ExistingChart.pptx");
```

## Steg 2: Komma åt bilden och diagrammet

```java
// Åtkomst till den första bilden
ISlide sld = pres.getSlides().get_Item(0);

// Få åtkomst till diagrammet på bilden
IChart chart = (IChart) sld.getShapes().get_Item(0);
```

## Steg 3: Ändra diagramdata och kategorinamn

```java
// Ställa in index för diagramdatabladet
int defaultWorksheetIndex = 0;

// Hämta diagramdataarbetsbladet
IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();

// Ändra namn på diagramkategorier
fact.getCell(defaultWorksheetIndex, 1, 0, "Modified Category 1");
fact.getCell(defaultWorksheetIndex, 2, 0, "Modified Category 2");
```

## Steg 4: Uppdatera första diagramserien

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

## Steg 5: Uppdatera den andra diagramserien

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
// Ändra diagramtypen till Klustrad cylindrar
chart.setType(ChartType.ClusteredCylinder);
```

## Steg 8: Spara den modifierade presentationen

```java
// Spara presentationen med det modifierade diagrammet
pres.save(dataDir + "AsposeChartModified_out.pptx", SaveFormat.Pptx);
```

Grattis! Du har framgångsrikt ändrat ett befintligt diagram i en PowerPoint-presentation med Aspose.Slides för Java. Du kan nu använda den här koden för att anpassa diagram i dina PowerPoint-presentationer programmatiskt.

## Komplett källkod för befintligt diagram i Java Slides

```java
// Sökvägen till dokumentkatalogen.
String dataDir = "Your Document Directory";
// Instansiera presentationsklass som representerar en PPTX-fil // Instansiera presentationsklass som representerar en PPTX-fil
Presentation pres = new Presentation(dataDir + "ExistingChart.pptx");
// Åtkomst till första bildmarkör
ISlide sld = pres.getSlides().get_Item(0);
// Lägg till diagram med standarddata
IChart chart = (IChart) sld.getShapes().get_Item(0);
// Ställa in index för diagramdatablad
int defaultWorksheetIndex = 0;
// Hämta diagramdataarbetsbladet
IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
// Ändra diagramkategorinamn
fact.getCell(defaultWorksheetIndex, 1, 0, "Modified Category 1");
fact.getCell(defaultWorksheetIndex, 2, 0, "Modified Category 2");
// Ta första diagramserien
IChartSeries series = chart.getChartData().getSeries().get_Item(0);
// Nu uppdateras seriedata
fact.getCell(defaultWorksheetIndex, 0, 1, "New_Series1");// Ändra serienamn
series.getDataPoints().get_Item(0).getValue().setData(90);
series.getDataPoints().get_Item(1).getValue().setData(123);
series.getDataPoints().get_Item(2).getValue().setData(44);
// Ta andra diagramserien
series = chart.getChartData().getSeries().get_Item(1);
// Nu uppdateras seriedata
fact.getCell(defaultWorksheetIndex, 0, 2, "New_Series2");// Ändra serienamn
series.getDataPoints().get_Item(0).getValue().setData(23);
series.getDataPoints().get_Item(1).getValue().setData(67);
series.getDataPoints().get_Item(2).getValue().setData(99);
// Nu lägger vi till en ny serie
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 3, "Series 3"), chart.getType());
// Ta den tredje diagramserien
series = chart.getChartData().getSeries().get_Item(2);
// Nu fyller seriedata
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 3, 20));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 3, 50));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 3, 30));
chart.setType(ChartType.ClusteredCylinder);
// Spara presentation med diagram
pres.save(dataDir + "AsposeChartModified_out.pptx", SaveFormat.Pptx);
```
## Slutsats

I den här omfattande handledningen har vi lärt oss hur man modifierar ett befintligt diagram i en PowerPoint-presentation med hjälp av Aspose.Slides för Java. Genom att följa steg-för-steg-guiden och använda källkodsexempel kan du enkelt anpassa och uppdatera diagram för att möta dina specifika behov. Här är en sammanfattning av vad vi gick igenom:

## Vanliga frågor

### Hur kan jag ändra diagramtypen?

Du kan ändra diagramtypen genom att använda `chart.setType(ChartType.ChartTypeHere)` metod. Ersätt `ChartTypeHere` med önskad diagramtyp, till exempel `ChartType.ClusteredCylinder` vårt exempel.

### Kan jag lägga till fler datapunkter i en serie?

Ja, du kan lägga till fler datapunkter i en serie med hjälp av `series.getDataPoints().addDataPointForBarSeries(cell)` metod. Se till att ange korrekt celldata.

### Hur uppdaterar jag kategorinamnen?

Du kan uppdatera kategorinamn genom att använda `fact.getCell(worksheetIndex, columnIndex, rowIndex, newValue)` för att ange de nya kategorinamnen.

### Hur ändrar jag serienamn?

För att ändra serienamn, använd `fact.getCell(worksheetIndex, columnIndex, rowIndex, newValue)` för att ange de nya serienamnen.

### Finns det något sätt att ta bort en serie från diagrammet?

Ja, du kan ta bort en serie från diagrammet med hjälp av `chart.getChartData().getSeries().removeAt(index)` metod, där `index` är indexet för den serie du vill ta bort.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}