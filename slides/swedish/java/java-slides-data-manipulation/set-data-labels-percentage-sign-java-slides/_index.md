---
"description": "Lär dig hur du anger dataetiketter med procenttecken i PowerPoint-presentationer med Aspose.Slides för Java. Skapa engagerande diagram med steg-för-steg-vägledning och källkod."
"linktitle": "Ange dataetiketter Procentuell inloggning i Java Slides"
"second_title": "Aspose.Slides Java PowerPoint-bearbetnings-API"
"title": "Ange dataetiketter Procentuell inloggning i Java Slides"
"url": "/sv/java/data-manipulation/set-data-labels-percentage-sign-java-slides/"
"weight": 17
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Ange dataetiketter Procentuell inloggning i Java Slides


## Introduktion till att ställa in dataetiketter Procentuell inloggning i Aspose.Slides för Java

I den här guiden går vi igenom processen för att ställa in dataetiketter med ett procenttecken med Aspose.Slides för Java. Vi skapar en PowerPoint-presentation med ett staplat kolumndiagram och konfigurerar dataetiketter för att visa procentsatser.

## Förkunskapskrav

Innan du börjar, se till att du har lagt till Aspose.Slides för Java-biblioteket i ditt projekt. Du kan ladda ner det från [här](https://releases.aspose.com/slides/java/).

## Steg 1: Skapa en ny presentation

Först skapar vi en ny PowerPoint-presentation med hjälp av Aspose.Slides.

```java
// Sökvägen till dokumentkatalogen.
String dataDir = "Your Document Directory";
// Skapa en instans av Presentation-klassen
Presentation presentation = new Presentation();
```

## Steg 2: Lägg till en bild och ett diagram

Sedan lägger vi till en bild och ett staplat kolumndiagram i presentationen.

```java
// Hämta referens till bilden
ISlide slide = presentation.getSlides().get_Item(0);

// Lägg till PercentsStackedColumn-diagrammet på en bild
IChart chart = slide.getShapes().addChart(ChartType.PercentsStackedColumn, 20, 20, 500, 400);
```

## Steg 3: Konfigurera axelnummerformat

För att visa procenttal måste vi konfigurera talformatet för diagrammets vertikala axel.

```java
// Sätt NumberFormatLinkedToSource till falskt
chart.getAxes().getVerticalAxis().setNumberFormatLinkedToSource(false);
chart.getAxes().getVerticalAxis().setNumberFormat("0.00%");
```

## Steg 4: Lägg till diagramdata

Vi lägger till data i diagrammet genom att skapa serier och datapunkter. I det här exemplet lägger vi till två serier med sina respektive datapunkter.

```java
// Hämta diagramdataarbetsbladet
IChartDataWorkbook workbook = chart.getChartData().getChartDataWorkbook();

// Lägg till ny serie
IChartSeries series = chart.getChartData().getSeries().add(workbook.getCell(defaultWorksheetIndex, 0, 1, "Reds"), chart.getType());
series.getDataPoints().addDataPointForBarSeries(workbook.getCell(defaultWorksheetIndex, 1, 1, 0.30));
series.getDataPoints().addDataPointForBarSeries(workbook.getCell(defaultWorksheetIndex, 2, 1, 0.50));
series.getDataPoints().addDataPointForBarSeries(workbook.getCell(defaultWorksheetIndex, 3, 1, 0.80));
series.getDataPoints().addDataPointForBarSeries(workbook.getCell(defaultWorksheetIndex, 4, 1, 0.65));

// Lägg till ny serie
IChartSeries series2 = chart.getChartData().getSeries().add(workbook.getCell(defaultWorksheetIndex, 0, 2, "Blues"), chart.getType());
series2.getDataPoints().addDataPointForBarSeries(workbook.getCell(defaultWorksheetIndex, 1, 2, 0.70));
series2.getDataPoints().addDataPointForBarSeries(workbook.getCell(defaultWorksheetIndex, 2, 2, 0.50));
series2.getDataPoints().addDataPointForBarSeries(workbook.getCell(defaultWorksheetIndex, 3, 2, 0.20));
series2.getDataPoints().addDataPointForBarSeries(workbook.getCell(defaultWorksheetIndex, 4, 2, 0.35));
```

## Steg 5: Anpassa dataetiketter

Nu ska vi anpassa utseendet på dataetiketterna.

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

Det var allt! Du har skapat en PowerPoint-presentation med ett staplat kolumndiagram och konfigurerat dataetiketter för att visa procentandelar med hjälp av Aspose.Slides för Java.

## Komplett källkod för procentuell inloggning i Java Slides, ange dataetiketter

```java
// Sökvägen till dokumentkatalogen.
String dataDir = "Your Document Directory";
// Skapa en instans av Presentation-klassen
Presentation presentation = new Presentation();
// Hämta referens till bilden
ISlide slide = presentation.getSlides().get_Item(0);
// Lägg till PercentsStackedColumn-diagrammet på en bild
IChart chart = slide.getShapes().addChart(ChartType.PercentsStackedColumn, 20, 20, 500, 400);
// Sätt NumberFormatLinkedToSource till falskt
chart.getAxes().getVerticalAxis().setNumberFormatLinkedToSource(false);
chart.getAxes().getVerticalAxis().setNumberFormat("0.00%");
chart.getChartData().getSeries().clear();
int defaultWorksheetIndex = 0;
// Hämta diagramdataarbetsbladet
IChartDataWorkbook workbook = chart.getChartData().getChartDataWorkbook();
// Lägg till ny serie
IChartSeries series = chart.getChartData().getSeries().add(workbook.getCell(defaultWorksheetIndex, 0, 1, "Reds"), chart.getType());
series.getDataPoints().addDataPointForBarSeries(workbook.getCell(defaultWorksheetIndex, 1, 1, 0.30));
series.getDataPoints().addDataPointForBarSeries(workbook.getCell(defaultWorksheetIndex, 2, 1, 0.50));
series.getDataPoints().addDataPointForBarSeries(workbook.getCell(defaultWorksheetIndex, 3, 1, 0.80));
series.getDataPoints().addDataPointForBarSeries(workbook.getCell(defaultWorksheetIndex, 4, 1, 0.65));
// Ställa in fyllningsfärg för serier
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
// Lägg till ny serie
IChartSeries series2 = chart.getChartData().getSeries().add(workbook.getCell(defaultWorksheetIndex, 0, 2, "Blues"), chart.getType());
series2.getDataPoints().addDataPointForBarSeries(workbook.getCell(defaultWorksheetIndex, 1, 2, 0.70));
series2.getDataPoints().addDataPointForBarSeries(workbook.getCell(defaultWorksheetIndex, 2, 2, 0.50));
series2.getDataPoints().addDataPointForBarSeries(workbook.getCell(defaultWorksheetIndex, 3, 2, 0.20));
series2.getDataPoints().addDataPointForBarSeries(workbook.getCell(defaultWorksheetIndex, 4, 2, 0.35));
// Inställning av fyllningstyp och färg
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

Genom att följa den här guiden har du lärt dig hur du skapar engagerande presentationer med procentbaserade dataetiketter, vilket kan vara särskilt användbart för att förmedla information effektivt i affärsrapporter, utbildningsmaterial med mera.

## Vanliga frågor

### Hur kan jag ändra färgerna på diagramserien?

Du kan ändra fyllningsfärgen för diagramserier med hjälp av `setFill` metod som visas i exemplet.

### Kan jag anpassa teckenstorleken på dataetiketterna?

Ja, du kan anpassa teckenstorleken på dataetiketter genom att ställa in `setFontHeight` egenskap som visas i koden.

### Hur kan jag lägga till fler serier i diagrammet?

Du kan lägga till ytterligare serier i diagrammet med hjälp av `add` metod på `IChartSeriesCollection` objekt.


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}