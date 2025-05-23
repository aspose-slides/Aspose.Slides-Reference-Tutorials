---
"description": "Skapa vanliga diagram i Java-presentationer med Aspose.Slides för Java. Steg-för-steg-guide och källkod för att skapa, anpassa och spara diagram i PowerPoint-presentationer."
"linktitle": "Vanliga diagram i Java-presentationer"
"second_title": "Aspose.Slides Java PowerPoint-bearbetnings-API"
"title": "Vanliga diagram i Java-presentationer"
"url": "/sv/java/chart-data-manipulation/normal-charts-java-slides/"
"weight": 21
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Vanliga diagram i Java-presentationer


## Introduktion till normala diagram i Java-presentationer

I den här handledningen går vi igenom processen för att skapa vanliga diagram i Java Slides med hjälp av Aspose.Slides för Java API. Vi kommer att använda steg-för-steg-instruktioner tillsammans med källkod för att visa hur man skapar ett klustrat stapeldiagram i en PowerPoint-presentation.

## Förkunskapskrav

Innan du börjar, se till att du har följande förutsättningar på plats:

1. Aspose.Slides för Java API installerat.
2. En Java-utvecklingsmiljö konfigurerad.
3. Grundläggande kunskaper i Java-programmering.

## Steg 1: Konfigurera projektet

Se till att du har en katalog för ditt projekt. Låt oss kalla den "Din dokumentkatalog" som nämns i koden. Du kan ersätta detta med den faktiska sökvägen till din projektkatalog.

```java
// Sökvägen till dokumentkatalogen.
String dataDir = "Your Document Directory";
// Skapa katalog om den inte redan finns.
boolean IsExists = new File(dataDir).exists();
if (!IsExists)
    new File(dataDir).mkdirs();
```

## Steg 2: Skapa en presentation

Nu ska vi skapa en PowerPoint-presentation och visa den första bilden.

```java
// Instansiera presentationsklassen som representerar en PPTX-fil
Presentation pres = new Presentation();
// Åtkomst till första bilden
ISlide sld = pres.getSlides().get_Item(0);
```

## Steg 3: Lägga till ett diagram

Vi lägger till ett klustrat stapeldiagram i bilden och anger dess titel.

```java
// Lägg till diagram med standarddata
IChart chart = sld.getShapes().addChart(ChartType.ClusteredColumn, 0, 0, 500, 500);
// Titel för sättningstabell
chart.getChartTitle().addTextFrameForOverriding("Sample Title");
chart.getChartTitle().getTextFrameForOverriding().getTextFrameFormat().setCenterText(NullableBool.True);
chart.getChartTitle().setHeight(20);
chart.setTitle(true);
```

## Steg 4: Ställa in diagramdata

Nästa steg är att ställa in diagramdata genom att definiera serier och kategorier.

```java
// Ställ in första serien på Visa värden
chart.getChartData().getSeries().get_Item(0).getLabels().getDefaultDataLabelFormat().setShowValue(true);

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

## Steg 5: Ifyllning av seriedata

Nu ska vi fylla i seriens datapunkter för diagrammet.

```java
// Ta första diagramserien
IChartSeries series = chart.getChartData().getSeries().get_Item(0);

// Ifyllning av seriedata
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 1, 20));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 50));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 30));

// Ställa in fyllningsfärg för serier
series.getFormat().getFill().setFillType(FillType.Solid);
series.getFormat().getFill().getSolidFillColor().setColor(Color.RED);

// Ta den andra diagramserien
series = chart.getChartData().getSeries().get_Item(1);

// Ifyllning av seriedata
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 2, 30));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 2, 10));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 2, 60));

// Ställa in fyllningsfärg för serier
series.getFormat().getFill().setFillType(FillType.Solid);
series.getFormat().getFill().getSolidFillColor().setColor(Color.GREEN);
```

## Steg 6: Anpassa etiketter

Nu ska vi anpassa dataetiketterna för diagramserien.

```java
// Första etiketten visar kategorinamnet
IDataLabel lbl = series.getDataPoints().get_Item(0).getLabel();
lbl.getDataLabelFormat().setShowCategoryName(true);

lbl = series.getDataPoints().get_Item(1).getLabel();
lbl.getDataLabelFormat().setShowSeriesName(true);

// Visa värde för den tredje etiketten med serienamn och avgränsare
lbl = series.getDataPoints().get_Item(2).getLabel();
lbl.getDataLabelFormat().setShowValue(true);
lbl.getDataLabelFormat().setShowSeriesName(true);
lbl.getDataLabelFormat().setSeparator("/");
```

## Steg 7: Spara presentationen

Spara slutligen presentationen med diagrammet i din projektkatalog.

```java
pres.save(dataDir + "AsposeChart_out.pptx", SaveFormat.Pptx);
```

Det var allt! Du har skapat ett klustrat stapeldiagram i en PowerPoint-presentation med Aspose.Slides för Java. Du kan anpassa diagrammet ytterligare efter dina behov.

## Komplett källkod för normala diagram i Java Slides

```java
// Sökvägen till dokumentkatalogen.
String dataDir = "Your Document Directory";
// Skapa katalog om den inte redan finns.
boolean IsExists = new File(dataDir).exists();
if (!IsExists)
	new File(dataDir).mkdirs();
// Instansiera presentationsklassen som representerar en PPTX-fil
Presentation pres = new Presentation();
// Åtkomst till första bilden
ISlide sld = pres.getSlides().get_Item(0);
// Lägg till diagram med standarddata
IChart chart = sld.getShapes().addChart(ChartType.ClusteredColumn, 0, 0, 500, 500);
// Titel för sättningstabell
// Chart.getChartTitle().getTextFrameForOverriding().setText("Exempeltitel");
chart.getChartTitle().addTextFrameForOverriding("Sample Title");
chart.getChartTitle().getTextFrameForOverriding().getTextFrameFormat().setCenterText(NullableBool.True);
chart.getChartTitle().setHeight(20);
chart.setTitle(true);
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
// Ställa in fyllningsfärg för serier
series.getFormat().getFill().setFillType(FillType.Solid);
series.getFormat().getFill().getSolidFillColor().setColor(Color.RED);
// Ta den andra diagramserien
series = chart.getChartData().getSeries().get_Item(1);
// Nu fyller seriedata
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 2, 30));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 2, 10));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 2, 60));
// Ställa in fyllningsfärg för serier
series.getFormat().getFill().setFillType(FillType.Solid);
series.getFormat().getFill().getSolidFillColor().setColor(Color.GREEN);
// Första etiketten kommer att visa kategorinamn
IDataLabel lbl = series.getDataPoints().get_Item(0).getLabel();
lbl.getDataLabelFormat().setShowCategoryName(true);
lbl = series.getDataPoints().get_Item(1).getLabel();
lbl.getDataLabelFormat().setShowSeriesName(true);
// Visa värde för tredje etiketten
lbl = series.getDataPoints().get_Item(2).getLabel();
lbl.getDataLabelFormat().setShowValue(true);
lbl.getDataLabelFormat().setShowSeriesName(true);
lbl.getDataLabelFormat().setSeparator("/");
// Spara presentation med diagram
pres.save(dataDir + "AsposeChart_out.pptx", SaveFormat.Pptx);
```
# Slutsats

I den här handledningen har vi lärt oss hur man skapar vanliga diagram i Java Slides med hjälp av Aspose.Slides för Java API. Vi gick igenom en steg-för-steg-guide med källkod för att skapa ett klustrat stapeldiagram i en PowerPoint-presentation.

## Vanliga frågor

### Hur kan jag ändra diagramtypen?

För att ändra diagramtypen, modifiera `ChartType` parametern när du lägger till diagrammet med hjälp av `sld.getShapes().addChart()`Du kan välja mellan olika diagramtyper som finns i Aspose.Slides.

### Kan jag ändra färgerna på diagramserien?

Ja, du kan ändra färgerna på diagramserien genom att ange fyllningsfärgen för varje serie med hjälp av `series.getFormat().getFill().getSolidFillColor().setColor(Color.YOUR_COLOR)`.

### Hur lägger jag till fler kategorier eller serier i diagrammet?

Du kan lägga till fler kategorier eller serier i diagrammet genom att lägga till nya datapunkter och etiketter med hjälp av `chart.getChartData().getCategories().add()` och `chart.getChartData().getSeries().add()` metoder.

### Hur kan jag anpassa diagrammets titel ytterligare?

Du kan anpassa diagrammets titel ytterligare genom att ändra egenskaperna för `chart.getChartTitle()` såsom textjustering, teckenstorlek och färg.

### Hur sparar jag diagrammet i ett annat filformat?

För att spara diagrammet i ett annat filformat, ändra `SaveFormat` parametern i `pres.save()` metod till önskat format (t.ex. PDF, PNG, JPEG).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}