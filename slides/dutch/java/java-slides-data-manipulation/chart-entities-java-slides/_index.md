---
title: Grafiekentiteiten in Java-dia's
linktitle: Grafiekentiteiten in Java-dia's
second_title: Aspose.Slides Java PowerPoint-verwerkings-API
description: Leer Java Slides-diagrammen maken en aanpassen met Aspose.Slides. Verbeter uw presentaties met krachtige diagramentiteiten.
weight: 13
url: /nl/java/data-manipulation/chart-entities-java-slides/
---

{< blocks/products/pf/main-wrap-class >}
{< blocks/products/pf/main-container >}
{< blocks/products/pf/tutorial-page-section >}


## Inleiding tot grafiekentiteiten in Java-dia's

Grafieken zijn krachtige hulpmiddelen voor het visualiseren van gegevens in presentaties. Of u nu bedrijfsrapporten, academische presentaties of een andere vorm van inhoud maakt, grafieken helpen informatie effectief over te brengen. Aspose.Slides voor Java biedt robuuste functies voor het werken met diagrammen, waardoor het een favoriete keuze is voor Java-ontwikkelaars.

## Vereisten

Voordat we in de wereld van diagramentiteiten duiken, moet u ervoor zorgen dat u aan de volgende vereisten voldoet:

- Java Development Kit (JDK) geïnstalleerd
- Aspose.Slides voor Java-bibliotheek gedownload en toegevoegd aan uw project
- Basiskennis van Java-programmeren

Laten we nu aan de slag gaan met het maken en aanpassen van diagrammen met Aspose.Slides voor Java.

## Stap 1: Een presentatie maken

De eerste stap is het maken van een nieuwe presentatie waarin u uw diagram toevoegt. Hier is een codefragment om een presentatie te maken:

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
```

## Stap 2: Een diagram toevoegen

Zodra u uw presentatie gereed heeft, is het tijd om een diagram toe te voegen. In dit voorbeeld voegen we een eenvoudig lijndiagram met markeringen toe. Hier ziet u hoe u het kunt doen:

```java
// Toegang tot de eerste dia
ISlide slide = pres.getSlides().get_Item(0);

// Het voorbeelddiagram toevoegen
IChart chart = slide.getShapes().addChart(ChartType.LineWithMarkers, 50, 50, 500, 400);
```

## Stap 3: Grafiektitel aanpassen

Een goed gedefinieerd diagram moet een titel hebben. Laten we een titel voor ons diagram instellen:

```java
// Diagramtitel instellen
chart.setTitle(true);
chart.getChartTitle().addTextFrameForOverriding("");
IPortion chartTitle = chart.getChartTitle().getTextFrameForOverriding().getParagraphs().get_Item(0).getPortions().get_Item(0);
chartTitle.setText("Sample Chart");
```

## Stap 4: Rasterlijnen opmaken

U kunt de hoofd- en secundaire rasterlijnen van uw diagram opmaken. Laten we wat opmaak instellen voor de rasterlijnen van de verticale as:

```java
// Instelling van de hoofdrasterlijnenopmaak voor de waarde-as
chart.getAxes().getVerticalAxis().getMajorGridLinesFormat().getLine().getFillFormat().setFillType(FillType.Solid);
chart.getAxes().getVerticalAxis().getMajorGridLinesFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.BLUE);
chart.getAxes().getVerticalAxis().getMajorGridLinesFormat().getLine().setWidth(5);
chart.getAxes().getVerticalAxis().getMajorGridLinesFormat().getLine().setDashStyle(LineDashStyle.DashDot);

// Instelling van het formaat van secundaire rasterlijnen voor de waarde-as
chart.getAxes().getVerticalAxis().getMinorGridLinesFormat().getLine().getFillFormat().setFillType(FillType.Solid);
chart.getAxes().getVerticalAxis().getMinorGridLinesFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.RED);
chart.getAxes().getVerticalAxis().getMinorGridLinesFormat().getLine().setWidth(3);
```

## Stap 5: Waarde-as aanpassen

U hebt controle over de getalnotatie, de maximum- en minimumwaarden van de waarde-as. Ga als volgt te werk om het aan te passen:

```java
// Formaat waarde-asnummer instellen
chart.getAxes().getVerticalAxis().setNumberFormatLinkedToSource(false);
chart.getAxes().getVerticalAxis().setDisplayUnit(DisplayUnitType.Thousands);
chart.getAxes().getVerticalAxis().setNumberFormat("0.0%");

// Maximale en minimale waarden van de grafiek instellen
chart.getAxes().getVerticalAxis().setAutomaticMajorUnit(false);
chart.getAxes().getVerticalAxis().setAutomaticMaxValue(false);
chart.getAxes().getVerticalAxis().setAutomaticMinorUnit(false);
chart.getAxes().getVerticalAxis().setAutomaticMinValue(false);
chart.getAxes().getVerticalAxis().setMaxValue(15f);
chart.getAxes().getVerticalAxis().setMinValue(-2f);
chart.getAxes().getVerticalAxis().setMinorUnit(0.5f);
chart.getAxes().getVerticalAxis().setMajorUnit(2.0f);
```

## Stap 6: Waarde-astitel toevoegen

Om uw diagram informatiever te maken, kunt u een titel aan de waarde-as toevoegen:

```java
// Titel van waarde-as instellen
chart.getAxes().getVerticalAxis().setTitle(true);
chart.getAxes().getVerticalAxis().getTitle().addTextFrameForOverriding("");
IPortion valtitle = chart.getAxes().getVerticalAxis().getTitle().getTextFrameForOverriding().getParagraphs().get_Item(0).getPortions().get_Item(0);
valtitle.setText("Primary Axis");
```

## Stap 7: Categorie-as opmaken

De categorie-as, die doorgaans gegevenscategorieën vertegenwoordigt, kan ook worden aangepast:

```java
// Instelling van de hoofdrasterlijnenopmaak voor de Categorie-as
chart.getAxes().getHorizontalAxis().getMajorGridLinesFormat().getLine().getFillFormat().setFillType(FillType.Solid);
chart.getAxes().getHorizontalAxis().getMajorGridLinesFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.GREEN);
chart.getAxes().getHorizontalAxis().getMajorGridLinesFormat().getLine().setWidth(5);

// Instelling van de indeling van secundaire rasterlijnen voor de Categorie-as
chart.getAxes().getHorizontalAxis().getMinorGridLinesFormat().getLine().getFillFormat().setFillType(FillType.Solid);
chart.getAxes().getHorizontalAxis().getMinorGridLinesFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.YELLOW);
chart.getAxes().getHorizontalAxis().getMinorGridLinesFormat().getLine().setWidth(3);
```

## Stap 8: Legenda's toevoegen

Legenda's helpen bij het verklaren van de gegevensreeksen in uw diagram. Laten we de legenda's aanpassen:

```java
// Legenda-teksteigenschappen instellen
IChartPortionFormat txtleg = chart.getLegend().getTextFormat().getPortionFormat();
txtleg.setFontBold(NullableBool.True);
txtleg.setFontHeight(16);
txtleg.setFontItalic(NullableBool.True);
txtleg.getFillFormat().setFillType(FillType.Solid);
txtleg.getFillFormat().getSolidFillColor().setColor(Color.RED);

// Stel diagramlegenda's in zonder overlappende diagrammen
chart.getLegend().setOverlay(true);
```

## Stap 9: De presentatie opslaan

Sla ten slotte uw presentatie op met het diagram:

```java
pres.save(dataDir + "FormattedChart_out.pptx", SaveFormat.Pptx);
```

## Volledige broncode voor diagramentiteiten in Java-dia's

```java
// Het pad naar de documentenmap.
String dataDir = "Your Document Directory";
// Maak een directory aan als deze nog niet aanwezig is.
boolean IsExists = new File(dataDir).exists();
if (!IsExists)
	new File(dataDir).mkdirs();
// Presentatie instantiëren// Presentatie instantiëren
Presentation pres = new Presentation();
try
{
	// Toegang tot de eerste dia
	ISlide slide = pres.getSlides().get_Item(0);
	// Het voorbeelddiagram toevoegen
	IChart chart = slide.getShapes().addChart(ChartType.LineWithMarkers, 50, 50, 500, 400);
	// Diagramtitel instellen
	chart.setTitle(true);
	chart.getChartTitle().addTextFrameForOverriding("");
	IPortion chartTitle = chart.getChartTitle().getTextFrameForOverriding().getParagraphs().get_Item(0).getPortions().get_Item(0);
	chartTitle.setText("Sample Chart");
	chartTitle.getPortionFormat().getFillFormat().setFillType(FillType.Solid);
	chartTitle.getPortionFormat().getFillFormat().getSolidFillColor().setColor(Color.GRAY);
	chartTitle.getPortionFormat().setFontHeight(20);
	chartTitle.getPortionFormat().setFontBold(NullableBool.True);
	chartTitle.getPortionFormat().setFontItalic(NullableBool.True);
	// Instelling van de hoofdrasterlijnenopmaak voor de waarde-as
	chart.getAxes().getVerticalAxis().getMajorGridLinesFormat().getLine().getFillFormat().setFillType(FillType.Solid);
	chart.getAxes().getVerticalAxis().getMajorGridLinesFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.BLUE);
	chart.getAxes().getVerticalAxis().getMajorGridLinesFormat().getLine().setWidth(5);
	chart.getAxes().getVerticalAxis().getMajorGridLinesFormat().getLine().setDashStyle(LineDashStyle.DashDot);
	// Instelling van het formaat van secundaire rasterlijnen voor de waarde-as
	chart.getAxes().getVerticalAxis().getMinorGridLinesFormat().getLine().getFillFormat().setFillType(FillType.Solid);
	chart.getAxes().getVerticalAxis().getMinorGridLinesFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.RED);
	chart.getAxes().getVerticalAxis().getMinorGridLinesFormat().getLine().setWidth(3);
	// Formaat waarde-asnummer instellen
	chart.getAxes().getVerticalAxis().setNumberFormatLinkedToSource(false);
	chart.getAxes().getVerticalAxis().setDisplayUnit(DisplayUnitType.Thousands);
	chart.getAxes().getVerticalAxis().setNumberFormat("0.0%");
	// Maximale en minimale waarden van de grafiek instellen
	chart.getAxes().getVerticalAxis().setAutomaticMajorUnit(false);
	chart.getAxes().getVerticalAxis().setAutomaticMaxValue(false);
	chart.getAxes().getVerticalAxis().setAutomaticMinorUnit(false);
	chart.getAxes().getVerticalAxis().setAutomaticMinValue(false);
	chart.getAxes().getVerticalAxis().setMaxValue(15f);
	chart.getAxes().getVerticalAxis().setMinValue(-2f);
	chart.getAxes().getVerticalAxis().setMinorUnit(0.5f);
	chart.getAxes().getVerticalAxis().setMajorUnit(2.0f);
	// Teksteigenschappen van waarde-as instellen
	IChartPortionFormat txtVal = chart.getAxes().getVerticalAxis().getTextFormat().getPortionFormat();
	txtVal.setFontBold(NullableBool.True);
	txtVal.setFontHeight(16);
	txtVal.setFontItalic(NullableBool.True);
	txtVal.getFillFormat().setFillType(FillType.Solid);
	txtVal.getFillFormat().getSolidFillColor().setColor(Color.GREEN);
	txtVal.setLatinFont(new FontData("Times New Roman"));
	// Titel van waarde-as instellen
	chart.getAxes().getVerticalAxis().setTitle(true);
	chart.getAxes().getVerticalAxis().getTitle().addTextFrameForOverriding("");
	IPortion valtitle = chart.getAxes().getVerticalAxis().getTitle().getTextFrameForOverriding().getParagraphs().get_Item(0).getPortions().get_Item(0);
	valtitle.setText("Primary Axis");
	valtitle.getPortionFormat().getFillFormat().setFillType(FillType.Solid);
	valtitle.getPortionFormat().getFillFormat().getSolidFillColor().setColor(Color.GRAY);
	valtitle.getPortionFormat().setFontHeight(20);
	valtitle.getPortionFormat().setFontBold(NullableBool.True);
	valtitle.getPortionFormat().setFontItalic(NullableBool.True);
	// Waarde-aslijnformaat instellen: Nu Obselete
	// chart.getAxes().getVerticalAxis().aVerticalAxis.l.AxisLine.setWidth(10);
	// chart.getAxes().getVerticalAxis().AxisLine.getFillFormat().setFillType(FillType.Solid);
	// Chart.getAxes().getVerticalAxis().AxisLine.getFillFormat().getSolidFillColor().Color = Kleur.Rood;
	// Instelling van de hoofdrasterlijnenopmaak voor de Categorie-as
	chart.getAxes().getHorizontalAxis().getMajorGridLinesFormat().getLine().getFillFormat().setFillType(FillType.Solid);
	chart.getAxes().getHorizontalAxis().getMajorGridLinesFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.GREEN);
	chart.getAxes().getHorizontalAxis().getMajorGridLinesFormat().getLine().setWidth(5);
	// Instelling van de indeling van secundaire rasterlijnen voor de Categorie-as
	chart.getAxes().getHorizontalAxis().getMinorGridLinesFormat().getLine().getFillFormat().setFillType(FillType.Solid);
	chart.getAxes().getHorizontalAxis().getMinorGridLinesFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.YELLOW);
	chart.getAxes().getHorizontalAxis().getMinorGridLinesFormat().getLine().setWidth(3);
	// Teksteigenschappen voor categorie-as instellen
	IChartPortionFormat txtCat = chart.getAxes().getHorizontalAxis().getTextFormat().getPortionFormat();
	txtCat.setFontBold(NullableBool.True);
	txtCat.setFontHeight(16);
	txtCat.setFontItalic(NullableBool.True);
	txtCat.getFillFormat().setFillType(FillType.Solid);
	txtCat.getFillFormat().getSolidFillColor().setColor(Color.BLUE);
	txtCat.setLatinFont(new FontData("Arial"));
	// Categorietitel instellen
	chart.getAxes().getHorizontalAxis().setTitle(true);
	chart.getAxes().getHorizontalAxis().getTitle().addTextFrameForOverriding("");
	IPortion catTitle = chart.getAxes().getHorizontalAxis().getTitle().getTextFrameForOverriding().getParagraphs().get_Item(0).getPortions().get_Item(0);
	catTitle.setText("Sample Category");
	catTitle.getPortionFormat().getFillFormat().setFillType(FillType.Solid);
	catTitle.getPortionFormat().getFillFormat().getSolidFillColor().setColor(Color.GRAY);
	catTitle.getPortionFormat().setFontHeight(20);
	catTitle.getPortionFormat().setFontBold(NullableBool.True);
	catTitle.getPortionFormat().setFontItalic(NullableBool.True);
	// Instellen van de categorie-aslabelpositie
	chart.getAxes().getHorizontalAxis().setTickLabelPosition(TickLabelPositionType.Low);
	// Instelling van de rotatiehoek van het categorie-aslabel
	chart.getAxes().getHorizontalAxis().setTickLabelRotationAngle(45);
	// Legenda-teksteigenschappen instellen
	IChartPortionFormat txtleg = chart.getLegend().getTextFormat().getPortionFormat();
	txtleg.setFontBold(NullableBool.True);
	txtleg.setFontHeight(16);
	txtleg.setFontItalic(NullableBool.True);
	txtleg.getFillFormat().setFillType(FillType.Solid);
	txtleg.getFillFormat().getSolidFillColor().setColor(Color.RED);
	// Stel diagramlegenda's in zonder overlappende diagrammen
	chart.getLegend().setOverlay(true);
	// Eerste reeks uitzetten op de secundaire waarde-as
	// Chart.getChartData().getSeries().get_Item(0).PlotOnSecondAxis = waar;
	// Kleur van de achterwand van het diagram instellen
	chart.getBackWall().setThickness(1);
	chart.getBackWall().getFormat().getFill().setFillType(FillType.Solid);
	chart.getBackWall().getFormat().getFill().getSolidFillColor().setColor(Color.ORANGE);
	chart.getFloor().getFormat().getFill().setFillType(FillType.Solid);
	chart.getFloor().getFormat().getFill().getSolidFillColor().getColor();
	//Kleur van het plotgebied instellen
	chart.getPlotArea().getFormat().getFill().setFillType(FillType.Solid);
	chart.getPlotArea().getFormat().getFill().getSolidFillColor().setColor(new Color(PresetColor.LightCyan));
	// Presentatie opslaan
	pres.save(dataDir + "FormattedChart_out.pptx", SaveFormat.Pptx);
}
finally
{
	if (pres != null) pres.dispose();
}
```

## Conclusie

In dit artikel hebben we de wereld van diagramentiteiten in Java Slides verkend met behulp van Aspose.Slides voor Java. U hebt geleerd hoe u diagrammen kunt maken, aanpassen en manipuleren om uw presentaties te verbeteren. Grafieken maken uw gegevens niet alleen visueel aantrekkelijk, maar helpen uw publiek ook complexe informatie gemakkelijker te begrijpen.

## Veelgestelde vragen

### Hoe wijzig ik het diagramtype?

 Om het diagramtype te wijzigen, gebruikt u de`chart.setType()` methode en geef het gewenste diagramtype op.

### Kan ik meerdere gegevensreeksen aan een diagram toevoegen?

 Ja, u kunt meerdere gegevensreeksen aan een diagram toevoegen met behulp van de`chart.getChartData().getSeries().addSeries()` methode.

### Hoe pas ik de diagramkleuren aan?

U kunt de diagramkleuren aanpassen door het opvulformaat in te stellen voor verschillende diagramelementen, zoals rasterlijnen, titel en legenda's.

### Kan ik 3D-diagrammen maken?

 Ja, Aspose.Slides voor Java ondersteunt het maken van 3D-diagrammen. U kunt de`ChartType` naar een 3D-diagramtype om er een te maken.

### Is Aspose.Slides voor Java compatibel met de nieuwste Java-versies?

Ja, Aspose.Slides voor Java wordt regelmatig bijgewerkt om de nieuwste Java-versies te ondersteunen en biedt compatibiliteit met een breed scala aan Java-omgevingen.
{< /blocks/products/pf/tutorial-page-section >}

{< /blocks/products/pf/main-container >}
{< /blocks/products/pf/main-wrap-class >}

{< blocks/products/products-backtop-button >}
