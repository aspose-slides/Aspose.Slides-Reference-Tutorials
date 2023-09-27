---
title: Ställ in dataetiketter Procent Sign in Java Slides
linktitle: Ställ in dataetiketter Procent Sign in Java Slides
second_title: Aspose.Slides Java PowerPoint Processing API
description: Lär dig hur du ställer in dataetiketter med procenttecken i PowerPoint-presentationer med Aspose.Slides för Java. Skapa engagerande diagram med steg-för-steg-vägledning och källkod.
type: docs
weight: 17
url: /sv/java/data-manipulation/set-data-labels-percentage-sign-java-slides/
---

## Introduktion till Ange dataetiketter Procent Logga in Aspose.Slides för Java

I den här guiden går vi igenom processen att ställa in dataetiketter med ett procenttecken med Aspose.Slides för Java. Vi kommer att skapa en PowerPoint-presentation med ett staplat kolumndiagram och konfigurera dataetiketter för att visa procentsatser.

## Förutsättningar

 Innan du börjar, se till att du har Aspose.Slides for Java-biblioteket lagt till ditt projekt. Du kan ladda ner den från[här](https://releases.aspose.com/slides/java/).

## Steg 1: Skapa en ny presentation

Först skapar vi en ny PowerPoint-presentation med Aspose.Slides.

```java
// Sökvägen till dokumentkatalogen.
String dataDir = "Your Document Directory";
// Skapa en instans av presentationsklassen
Presentation presentation = new Presentation();
```

## Steg 2: Lägg till en bild och ett diagram

Därefter lägger vi till en bild och ett staplat kolumndiagram till presentationen.

```java
// Få referens till bilden
ISlide slide = presentation.getSlides().get_Item(0);

// Lägg till PercentsStackedColumn-diagram på en bild
IChart chart = slide.getShapes().addChart(ChartType.PercentsStackedColumn, 20, 20, 500, 400);
```

## Steg 3: Konfigurera axelnummerformat

För att visa procentsatser måste vi konfigurera talformatet för diagrammets vertikala axel.

```java
//Ställ in NumberFormatLinkedToSource på false
chart.getAxes().getVerticalAxis().setNumberFormatLinkedToSource(false);
chart.getAxes().getVerticalAxis().setNumberFormat("0.00%");
```

## Steg 4: Lägg till diagramdata

Vi lägger till data i diagrammet genom att skapa serier och datapunkter. I det här exemplet lägger vi till två serier med sina respektive datapunkter.

```java
//Hämta arbetsbladet för diagramdata
IChartDataWorkbook workbook = chart.getChartData().getChartDataWorkbook();

// Lägg till nya serier
IChartSeries series = chart.getChartData().getSeries().add(workbook.getCell(defaultWorksheetIndex, 0, 1, "Reds"), chart.getType());
series.getDataPoints().addDataPointForBarSeries(workbook.getCell(defaultWorksheetIndex, 1, 1, 0.30));
series.getDataPoints().addDataPointForBarSeries(workbook.getCell(defaultWorksheetIndex, 2, 1, 0.50));
series.getDataPoints().addDataPointForBarSeries(workbook.getCell(defaultWorksheetIndex, 3, 1, 0.80));
series.getDataPoints().addDataPointForBarSeries(workbook.getCell(defaultWorksheetIndex, 4, 1, 0.65));

// Lägg till nya serier
IChartSeries series2 = chart.getChartData().getSeries().add(workbook.getCell(defaultWorksheetIndex, 0, 2, "Blues"), chart.getType());
series2.getDataPoints().addDataPointForBarSeries(workbook.getCell(defaultWorksheetIndex, 1, 2, 0.70));
series2.getDataPoints().addDataPointForBarSeries(workbook.getCell(defaultWorksheetIndex, 2, 2, 0.50));
series2.getDataPoints().addDataPointForBarSeries(workbook.getCell(defaultWorksheetIndex, 3, 2, 0.20));
series2.getDataPoints().addDataPointForBarSeries(workbook.getCell(defaultWorksheetIndex, 4, 2, 0.35));
```

## Steg 5: Anpassa dataetiketter

Låt oss nu anpassa utseendet på dataetiketterna.

```java
// Ställa in LabelFormat-egenskaper
series.getLabels().getDefaultDataLabelFormat().setShowValue(true);
series.getLabels().getDefaultDataLabelFormat().setNumberFormatLinkedToSource(false);
series.getLabels().getDefaultDataLabelFormat().setNumberFormat("0.0%");
series.getLabels().getDefaultDataLabelFormat().getTextFormat().getPortionFormat().setFontHeight(10);
series.getLabels().getDefaultDataLabelFormat().getTextFormat().getPortionFormat().getFillFormat().setFillType(FillType.Solid);
series.getLabels().getDefaultDataLabelFormat().getTextFormat().getPortionFormat().getFillFormat().getSolidFillColor().setColor(Color.WHITE);
series.getLabels().getDefaultDataLabelFormat().setShowValue(true);

series2.getLabels().getDefaultDataLabelFormat().setShowValue(true);
series2.getLabels().getDefaultDataLabelFormat().setNumberFormatLinkedToSource(false);
series2.getLabels().getDefaultDataLabelFormat().setNumberFormat("0.0%");
series2.getLabels().getDefaultDataLabelFormat().getTextFormat().getPortionFormat().setFontHeight(10);
series2.getLabels().getDefaultDataLabelFormat().getTextFormat().getPortionFormat().getFillFormat().setFillType(FillType.Solid);
series2.getLabels().getDefaultDataLabelFormat().getTextFormat().getPortionFormat().getFillFormat().getSolidFillColor().setColor(Color.WHITE);
```

## Steg 6: Spara presentationen

Slutligen sparar vi presentationen till en PowerPoint-fil.

```java
// Skriv presentation till disk
presentation.save(dataDir + "SetDataLabelsPercentageSign_out.pptx", SaveFormat.Pptx);
```

Det är allt! Du har framgångsrikt skapat en PowerPoint-presentation med ett staplat kolumndiagram och konfigurerat dataetiketter för att visa procentsatser med Aspose.Slides för Java.

## Komplett källkod för angivna dataetiketter Procent Logga in Java Slides

```java
// Sökvägen till dokumentkatalogen.
String dataDir = "Your Document Directory";
// Skapa en instans av presentationsklassen
Presentation presentation = new Presentation();
// Få referens till bilden
ISlide slide = presentation.getSlides().get_Item(0);
// Lägg till PercentsStackedColumn-diagram på en bild
IChart chart = slide.getShapes().addChart(ChartType.PercentsStackedColumn, 20, 20, 500, 400);
//Ställ in NumberFormatLinkedToSource på false
chart.getAxes().getVerticalAxis().setNumberFormatLinkedToSource(false);
chart.getAxes().getVerticalAxis().setNumberFormat("0.00%");
chart.getChartData().getSeries().clear();
int defaultWorksheetIndex = 0;
//Hämta arbetsbladet för diagramdata
IChartDataWorkbook workbook = chart.getChartData().getChartDataWorkbook();
// Lägg till nya serier
IChartSeries series = chart.getChartData().getSeries().add(workbook.getCell(defaultWorksheetIndex, 0, 1, "Reds"), chart.getType());
series.getDataPoints().addDataPointForBarSeries(workbook.getCell(defaultWorksheetIndex, 1, 1, 0.30));
series.getDataPoints().addDataPointForBarSeries(workbook.getCell(defaultWorksheetIndex, 2, 1, 0.50));
series.getDataPoints().addDataPointForBarSeries(workbook.getCell(defaultWorksheetIndex, 3, 1, 0.80));
series.getDataPoints().addDataPointForBarSeries(workbook.getCell(defaultWorksheetIndex, 4, 1, 0.65));
// Ställa in fyllningsfärgen för serien
series.getFormat().getFill().setFillType(FillType.Solid);
series.getFormat().getFill().getSolidFillColor().setColor(Color.RED);
// Ställa in LabelFormat-egenskaper
series.getLabels().getDefaultDataLabelFormat().setShowValue(true);
series.getLabels().getDefaultDataLabelFormat().setNumberFormatLinkedToSource(false);
series.getLabels().getDefaultDataLabelFormat().setNumberFormat("0.0%");
series.getLabels().getDefaultDataLabelFormat().getTextFormat().getPortionFormat().setFontHeight(10);
series.getLabels().getDefaultDataLabelFormat().getTextFormat().getPortionFormat().getFillFormat().setFillType(FillType.Solid);
series.getLabels().getDefaultDataLabelFormat().getTextFormat().getPortionFormat().getFillFormat().getSolidFillColor().setColor(Color.WHITE);
series.getLabels().getDefaultDataLabelFormat().setShowValue(true);
// Lägg till nya serier
IChartSeries series2 = chart.getChartData().getSeries().add(workbook.getCell(defaultWorksheetIndex, 0, 2, "Blues"), chart.getType());
series2.getDataPoints().addDataPointForBarSeries(workbook.getCell(defaultWorksheetIndex, 1, 2, 0.70));
series2.getDataPoints().addDataPointForBarSeries(workbook.getCell(defaultWorksheetIndex, 2, 2, 0.50));
series2.getDataPoints().addDataPointForBarSeries(workbook.getCell(defaultWorksheetIndex, 3, 2, 0.20));
series2.getDataPoints().addDataPointForBarSeries(workbook.getCell(defaultWorksheetIndex, 4, 2, 0.35));
// Inställning Fyllningstyp och färg
series2.getFormat().getFill().setFillType(FillType.Solid);
series2.getFormat().getFill().getSolidFillColor().setColor(Color.BLUE);
series2.getLabels().getDefaultDataLabelFormat().setShowValue(true);
series2.getLabels().getDefaultDataLabelFormat().setNumberFormatLinkedToSource(false);
series2.getLabels().getDefaultDataLabelFormat().setNumberFormat("0.0%");
series2.getLabels().getDefaultDataLabelFormat().getTextFormat().getPortionFormat().setFontHeight(10);
series2.getLabels().getDefaultDataLabelFormat().getTextFormat().getPortionFormat().getFillFormat().setFillType(FillType.Solid);
series2.getLabels().getDefaultDataLabelFormat().getTextFormat().getPortionFormat().getFillFormat().getSolidFillColor().setColor(Color.WHITE);
// Skriv presentation till disk
presentation.save(dataDir + "SetDataLabelsPercentageSign_out.pptx", SaveFormat.Pptx);
```

## Slutsats

Genom att följa den här guiden har du lärt dig hur du skapar engagerande presentationer med procentbaserade dataetiketter, vilket kan vara särskilt användbart för att effektivt förmedla information i affärsrapporter, utbildningsmaterial och mer.

## FAQ's

### Hur kan jag ändra färgerna i diagramserien?

 Du kan ändra fyllningsfärgen för diagramserier med hjälp av`setFill` metod som visas i exemplet.

### Kan jag anpassa teckensnittsstorleken på dataetiketterna?

 Ja, du kan anpassa teckensnittsstorleken för dataetiketter genom att ställa in`setFontHeight` egendom som visas i koden.

### Hur kan jag lägga till fler serier i diagrammet?

 Du kan lägga till ytterligare serier till diagrammet genom att använda`add` metod på`IChartSeriesCollection` objekt.
