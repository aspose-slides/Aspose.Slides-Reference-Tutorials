---
title: Normala diagram i Java Slides
linktitle: Normala diagram i Java Slides
second_title: Aspose.Slides Java PowerPoint Processing API
description: Skapa normala diagram i Java Slides med Aspose.Slides för Java. Steg-för-steg-guide och källkod för att skapa, anpassa och spara diagram i PowerPoint-presentationer.
weight: 21
url: /sv/java/chart-data-manipulation/normal-charts-java-slides/
---

{< blocks/products/pf/main-wrap-class >}
{< blocks/products/pf/main-container >}
{< blocks/products/pf/tutorial-page-section >}


## Introduktion till normala diagram i Java Slides

den här handledningen kommer vi att gå igenom processen att skapa normala diagram i Java Slides med hjälp av Aspose.Slides for Java API. Vi kommer att använda steg-för-steg-instruktioner tillsammans med källkod för att visa hur man skapar ett klustrade kolumndiagram i en PowerPoint-presentation.

## Förutsättningar

Innan du börjar, se till att du har följande förutsättningar på plats:

1. Aspose.Slides för Java API installerat.
2. En Java-utvecklingsmiljö inrättad.
3. Grundläggande kunskaper i Java-programmering.

## Steg 1: Konfigurera projektet

Se till att du har en katalog för ditt projekt. Låt oss kalla det "Din dokumentkatalog" som nämns i koden. Du kan ersätta detta med den faktiska sökvägen till din projektkatalog.

```java
// Sökvägen till dokumentkatalogen.
String dataDir = "Your Document Directory";
// Skapa katalog om den inte redan finns.
boolean IsExists = new File(dataDir).exists();
if (!IsExists)
    new File(dataDir).mkdirs();
```

## Steg 2: Skapa en presentation

Låt oss nu skapa en PowerPoint-presentation och få tillgång till dess första bild.

```java
// Instantiate Presentation-klass som representerar PPTX-fil
Presentation pres = new Presentation();
// Få tillgång till första bilden
ISlide sld = pres.getSlides().get_Item(0);
```

## Steg 3: Lägga till ett diagram

Vi kommer att lägga till ett klustrade kolumndiagram till bilden och ange dess titel.

```java
// Lägg till diagram med standarddata
IChart chart = sld.getShapes().addChart(ChartType.ClusteredColumn, 0, 0, 500, 500);
// Inställningsdiagram Titel
chart.getChartTitle().addTextFrameForOverriding("Sample Title");
chart.getChartTitle().getTextFrameForOverriding().getTextFrameFormat().setCenterText(NullableBool.True);
chart.getChartTitle().setHeight(20);
chart.setTitle(true);
```

## Steg 4: Ställ in sjökortsdata

Därefter kommer vi att ställa in diagramdata genom att definiera serier och kategorier.

```java
// Ställ in första serien på Visa värden
chart.getChartData().getSeries().get_Item(0).getLabels().getDefaultDataLabelFormat().setShowValue(true);

// Ställa in index för diagramdatabladet
int defaultWorksheetIndex = 0;

// Hämta arbetsbladet för diagramdata
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

## Steg 5: Fylla på seriedata

Låt oss nu fylla i seriedatapunkterna för diagrammet.

```java
// Ta första diagramserien
IChartSeries series = chart.getChartData().getSeries().get_Item(0);

// Fyller på seriedata
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 1, 20));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 50));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 30));

// Ställa in fyllningsfärg för serier
series.getFormat().getFill().setFillType(FillType.Solid);
series.getFormat().getFill().getSolidFillColor().setColor(Color.RED);

// Ta andra diagramserien
series = chart.getChartData().getSeries().get_Item(1);

// Fyller på seriedata
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 2, 30));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 2, 10));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 2, 60));

// Ställa in fyllningsfärg för serier
series.getFormat().getFill().setFillType(FillType.Solid);
series.getFormat().getFill().getSolidFillColor().setColor(Color.GREEN);
```

## Steg 6: Anpassa etiketter

Låt oss anpassa dataetiketterna för diagramserien.

```java
// Första etiketten kommer att visa Kategorinamn
IDataLabel lbl = series.getDataPoints().get_Item(0).getLabel();
lbl.getDataLabelFormat().setShowCategoryName(true);

lbl = series.getDataPoints().get_Item(1).getLabel();
lbl.getDataLabelFormat().setShowSeriesName(true);

// Visa värde för den tredje etiketten med serienamn och separator
lbl = series.getDataPoints().get_Item(2).getLabel();
lbl.getDataLabelFormat().setShowValue(true);
lbl.getDataLabelFormat().setShowSeriesName(true);
lbl.getDataLabelFormat().setSeparator("/");
```

## Steg 7: Spara presentationen

Slutligen sparar du presentationen med diagrammet i din projektkatalog.

```java
pres.save(dataDir + "AsposeChart_out.pptx", SaveFormat.Pptx);
```

Det är allt! Du har framgångsrikt skapat ett klustrat kolumndiagram i en PowerPoint-presentation med Aspose.Slides för Java. Du kan anpassa detta diagram ytterligare enligt dina krav.

## Komplett källkod för normala diagram i Java Slides

```java
// Sökvägen till dokumentkatalogen.
String dataDir = "Your Document Directory";
// Skapa katalog om den inte redan finns.
boolean IsExists = new File(dataDir).exists();
if (!IsExists)
	new File(dataDir).mkdirs();
// Instantiate Presentation-klass som representerar PPTX-fil
Presentation pres = new Presentation();
// Få tillgång till första bilden
ISlide sld = pres.getSlides().get_Item(0);
// Lägg till diagram med standarddata
IChart chart = sld.getShapes().addChart(ChartType.ClusteredColumn, 0, 0, 500, 500);
// Inställningsdiagram Titel
// Chart.getChartTitle().getTextFrameForOverriding().setText("Sample Title");
chart.getChartTitle().addTextFrameForOverriding("Sample Title");
chart.getChartTitle().getTextFrameForOverriding().getTextFrameFormat().setCenterText(NullableBool.True);
chart.getChartTitle().setHeight(20);
chart.setTitle(true);
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
// Lägger till nya serier
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 1, "Series 1"), chart.getType());
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 2, "Series 2"), chart.getType());
// Lägger till nya kategorier
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 1, 0, "Caetegoty 1"));
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 2, 0, "Caetegoty 2"));
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 3, 0, "Caetegoty 3"));
// Ta första diagramserien
IChartSeries series = chart.getChartData().getSeries().get_Item(0);
// Fyller nu på seriedata
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 1, 20));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 50));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 30));
// Ställa in fyllningsfärg för serier
series.getFormat().getFill().setFillType(FillType.Solid);
series.getFormat().getFill().getSolidFillColor().setColor(Color.RED);
// Ta andra diagramserien
series = chart.getChartData().getSeries().get_Item(1);
// Fyller nu på seriedata
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 2, 30));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 2, 10));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 2, 60));
// Ställa in fyllningsfärg för serier
series.getFormat().getFill().setFillType(FillType.Solid);
series.getFormat().getFill().getSolidFillColor().setColor(Color.GREEN);
// Första etiketten kommer att visa Kategorinamn
IDataLabel lbl = series.getDataPoints().get_Item(0).getLabel();
lbl.getDataLabelFormat().setShowCategoryName(true);
lbl = series.getDataPoints().get_Item(1).getLabel();
lbl.getDataLabelFormat().setShowSeriesName(true);
// Visa värde för tredje etikett
lbl = series.getDataPoints().get_Item(2).getLabel();
lbl.getDataLabelFormat().setShowValue(true);
lbl.getDataLabelFormat().setShowSeriesName(true);
lbl.getDataLabelFormat().setSeparator("/");
// Spara presentationen med diagram
pres.save(dataDir + "AsposeChart_out.pptx", SaveFormat.Pptx);
```
# Slutsats

I den här handledningen har vi lärt oss hur man skapar normala diagram i Java Slides med hjälp av Aspose.Slides for Java API. Vi gick igenom en steg-för-steg-guide med källkod för att skapa ett klustrat kolumndiagram i en PowerPoint-presentation.

## FAQ's

### Hur kan jag ändra diagramtypen?

 För att ändra diagramtypen, ändra`ChartType`parameter när du lägger till diagrammet med hjälp av`sld.getShapes().addChart()`. Du kan välja mellan olika diagramtyper tillgängliga i Aspose.Slides.

### Kan jag ändra färgerna på diagramserien?

 Ja, du kan ändra färgerna i diagramserien genom att ställa in fyllningsfärgen för varje serie med`series.getFormat().getFill().getSolidFillColor().setColor(Color.YOUR_COLOR)`.

### Hur lägger jag till fler kategorier eller serier i diagrammet?

 Du kan lägga till fler kategorier eller serier i diagrammet genom att lägga till nya datapunkter och etiketter med hjälp av`chart.getChartData().getCategories().add()` och`chart.getChartData().getSeries().add()` metoder.

### Hur kan jag anpassa diagramtiteln ytterligare?

 Du kan anpassa diagramtiteln ytterligare genom att ändra egenskaperna för`chart.getChartTitle()` som textjustering, teckenstorlek och färg.

### Hur sparar jag diagrammet i ett annat filformat?

 För att spara diagrammet till ett annat filformat, ändra`SaveFormat` parametern i`pres.save()` till önskat format (t.ex. PDF, PNG, JPEG).
{< /blocks/products/pf/tutorial-page-section >}

{< /blocks/products/pf/main-container >}
{< /blocks/products/pf/main-wrap-class >}

{< blocks/products/products-backtop-button >}
