---
"description": "Lär dig hur du skapar punktdiagram i Java med Aspose.Slides. Steg-för-steg-guide med Java-källkod för datavisualisering i presentationer."
"linktitle": "Spridda diagram i Java-presentationer"
"second_title": "Aspose.Slides Java PowerPoint-bearbetnings-API"
"title": "Spridda diagram i Java-presentationer"
"url": "/sv/java/chart-creation/scattered-chart-java-slides/"
"weight": 11
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Spridda diagram i Java-presentationer


## Introduktion till spridda diagram i Aspose.Slides för Java

I den här handledningen guidar vi dig genom processen att skapa ett punktdiagram med Aspose.Slides för Java. Punktdiagram är användbara för att visualisera datapunkter på ett tvådimensionellt plan. Vi tillhandahåller steg-för-steg-instruktioner och inkluderar Java-källkod för din bekvämlighet.

## Förkunskapskrav

Innan du börjar, se till att du har följande förutsättningar på plats:

1. [Aspose.Slides för Java](https://products.aspose.com/slides/java) installerad.
2. En Java-utvecklingsmiljö konfigurerad.

## Steg 1: Initiera presentationen

Importera först de nödvändiga biblioteken och skapa en ny presentation.

```java
// Sökvägen till dokumentkatalogen.
String dataDir = "Your Document Directory";

// Skapa katalog om den inte redan finns.
boolean IsExists = new File(dataDir).exists();
if (!IsExists)
    new File(dataDir).mkdirs();

// Skapa en ny presentation
Presentation pres = new Presentation();
```

## Steg 2: Lägg till en bild och skapa punktdiagrammet

Lägg sedan till en bild och skapa ett spridningsdiagram på den. Vi använder `ScatterWithSmoothLines` diagramtypen i det här exemplet.

```java
// Hämta den första bilden
ISlide slide = pres.getSlides().get_Item(0);

// Skapa spridningsdiagrammet
IChart chart = slide.getShapes().addChart(ChartType.ScatterWithSmoothLines, 0, 0, 400, 400);
```

## Steg 3: Förbered diagramdata

Nu ska vi förbereda data för vårt spridningsdiagram. Vi lägger till två serier, var och en med flera datapunkter.

```java
// Hämta standardindex för diagramdatakalkylblad
int defaultWorksheetIndex = 0;

// Hämta diagramdataarbetsbladet
IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();

// Ta bort demoserien
chart.getChartData().getSeries().clear();

// Lägg till den första serien
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 1, 1, "Series 1"), chart.getType());
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 1, 3, "Series 2"), chart.getType());

// Ta den första diagramserien
IChartSeries series = chart.getChartData().getSeries().get_Item(0);

// Lägg till datapunkter i den första serien
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 1), fact.getCell(defaultWorksheetIndex, 2, 2, 3));
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 2), fact.getCell(defaultWorksheetIndex, 3, 2, 10));

// Redigera serietypen
series.setType(ChartType.ScatterWithStraightLinesAndMarkers);
series.getMarker().setSize(10); // Ändra markörstorlek
series.getMarker().setSymbol(MarkerStyleType.Star); // Ändra markörsymbol

// Ta den andra diagramserien
series = chart.getChartData().getSeries().get_Item(1);

// Lägg till datapunkter i den andra serien
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 2, 3, 5), fact.getCell(defaultWorksheetIndex, 2, 4, 2));
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 3, 3, 3), fact.getCell(defaultWorksheetIndex, 3, 4, 1));
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 4, 3, 2), fact.getCell(defaultWorksheetIndex, 4, 4, 2));
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 5, 3, 5), fact.getCell(defaultWorksheetIndex, 5, 4, 1));

// Ändra markörstilen för den andra serien
series.getMarker().setSize(10);
series.getMarker().setSymbol(MarkerStyleType.Circle);
```

## Steg 4: Spara presentationen

Spara slutligen presentationen med punktdiagrammet till en PPTX-fil.

```java
pres.save(dataDir + "AsposeChart_out.pptx", SaveFormat.Pptx);
```

Det var allt! Du har skapat ett punktdiagram med Aspose.Slides för Java. Du kan nu anpassa det här exemplet ytterligare för att passa dina specifika data- och designkrav.

## Komplett källkod för spridda diagram i Java Slides
```java
// Sökvägen till dokumentkatalogen.
String dataDir = "Your Document Directory";
// Skapa katalog om den inte redan finns.
boolean IsExists = new File(dataDir).exists();
if (!IsExists)
	new File(dataDir).mkdirs();
Presentation pres = new Presentation();
ISlide slide = pres.getSlides().get_Item(0);
// Skapa standarddiagrammet
IChart chart = slide.getShapes().addChart(ChartType.ScatterWithSmoothLines, 0, 0, 400, 400);
// Hämta standardindex för diagramdatakalkylblad
int defaultWorksheetIndex = 0;
// Hämta diagramdataarbetsbladet
IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
// Ta bort demoserien
chart.getChartData().getSeries().clear();
// Lägg till ny serie
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 1, 1, "Series 1"), chart.getType());
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 1, 3, "Series 2"), chart.getType());
// Ta första diagramserien
IChartSeries series = chart.getChartData().getSeries().get_Item(0);
// Lägg till en ny punkt (1:3) där.
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 1), fact.getCell(defaultWorksheetIndex, 2, 2, 3));
// Lägg till ny punkt (2:10)
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 2), fact.getCell(defaultWorksheetIndex, 3, 2, 10));
// Redigera serietypen
series.setType(ChartType.ScatterWithStraightLinesAndMarkers);
// Ändra markören för diagramserien
series.getMarker().setSize(10);
series.getMarker().setSymbol(MarkerStyleType.Star);
// Ta den andra diagramserien
series = chart.getChartData().getSeries().get_Item(1);
// Lägg till ny punkt (5:2) där.
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 2, 3, 5), fact.getCell(defaultWorksheetIndex, 2, 4, 2));
// Lägg till ny punkt (3:1)
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 3, 3, 3), fact.getCell(defaultWorksheetIndex, 3, 4, 1));
// Lägg till ny punkt (2:2)
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 4, 3, 2), fact.getCell(defaultWorksheetIndex, 4, 4, 2));
// Lägg till ny punkt (5:1)
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 5, 3, 5), fact.getCell(defaultWorksheetIndex, 5, 4, 1));
// Ändra markören för diagramserien
series.getMarker().setSize(10);
series.getMarker().setSymbol(MarkerStyleType.Circle);
pres.save(dataDir + "AsposeChart_out.pptx", SaveFormat.Pptx);
```

## Slutsats

I den här handledningen har vi guidat dig genom processen att skapa ett punktdiagram med Aspose.Slides för Java. Punktdiagram är kraftfulla verktyg för att visualisera datapunkter i ett tvådimensionellt utrymme, vilket gör det enklare att analysera och förstå komplexa datarelationer.

## Vanliga frågor

### Hur kan jag ändra diagramtypen?

För att ändra diagramtyp, använd `setType` metoden på diagramserien och ange önskad diagramtyp. Till exempel, `series.setType(ChartType.Line)` skulle ändra serien till ett linjediagram.

### Hur anpassar jag markörens storlek och stil?

Du kan ändra markörens storlek och stil med hjälp av `getMarker` metoden på serien och ange sedan storlek och symbolegenskaper. Till exempel:

```java
series.getMarker().setSize(10);
series.getMarker().setSymbol(MarkerStyleType.Circle);
```

Utforska gärna fler anpassningsalternativ i dokumentationen för Aspose.Slides för Java.

Kom ihåg att byta ut `"Your Document Directory"` med den faktiska sökvägen där du vill spara presentationen.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}