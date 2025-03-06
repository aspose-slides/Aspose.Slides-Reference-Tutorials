---
title: Ställa in automatiska cirkeldiagramsfärger i Java Slides
linktitle: Ställa in automatiska cirkeldiagramsfärger i Java Slides
second_title: Aspose.Slides Java PowerPoint Processing API
description: Lär dig hur du skapar dynamiska cirkeldiagram med automatiska segmentfärger i Java PowerPoint-presentationer med Aspose.Slides för Java. Steg-för-steg guide med källkod.
weight: 24
url: /sv/java/data-manipulation/setting-automatic-pie-chart-slice-colors-java-slides/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Ställa in automatiska cirkeldiagramsfärger i Java Slides


## Introduktion till att ställa in automatiska cirkeldiagramsfärger i Java Slides

I den här handledningen kommer vi att utforska hur man skapar ett cirkeldiagram i en PowerPoint-presentation med Aspose.Slides för Java och ställer in automatiska segmentfärger för diagrammet. Vi kommer att ge steg-för-steg-vägledning tillsammans med källkod.

## Förutsättningar

 Innan du börjar, se till att du har Aspose.Slides för Java-biblioteket installerat och konfigurerat i ditt Java-projekt. Du kan ladda ner biblioteket från Asposes webbplats:[Ladda ner Aspose.Slides för Java](https://releases.aspose.com/slides/java/).

## Steg 1: Importera nödvändiga paket

Först måste du importera de nödvändiga paketen från Aspose.Slides för Java:

```java
import com.aspose.slides.ChartType;
import com.aspose.slides.IChart;
import com.aspose.slides.IChartSeries;
import com.aspose.slides.ISlide;
import com.aspose.slides.Presentation;
import com.aspose.slides.SaveFormat;
import com.aspose.slides.NullableBool;
import com.aspose.slides.charts.IChartDataWorkbook;
```

## Steg 2: Skapa en PowerPoint-presentation

 Instantiera`Presentation` klass för att skapa en ny PowerPoint-presentation:

```java
String dataDir = "Your Document Directory";
Presentation presentation = new Presentation();
```

## Steg 3: Lägg till en bild

Gå till den första bilden i presentationen och lägg till ett diagram med standarddata:

```java
ISlide slide = presentation.getSlides().get_Item(0);
IChart chart = slide.getShapes().addChart(ChartType.Pie, 100, 100, 400, 400);
```

## Steg 4: Ställ in diagramtitel

Ange en titel för diagrammet:

```java
chart.getChartTitle().addTextFrameForOverriding("Sample Title");
chart.getChartTitle().getTextFrameForOverriding().getTextFrameFormat().setCenterText(NullableBool.True);
chart.getChartTitle().setHeight(20);
chart.setTitle(true);
```

## Steg 5: Konfigurera sjökortsdata

Ställ in diagrammet för att visa värden för den första serien och konfigurera diagramdata:

```java
chart.getChartData().getSeries().get_Item(0).getLabels().getDefaultDataLabelFormat().setShowValue(true);

int defaultWorksheetIndex = 0;
IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
chart.getChartData().getSeries().clear();
chart.getChartData().getCategories().clear();
```

## Steg 6: Lägg till kategorier och serier

Lägg till nya kategorier och serier i diagrammet:

```java
chart.getChartData().getCategories().add(fact.getCell(0, 1, 0, "First Qtr"));
chart.getChartData().getCategories().add(fact.getCell(0, 2, 0, "2nd Qtr"));
chart.getChartData().getCategories().add(fact.getCell(0, 3, 0, "3rd Qtr"));

IChartSeries series = chart.getChartData().getSeries().add(fact.getCell(0, 0, 1, "Series 1"), chart.getType());
```

## Steg 7: Fyll i seriedata

Fyll i seriedata för cirkeldiagrammet:

```java
series.getDataPoints().addDataPointForPieSeries(fact.getCell(defaultWorksheetIndex, 1, 1, 20));
series.getDataPoints().addDataPointForPieSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 50));
series.getDataPoints().addDataPointForPieSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 30));
```

## Steg 8: Aktivera varierade skivfärger

Aktivera olika skivfärger för cirkeldiagrammet:

```java
series.getParentSeriesGroup().setColorVaried(true);
```

## Steg 9: Spara presentationen

Slutligen sparar du presentationen i en PowerPoint-fil:

```java
presentation.save(dataDir + "Pie.pptx", SaveFormat.Pptx);
```

## Komplett källkod för att ställa in automatiska cirkeldiagramsfärger i Java Slides

```java
// Sökvägen till dokumentkatalogen.
String dataDir = "Your Document Directory";
// Instantiate Presentation-klass som representerar PPTX-fil
Presentation presentation = new Presentation();
try
{
	// Få tillgång till första bilden
	ISlide slides = presentation.getSlides().get_Item(0);
	// Lägg till diagram med standarddata
	IChart chart = slides.getShapes().addChart(ChartType.Pie, 100, 100, 400, 400);
	// Inställningsdiagram Titel
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
	// Lägger till nya kategorier
	chart.getChartData().getCategories().add(fact.getCell(0, 1, 0, "First Qtr"));
	chart.getChartData().getCategories().add(fact.getCell(0, 2, 0, "2nd Qtr"));
	chart.getChartData().getCategories().add(fact.getCell(0, 3, 0, "3rd Qtr"));
	// Lägger till nya serier
	IChartSeries series = chart.getChartData().getSeries().add(fact.getCell(0, 0, 1, "Series 1"), chart.getType());
	// Fyller nu på seriedata
	series.getDataPoints().addDataPointForPieSeries(fact.getCell(defaultWorksheetIndex, 1, 1, 20));
	series.getDataPoints().addDataPointForPieSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 50));
	series.getDataPoints().addDataPointForPieSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 30));
	series.getParentSeriesGroup().setColorVaried(true);
	presentation.save(dataDir + "Pie.pptx", SaveFormat.Pptx);
}
finally
{
	if (presentation != null) presentation.dispose();
}
```

## Slutsats

Du har framgångsrikt skapat ett cirkeldiagram i en PowerPoint-presentation med Aspose.Slides för Java och konfigurerat det att ha automatiska segmentfärger. Denna steg-för-steg-guide ger dig den nödvändiga källkoden för att uppnå detta. Du kan anpassa diagrammet och presentationen ytterligare efter behov.

## FAQ's

### Hur kan jag anpassa färgerna på enskilda skivor i cirkeldiagrammet?

 För att anpassa färgerna på enskilda skivor i cirkeldiagrammet kan du använda`getAutomaticSeriesColors` metod för att hämta standardfärgschemat och sedan ändra färgerna efter behov. Här är ett exempel:

```java
//Hämta standardfärgschemat
IColorFormatCollection colors = chart.getChartData().getSeries().get_Item(0).getAutomaticSeriesColors();

// Ändra färgerna efter behov
colors.get_Item(0).setColor(Color.RED); // Ställ in färgen på den första skivan till röd
colors.get_Item(1).setColor(Color.BLUE); // Ställ in färgen på den andra skivan till blå
// Lägg till fler färgändringar efter behov
```

### Hur kan jag lägga till en förklaring till cirkeldiagrammet?

 För att lägga till en förklaring till cirkeldiagrammet kan du använda`getLegend` metod och konfigurera den enligt följande:

```java
ILegend legend = chart.getLegend();
legend.setPosition(LegendPositionType.Right); // Ställ in förklaringspositionen
legend.setOverlay(true); // Visa förklaringen över diagrammet
```

### Kan jag ändra titelns teckensnitt och stil?

Ja, du kan ändra titelns teckensnitt och stil. Använd följande kod för att ställa in titelns teckensnitt och stil:

```java
chart.getChartTitle().getTextFrameForOverriding().getParagraphs().get_Item(0).getPortions().get_Item(0).getPortionFormat().setFontHeight(20); // Ställ in teckenstorlek
chart.getChartTitle().getTextFrameForOverriding().getParagraphs().get_Item(0).getPortions().get_Item(0).getPortionFormat().setFontBold(NullableBool.True); // Gör rubriken fet
chart.getChartTitle().getTextFrameForOverriding().getParagraphs().get_Item(0).getPortions().get_Item(0).getPortionFormat().setFontItalic(NullableBool.True); // Gör rubriken kursiv
```

Du kan justera teckenstorlek, djärvhet och kursiv stil efter behov.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
