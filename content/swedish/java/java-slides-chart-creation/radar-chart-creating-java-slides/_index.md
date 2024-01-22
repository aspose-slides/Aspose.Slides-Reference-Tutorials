---
title: Radardiagram skapa i Java Slides
linktitle: Radardiagram skapa i Java Slides
second_title: Aspose.Slides Java PowerPoint Processing API
description: Lär dig hur du skapar radardiagram i Java PowerPoint-presentationer med Aspose.Slides för Java API.
type: docs
weight: 10
url: /sv/java/chart-creation/radar-chart-creating-java-slides/
---

## Introduktion till att skapa ett radardiagram i Java Slides

I den här handledningen kommer vi att guida dig genom processen att skapa ett radardiagram med Aspose.Slides för Java API. Radardiagram är användbara för att visualisera data i ett cirkulärt mönster, vilket gör det lättare att jämföra flera dataserier. Vi kommer att tillhandahålla steg-för-steg-instruktioner tillsammans med Java-källkod.

## Förutsättningar

 Innan vi börjar, se till att du har Aspose.Slides för Java-biblioteket integrerat i ditt projekt. Du kan ladda ner biblioteket från[här](https://releases.aspose.com/slides/java/).

## Steg 1: Konfigurera presentationen

Låt oss börja med att skapa en ny PowerPoint-presentation och lägga till en bild till den.

```java
String outPath = RunExamples.getOutPath() + File.separator + "RadarChart_Out.pptx";
Presentation pres = new Presentation();
```

## Steg 2: Lägga till ett radardiagram

Därefter lägger vi till ett radardiagram till bilden. Vi kommer att specificera diagrammets position och dimensioner.

```java
ISlide sld = pres.getSlides().get_Item(0);
IChart ichart = sld.getShapes().addChart(ChartType.Radar, 0, 0, 400, 400);
```

## Steg 3: Ställ in sjökortsdata

Vi kommer nu att ställa in diagramdata. Detta innebär att skapa en dataarbetsbok, lägga till kategorier och lägga till serier.

```java
int defaultWorksheetIndex = 0;
IChartDataWorkbook fact = ichart.getChartData().getChartDataWorkbook();

// Ange diagramtitel
ichart.getChartTitle().addTextFrameForOverriding("Radar Chart");

// Ta bort standardgenererade serier och kategorier
ichart.getChartData().getCategories().clear();
ichart.getChartData().getSeries().clear();

// Lägger till nya kategorier
ichart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 1, 0, "Category 1"));
ichart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 2, 0, "Category 3"));
ichart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 3, 0, "Category 5"));
ichart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 4, 0, "Category 7"));
ichart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 5, 0, "Category 9"));
ichart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 6, 0, "Category 11"));

// Lägger till nya serier
ichart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 1, "Series 1"), ichart.getType());
ichart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 2, "Series 2"), ichart.getType());
```

## Steg 4: Fylla på seriedata

Nu kommer vi att fylla i seriedata för vårt radardiagram.

```java
// Fyll i seriedata för serie 1
IChartSeries series = ichart.getChartData().getSeries().get_Item(0);
series.getDataPoints().addDataPointForRadarSeries(fact.getCell(defaultWorksheetIndex, 1, 1, 2.7));
series.getDataPoints().addDataPointForRadarSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 2.4));
series.getDataPoints().addDataPointForRadarSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 1.5));
series.getDataPoints().addDataPointForRadarSeries(fact.getCell(defaultWorksheetIndex, 4, 1, 3.5));
series.getDataPoints().addDataPointForRadarSeries(fact.getCell(defaultWorksheetIndex, 5, 1, 5));
series.getDataPoints().addDataPointForRadarSeries(fact.getCell(defaultWorksheetIndex, 6, 1, 3.5));

// Ställ in seriefärg
series.getFormat().getLine().getFillFormat().setFillType(FillType.Solid);
series.getFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.RED);

// Fyll i seriedata för serie 2
series = ichart.getChartData().getSeries().get_Item(1);
series.getDataPoints().addDataPointForRadarSeries(fact.getCell(defaultWorksheetIndex, 1, 2, 2.5));
series.getDataPoints().addDataPointForRadarSeries(fact.getCell(defaultWorksheetIndex, 2, 2, 2.4));
series.getDataPoints().addDataPointForRadarSeries(fact.getCell(defaultWorksheetIndex, 3, 2, 1.6));
series.getDataPoints().addDataPointForRadarSeries(fact.getCell(defaultWorksheetIndex, 4, 2, 3.5));
series.getDataPoints().addDataPointForRadarSeries(fact.getCell(defaultWorksheetIndex, 5, 2, 4));
series.getDataPoints().addDataPointForRadarSeries(fact.getCell(defaultWorksheetIndex, 6, 2, 3.6));

// Ställ in seriefärg
series.getFormat().getLine().getFillFormat().setFillType(FillType.Solid);
series.getFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.ORANGE);
```

## Steg 5: Anpassa Axis och Legends

Låt oss anpassa axeln och legenderna för vårt radardiagram.

```java
// Ställ in förklaringsposition
ichart.getLegend().setPosition(LegendPositionType.Bottom);

// Ställa in textegenskaper för kategoriaxel
IChartPortionFormat txtCat = ichart.getAxes().getHorizontalAxis().getTextFormat().getPortionFormat();
txtCat.setFontBold(NullableBool.True);
txtCat.setFontHeight(10);
txtCat.getFillFormat().setFillType(FillType.Solid);
txtCat.getFillFormat().getSolidFillColor().setColor(new Color(PresetColor.DimGray));
txtCat.setLatinFont(new FontData("Calibri"));

// Ställa in teckenförklaringstextegenskaper
IChartPortionFormat txtleg = ichart.getLegend().getTextFormat().getPortionFormat();
txtleg.setFontBold(NullableBool.True);
txtleg.setFontHeight(10);
txtleg.getFillFormat().setFillType(FillType.Solid);
txtleg.getFillFormat().getSolidFillColor().setColor(new Color(PresetColor.DimGray));
txtleg.setLatinFont(new FontData("Calibri"));

// Ställa in värdeaxeltextegenskaper
IChartPortionFormat txtVal = ichart.getAxes().getVerticalAxis().getTextFormat().getPortionFormat();
txtVal.setFontBold(NullableBool.True);
txtVal.setFontHeight(10);
txtVal.getFillFormat().setFillType(FillType.Solid);
txtVal.getFillFormat().getSolidFillColor().setColor(new Color(PresetColor.DimGray));
txtVal.setLatinFont(new FontData("Calibri"));

// Inställningsvärdes axelnummerformat
ichart.getAxes().getVerticalAxis().setNumberFormatLinkedToSource(false);
ichart.getAxes().getVerticalAxis().setNumberFormat("\"$\"#,##0.00");

// Inställningsdiagram huvudenhetsvärde
ichart.getAxes().getVerticalAxis().setAutomaticMajorUnit(false);
ichart.getAxes().getVerticalAxis().setMajorUnit(1.25f);
```

## Steg 6: Spara presentationen

Slutligen, spara den genererade presentationen med radardiagrammet

.

```java
pres.save(outPath, SaveFormat.Pptx);
```

Det är allt! Du har framgångsrikt skapat ett radardiagram i en PowerPoint-presentation med Aspose.Slides för Java. Du kan nu anpassa detta exempel ytterligare för att passa dina specifika behov.

## Komplett källkod för att skapa radardiagram i Java Slides

```java
String outPath = RunExamples.getOutPath() + File.separator + "RadarChart_Out.pptx";
Presentation pres = new Presentation();
try
{
	// Få tillgång till första bilden
	ISlide sld = pres.getSlides().get_Item(0);
	// Lägg till radardiagram
	IChart ichart = sld.getShapes().addChart(ChartType.Radar, 0, 0, 400, 400);
	// Ställa in index för diagramdatabladet
	int defaultWorksheetIndex = 0;
	// Hämta arbetsbladet för diagramdata
	IChartDataWorkbook fact = ichart.getChartData().getChartDataWorkbook();
	// Ange diagramtitel
	ichart.getChartTitle().addTextFrameForOverriding("Radar Chart");
	// Ta bort standardgenererade serier och kategorier
	ichart.getChartData().getCategories().clear();
	ichart.getChartData().getSeries().clear();
	// Lägger till nya kategorier
	ichart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 1, 0, "Caetegoty 1"));
	ichart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 2, 0, "Caetegoty 3"));
	ichart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 3, 0, "Caetegoty 5"));
	ichart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 4, 0, "Caetegoty 7"));
	ichart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 5, 0, "Caetegoty 9"));
	ichart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 6, 0, "Caetegoty 11"));
	// Lägger till nya serier
	ichart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 1, "Series 1"), ichart.getType());
	ichart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 2, "Series 2"), ichart.getType());
	// Fyller nu på seriedata
	IChartSeries series = ichart.getChartData().getSeries().get_Item(0);
	series.getDataPoints().addDataPointForRadarSeries(fact.getCell(defaultWorksheetIndex, 1, 1, 2.7));
	series.getDataPoints().addDataPointForRadarSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 2.4));
	series.getDataPoints().addDataPointForRadarSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 1.5));
	series.getDataPoints().addDataPointForRadarSeries(fact.getCell(defaultWorksheetIndex, 4, 1, 3.5));
	series.getDataPoints().addDataPointForRadarSeries(fact.getCell(defaultWorksheetIndex, 5, 1, 5));
	series.getDataPoints().addDataPointForRadarSeries(fact.getCell(defaultWorksheetIndex, 6, 1, 3.5));
	// Ställ in seriefärg
	series.getFormat().getLine().getFillFormat().setFillType(FillType.Solid);
	series.getFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.RED);
	// Fyller nu på en annan seriedata
	series = ichart.getChartData().getSeries().get_Item(1);
	series.getDataPoints().addDataPointForRadarSeries(fact.getCell(defaultWorksheetIndex, 1, 2, 2.5));
	series.getDataPoints().addDataPointForRadarSeries(fact.getCell(defaultWorksheetIndex, 2, 2, 2.4));
	series.getDataPoints().addDataPointForRadarSeries(fact.getCell(defaultWorksheetIndex, 3, 2, 1.6));
	series.getDataPoints().addDataPointForRadarSeries(fact.getCell(defaultWorksheetIndex, 4, 2, 3.5));
	series.getDataPoints().addDataPointForRadarSeries(fact.getCell(defaultWorksheetIndex, 5, 2, 4));
	series.getDataPoints().addDataPointForRadarSeries(fact.getCell(defaultWorksheetIndex, 6, 2, 3.6));
	// Ställ in seriefärg
	series.getFormat().getLine().getFillFormat().setFillType(FillType.Solid);
	series.getFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.ORANGE);
	// Ställ in förklaringsposition
	ichart.getLegend().setPosition(LegendPositionType.Bottom);
	// Ställa in textegenskaper för kategoriaxel
	IChartPortionFormat txtCat = ichart.getAxes().getHorizontalAxis().getTextFormat().getPortionFormat();
	txtCat.setFontBold(NullableBool.True);
	txtCat.setFontHeight(10);
	txtCat.getFillFormat().setFillType(FillType.Solid);
	txtCat.getFillFormat().getSolidFillColor().setColor(new Color(PresetColor.DimGray));
	txtCat.setLatinFont(new FontData("Calibri"));
	// Ställa in teckenförklaringstextegenskaper
	IChartPortionFormat txtleg = ichart.getLegend().getTextFormat().getPortionFormat();
	txtleg.setFontBold(NullableBool.True);
	txtleg.setFontHeight(10);
	txtleg.getFillFormat().setFillType(FillType.Solid);
	txtleg.getFillFormat().getSolidFillColor().setColor(new Color(PresetColor.DimGray));
	txtCat.setLatinFont(new FontData("Calibri"));
	// Ställa in värdeaxeltextegenskaper
	IChartPortionFormat txtVal = ichart.getAxes().getVerticalAxis().getTextFormat().getPortionFormat();
	txtVal.setFontBold(NullableBool.True);
	txtVal.setFontHeight(10);
	txtVal.getFillFormat().setFillType(FillType.Solid);
	txtVal.getFillFormat().getSolidFillColor().setColor(new Color(PresetColor.DimGray));
	txtVal.setLatinFont(new FontData("Calibri"));
	// Inställningsvärdes axelnummerformat
	ichart.getAxes().getVerticalAxis().setNumberFormatLinkedToSource(false);
	ichart.getAxes().getVerticalAxis().setNumberFormat("\"$\"#,##0.00");
	// Inställningsdiagram huvudenhetsvärde
	ichart.getAxes().getVerticalAxis().setAutomaticMajorUnit(false);
	ichart.getAxes().getVerticalAxis().setMajorUnit(1.25f);
	// Spara genererad presentation
	pres.save(outPath, SaveFormat.Pptx);
}
finally
{
	if (pres != null) pres.dispose();
}
```

## Slutsats

I den här handledningen har du lärt dig hur du skapar ett radardiagram i en PowerPoint-presentation med Aspose.Slides för Java. Du kan tillämpa dessa koncept för att visualisera och presentera dina data effektivt i dina Java-applikationer.

## FAQ's

### Hur kan jag ändra diagrammets titel?

För att ändra diagramtiteln, ändra följande rad:
```java
ichart.getChartTitle().addTextFrameForOverriding("Radar Chart");
```

### Kan jag lägga till fler dataserier till radardiagrammet?

Ja, du kan lägga till fler dataserier genom att följa stegen i "Steg 3" och "Steg 4" för varje ytterligare serie du vill inkludera.

### Hur anpassar jag diagramfärgerna?

 Du kan anpassa seriefärgerna genom att ändra linjerna som anger`SolidFillColor` egendom för varje serie. Till exempel:
```java
series.getFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.RED);
```

### Hur kan jag ändra axeletiketter och formatering?

Se "Steg 5" för att anpassa axeletiketter och formatering, inklusive teckenstorlek och färg.

### Hur sparar jag diagrammet i ett annat filformat?

 Du kan ändra utdataformatet genom att ändra filtillägget i`outPath` variabel och använder lämplig`SaveFormat` . Till exempel, för att spara som en PDF, använd`SaveFormat.Pdf`.