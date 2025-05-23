---
"description": "Leer hoe u radardiagrammen maakt in Java PowerPoint-presentaties met Aspose.Slides voor Java API."
"linktitle": "Radardiagram maken in Java-dia's"
"second_title": "Aspose.Slides Java PowerPoint-verwerkings-API"
"title": "Radardiagram maken in Java-dia's"
"url": "/nl/java/chart-creation/radar-chart-creating-java-slides/"
"weight": 10
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Radardiagram maken in Java-dia's


## Inleiding tot het maken van een radardiagram in Java Slides

In deze tutorial begeleiden we je bij het maken van een radardiagram met behulp van de Aspose.Slides voor Java API. Radardiagrammen zijn handig om data in een cirkelvormig patroon te visualiseren, waardoor het gemakkelijker wordt om meerdere datareeksen te vergelijken. We bieden stapsgewijze instructies en Java-broncode.

## Vereisten

Voordat we beginnen, zorg ervoor dat je de Aspose.Slides voor Java-bibliotheek in je project hebt geïntegreerd. Je kunt de bibliotheek downloaden van [hier](https://releases.aspose.com/slides/java/).

## Stap 1: De presentatie instellen

Laten we beginnen met het opzetten van een nieuwe PowerPoint-presentatie en het toevoegen van een dia eraan.

```java
String outPath = "Your Output Directory" + File.separator + "RadarChart_Out.pptx";
Presentation pres = new Presentation();
```

## Stap 2: Een radardiagram toevoegen

Vervolgens voegen we een radardiagram toe aan de dia. We specificeren de positie en afmetingen van het diagram.

```java
ISlide sld = pres.getSlides().get_Item(0);
IChart ichart = sld.getShapes().addChart(ChartType.Radar, 0, 0, 400, 400);
```

## Stap 3: Grafiekgegevens instellen

We gaan nu de grafiekgegevens instellen. Dit houdt in dat we een gegevenswerkmap aanmaken, categorieën en reeksen toevoegen.

```java
int defaultWorksheetIndex = 0;
IChartDataWorkbook fact = ichart.getChartData().getChartDataWorkbook();

// Titel van grafiek instellen
ichart.getChartTitle().addTextFrameForOverriding("Radar Chart");

// Standaard gegenereerde series en categorieën verwijderen
ichart.getChartData().getCategories().clear();
ichart.getChartData().getSeries().clear();

// Nieuwe categorieën toevoegen
ichart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 1, 0, "Category 1"));
ichart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 2, 0, "Category 3"));
ichart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 3, 0, "Category 5"));
ichart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 4, 0, "Category 7"));
ichart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 5, 0, "Category 9"));
ichart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 6, 0, "Category 11"));

// Nieuwe series toevoegen
ichart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 1, "Series 1"), ichart.getType());
ichart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 2, "Series 2"), ichart.getType());
```

## Stap 4: Reeksgegevens vullen

Nu gaan we de reeksgegevens voor ons radardiagram invullen.

```java
// Vul reeksgegevens in voor Reeks 1
IChartSeries series = ichart.getChartData().getSeries().get_Item(0);
series.getDataPoints().addDataPointForRadarSeries(fact.getCell(defaultWorksheetIndex, 1, 1, 2.7));
series.getDataPoints().addDataPointForRadarSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 2.4));
series.getDataPoints().addDataPointForRadarSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 1.5));
series.getDataPoints().addDataPointForRadarSeries(fact.getCell(defaultWorksheetIndex, 4, 1, 3.5));
series.getDataPoints().addDataPointForRadarSeries(fact.getCell(defaultWorksheetIndex, 5, 1, 5));
series.getDataPoints().addDataPointForRadarSeries(fact.getCell(defaultWorksheetIndex, 6, 1, 3.5));

// Seriekleur instellen
series.getFormat().getLine().getFillFormat().setFillType(FillType.Solid);
series.getFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.RED);

// Vul reeksgegevens in voor Reeks 2
series = ichart.getChartData().getSeries().get_Item(1);
series.getDataPoints().addDataPointForRadarSeries(fact.getCell(defaultWorksheetIndex, 1, 2, 2.5));
series.getDataPoints().addDataPointForRadarSeries(fact.getCell(defaultWorksheetIndex, 2, 2, 2.4));
series.getDataPoints().addDataPointForRadarSeries(fact.getCell(defaultWorksheetIndex, 3, 2, 1.6));
series.getDataPoints().addDataPointForRadarSeries(fact.getCell(defaultWorksheetIndex, 4, 2, 3.5));
series.getDataPoints().addDataPointForRadarSeries(fact.getCell(defaultWorksheetIndex, 5, 2, 4));
series.getDataPoints().addDataPointForRadarSeries(fact.getCell(defaultWorksheetIndex, 6, 2, 3.6));

// Seriekleur instellen
series.getFormat().getLine().getFillFormat().setFillType(FillType.Solid);
series.getFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.ORANGE);
```

## Stap 5: Assen en legenda's aanpassen

Laten we de assen en legenda's voor ons radardiagram aanpassen.

```java
// Legendapositie instellen
ichart.getLegend().setPosition(LegendPositionType.Bottom);

// Instellen van categorie-asteksteigenschappen
IChartPortionFormat txtCat = ichart.getAxes().getHorizontalAxis().getTextFormat().getPortionFormat();
txtCat.setFontBold(NullableBool.True);
txtCat.setFontHeight(10);
txtCat.getFillFormat().setFillType(FillType.Solid);
txtCat.getFillFormat().getSolidFillColor().setColor(new Color(PresetColor.DimGray));
txtCat.setLatinFont(new FontData("Calibri"));

// Legenda-teksteigenschappen instellen
IChartPortionFormat txtleg = ichart.getLegend().getTextFormat().getPortionFormat();
txtleg.setFontBold(NullableBool.True);
txtleg.setFontHeight(10);
txtleg.getFillFormat().setFillType(FillType.Solid);
txtleg.getFillFormat().getSolidFillColor().setColor(new Color(PresetColor.DimGray));
txtleg.setLatinFont(new FontData("Calibri"));

// Eigenschappen van waarde-astekst instellen
IChartPortionFormat txtVal = ichart.getAxes().getVerticalAxis().getTextFormat().getPortionFormat();
txtVal.setFontBold(NullableBool.True);
txtVal.setFontHeight(10);
txtVal.getFillFormat().setFillType(FillType.Solid);
txtVal.getFillFormat().getSolidFillColor().setColor(new Color(PresetColor.DimGray));
txtVal.setLatinFont(new FontData("Calibri"));

// Instellen van waarde-asnummerformaat
ichart.getAxes().getVerticalAxis().setNumberFormatLinkedToSource(false);
ichart.getAxes().getVerticalAxis().setNumberFormat("\"$\"#,##0.00");

// Instellen van de belangrijkste eenheidswaarde van de grafiek
ichart.getAxes().getVerticalAxis().setAutomaticMajorUnit(false);
ichart.getAxes().getVerticalAxis().setMajorUnit(1.25f);
```

## Stap 6: De presentatie opslaan

Sla ten slotte de gegenereerde presentatie met het radardiagram op

.

```java
pres.save(outPath, SaveFormat.Pptx);
```

Dat is alles! Je hebt met succes een radardiagram gemaakt in een PowerPoint-presentatie met Aspose.Slides voor Java. Je kunt dit voorbeeld nu verder aanpassen aan je specifieke behoeften.

## Volledige broncode voor het maken van radardiagrammen in Java-dia's

```java
String outPath = "Your Output Directory" + File.separator + "RadarChart_Out.pptx";
Presentation pres = new Presentation();
try
{
	// Toegang tot eerste dia
	ISlide sld = pres.getSlides().get_Item(0);
	// Radarkaart toevoegen
	IChart ichart = sld.getShapes().addChart(ChartType.Radar, 0, 0, 400, 400);
	// De index van het grafiekgegevensblad instellen
	int defaultWorksheetIndex = 0;
	// Werkblad voor het ophalen van grafiekgegevens
	IChartDataWorkbook fact = ichart.getChartData().getChartDataWorkbook();
	// Titel van grafiek instellen
	ichart.getChartTitle().addTextFrameForOverriding("Radar Chart");
	// Standaard gegenereerde series en categorieën verwijderen
	ichart.getChartData().getCategories().clear();
	ichart.getChartData().getSeries().clear();
	// Nieuwe categorieën toevoegen
	ichart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 1, 0, "Caetegoty 1"));
	ichart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 2, 0, "Caetegoty 3"));
	ichart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 3, 0, "Caetegoty 5"));
	ichart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 4, 0, "Caetegoty 7"));
	ichart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 5, 0, "Caetegoty 9"));
	ichart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 6, 0, "Caetegoty 11"));
	// Nieuwe series toevoegen
	ichart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 1, "Series 1"), ichart.getType());
	ichart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 2, "Series 2"), ichart.getType());
	// Nu worden reeksgegevens ingevuld
	IChartSeries series = ichart.getChartData().getSeries().get_Item(0);
	series.getDataPoints().addDataPointForRadarSeries(fact.getCell(defaultWorksheetIndex, 1, 1, 2.7));
	series.getDataPoints().addDataPointForRadarSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 2.4));
	series.getDataPoints().addDataPointForRadarSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 1.5));
	series.getDataPoints().addDataPointForRadarSeries(fact.getCell(defaultWorksheetIndex, 4, 1, 3.5));
	series.getDataPoints().addDataPointForRadarSeries(fact.getCell(defaultWorksheetIndex, 5, 1, 5));
	series.getDataPoints().addDataPointForRadarSeries(fact.getCell(defaultWorksheetIndex, 6, 1, 3.5));
	// Seriekleur instellen
	series.getFormat().getLine().getFillFormat().setFillType(FillType.Solid);
	series.getFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.RED);
	// Nu nog een reeks gegevens invullen
	series = ichart.getChartData().getSeries().get_Item(1);
	series.getDataPoints().addDataPointForRadarSeries(fact.getCell(defaultWorksheetIndex, 1, 2, 2.5));
	series.getDataPoints().addDataPointForRadarSeries(fact.getCell(defaultWorksheetIndex, 2, 2, 2.4));
	series.getDataPoints().addDataPointForRadarSeries(fact.getCell(defaultWorksheetIndex, 3, 2, 1.6));
	series.getDataPoints().addDataPointForRadarSeries(fact.getCell(defaultWorksheetIndex, 4, 2, 3.5));
	series.getDataPoints().addDataPointForRadarSeries(fact.getCell(defaultWorksheetIndex, 5, 2, 4));
	series.getDataPoints().addDataPointForRadarSeries(fact.getCell(defaultWorksheetIndex, 6, 2, 3.6));
	// Seriekleur instellen
	series.getFormat().getLine().getFillFormat().setFillType(FillType.Solid);
	series.getFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.ORANGE);
	// Legendapositie instellen
	ichart.getLegend().setPosition(LegendPositionType.Bottom);
	// Instellen van categorie-asteksteigenschappen
	IChartPortionFormat txtCat = ichart.getAxes().getHorizontalAxis().getTextFormat().getPortionFormat();
	txtCat.setFontBold(NullableBool.True);
	txtCat.setFontHeight(10);
	txtCat.getFillFormat().setFillType(FillType.Solid);
	txtCat.getFillFormat().getSolidFillColor().setColor(new Color(PresetColor.DimGray));
	txtCat.setLatinFont(new FontData("Calibri"));
	// Legenda-teksteigenschappen instellen
	IChartPortionFormat txtleg = ichart.getLegend().getTextFormat().getPortionFormat();
	txtleg.setFontBold(NullableBool.True);
	txtleg.setFontHeight(10);
	txtleg.getFillFormat().setFillType(FillType.Solid);
	txtleg.getFillFormat().getSolidFillColor().setColor(new Color(PresetColor.DimGray));
	txtCat.setLatinFont(new FontData("Calibri"));
	// Eigenschappen van waarde-astekst instellen
	IChartPortionFormat txtVal = ichart.getAxes().getVerticalAxis().getTextFormat().getPortionFormat();
	txtVal.setFontBold(NullableBool.True);
	txtVal.setFontHeight(10);
	txtVal.getFillFormat().setFillType(FillType.Solid);
	txtVal.getFillFormat().getSolidFillColor().setColor(new Color(PresetColor.DimGray));
	txtVal.setLatinFont(new FontData("Calibri"));
	// Instellen van waarde-asnummerformaat
	ichart.getAxes().getVerticalAxis().setNumberFormatLinkedToSource(false);
	ichart.getAxes().getVerticalAxis().setNumberFormat("\"$\"#,##0.00");
	// Instellen van de belangrijkste eenheidswaarde van de grafiek
	ichart.getAxes().getVerticalAxis().setAutomaticMajorUnit(false);
	ichart.getAxes().getVerticalAxis().setMajorUnit(1.25f);
	// Gegenereerde presentatie opslaan
	pres.save(outPath, SaveFormat.Pptx);
}
finally
{
	if (pres != null) pres.dispose();
}
```

## Conclusie

In deze tutorial heb je geleerd hoe je een radardiagram maakt in een PowerPoint-presentatie met Aspose.Slides voor Java. Je kunt deze concepten toepassen om je gegevens effectief te visualiseren en presenteren in je Java-applicaties.

## Veelgestelde vragen

### Hoe kan ik de grafiektitel wijzigen?

Om de grafiektitel te wijzigen, wijzigt u de volgende regel:
```java
ichart.getChartTitle().addTextFrameForOverriding("Radar Chart");
```

### Kan ik meer gegevensreeksen aan het radardiagram toevoegen?

Ja, u kunt meer gegevensreeksen toevoegen door de stappen in 'Stap 3' en 'Stap 4' te volgen voor elke extra reeks die u wilt opnemen.

### Hoe pas ik de grafiekkleuren aan?

U kunt de seriekleuren aanpassen door de lijnen te wijzigen die de `SolidFillColor` Eigenschap voor elke reeks. Bijvoorbeeld:
```java
series.getFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.RED);
```

### Hoe kan ik de aslabels en opmaak wijzigen?

Zie "Stap 5" om de aslabels en opmaak aan te passen, inclusief lettertypegrootte en kleur.

### Hoe kan ik de grafiek opslaan in een ander bestandsformaat?

U kunt het uitvoerformaat wijzigen door de bestandsextensie in de `outPath` variabele en met behulp van de juiste `SaveFormat`Om bijvoorbeeld als PDF op te slaan, gebruikt u `SaveFormat.Pdf`.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}