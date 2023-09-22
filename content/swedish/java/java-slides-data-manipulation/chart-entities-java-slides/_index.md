---
title: Diagramenheter i Java Slides
linktitle: Diagramenheter i Java Slides
second_title: Aspose.Slides Java PowerPoint Processing API
description: Lär dig att skapa och anpassa Java Slides-diagram med Aspose.Slides. Förbättra dina presentationer med kraftfulla diagramenheter.
type: docs
weight: 13
url: /sv/java/data-manipulation/chart-entities-java-slides/
---

## Introduktion till diagramenheter i Java Slides

Diagram är kraftfulla verktyg för att visualisera data i presentationer. Oavsett om du skapar affärsrapporter, akademiska presentationer eller någon annan form av innehåll, hjälper diagram att förmedla information effektivt. Aspose.Slides för Java tillhandahåller robusta funktioner för att arbeta med diagram, vilket gör det till ett bra val för Java-utvecklare.

## Förutsättningar

Innan vi dyker in i världen av sjökortsenheter, se till att du har följande förutsättningar på plats:

- Java Development Kit (JDK) installerat
- Aspose.Slides för Java-biblioteket har laddats ner och lagts till i ditt projekt
- Grundläggande kunskaper i Java-programmering

Låt oss nu börja med att skapa och anpassa diagram med Aspose.Slides för Java.

## Steg 1: Skapa en presentation

Det första steget är att skapa en ny presentation där du lägger till ditt diagram. Här är ett kodavsnitt för att skapa en presentation:

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
```

## Steg 2: Lägga till ett diagram

När du har din presentation klar är det dags att lägga till ett diagram. I det här exemplet lägger vi till ett enkelt linjediagram med markörer. Så här kan du göra det:

```java
// Åtkomst till den första bilden
ISlide slide = pres.getSlides().get_Item(0);

//Lägger till exempeldiagrammet
IChart chart = slide.getShapes().addChart(ChartType.LineWithMarkers, 50, 50, 500, 400);
```

## Steg 3: Anpassa diagramtitel

Ett väldefinierat diagram bör ha en titel. Låt oss sätta en titel för vårt diagram:

```java
// Ställa in diagramtitel
chart.setTitle(true);
chart.getChartTitle().addTextFrameForOverriding("");
IPortion chartTitle = chart.getChartTitle().getTextFrameForOverriding().getParagraphs().get_Item(0).getPortions().get_Item(0);
chartTitle.setText("Sample Chart");
```

## Steg 4: Formatera rutnätslinjer

Du kan formatera de stora och mindre rutnätslinjerna i ditt diagram. Låt oss ställa in lite formatering för de vertikala axellinjerna:

```java
// Ställa in format för större rutnätslinjer för värdeaxeln
chart.getAxes().getVerticalAxis().getMajorGridLinesFormat().getLine().getFillFormat().setFillType(FillType.Solid);
chart.getAxes().getVerticalAxis().getMajorGridLinesFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.BLUE);
chart.getAxes().getVerticalAxis().getMajorGridLinesFormat().getLine().setWidth(5);
chart.getAxes().getVerticalAxis().getMajorGridLinesFormat().getLine().setDashStyle(LineDashStyle.DashDot);

// Ställa in format för mindre rutnätslinjer för värdeaxeln
chart.getAxes().getVerticalAxis().getMinorGridLinesFormat().getLine().getFillFormat().setFillType(FillType.Solid);
chart.getAxes().getVerticalAxis().getMinorGridLinesFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.RED);
chart.getAxes().getVerticalAxis().getMinorGridLinesFormat().getLine().setWidth(3);
```

## Steg 5: Anpassa värdeaxeln

Du har kontroll över talformatet, max- och minvärdena för värdeaxeln. Så här anpassar du det:

```java
// Inställningsvärdes axelnummerformat
chart.getAxes().getVerticalAxis().setNumberFormatLinkedToSource(false);
chart.getAxes().getVerticalAxis().setDisplayUnit(DisplayUnitType.Thousands);
chart.getAxes().getVerticalAxis().setNumberFormat("0.0%");

// Inställning av diagrammaximum, minimivärden
chart.getAxes().getVerticalAxis().setAutomaticMajorUnit(false);
chart.getAxes().getVerticalAxis().setAutomaticMaxValue(false);
chart.getAxes().getVerticalAxis().setAutomaticMinorUnit(false);
chart.getAxes().getVerticalAxis().setAutomaticMinValue(false);
chart.getAxes().getVerticalAxis().setMaxValue(15f);
chart.getAxes().getVerticalAxis().setMinValue(-2f);
chart.getAxes().getVerticalAxis().setMinorUnit(0.5f);
chart.getAxes().getVerticalAxis().setMajorUnit(2.0f);
```

## Steg 6: Lägga till värdeaxeltitel

För att göra ditt diagram mer informativt kan du lägga till en titel på värdeaxeln:

```java
// Inställningsvärdes axeltitel
chart.getAxes().getVerticalAxis().setTitle(true);
chart.getAxes().getVerticalAxis().getTitle().addTextFrameForOverriding("");
IPortion valtitle = chart.getAxes().getVerticalAxis().getTitle().getTextFrameForOverriding().getParagraphs().get_Item(0).getPortions().get_Item(0);
valtitle.setText("Primary Axis");
```

## Steg 7: Formatera kategoriaxel

Kategoriaxeln, som vanligtvis representerar datakategorier, kan också anpassas:

```java
// Ställa in format för huvudrutnätslinjer för kategoriaxel
chart.getAxes().getHorizontalAxis().getMajorGridLinesFormat().getLine().getFillFormat().setFillType(FillType.Solid);
chart.getAxes().getHorizontalAxis().getMajorGridLinesFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.GREEN);
chart.getAxes().getHorizontalAxis().getMajorGridLinesFormat().getLine().setWidth(5);

//Ställa in format för mindre rutnätslinjer för kategoriaxel
chart.getAxes().getHorizontalAxis().getMinorGridLinesFormat().getLine().getFillFormat().setFillType(FillType.Solid);
chart.getAxes().getHorizontalAxis().getMinorGridLinesFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.YELLOW);
chart.getAxes().getHorizontalAxis().getMinorGridLinesFormat().getLine().setWidth(3);
```

## Steg 8: Lägga till legender

Förklaringar hjälper till att förklara dataserien i ditt diagram. Låt oss anpassa legenderna:

```java
// Ställa in teckentextegenskaper
IChartPortionFormat txtleg = chart.getLegend().getTextFormat().getPortionFormat();
txtleg.setFontBold(NullableBool.True);
txtleg.setFontHeight(16);
txtleg.setFontItalic(NullableBool.True);
txtleg.getFillFormat().setFillType(FillType.Solid);
txtleg.getFillFormat().getSolidFillColor().setColor(Color.RED);

// Ställ in visa diagramförklaringar utan överlappande diagram
chart.getLegend().setOverlay(true);
```

## Steg 9: Spara presentationen

Slutligen, spara din presentation med diagrammet:

```java
pres.save(dataDir + "FormattedChart_out.pptx", SaveFormat.Pptx);
```

## Komplett källkod för diagramenheter i Java Slides

```java
// Sökvägen till dokumentkatalogen.
String dataDir = "Your Document Directory";
// Skapa katalog om den inte redan finns.
boolean IsExists = new File(dataDir).exists();
if (!IsExists)
	new File(dataDir).mkdirs();
// Instantiating presentation// Instantiating presentation
Presentation pres = new Presentation();
try
{
	// Åtkomst till den första bilden
	ISlide slide = pres.getSlides().get_Item(0);
	//Lägger till exempeldiagrammet
	IChart chart = slide.getShapes().addChart(ChartType.LineWithMarkers, 50, 50, 500, 400);
	// Ställa in diagramtitel
	chart.setTitle(true);
	chart.getChartTitle().addTextFrameForOverriding("");
	IPortion chartTitle = chart.getChartTitle().getTextFrameForOverriding().getParagraphs().get_Item(0).getPortions().get_Item(0);
	chartTitle.setText("Sample Chart");
	chartTitle.getPortionFormat().getFillFormat().setFillType(FillType.Solid);
	chartTitle.getPortionFormat().getFillFormat().getSolidFillColor().setColor(Color.GRAY);
	chartTitle.getPortionFormat().setFontHeight(20);
	chartTitle.getPortionFormat().setFontBold(NullableBool.True);
	chartTitle.getPortionFormat().setFontItalic(NullableBool.True);
	// Ställa in format för större rutnätslinjer för värdeaxeln
	chart.getAxes().getVerticalAxis().getMajorGridLinesFormat().getLine().getFillFormat().setFillType(FillType.Solid);
	chart.getAxes().getVerticalAxis().getMajorGridLinesFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.BLUE);
	chart.getAxes().getVerticalAxis().getMajorGridLinesFormat().getLine().setWidth(5);
	chart.getAxes().getVerticalAxis().getMajorGridLinesFormat().getLine().setDashStyle(LineDashStyle.DashDot);
	// Ställa in format för mindre rutnätslinjer för värdeaxeln
	chart.getAxes().getVerticalAxis().getMinorGridLinesFormat().getLine().getFillFormat().setFillType(FillType.Solid);
	chart.getAxes().getVerticalAxis().getMinorGridLinesFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.RED);
	chart.getAxes().getVerticalAxis().getMinorGridLinesFormat().getLine().setWidth(3);
	// Inställningsvärdes axelnummerformat
	chart.getAxes().getVerticalAxis().setNumberFormatLinkedToSource(false);
	chart.getAxes().getVerticalAxis().setDisplayUnit(DisplayUnitType.Thousands);
	chart.getAxes().getVerticalAxis().setNumberFormat("0.0%");
	// Inställning av diagrammaximum, minimivärden
	chart.getAxes().getVerticalAxis().setAutomaticMajorUnit(false);
	chart.getAxes().getVerticalAxis().setAutomaticMaxValue(false);
	chart.getAxes().getVerticalAxis().setAutomaticMinorUnit(false);
	chart.getAxes().getVerticalAxis().setAutomaticMinValue(false);
	chart.getAxes().getVerticalAxis().setMaxValue(15f);
	chart.getAxes().getVerticalAxis().setMinValue(-2f);
	chart.getAxes().getVerticalAxis().setMinorUnit(0.5f);
	chart.getAxes().getVerticalAxis().setMajorUnit(2.0f);
	// Ställa in värdeaxeltextegenskaper
	IChartPortionFormat txtVal = chart.getAxes().getVerticalAxis().getTextFormat().getPortionFormat();
	txtVal.setFontBold(NullableBool.True);
	txtVal.setFontHeight(16);
	txtVal.setFontItalic(NullableBool.True);
	txtVal.getFillFormat().setFillType(FillType.Solid);
	txtVal.getFillFormat().getSolidFillColor().setColor(Color.GREEN);
	txtVal.setLatinFont(new FontData("Times New Roman"));
	// Inställningsvärdes axeltitel
	chart.getAxes().getVerticalAxis().setTitle(true);
	chart.getAxes().getVerticalAxis().getTitle().addTextFrameForOverriding("");
	IPortion valtitle = chart.getAxes().getVerticalAxis().getTitle().getTextFrameForOverriding().getParagraphs().get_Item(0).getPortions().get_Item(0);
	valtitle.setText("Primary Axis");
	valtitle.getPortionFormat().getFillFormat().setFillType(FillType.Solid);
	valtitle.getPortionFormat().getFillFormat().getSolidFillColor().setColor(Color.GRAY);
	valtitle.getPortionFormat().setFontHeight(20);
	valtitle.getPortionFormat().setFontBold(NullableBool.True);
	valtitle.getPortionFormat().setFontItalic(NullableBool.True);
	// Inställningsvärde axellinjeformat: Nu föråldrad
	// chart.getAxes().getVerticalAxis().aVerticalAxis.l.AxisLine.setWidth(10);
	// chart.getAxes().getVerticalAxis().AxisLine.getFillFormat().setFillType(FillType.Solid);
	// Chart.getAxes().getVerticalAxis().AxisLine.getFillFormat().getSolidFillColor().Color = Color.Red;
	// Ställa in format för huvudrutnätslinjer för kategoriaxel
	chart.getAxes().getHorizontalAxis().getMajorGridLinesFormat().getLine().getFillFormat().setFillType(FillType.Solid);
	chart.getAxes().getHorizontalAxis().getMajorGridLinesFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.GREEN);
	chart.getAxes().getHorizontalAxis().getMajorGridLinesFormat().getLine().setWidth(5);
	//Ställa in format för mindre rutnätslinjer för kategoriaxel
	chart.getAxes().getHorizontalAxis().getMinorGridLinesFormat().getLine().getFillFormat().setFillType(FillType.Solid);
	chart.getAxes().getHorizontalAxis().getMinorGridLinesFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.YELLOW);
	chart.getAxes().getHorizontalAxis().getMinorGridLinesFormat().getLine().setWidth(3);
	// Ställa in textegenskaper för kategoriaxel
	IChartPortionFormat txtCat = chart.getAxes().getHorizontalAxis().getTextFormat().getPortionFormat();
	txtCat.setFontBold(NullableBool.True);
	txtCat.setFontHeight(16);
	txtCat.setFontItalic(NullableBool.True);
	txtCat.getFillFormat().setFillType(FillType.Solid);
	txtCat.getFillFormat().getSolidFillColor().setColor(Color.BLUE);
	txtCat.setLatinFont(new FontData("Arial"));
	// Ställa in kategorititel
	chart.getAxes().getHorizontalAxis().setTitle(true);
	chart.getAxes().getHorizontalAxis().getTitle().addTextFrameForOverriding("");
	IPortion catTitle = chart.getAxes().getHorizontalAxis().getTitle().getTextFrameForOverriding().getParagraphs().get_Item(0).getPortions().get_Item(0);
	catTitle.setText("Sample Category");
	catTitle.getPortionFormat().getFillFormat().setFillType(FillType.Solid);
	catTitle.getPortionFormat().getFillFormat().getSolidFillColor().setColor(Color.GRAY);
	catTitle.getPortionFormat().setFontHeight(20);
	catTitle.getPortionFormat().setFontBold(NullableBool.True);
	catTitle.getPortionFormat().setFontItalic(NullableBool.True);
	// Ställa in kategoriaxellabelposition
	chart.getAxes().getHorizontalAxis().setTickLabelPosition(TickLabelPositionType.Low);
	// Inställning av kategoriaxellabel rotationsvinkel
	chart.getAxes().getHorizontalAxis().setTickLabelRotationAngle(45);
	// Ställa in teckentextegenskaper
	IChartPortionFormat txtleg = chart.getLegend().getTextFormat().getPortionFormat();
	txtleg.setFontBold(NullableBool.True);
	txtleg.setFontHeight(16);
	txtleg.setFontItalic(NullableBool.True);
	txtleg.getFillFormat().setFillType(FillType.Solid);
	txtleg.getFillFormat().getSolidFillColor().setColor(Color.RED);
	// Ställ in visa diagramförklaringar utan överlappande diagram
	chart.getLegend().setOverlay(true);
	// Plotta första serien på sekundär värdeaxel
	//Chart.getChartData().getSeries().get_Item(0).PlotOnSecondAxis = true;
	// Inställningsdiagram bakväggfärg
	chart.getBackWall().setThickness(1);
	chart.getBackWall().getFormat().getFill().setFillType(FillType.Solid);
	chart.getBackWall().getFormat().getFill().getSolidFillColor().setColor(Color.ORANGE);
	chart.getFloor().getFormat().getFill().setFillType(FillType.Solid);
	chart.getFloor().getFormat().getFill().getSolidFillColor().getColor();
	// Ställa in färg för plottyta
	chart.getPlotArea().getFormat().getFill().setFillType(FillType.Solid);
	chart.getPlotArea().getFormat().getFill().getSolidFillColor().setColor(new Color(PresetColor.LightCyan));
	// Spara presentation
	pres.save(dataDir + "FormattedChart_out.pptx", SaveFormat.Pptx);
}
finally
{
	if (pres != null) pres.dispose();
}
```

## Slutsats

I den här artikeln har vi utforskat världen av diagramenheter i Java Slides med Aspose.Slides för Java. Du har lärt dig hur du skapar, anpassar och manipulerar diagram för att förbättra dina presentationer. Diagram gör inte bara dina data visuellt tilltalande utan hjälper också din publik att förstå komplex information lättare.

## FAQ's

### Hur ändrar jag diagramtypen?

 För att ändra diagramtypen, använd`chart.setType()` metod och ange önskad diagramtyp.

### Kan jag lägga till flera dataserier i ett diagram?

 Ja, du kan lägga till flera dataserier till ett diagram med hjälp av`chart.getChartData().getSeries().addSeries()` metod.

### Hur anpassar jag diagramfärgerna?

Du kan anpassa diagramfärgerna genom att ställa in fyllningsformatet för olika diagramelement, som rutnätslinjer, titel och förklaringar.

### Kan jag skapa 3D-diagram?

 Ja, Aspose.Slides för Java stöder skapandet av 3D-diagram. Du kan ställa in`ChartType` till en 3D-diagramtyp för att skapa en.

### Är Aspose.Slides för Java kompatibel med de senaste Java-versionerna?

Ja, Aspose.Slides för Java uppdateras regelbundet för att stödja de senaste Java-versionerna och ger kompatibilitet över ett brett utbud av Java-miljöer.