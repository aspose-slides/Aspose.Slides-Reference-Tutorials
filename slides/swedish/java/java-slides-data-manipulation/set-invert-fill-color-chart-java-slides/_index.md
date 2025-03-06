---
title: Ställ in Invertera fyllningsfärgdiagram i Java Slides
linktitle: Ställ in Invertera fyllningsfärgdiagram i Java Slides
second_title: Aspose.Slides Java PowerPoint Processing API
description: Lär dig hur du ställer in inverterade fyllningsfärger för Java Slides-diagram med Aspose.Slides. Förbättra dina diagramvisualiseringar med den här steg-för-steg-guiden och källkoden.
weight: 22
url: /sv/java/data-manipulation/set-invert-fill-color-chart-java-slides/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}


## Introduktion till att ställa in inverterat fyllningsfärgdiagram i Java Slides

den här handledningen kommer vi att visa hur man ställer in den inverterade fyllningsfärgen för ett diagram i Java Slides med Aspose.Slides för Java. Invertering av fyllningsfärg är en användbar funktion när du vill markera negativa värden i ett diagram med en specifik färg. Vi kommer att tillhandahålla steg-för-steg-instruktioner och källkod för att uppnå detta.

## Förutsättningar

Innan du börjar, se till att du har följande förutsättningar på plats:

1. Aspose.Slides för Java-biblioteket installerat.
2. Java utvecklingsmiljö inrättad.

## Steg 1: Skapa en presentation

Först måste vi skapa en presentation att lägga till vårt diagram till. Du kan använda följande kod för att skapa en presentation:

```java
// Sökvägen till dokumentkatalogen.
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
```

## Steg 2: Lägg till ett diagram

Därefter kommer vi att lägga till ett klustrat kolumndiagram till presentationen. Så här kan du göra det:

```java
IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 100, 100, 400, 300);
```

## Steg 3: Ställ in sjökortsdata

Låt oss nu ställa in diagramdata, inklusive serier och kategorier:

```java
IChartDataWorkbook workBook = chart.getChartData().getChartDataWorkbook();
chart.getChartData().getSeries().clear();
chart.getChartData().getCategories().clear();

// Lägger till nya serier och kategorier
chart.getChartData().getSeries().add(workBook.getCell(0, 0, 1, "Series 1"), chart.getType());
chart.getChartData().getCategories().add(workBook.getCell(0, 1, 0, "Category 1"));
chart.getChartData().getCategories().add(workBook.getCell(0, 2, 0, "Category 2"));
chart.getChartData().getCategories().add(workBook.getCell(0, 3, 0, "Category 3"));
```

## Steg 4: Fyll i seriedata

Låt oss nu fylla i seriedata för diagrammet:

```java
IChartSeries series = chart.getChartData().getSeries().get_Item(0);
series.getDataPoints().addDataPointForBarSeries(workBook.getCell(0, 1, 1, -20));
series.getDataPoints().addDataPointForBarSeries(workBook.getCell(0, 2, 1, 50));
series.getDataPoints().addDataPointForBarSeries(workBook.getCell(0, 3, 1, -30));
```

## Steg 5: Ställ in Invertera fyllningsfärg

För att ställa in den inverterade fyllningsfärgen för diagramserien kan du använda följande kod:

```java
Color seriesColor = series.getAutomaticSeriesColor();
series.setInvertIfNegative(true);
series.getFormat().getFill().setFillType(FillType.Solid);
series.getFormat().getFill().getSolidFillColor().setColor(seriesColor);
series.getInvertedSolidFillColor().setColor(Color.RED);
```

I ovanstående kod ställer vi in serien för att invertera fyllningsfärg för negativa värden och specificera färgen för den inverterade fyllningen.

## Steg 6: Spara presentationen

Spara slutligen presentationen med diagrammet:

```java
pres.save(dataDir + "SetInvertFillColorChart_out.pptx", SaveFormat.Pptx);
```

## Komplett källkod för Set Invert Fill Color Chart i Java Slides

```java
// Sökvägen till dokumentkatalogen.
String dataDir = "Your Document Directory";
Color inverColor = Color.RED;
Presentation pres = new Presentation();
try
{
IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 100, 100, 400, 300);
IChartDataWorkbook workBook = chart.getChartData().getChartDataWorkbook();
chart.getChartData().getSeries().clear();
chart.getChartData().getCategories().clear();
// Lägger till nya serier och kategorier
chart.getChartData().getSeries().add(workBook.getCell(0, 0, 1, "Series 1"), chart.getType());
chart.getChartData().getCategories().add(workBook.getCell(0, 1, 0, "Category 1"));
chart.getChartData().getCategories().add(workBook.getCell(0, 2, 0, "Category 2"));
chart.getChartData().getCategories().add(workBook.getCell(0, 3, 0, "Category 3"));
// Ta första diagramserien och fylla i seriedata.
IChartSeries series = chart.getChartData().getSeries().get_Item(0);
series.getDataPoints().addDataPointForBarSeries(workBook.getCell(0, 1, 1, -20));
series.getDataPoints().addDataPointForBarSeries(workBook.getCell(0, 2, 1, 50));
series.getDataPoints().addDataPointForBarSeries(workBook.getCell(0, 3, 1, -30));
Color seriesColor = series.getAutomaticSeriesColor();
series.setInvertIfNegative(true);
series.getFormat().getFill().setFillType(FillType.Solid);
series.getFormat().getFill().getSolidFillColor().setColor(seriesColor);
series.getInvertedSolidFillColor().setColor(Color.RED);
pres.save(dataDir + "SetInvertFillColorChart_out.pptx", SaveFormat.Pptx);
}
finally
{
if (pres != null) pres.dispose();
}
```

## Slutsats

I den här handledningen har vi visat dig hur du ställer in den inverterade fyllningsfärgen för ett diagram i Java Slides med Aspose.Slides för Java. Den här funktionen låter dig markera negativa värden i dina diagram med en specifik färg, vilket gör dina data mer visuellt informativa.

## FAQ's

I det här avsnittet kommer vi att ta upp några vanliga frågor relaterade till att ställa in den inverterade fyllningsfärgen för ett diagram i Java Slides med Aspose.Slides för Java.

### Hur installerar jag Aspose.Slides för Java?

 Du kan installera Aspose.Slides för Java genom att inkludera Aspose.Slides JAR-filer i ditt Java-projekt. Du kan ladda ner biblioteket från[Aspose.Slides för Java nedladdningssida](https://releases.aspose.com/slides/java/). Följ installationsinstruktionerna i dokumentationen för din specifika utvecklingsmiljö.

### Kan jag anpassa färgen för inverterad fyllning i diagramserien?

Ja, du kan anpassa färgen för den inverterade fyllningen i diagramserien. I det medföljande kodexemplet är`series.getInvertedSolidFillColor().setColor(Color.RED)` linje ställer in färgen till röd för den inverterade fyllningen. Du kan byta ut`Color.RED` med valfri annan färg.

### Hur kan jag ändra diagramtypen i Aspose.Slides för Java?

 Du kan ändra diagramtypen genom att ändra`ChartType` parameter när du lägger till ett diagram i presentationen. I kodexemplet använde vi`ChartType.ClusteredColumn` . Du kan utforska andra diagramtyper som linjediagram, stapeldiagram, cirkeldiagram, etc., genom att ange lämpligt`ChartType` uppräkningsvärde.

### Hur lägger jag till flera dataserier i ett diagram?

 För att lägga till flera dataserier till ett diagram kan du använda`chart.getChartData().getSeries().add(...)` metod för varje serie du vill lägga till. Se till att tillhandahålla lämpliga datapunkter och etiketter för varje serie för att fylla ditt diagram med flera serier.

### Finns det något sätt att anpassa andra aspekter av diagrammets utseende?

Ja, du kan anpassa olika aspekter av diagrammets utseende, inklusive axeletiketter, titlar, legender och mer med Aspose.Slides för Java. Se dokumentationen för detaljerad vägledning om anpassning av diagramelement och utseende.

### Kan jag spara diagrammet i olika format?

 Ja, du kan spara diagrammet i olika format med Aspose.Slides för Java. I det medföljande kodexemplet sparade vi presentationen som en PPTX-fil. Du kan använda olika`SaveFormat` alternativ för att spara den i andra format som PDF, PNG eller SVG, beroende på dina krav.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
