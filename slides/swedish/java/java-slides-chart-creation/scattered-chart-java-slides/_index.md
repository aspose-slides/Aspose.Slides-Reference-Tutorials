---
title: Spridda diagram i Java Slides
linktitle: Spridda diagram i Java Slides
second_title: Aspose.Slides Java PowerPoint Processing API
description: Lär dig hur du skapar spridningsdiagram i Java med Aspose.Slides. Steg-för-steg-guide med Java-källkod för datavisualisering i presentationer.
weight: 11
url: /sv/java/chart-creation/scattered-chart-java-slides/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}


## Introduktion till spridda diagram i Aspose.Slides för Java

I den här handledningen kommer vi att guida dig genom processen att skapa ett scatterdiagram med Aspose.Slides för Java. Spridningsdiagram är användbara för att visualisera datapunkter på ett tvådimensionellt plan. Vi tillhandahåller steg-för-steg-instruktioner och inkluderar Java-källkod för din bekvämlighet.

## Förutsättningar

Innan du börjar, se till att du har följande förutsättningar på plats:

1. [Aspose.Slides för Java](https://products.aspose.com/slides/java) installerat.
2. En Java-utvecklingsmiljö inrättad.

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

## Steg 2: Lägg till en bild och skapa spridningsdiagrammet

 Lägg sedan till en bild och skapa ett punktdiagram på den. Vi kommer att använda`ScatterWithSmoothLines`diagramtyp i det här exemplet.

```java
// Få den första bilden
ISlide slide = pres.getSlides().get_Item(0);

// Skapar spridningsdiagrammet
IChart chart = slide.getShapes().addChart(ChartType.ScatterWithSmoothLines, 0, 0, 400, 400);
```

## Steg 3: Förbered diagramdata

Låt oss nu förbereda data för vårt spridningsdiagram. Vi lägger till två serier, var och en med flera datapunkter.

```java
// Hämta standarddiagrammets kalkylbladsindex
int defaultWorksheetIndex = 0;

// Hämta arbetsbladet för diagramdata
IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();

// Ta bort demoserier
chart.getChartData().getSeries().clear();

// Lägg till den första serien
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 1, 1, "Series 1"), chart.getType());
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 1, 3, "Series 2"), chart.getType());

// Ta den första diagramserien
IChartSeries series = chart.getChartData().getSeries().get_Item(0);

// Lägg till datapunkter i den första serien
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 1), fact.getCell(defaultWorksheetIndex, 2, 2, 3));
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 2), fact.getCell(defaultWorksheetIndex, 3, 2, 10));

// Redigera typen av serie
series.setType(ChartType.ScatterWithStraightLinesAndMarkers);
series.getMarker().setSize(10); // Ändra markörstorlek
series.getMarker().setSymbol(MarkerStyleType.Star); // Byt markörsymbol

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

Det är allt! Du har framgångsrikt skapat ett scatterdiagram med Aspose.Slides för Java. Du kan nu anpassa detta exempel ytterligare för att passa dina specifika data och designkrav.

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
//Skapar standarddiagrammet
IChart chart = slide.getShapes().addChart(ChartType.ScatterWithSmoothLines, 0, 0, 400, 400);
// Hämta standarddiagrammets kalkylbladsindex
int defaultWorksheetIndex = 0;
// Hämta arbetsbladet för diagramdata
IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
// Ta bort demoserier
chart.getChartData().getSeries().clear();
// Lägg till nya serier
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 1, 1, "Series 1"), chart.getType());
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 1, 3, "Series 2"), chart.getType());
// Ta första diagramserien
IChartSeries series = chart.getChartData().getSeries().get_Item(0);
// Lägg till ny punkt (1:3) där.
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 1), fact.getCell(defaultWorksheetIndex, 2, 2, 3));
// Lägg till ny punkt (2:10)
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 2), fact.getCell(defaultWorksheetIndex, 3, 2, 10));
// Redigera typen av serie
series.setType(ChartType.ScatterWithStraightLinesAndMarkers);
// Ändra diagramseriemarkören
series.getMarker().setSize(10);
series.getMarker().setSymbol(MarkerStyleType.Star);
// Ta andra diagramserien
series = chart.getChartData().getSeries().get_Item(1);
// Lägg till ny punkt (5:2) där.
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 2, 3, 5), fact.getCell(defaultWorksheetIndex, 2, 4, 2));
// Lägg till ny punkt (3:1)
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 3, 3, 3), fact.getCell(defaultWorksheetIndex, 3, 4, 1));
// Lägg till ny punkt (2:2)
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 4, 3, 2), fact.getCell(defaultWorksheetIndex, 4, 4, 2));
// Lägg till ny punkt (5:1)
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 5, 3, 5), fact.getCell(defaultWorksheetIndex, 5, 4, 1));
// Ändra diagramseriemarkören
series.getMarker().setSize(10);
series.getMarker().setSymbol(MarkerStyleType.Circle);
pres.save(dataDir + "AsposeChart_out.pptx", SaveFormat.Pptx);
```

## Slutsats

I den här handledningen har vi gått igenom processen för att skapa ett scatterdiagram med Aspose.Slides för Java. Spridningsdiagram är kraftfulla verktyg för att visualisera datapunkter i ett tvådimensionellt utrymme, vilket gör det lättare att analysera och förstå komplexa datarelationer.

## FAQ's

### Hur kan jag ändra diagramtypen?

 För att ändra diagramtypen, använd`setType` metod på diagramserien och ange önskad diagramtyp. Till exempel,`series.setType(ChartType.Line)` skulle ändra serien till ett linjediagram.

### Hur anpassar jag markörens storlek och stil?

 Du kan ändra markörens storlek och stil med hjälp av`getMarker` metod på serien och ställ sedan in storlek och symbolegenskaper. Till exempel:

```java
series.getMarker().setSize(10);
series.getMarker().setSymbol(MarkerStyleType.Circle);
```

Utforska gärna fler anpassningsalternativ i Aspose.Slides för Java-dokumentationen.

 Kom ihåg att byta ut`"Your Document Directory"` med den faktiska sökvägen där du vill spara presentationen.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
