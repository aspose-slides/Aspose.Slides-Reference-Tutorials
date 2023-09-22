---
title: Ställa in bildtext för dataetikett i Java Slides
linktitle: Ställa in bildtext för dataetikett i Java Slides
second_title: Aspose.Slides Java PowerPoint Processing API
description: Lär dig hur du ställer in bildtexter för dataetiketter i Aspose.Slides för Java. Steg-för-steg guide med källkod.
type: docs
weight: 25
url: /sv/java/data-manipulation/setting-callout-data-label-java-slides/
---

## Introduktion till inställning av bildtext för dataetikett i Aspose.Slides för Java

I den här handledningen kommer vi att visa hur man ställer in bildtexter för dataetiketter i ett diagram med Aspose.Slides för Java. Bildtexter kan vara användbara för att markera specifika datapunkter i ditt diagram. Vi går igenom koden steg för steg och tillhandahåller den nödvändiga källkoden.

## Förutsättningar

- Du bör ha Aspose.Slides för Java installerat.
- Skapa ett Java-projekt och lägg till Aspose.Slides-biblioteket i ditt projekt.

## Steg 1: Skapa en presentation och lägg till ett diagram

 Först måste vi skapa en presentation och lägga till ett diagram till en bild. Se till att byta ut`"Your Document Directory"` med den faktiska sökvägen till din dokumentkatalog.

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "testc.pptx");
ISlide slide = pres.getSlides().get_Item(0);
IChart chart = slide.getShapes().addChart(ChartType.Doughnut, 10, 10, 500, 500, false);
```

## Steg 2: Konfigurera diagrammet

Därefter konfigurerar vi diagrammet genom att ställa in egenskaper som förklaring, serier och kategorier.

```java
IChartDataWorkbook workBook = chart.getChartData().getChartDataWorkbook();
chart.getChartData().getSeries().clear();
chart.getChartData().getCategories().clear();
chart.setLegend(false);

//Konfigurera serier och kategorier (Du kan justera antalet serier och kategorier)
int seriesIndex = 0;
while (seriesIndex < 15) {
    IChartSeries series = chart.getChartData().getSeries().add(workBook.getCell(0, 0, seriesIndex + 1, "SERIES " + seriesIndex), chart.getType());
    series.setExplosion(0);
    series.getParentSeriesGroup().setDoughnutHoleSize((byte) 20);
    series.getParentSeriesGroup().setFirstSliceAngle(351);
    seriesIndex++;
}

int categoryIndex = 0;
while (categoryIndex < 15) {
    chart.getChartData().getCategories().add(workBook.getCell(0, categoryIndex + 1, 0, "CATEGORY " + categoryIndex));
    int i = 0;
    while (i < chart.getChartData().getSeries().size()) {
        // Lägg till datapunkter här
        // ...
        i++;
    }
    categoryIndex++;
}
```

## Steg 3: Anpassa dataetiketter

Nu kommer vi att anpassa dataetiketterna, inklusive att ställa in länktexter för den senaste serien.

```java
int i = 0;
while (i < chart.getChartData().getSeries().size()) {
    IChartSeries iCS = chart.getChartData().getSeries().get_Item(i);
    IChartDataPoint dataPoint = iCS.getDataPoints().addDataPointForDoughnutSeries(workBook.getCell(0, categoryIndex + 1, i + 1, 1));
    dataPoint.getFormat().getFill().setFillType(FillType.Solid);
    // Anpassa datapunktsformatering (Fill, Line, etc.)

    if (i == chart.getChartData().getSeries().size() - 1) {
        IDataLabel lbl = dataPoint.getLabel();
        lbl.getTextFormat().getTextBlockFormat().setAutofitType(TextAutofitType.Shape);
        // Anpassa etikettformatering (teckensnitt, fyllning, etc.)
        lbl.getDataLabelFormat().setShowValue(false);
        lbl.getDataLabelFormat().setShowCategoryName(true);
        lbl.getDataLabelFormat().setShowSeriesName(false);
        // Aktivera länktexter
        lbl.getDataLabelFormat().setShowLabelAsDataCallout(true);
        lbl.getDataLabelFormat().setShowLeaderLines(true);
    }
    i++;
}
```

## Steg 4: Spara presentationen

Slutligen, spara presentationen med det konfigurerade diagrammet.

```java
pres.save("chart.pptx", SaveFormat.Pptx);
```

Nu har du framgångsrikt ställt in bildtexter för dataetiketter i ett diagram med Aspose.Slides för Java. Anpassa koden enligt dina specifika diagram och datakrav.

## Komplett källkod för inställning av bildtext för dataetikett i Java Slides

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "testc.pptx");
ISlide slide = pres.getSlides().get_Item(0);
IChart chart = slide.getShapes().addChart(ChartType.Doughnut, 10, 10, 500, 500, false);
IChartDataWorkbook workBook = chart.getChartData().getChartDataWorkbook();
chart.getChartData().getSeries().clear();
chart.getChartData().getCategories().clear();
chart.setLegend(false);
int seriesIndex = 0;
while (seriesIndex < 15)
{
	IChartSeries series = chart.getChartData().getSeries().add(workBook.getCell(0, 0, seriesIndex + 1, "SERIES " + seriesIndex), chart.getType());
	series.setExplosion(0);
	series.getParentSeriesGroup().setDoughnutHoleSize((byte) 20);
	series.getParentSeriesGroup().setFirstSliceAngle(351);
	seriesIndex++;
}
int categoryIndex = 0;
while (categoryIndex < 15)
{
	chart.getChartData().getCategories().add(workBook.getCell(0, categoryIndex + 1, 0, "CATEGORY " + categoryIndex));
	int i = 0;
	while (i < chart.getChartData().getSeries().size())
	{
		IChartSeries iCS = chart.getChartData().getSeries().get_Item(i);
		IChartDataPoint dataPoint = iCS.getDataPoints().addDataPointForDoughnutSeries(workBook.getCell(0, categoryIndex + 1, i + 1, 1));
		dataPoint.getFormat().getFill().setFillType(FillType.Solid);
		dataPoint.getFormat().getLine().getFillFormat().setFillType(FillType.Solid);
		dataPoint.getFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.WHITE);
		dataPoint.getFormat().getLine().setWidth(1);
		dataPoint.getFormat().getLine().setStyle(LineStyle.Single);
		dataPoint.getFormat().getLine().setDashStyle(LineDashStyle.Solid);
		if (i == chart.getChartData().getSeries().size() - 1)
		{
			IDataLabel lbl = dataPoint.getLabel();
			lbl.getTextFormat().getTextBlockFormat().setAutofitType(TextAutofitType.Shape);
			lbl.getDataLabelFormat().getTextFormat().getPortionFormat().setFontBold(NullableBool.True);
			lbl.getDataLabelFormat().getTextFormat().getPortionFormat().setLatinFont(new FontData("DINPro-Bold"));
			lbl.getDataLabelFormat().getTextFormat().getPortionFormat().setFontHeight(12);
			lbl.getDataLabelFormat().getTextFormat().getPortionFormat().getFillFormat().setFillType(FillType.Solid);
			lbl.getDataLabelFormat().getTextFormat().getPortionFormat().getFillFormat().getSolidFillColor().setColor(Color.LIGHT_GRAY);
			lbl.getDataLabelFormat().getFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.WHITE);
			lbl.getDataLabelFormat().setShowValue(false);
			lbl.getDataLabelFormat().setShowCategoryName(true);
			lbl.getDataLabelFormat().setShowSeriesName(false);
			//lbl.getDataLabelFormat().setShowLabelAsDataCallout(true);
			lbl.getDataLabelFormat().setShowLeaderLines(true);
			lbl.getDataLabelFormat().setShowLabelAsDataCallout(false);
			chart.validateChartLayout();
			lbl.setX(lbl.getX() + (float) 0.5);
			lbl.setY(lbl.getY() + (float) 0.5);
		}
		i++;
	}
	categoryIndex++;
}
pres.save("chart.pptx", SaveFormat.Pptx);
```

## Slutsats

den här handledningen har vi utforskat hur man ställer in bildtexter för dataetiketter i ett diagram med Aspose.Slides för Java. Bildtexter är värdefulla verktyg för att betona specifika datapunkter i dina diagram och presentationer. Vi har tillhandahållit en steg-för-steg-guide tillsammans med källkod för att hjälpa dig uppnå denna anpassning.

## FAQ's

### Hur anpassar jag utseendet på dataetiketter?

För att anpassa utseendet på dataetiketter kan du ändra egenskaper som typsnitt, fyllning och linjestilar. Till exempel:

```java
IDataLabel lbl = dataPoint.getLabel();
lbl.getTextFormat().getTextBlockFormat().setAutofitType(TextAutofitType.Shape);
lbl.getDataLabelFormat().getTextFormat().getPortionFormat().setFontBold(NullableBool.True);
lbl.getDataLabelFormat().getTextFormat().getPortionFormat().setLatinFont(new FontData("DINPro-Bold"));
lbl.getDataLabelFormat().getTextFormat().getPortionFormat().setFontHeight(12);
lbl.getDataLabelFormat().getTextFormat().getPortionFormat().getFillFormat().setFillType(FillType.Solid);
lbl.getDataLabelFormat().getTextFormat().getPortionFormat().getFillFormat().getSolidFillColor().setColor(Color.LIGHT_GRAY);
lbl.getDataLabelFormat().getFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.WHITE);
```

### Hur kan jag aktivera eller inaktivera bildtexter för dataetiketter?

 För att aktivera eller inaktivera bildtexter för dataetiketter, använd`setShowLabelAsDataCallout` metod. Ställ in den på`true` för att aktivera bildtexter och`false` för att inaktivera dem.

```java
lbl.getDataLabelFormat().setShowLabelAsDataCallout(true); // Aktivera länktexter
lbl.getDataLabelFormat().setShowLabelAsDataCallout(false); // Inaktivera länktexter
```

### Kan jag anpassa ledarlinjerna för dataetiketter?

Ja, du kan anpassa ledarlinjerna för dataetiketter med hjälp av egenskaper som linjestil, färg och bredd. Till exempel:

```java
lbl.getDataLabelFormat().setShowLeaderLines(true); // Aktivera ledarlinjer
lbl.getDataLabelFormat().getLeaderLinesFormat().getFormat().getLine().setStyle(LineStyle.Single);
lbl.getDataLabelFormat().getLeaderLinesFormat().getFormat().getLine().setWidth(1);
lbl.getDataLabelFormat().getLeaderLinesFormat().getFormat().getLine().getFillFormat().setFillType(FillType.Solid);
lbl.getDataLabelFormat().getLeaderLinesFormat().getFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.BLACK);
```

Det här är några vanliga anpassningsalternativ för dataetiketter och bildtexter i Aspose.Slides för Java. Du kan skräddarsy utseendet ytterligare efter dina specifika behov.