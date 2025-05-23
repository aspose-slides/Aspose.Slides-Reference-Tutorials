---
"description": "Lär dig lägga till ringformulär i Java Slides med Aspose.Slides för Java. Steg-för-steg-guide med källkod för förbättrade presentationer."
"linktitle": "Lägg till ringformulär i Java Slides"
"second_title": "Aspose.Slides Java PowerPoint-bearbetnings-API"
"title": "Lägg till ringformulär i Java Slides"
"url": "/sv/java/chart-data-manipulation/add-doughnut-callout-java-slides/"
"weight": 12
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Lägg till ringformulär i Java Slides


## Introduktion till att lägga till en ringformad callout i Java Slides med Aspose.Slides för Java

I den här handledningen går vi igenom processen för att lägga till en Doughnut Callout till en bild i Java med hjälp av Aspose.Slides för Java. En Doughnut Callout är ett diagramelement som kan användas för att markera specifika datapunkter i ett Doughnut-diagram. Vi kommer att förse dig med steg-för-steg-instruktioner och fullständig källkod för din bekvämlighet.

## Förkunskapskrav

Innan du börjar, se till att du har följande förutsättningar på plats:

1. Java-utvecklingsmiljö
2. Aspose.Slides för Java-biblioteket
3. Integrerad utvecklingsmiljö (IDE) som Eclipse eller IntelliJ IDEA
4. En PowerPoint-presentation där du vill lägga till ringtexten

## Steg 1: Konfigurera ditt Java-projekt

1. Skapa ett nytt Java-projekt i din valda IDE.
2. Lägg till Aspose.Slides för Java-biblioteket i ditt projekt som ett beroende.

## Steg 2: Initiera presentationen

För att komma igång måste du initiera en PowerPoint-presentation och skapa en bild där du vill lägga till ringformuläret. Här är koden för att uppnå detta:

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "testc.pptx");
ISlide slide = pres.getSlides().get_Item(0);
```

Se till att byta ut `"Your Document Directory"` med den faktiska sökvägen till din PowerPoint-presentationsfil.

## Steg 3: Skapa ett ringdiagram

Nästa steg är att skapa ett ringdiagram på bilden. Du kan anpassa diagrammets position och storlek efter dina behov. Här är koden för att lägga till ett ringdiagram:

```java
IChart chart = slide.getShapes().addChart(ChartType.Doughnut, 10, 10, 500, 500, false);
```

## Steg 4: Anpassa ringdiagrammet

Nu är det dags att anpassa ringdiagrammet. Vi kommer att ställa in olika egenskaper, som att ta bort förklaringen, konfigurera hålstorleken och justera den första skivans vinkel. Här är koden:

```java
IChartDataWorkbook workBook = chart.getChartData().getChartDataWorkbook();
chart.getChartData().getSeries().clear();
chart.getChartData().getCategories().clear();
chart.setLegend(false);
int seriesIndex = 0;
while (seriesIndex < 15) {
    IChartSeries series = chart.getChartData().getSeries().add(workBook.getCell(0, 0, seriesIndex + 1, "SERIES " + seriesIndex), chart.getType());
    series.setExplosion(0);
    series.getParentSeriesGroup().setDoughnutHoleSize((byte) 20);
    series.getParentSeriesGroup().setFirstSliceAngle(351);
    seriesIndex++;
}
```

Det här kodavsnittet anger egenskaperna för ringdiagrammet. Du kan justera värdena efter dina specifika behov.

## Steg 5: Lägg till data i ringdiagrammet

Nu ska vi lägga till data i ringdiagrammet. Vi kommer också att anpassa datapunkternas utseende. Här är koden för att åstadkomma detta:

```java
int categoryIndex = 0;
while (categoryIndex < 15) {
    chart.getChartData().getCategories().add(workBook.getCell(0, categoryIndex + 1, 0, "CATEGORY " + categoryIndex));
    int i = 0;
    while (i < chart.getChartData().getSeries().size()) {
        IChartSeries iCS = chart.getChartData().getSeries().get_Item(i);
        IChartDataPoint dataPoint = iCS.getDataPoints().addDataPointForDoughnutSeries(workBook.getCell(0, categoryIndex + 1, i + 1, 1));
        dataPoint.getFormat().getFill().setFillType(FillType.Solid);
        // Anpassa datapunktens utseende här
        i++;
    }
    categoryIndex++;
}
```

I den här koden lägger vi till kategorier och datapunkter i ringdiagrammet. Du kan ytterligare anpassa utseendet på datapunkterna efter behov.

## Steg 6: Spara presentationen

Slutligen, glöm inte att spara din presentation efter att du har lagt till Doughnut Callout. Här är koden för att spara presentationen:

```java
pres.save(dataDir + "chart.pptx", SaveFormat.Pptx);
```

Se till att byta ut `"chart.pptx"` med ditt önskade filnamn.

Grattis! Du har lagt till en ringdiagram-callout till en Java-bild med hjälp av Aspose.Slides för Java. Du kan nu köra ditt Java-program för att generera PowerPoint-presentationen med ringdiagrammet och callouten.

## Komplett källkod för Lägg till munk-callout i Java Slides

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
pres.save(dataDir + "chart.pptx", SaveFormat.Pptx);
```

## Slutsats

I den här handledningen har vi gått igenom processen att lägga till en ringdiagram-callout till en Java-bild med hjälp av Aspose.Slides för Java. Du har lärt dig hur du skapar ett ringdiagram, anpassar dess utseende och lägger till datapunkter. Känn dig fri att ytterligare förbättra dina presentationer med detta kraftfulla bibliotek och utforska fler diagramalternativ.

## Vanliga frågor

### Hur kan jag ändra utseendet på munkbilden?

Du kan anpassa utseendet på ringformuläret genom att ändra egenskaperna för datapunkterna i diagrammet. I den medföljande koden kan du se hur du ställer in fyllningsfärg, linjefärg, teckensnitt och andra attribut för datapunkter.

### Kan jag lägga till fler datapunkter i ringdiagrammet?

Ja, du kan lägga till så många datapunkter som behövs i ringdiagrammet. Förläng helt enkelt looparna i koden där kategorier och datapunkter läggs till och ange lämplig data och formatering.

### Hur kan jag justera positionen och storleken på ringdiagrammet på bilden?

Du kan ändra position och storlek på ringdiagrammet genom att modifiera parametrarna i `addChart` metod. De fyra siffrorna i den metoden motsvarar X- och Y-koordinaterna för diagrammets övre vänstra hörn respektive dess bredd och höjd.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}