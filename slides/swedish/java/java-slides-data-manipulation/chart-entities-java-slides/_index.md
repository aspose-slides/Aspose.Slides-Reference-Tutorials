---
"description": "Lär dig skapa och anpassa Java Slides-diagram med Aspose.Slides. Förbättra dina presentationer med kraftfulla diagramenheter."
"linktitle": "Diagramenheter i Java Slides"
"second_title": "Aspose.Slides Java PowerPoint-bearbetnings-API"
"title": "Diagramenheter i Java Slides"
"url": "/sv/java/data-manipulation/chart-entities-java-slides/"
"weight": 13
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Diagramenheter i Java Slides


## Introduktion till diagramenheter i Java Slides

Diagram är kraftfulla verktyg för att visualisera data i presentationer. Oavsett om du skapar affärsrapporter, akademiska presentationer eller någon annan form av innehåll, hjälper diagram till att förmedla information effektivt. Aspose.Slides för Java erbjuder robusta funktioner för att arbeta med diagram, vilket gör det till ett självklart val för Java-utvecklare.

## Förkunskapskrav

Innan vi dyker in i diagramenheternas värld, se till att du har följande förutsättningar på plats:

- Java Development Kit (JDK) installerat
- Aspose.Slides för Java-biblioteket har laddats ner och lagts till i ditt projekt
- Grundläggande kunskaper i Java-programmering

Nu ska vi börja med att skapa och anpassa diagram med Aspose.Slides för Java.

## Steg 1: Skapa en presentation

Det första steget är att skapa en ny presentation där du lägger till ditt diagram. Här är ett kodavsnitt för att skapa en presentation:

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
```

## Steg 2: Lägga till ett diagram

När du har din presentation klar är det dags att lägga till ett diagram. I det här exemplet lägger vi till ett enkelt linjediagram med markörer. Så här gör du:

```java
// Åtkomst till den första bilden
ISlide slide = pres.getSlides().get_Item(0);

// Lägga till exempeldiagrammet
IChart chart = slide.getShapes().addChart(ChartType.LineWithMarkers, 50, 50, 500, 400);
```

## Steg 3: Anpassa diagramtitel

Ett väldefinierat diagram bör ha en titel. Låt oss ange en titel för vårt diagram:

```java
// Titel på inställningstabell
chart.setTitle(true);
chart.getChartTitle().addTextFrameForOverriding("");
IPortion chartTitle = chart.getChartTitle().getTextFrameForOverriding().getParagraphs().get_Item(0).getPortions().get_Item(0);
chartTitle.setText("Sample Chart");
```

## Steg 4: Formatera rutnät

Du kan formatera de större och mindre rutnätslinjerna i ditt diagram. Nu ställer vi in lite formatering för rutnätslinjerna på den vertikala axeln:

```java
// Ställa in format för huvudrutnät för värdeaxel
chart.getAxes().getVerticalAxis().getMajorGridLinesFormat().getLine().getFillFormat().setFillType(FillType.Solid);
chart.getAxes().getVerticalAxis().getMajorGridLinesFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.BLUE);
chart.getAxes().getVerticalAxis().getMajorGridLinesFormat().getLine().setWidth(5);
chart.getAxes().getVerticalAxis().getMajorGridLinesFormat().getLine().setDashStyle(LineDashStyle.DashDot);

// Ställa in format för mindre rutnät för värdeaxel
chart.getAxes().getVerticalAxis().getMinorGridLinesFormat().getLine().getFillFormat().setFillType(FillType.Solid);
chart.getAxes().getVerticalAxis().getMinorGridLinesFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.RED);
chart.getAxes().getVerticalAxis().getMinorGridLinesFormat().getLine().setWidth(3);
```

## Steg 5: Anpassa värdeaxeln

Du har kontroll över talformatet, max- och minimivärdena för värdeaxeln. Så här anpassar du det:

```java
// Inställning av värdeaxelns talformat
chart.getAxes().getVerticalAxis().setNumberFormatLinkedToSource(false);
chart.getAxes().getVerticalAxis().setDisplayUnit(DisplayUnitType.Thousands);
chart.getAxes().getVerticalAxis().setNumberFormat("0.0%");

// Maximala och minimala värden i spridningstabellen
chart.getAxes().getVerticalAxis().setAutomaticMajorUnit(false);
chart.getAxes().getVerticalAxis().setAutomaticMaxValue(false);
chart.getAxes().getVerticalAxis().setAutomaticMinorUnit(false);
chart.getAxes().getVerticalAxis().setAutomaticMinValue(false);
chart.getAxes().getVerticalAxis().setMaxValue(15f);
chart.getAxes().getVerticalAxis().setMinValue(-2f);
chart.getAxes().getVerticalAxis().setMinorUnit(0.5f);
chart.getAxes().getVerticalAxis().setMajorUnit(2.0f);
```

## Steg 6: Axeltitel för att lägga till värde

För att göra ditt diagram mer informativt kan du lägga till en titel på värdeaxeln:

```java
// Inställning av värdeaxeltitel
chart.getAxes().getVerticalAxis().setTitle(true);
chart.getAxes().getVerticalAxis().getTitle().addTextFrameForOverriding("");
IPortion valtitle = chart.getAxes().getVerticalAxis().getTitle().getTextFrameForOverriding().getParagraphs().get_Item(0).getPortions().get_Item(0);
valtitle.setText("Primary Axis");
```

## Steg 7: Formatera kategoriaxeln

Kategoriaxeln, som vanligtvis representerar datakategorier, kan också anpassas:

```java
// Ställa in format för huvudrutnät för kategoriaxel
chart.getAxes().getHorizontalAxis().getMajorGridLinesFormat().getLine().getFillFormat().setFillType(FillType.Solid);
chart.getAxes().getHorizontalAxis().getMajorGridLinesFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.GREEN);
chart.getAxes().getHorizontalAxis().getMajorGridLinesFormat().getLine().setWidth(5);

// Ställa in format för mindre rutnät för kategoriaxel
chart.getAxes().getHorizontalAxis().getMinorGridLinesFormat().getLine().getFillFormat().setFillType(FillType.Solid);
chart.getAxes().getHorizontalAxis().getMinorGridLinesFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.YELLOW);
chart.getAxes().getHorizontalAxis().getMinorGridLinesFormat().getLine().setWidth(3);
```

## Steg 8: Lägga till förklaringar

Förklaringar hjälper till att förklara dataserierna i ditt diagram. Nu ska vi anpassa förklaringarna:

```java
// Ställa in egenskaper för förklaringar
IChartPortionFormat txtleg = chart.getLegend().getTextFormat().getPortionFormat();
txtleg.setFontBold(NullableBool.True);
txtleg.setFontHeight(16);
txtleg.setFontItalic(NullableBool.True);
txtleg.getFillFormat().setFillType(FillType.Solid);
txtleg.getFillFormat().getSolidFillColor().setColor(Color.RED);

// Ställ in att visa diagramförklaringar utan överlappande diagram
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
// Instansierar presentation // Instansierar presentation
Presentation pres = new Presentation();
try
{
	// Åtkomst till den första bilden
	ISlide slide = pres.getSlides().get_Item(0);
	// Lägga till exempeldiagrammet
	IChart chart = slide.getShapes().addChart(ChartType.LineWithMarkers, 50, 50, 500, 400);
	// Titel på inställningstabell
	chart.setTitle(true);
	chart.getChartTitle().addTextFrameForOverriding("");
	IPortion chartTitle = chart.getChartTitle().getTextFrameForOverriding().getParagraphs().get_Item(0).getPortions().get_Item(0);
	chartTitle.setText("Sample Chart");
	chartTitle.getPortionFormat().getFillFormat().setFillType(FillType.Solid);
	chartTitle.getPortionFormat().getFillFormat().getSolidFillColor().setColor(Color.GRAY);
	chartTitle.getPortionFormat().setFontHeight(20);
	chartTitle.getPortionFormat().setFontBold(NullableBool.True);
	chartTitle.getPortionFormat().setFontItalic(NullableBool.True);
	// Ställa in format för huvudrutnät för värdeaxel
	chart.getAxes().getVerticalAxis().getMajorGridLinesFormat().getLine().getFillFormat().setFillType(FillType.Solid);
	chart.getAxes().getVerticalAxis().getMajorGridLinesFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.BLUE);
	chart.getAxes().getVerticalAxis().getMajorGridLinesFormat().getLine().setWidth(5);
	chart.getAxes().getVerticalAxis().getMajorGridLinesFormat().getLine().setDashStyle(LineDashStyle.DashDot);
	// Ställa in format för mindre rutnät för värdeaxel
	chart.getAxes().getVerticalAxis().getMinorGridLinesFormat().getLine().getFillFormat().setFillType(FillType.Solid);
	chart.getAxes().getVerticalAxis().getMinorGridLinesFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.RED);
	chart.getAxes().getVerticalAxis().getMinorGridLinesFormat().getLine().setWidth(3);
	// Inställning av värdeaxelns talformat
	chart.getAxes().getVerticalAxis().setNumberFormatLinkedToSource(false);
	chart.getAxes().getVerticalAxis().setDisplayUnit(DisplayUnitType.Thousands);
	chart.getAxes().getVerticalAxis().setNumberFormat("0.0%");
	// Maximala och minimala värden i spridningstabellen
	chart.getAxes().getVerticalAxis().setAutomaticMajorUnit(false);
	chart.getAxes().getVerticalAxis().setAutomaticMaxValue(false);
	chart.getAxes().getVerticalAxis().setAutomaticMinorUnit(false);
	chart.getAxes().getVerticalAxis().setAutomaticMinValue(false);
	chart.getAxes().getVerticalAxis().setMaxValue(15f);
	chart.getAxes().getVerticalAxis().setMinValue(-2f);
	chart.getAxes().getVerticalAxis().setMinorUnit(0.5f);
	chart.getAxes().getVerticalAxis().setMajorUnit(2.0f);
	// Inställning av värdeaxeltextegenskaper
	IChartPortionFormat txtVal = chart.getAxes().getVerticalAxis().getTextFormat().getPortionFormat();
	txtVal.setFontBold(NullableBool.True);
	txtVal.setFontHeight(16);
	txtVal.setFontItalic(NullableBool.True);
	txtVal.getFillFormat().setFillType(FillType.Solid);
	txtVal.getFillFormat().getSolidFillColor().setColor(Color.GREEN);
	txtVal.setLatinFont(new FontData("Times New Roman"));
	// Inställning av värdeaxeltitel
	chart.getAxes().getVerticalAxis().setTitle(true);
	chart.getAxes().getVerticalAxis().getTitle().addTextFrameForOverriding("");
	IPortion valtitle = chart.getAxes().getVerticalAxis().getTitle().getTextFrameForOverriding().getParagraphs().get_Item(0).getPortions().get_Item(0);
	valtitle.setText("Primary Axis");
	valtitle.getPortionFormat().getFillFormat().setFillType(FillType.Solid);
	valtitle.getPortionFormat().getFillFormat().getSolidFillColor().setColor(Color.GRAY);
	valtitle.getPortionFormat().setFontHeight(20);
	valtitle.getPortionFormat().setFontBold(NullableBool.True);
	valtitle.getPortionFormat().setFontItalic(NullableBool.True);
	// Inställning av värdeaxellinjeformat: Nu föråldrad
	// chart.getAxes().getVerticalAxis().aVerticalAxis.l.AxisLine.setWidth(10);
	// chart.getAxes().getVerticalAxis().AxisLine.getFillFormat().setFillType(FillType.Solid);
	// Chart.getAxes().getVerticalAxis().AxisLine.getFillFormat().getSolidFillColor().Color = Color.Red;
	// Ställa in format för huvudrutnät för kategoriaxel
	chart.getAxes().getHorizontalAxis().getMajorGridLinesFormat().getLine().getFillFormat().setFillType(FillType.Solid);
	chart.getAxes().getHorizontalAxis().getMajorGridLinesFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.GREEN);
	chart.getAxes().getHorizontalAxis().getMajorGridLinesFormat().getLine().setWidth(5);
	// Ställa in format för mindre rutnät för kategoriaxel
	chart.getAxes().getHorizontalAxis().getMinorGridLinesFormat().getLine().getFillFormat().setFillType(FillType.Solid);
	chart.getAxes().getHorizontalAxis().getMinorGridLinesFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.YELLOW);
	chart.getAxes().getHorizontalAxis().getMinorGridLinesFormat().getLine().setWidth(3);
	// Ställa in textegenskaper för kategoriaxeln
	IChartPortionFormat txtCat = chart.getAxes().getHorizontalAxis().getTextFormat().getPortionFormat();
	txtCat.setFontBold(NullableBool.True);
	txtCat.setFontHeight(16);
	txtCat.setFontItalic(NullableBool.True);
	txtCat.getFillFormat().setFillType(FillType.Solid);
	txtCat.getFillFormat().getSolidFillColor().setColor(Color.BLUE);
	txtCat.setLatinFont(new FontData("Arial"));
	// Inställning av kategorititel
	chart.getAxes().getHorizontalAxis().setTitle(true);
	chart.getAxes().getHorizontalAxis().getTitle().addTextFrameForOverriding("");
	IPortion catTitle = chart.getAxes().getHorizontalAxis().getTitle().getTextFrameForOverriding().getParagraphs().get_Item(0).getPortions().get_Item(0);
	catTitle.setText("Sample Category");
	catTitle.getPortionFormat().getFillFormat().setFillType(FillType.Solid);
	catTitle.getPortionFormat().getFillFormat().getSolidFillColor().setColor(Color.GRAY);
	catTitle.getPortionFormat().setFontHeight(20);
	catTitle.getPortionFormat().setFontBold(NullableBool.True);
	catTitle.getPortionFormat().setFontItalic(NullableBool.True);
	// Ställa in kategoriaxelns etikettposition
	chart.getAxes().getHorizontalAxis().setTickLabelPosition(TickLabelPositionType.Low);
	// Inställning av kategoriaxeletikett rotationsvinkel
	chart.getAxes().getHorizontalAxis().setTickLabelRotationAngle(45);
	// Ställa in egenskaper för förklaringar
	IChartPortionFormat txtleg = chart.getLegend().getTextFormat().getPortionFormat();
	txtleg.setFontBold(NullableBool.True);
	txtleg.setFontHeight(16);
	txtleg.setFontItalic(NullableBool.True);
	txtleg.getFillFormat().setFillType(FillType.Solid);
	txtleg.getFillFormat().getSolidFillColor().setColor(Color.RED);
	// Ställ in att visa diagramförklaringar utan överlappande diagram
	chart.getLegend().setOverlay(true);
	// Rita första serien på sekundär värdeaxel
	// Diagram.getChartData().getSeries().get_Item(0).PlotOnSecondAxis = true;
	// Sättningstabell för bakväggsfärg
	chart.getBackWall().setThickness(1);
	chart.getBackWall().getFormat().getFill().setFillType(FillType.Solid);
	chart.getBackWall().getFormat().getFill().getSolidFillColor().setColor(Color.ORANGE);
	chart.getFloor().getFormat().getFill().setFillType(FillType.Solid);
	chart.getFloor().getFormat().getFill().getSolidFillColor().getColor();
	// Ställa in färgen på ritningsområdet
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

I den här artikeln har vi utforskat diagramenheternas värld i Java Slides med hjälp av Aspose.Slides för Java. Du har lärt dig hur du skapar, anpassar och manipulerar diagram för att förbättra dina presentationer. Diagram gör inte bara dina data visuellt tilltalande utan hjälper också din publik att förstå komplex information lättare.

## Vanliga frågor

### Hur ändrar jag diagramtypen?

För att ändra diagramtyp, använd `chart.setType()` metod och ange önskad diagramtyp.

### Kan jag lägga till flera dataserier i ett diagram?

Ja, du kan lägga till flera dataserier i ett diagram med hjälp av `chart.getChartData().getSeries().addSeries()` metod.

### Hur anpassar jag diagrammets färger?

Du kan anpassa diagramfärgerna genom att ställa in fyllningsformatet för olika diagramelement, till exempel rutnät, rubrik och förklaringar.

### Kan jag skapa 3D-diagram?

Ja, Aspose.Slides för Java stöder skapandet av 3D-diagram. Du kan ställa in `ChartType` till en 3D-diagramtyp för att skapa en.

### Är Aspose.Slides för Java kompatibelt med de senaste Java-versionerna?

Ja, Aspose.Slides för Java uppdateras regelbundet för att stödja de senaste Java-versionerna och ger kompatibilitet över en mängd olika Java-miljöer.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}