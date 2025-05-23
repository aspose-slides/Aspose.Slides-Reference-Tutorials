---
"description": "Leer hoe u Java Slides-grafieken kunt maken en aanpassen met Aspose.Slides. Verbeter uw presentaties met krachtige diagramentiteiten."
"linktitle": "Grafiekentiteiten in Java-dia's"
"second_title": "Aspose.Slides Java PowerPoint-verwerkings-API"
"title": "Grafiekentiteiten in Java-dia's"
"url": "/nl/java/data-manipulation/chart-entities-java-slides/"
"weight": 13
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Grafiekentiteiten in Java-dia's


## Inleiding tot diagramentiteiten in Java-dia's

Grafieken zijn krachtige tools voor het visualiseren van gegevens in presentaties. Of u nu bedrijfsrapporten, academische presentaties of andere content maakt, grafieken helpen om informatie effectief over te brengen. Aspose.Slides voor Java biedt robuuste functies voor het werken met grafieken, waardoor het een ideale keuze is voor Java-ontwikkelaars.

## Vereisten

Voordat we in de wereld van grafiekentiteiten duiken, moet u ervoor zorgen dat u aan de volgende vereisten voldoet:

- Java Development Kit (JDK) geïnstalleerd
- Aspose.Slides voor Java-bibliotheek gedownload en toegevoegd aan uw project
- Basiskennis van Java-programmering

Laten we nu beginnen met het maken en aanpassen van grafieken met Aspose.Slides voor Java.

## Stap 1: Een presentatie maken

De eerste stap is het maken van een nieuwe presentatie waaraan u uw grafiek toevoegt. Hier is een codefragment om een presentatie te maken:

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
```

## Stap 2: Een grafiek toevoegen

Zodra je presentatie klaar is, is het tijd om een grafiek toe te voegen. In dit voorbeeld voegen we een eenvoudige lijngrafiek met markeringen toe. Zo doe je dat:

```java
// Toegang tot de eerste dia
ISlide slide = pres.getSlides().get_Item(0);

// Het voorbeelddiagram toevoegen
IChart chart = slide.getShapes().addChart(ChartType.LineWithMarkers, 50, 50, 500, 400);
```

## Stap 3: De grafiektitel aanpassen

Een goed gedefinieerde grafiek heeft een titel nodig. Laten we een titel voor onze grafiek kiezen:

```java
// Titel van de grafiek instellen
chart.setTitle(true);
chart.getChartTitle().addTextFrameForOverriding("");
IPortion chartTitle = chart.getChartTitle().getTextFrameForOverriding().getParagraphs().get_Item(0).getPortions().get_Item(0);
chartTitle.setText("Sample Chart");
```

## Stap 4: Rasterlijnen opmaken

U kunt de hoofd- en subrasterlijnen van uw grafiek opmaken. Laten we de opmaak van de verticale rasterlijnen instellen:

```java
// Instellen van de opmaak van de belangrijkste rasterlijnen voor de waarde-as
chart.getAxes().getVerticalAxis().getMajorGridLinesFormat().getLine().getFillFormat().setFillType(FillType.Solid);
chart.getAxes().getVerticalAxis().getMajorGridLinesFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.BLUE);
chart.getAxes().getVerticalAxis().getMajorGridLinesFormat().getLine().setWidth(5);
chart.getAxes().getVerticalAxis().getMajorGridLinesFormat().getLine().setDashStyle(LineDashStyle.DashDot);

// Instellen van de opmaak van kleine rasterlijnen voor de waarde-as
chart.getAxes().getVerticalAxis().getMinorGridLinesFormat().getLine().getFillFormat().setFillType(FillType.Solid);
chart.getAxes().getVerticalAxis().getMinorGridLinesFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.RED);
chart.getAxes().getVerticalAxis().getMinorGridLinesFormat().getLine().setWidth(3);
```

## Stap 5: Waarde-as aanpassen

U hebt controle over de getalnotatie, de maximum- en minimumwaarden van de waarde-as. Zo kunt u deze aanpassen:

```java
// Instellen van waarde-asnummerformaat
chart.getAxes().getVerticalAxis().setNumberFormatLinkedToSource(false);
chart.getAxes().getVerticalAxis().setDisplayUnit(DisplayUnitType.Thousands);
chart.getAxes().getVerticalAxis().setNumberFormat("0.0%");

// Instellen van grafiek maximale, minimale waarden
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

Om uw grafiek informatiever te maken, kunt u een titel toevoegen aan de waarde-as:

```java
// Titel van de waarde-as instellen
chart.getAxes().getVerticalAxis().setTitle(true);
chart.getAxes().getVerticalAxis().getTitle().addTextFrameForOverriding("");
IPortion valtitle = chart.getAxes().getVerticalAxis().getTitle().getTextFrameForOverriding().getParagraphs().get_Item(0).getPortions().get_Item(0);
valtitle.setText("Primary Axis");
```

## Stap 7: Categorie-as opmaken

De categorie-as, die doorgaans gegevenscategorieën vertegenwoordigt, kan ook worden aangepast:

```java
// Instellen van de opmaak van de belangrijkste rasterlijnen voor de categorie-as
chart.getAxes().getHorizontalAxis().getMajorGridLinesFormat().getLine().getFillFormat().setFillType(FillType.Solid);
chart.getAxes().getHorizontalAxis().getMajorGridLinesFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.GREEN);
chart.getAxes().getHorizontalAxis().getMajorGridLinesFormat().getLine().setWidth(5);

// Instellen van de indeling van kleine rasterlijnen voor de categorie-as
chart.getAxes().getHorizontalAxis().getMinorGridLinesFormat().getLine().getFillFormat().setFillType(FillType.Solid);
chart.getAxes().getHorizontalAxis().getMinorGridLinesFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.YELLOW);
chart.getAxes().getHorizontalAxis().getMinorGridLinesFormat().getLine().setWidth(3);
```

## Stap 8: Legenda toevoegen

Legenda's helpen de gegevensreeksen in uw grafiek te verduidelijken. Laten we de legenda's aanpassen:

```java
// Legenda-teksteigenschappen instellen
IChartPortionFormat txtleg = chart.getLegend().getTextFormat().getPortionFormat();
txtleg.setFontBold(NullableBool.True);
txtleg.setFontHeight(16);
txtleg.setFontItalic(NullableBool.True);
txtleg.getFillFormat().setFillType(FillType.Solid);
txtleg.getFillFormat().getSolidFillColor().setColor(Color.RED);

// Legenda's van grafieken weergeven zonder overlappende grafieken
chart.getLegend().setOverlay(true);
```

## Stap 9: De presentatie opslaan

Sla ten slotte uw presentatie met de grafiek op:

```java
pres.save(dataDir + "FormattedChart_out.pptx", SaveFormat.Pptx);
```

## Volledige broncode voor grafiekentiteiten in Java-dia's

```java
// Het pad naar de documentenmap.
String dataDir = "Your Document Directory";
// Maak een map aan als deze nog niet bestaat.
boolean IsExists = new File(dataDir).exists();
if (!IsExists)
	new File(dataDir).mkdirs();
// Instantiëren van presentatie// Instantiëren van presentatie
Presentation pres = new Presentation();
try
{
	// Toegang tot de eerste dia
	ISlide slide = pres.getSlides().get_Item(0);
	// Het voorbeelddiagram toevoegen
	IChart chart = slide.getShapes().addChart(ChartType.LineWithMarkers, 50, 50, 500, 400);
	// Titel van de grafiek instellen
	chart.setTitle(true);
	chart.getChartTitle().addTextFrameForOverriding("");
	IPortion chartTitle = chart.getChartTitle().getTextFrameForOverriding().getParagraphs().get_Item(0).getPortions().get_Item(0);
	chartTitle.setText("Sample Chart");
	chartTitle.getPortionFormat().getFillFormat().setFillType(FillType.Solid);
	chartTitle.getPortionFormat().getFillFormat().getSolidFillColor().setColor(Color.GRAY);
	chartTitle.getPortionFormat().setFontHeight(20);
	chartTitle.getPortionFormat().setFontBold(NullableBool.True);
	chartTitle.getPortionFormat().setFontItalic(NullableBool.True);
	// Instellen van de opmaak van de belangrijkste rasterlijnen voor de waarde-as
	chart.getAxes().getVerticalAxis().getMajorGridLinesFormat().getLine().getFillFormat().setFillType(FillType.Solid);
	chart.getAxes().getVerticalAxis().getMajorGridLinesFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.BLUE);
	chart.getAxes().getVerticalAxis().getMajorGridLinesFormat().getLine().setWidth(5);
	chart.getAxes().getVerticalAxis().getMajorGridLinesFormat().getLine().setDashStyle(LineDashStyle.DashDot);
	// Instellen van de opmaak van kleine rasterlijnen voor de waarde-as
	chart.getAxes().getVerticalAxis().getMinorGridLinesFormat().getLine().getFillFormat().setFillType(FillType.Solid);
	chart.getAxes().getVerticalAxis().getMinorGridLinesFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.RED);
	chart.getAxes().getVerticalAxis().getMinorGridLinesFormat().getLine().setWidth(3);
	// Instellen van waarde-asnummerformaat
	chart.getAxes().getVerticalAxis().setNumberFormatLinkedToSource(false);
	chart.getAxes().getVerticalAxis().setDisplayUnit(DisplayUnitType.Thousands);
	chart.getAxes().getVerticalAxis().setNumberFormat("0.0%");
	// Instellen van grafiek maximale, minimale waarden
	chart.getAxes().getVerticalAxis().setAutomaticMajorUnit(false);
	chart.getAxes().getVerticalAxis().setAutomaticMaxValue(false);
	chart.getAxes().getVerticalAxis().setAutomaticMinorUnit(false);
	chart.getAxes().getVerticalAxis().setAutomaticMinValue(false);
	chart.getAxes().getVerticalAxis().setMaxValue(15f);
	chart.getAxes().getVerticalAxis().setMinValue(-2f);
	chart.getAxes().getVerticalAxis().setMinorUnit(0.5f);
	chart.getAxes().getVerticalAxis().setMajorUnit(2.0f);
	// Eigenschappen van waarde-astekst instellen
	IChartPortionFormat txtVal = chart.getAxes().getVerticalAxis().getTextFormat().getPortionFormat();
	txtVal.setFontBold(NullableBool.True);
	txtVal.setFontHeight(16);
	txtVal.setFontItalic(NullableBool.True);
	txtVal.getFillFormat().setFillType(FillType.Solid);
	txtVal.getFillFormat().getSolidFillColor().setColor(Color.GREEN);
	txtVal.setLatinFont(new FontData("Times New Roman"));
	// Titel van de waarde-as instellen
	chart.getAxes().getVerticalAxis().setTitle(true);
	chart.getAxes().getVerticalAxis().getTitle().addTextFrameForOverriding("");
	IPortion valtitle = chart.getAxes().getVerticalAxis().getTitle().getTextFrameForOverriding().getParagraphs().get_Item(0).getPortions().get_Item(0);
	valtitle.setText("Primary Axis");
	valtitle.getPortionFormat().getFillFormat().setFillType(FillType.Solid);
	valtitle.getPortionFormat().getFillFormat().getSolidFillColor().setColor(Color.GRAY);
	valtitle.getPortionFormat().setFontHeight(20);
	valtitle.getPortionFormat().setFontBold(NullableBool.True);
	valtitle.getPortionFormat().setFontItalic(NullableBool.True);
	// Instellen waarde-aslijnopmaak: Nu verouderd
	// grafiek.getAxes().getVerticalAxis().aVerticalAxis.l.AxisLine.setWidth(10);
	// chart.getAxes().getVerticalAxis().AxisLine.getFillFormat().setFillType(FillType.Solid);
	// Chart.getAxes().getVerticalAxis().AxisLine.getFillFormat().getSolidFillColor().Color = Kleur.Rood;
	// Instellen van de opmaak van de belangrijkste rasterlijnen voor de categorie-as
	chart.getAxes().getHorizontalAxis().getMajorGridLinesFormat().getLine().getFillFormat().setFillType(FillType.Solid);
	chart.getAxes().getHorizontalAxis().getMajorGridLinesFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.GREEN);
	chart.getAxes().getHorizontalAxis().getMajorGridLinesFormat().getLine().setWidth(5);
	// Instellen van de indeling van kleine rasterlijnen voor de categorie-as
	chart.getAxes().getHorizontalAxis().getMinorGridLinesFormat().getLine().getFillFormat().setFillType(FillType.Solid);
	chart.getAxes().getHorizontalAxis().getMinorGridLinesFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.YELLOW);
	chart.getAxes().getHorizontalAxis().getMinorGridLinesFormat().getLine().setWidth(3);
	// Instellen van categorie-asteksteigenschappen
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
	// Positie van het categorie-aslabel instellen
	chart.getAxes().getHorizontalAxis().setTickLabelPosition(TickLabelPositionType.Low);
	// Instellen van de rotatiehoek van het aslabel van de categorie
	chart.getAxes().getHorizontalAxis().setTickLabelRotationAngle(45);
	// Legenda-teksteigenschappen instellen
	IChartPortionFormat txtleg = chart.getLegend().getTextFormat().getPortionFormat();
	txtleg.setFontBold(NullableBool.True);
	txtleg.setFontHeight(16);
	txtleg.setFontItalic(NullableBool.True);
	txtleg.getFillFormat().setFillType(FillType.Solid);
	txtleg.getFillFormat().getSolidFillColor().setColor(Color.RED);
	// Legenda's van grafieken weergeven zonder overlappende grafieken
	chart.getLegend().setOverlay(true);
	// Eerste reeks uitzetten op secundaire waarde-as
	// Grafiek.getChartData().getSeries().get_Item(0).PlotOnSecondAxis = true;
	// Kleur van de achterwand van de grafiek instellen
	chart.getBackWall().setThickness(1);
	chart.getBackWall().getFormat().getFill().setFillType(FillType.Solid);
	chart.getBackWall().getFormat().getFill().getSolidFillColor().setColor(Color.ORANGE);
	chart.getFloor().getFormat().getFill().setFillType(FillType.Solid);
	chart.getFloor().getFormat().getFill().getSolidFillColor().getColor();
	// Kleur van plotgebied instellen
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

In dit artikel hebben we de wereld van diagramentiteiten in Java Slides verkend met behulp van Aspose.Slides voor Java. Je hebt geleerd hoe je diagrammen kunt maken, aanpassen en bewerken om je presentaties te verbeteren. Diagrammen maken je gegevens niet alleen visueel aantrekkelijk, maar helpen je publiek ook om complexe informatie gemakkelijker te begrijpen.

## Veelgestelde vragen

### Hoe verander ik het grafiektype?

Om het grafiektype te wijzigen, gebruikt u de `chart.setType()` en geef het gewenste grafiektype op.

### Kan ik meerdere gegevensreeksen aan een grafiek toevoegen?

Ja, u kunt meerdere gegevensreeksen aan een grafiek toevoegen met behulp van de `chart.getChartData().getSeries().addSeries()` methode.

### Hoe pas ik de grafiekkleuren aan?

U kunt de kleuren van het diagram aanpassen door de opvulopmaak voor verschillende elementen in het diagram in te stellen, zoals rasterlijnen, titel en legenda.

### Kan ik 3D-diagrammen maken?

Ja, Aspose.Slides voor Java ondersteunt het maken van 3D-grafieken. U kunt de `ChartType` naar een 3D-diagramtype om er een te maken.

### Is Aspose.Slides voor Java compatibel met de nieuwste Java-versies?

Ja, Aspose.Slides voor Java wordt regelmatig bijgewerkt ter ondersteuning van de nieuwste Java-versies en is compatibel met een breed scala aan Java-omgevingen.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}