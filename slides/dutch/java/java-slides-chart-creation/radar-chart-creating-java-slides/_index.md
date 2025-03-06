---
title: Radardiagram maken in Java-dia's
linktitle: Radardiagram maken in Java-dia's
second_title: Aspose.Slides Java PowerPoint-verwerkings-API
description: Leer hoe u radardiagrammen kunt maken in Java PowerPoint-presentaties met behulp van de Aspose.Slides voor Java API.
type: docs
weight: 10
url: /nl/java/chart-creation/radar-chart-creating-java-slides/
---

## Inleiding tot het maken van een radardiagram in Java-dia's

In deze zelfstudie begeleiden we u bij het maken van een radardiagram met behulp van de Aspose.Slides voor Java API. Radardiagrammen zijn handig voor het visualiseren van gegevens in een cirkelvormig patroon, waardoor het gemakkelijker wordt om meerdere gegevensreeksen te vergelijken. We bieden stapsgewijze instructies samen met de Java-broncode.

## Vereisten

 Voordat we beginnen, moet u ervoor zorgen dat de Aspose.Slides voor Java-bibliotheek in uw project is geïntegreerd. U kunt de bibliotheek downloaden van[hier](https://releases.aspose.com/slides/java/).

## Stap 1: De presentatie opzetten

Laten we beginnen met het opzetten van een nieuwe PowerPoint-presentatie en het toevoegen van een dia eraan.

```java
String outPath = "Your Output Directory" + File.separator + "RadarChart_Out.pptx";
Presentation pres = new Presentation();
```

## Stap 2: Een radardiagram toevoegen

Vervolgens voegen we een radardiagram aan de dia toe. We zullen de positie en afmetingen van het diagram specificeren.

```java
ISlide sld = pres.getSlides().get_Item(0);
IChart ichart = sld.getShapes().addChart(ChartType.Radar, 0, 0, 400, 400);
```

## Stap 3: Grafiekgegevens instellen

We gaan nu de grafiekgegevens instellen. Dit omvat het maken van een gegevenswerkmap, het toevoegen van categorieën en het toevoegen van series.

```java
int defaultWorksheetIndex = 0;
IChartDataWorkbook fact = ichart.getChartData().getChartDataWorkbook();

// Diagramtitel instellen
ichart.getChartTitle().addTextFrameForOverriding("Radar Chart");

// Verwijder standaard gegenereerde series en categorieën
ichart.getChartData().getCategories().clear();
ichart.getChartData().getSeries().clear();

// Nieuwe categorieën toevoegen
ichart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 1, 0, "Category 1"));
ichart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 2, 0, "Category 3"));
ichart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 3, 0, "Category 5"));
ichart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 4, 0, "Category 7"));
ichart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 5, 0, "Category 9"));
ichart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 6, 0, "Category 11"));

// Nieuwe serie toevoegen
ichart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 1, "Series 1"), ichart.getType());
ichart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 2, "Series 2"), ichart.getType());
```

## Stap 4: Seriegegevens invullen

Nu zullen we de seriegegevens voor onze radarkaart invullen.

```java
// Vul seriegegevens in voor serie 1
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

// Vul seriegegevens in voor serie 2
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

## Stap 5: As en legenda's aanpassen

Laten we de as en legenda's voor onze radargrafiek aanpassen.

```java
// Legendapositie instellen
ichart.getLegend().setPosition(LegendPositionType.Bottom);

// Teksteigenschappen voor categorie-as instellen
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

// Teksteigenschappen van waarde-as instellen
IChartPortionFormat txtVal = ichart.getAxes().getVerticalAxis().getTextFormat().getPortionFormat();
txtVal.setFontBold(NullableBool.True);
txtVal.setFontHeight(10);
txtVal.getFillFormat().setFillType(FillType.Solid);
txtVal.getFillFormat().getSolidFillColor().setColor(new Color(PresetColor.DimGray));
txtVal.setLatinFont(new FontData("Calibri"));

// Formaat waarde-asnummer instellen
ichart.getAxes().getVerticalAxis().setNumberFormatLinkedToSource(false);
ichart.getAxes().getVerticalAxis().setNumberFormat("\"$\"#,##0.00");

// Instelling van de belangrijkste eenheidswaarde van het diagram
ichart.getAxes().getVerticalAxis().setAutomaticMajorUnit(false);
ichart.getAxes().getVerticalAxis().setMajorUnit(1.25f);
```

## Stap 6: De presentatie opslaan

Sla ten slotte de gegenereerde presentatie op met het radardiagram

.

```java
pres.save(outPath, SaveFormat.Pptx);
```

Dat is het! U hebt met succes een radardiagram gemaakt in een PowerPoint-presentatie met Aspose.Slides voor Java. U kunt dit voorbeeld nu verder aanpassen aan uw specifieke behoeften.

## Volledige broncode voor het maken van radardiagrammen in Java-dia's

```java
String outPath = "Your Output Directory" + File.separator + "RadarChart_Out.pptx";
Presentation pres = new Presentation();
try
{
	// Toegang tot de eerste dia
	ISlide sld = pres.getSlides().get_Item(0);
	// Radardiagram toevoegen
	IChart ichart = sld.getShapes().addChart(ChartType.Radar, 0, 0, 400, 400);
	// De index van het kaartgegevensblad instellen
	int defaultWorksheetIndex = 0;
	// Het werkblad met diagramgegevens ophalen
	IChartDataWorkbook fact = ichart.getChartData().getChartDataWorkbook();
	// Diagramtitel instellen
	ichart.getChartTitle().addTextFrameForOverriding("Radar Chart");
	// Verwijder standaard gegenereerde series en categorieën
	ichart.getChartData().getCategories().clear();
	ichart.getChartData().getSeries().clear();
	// Nieuwe categorieën toevoegen
	ichart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 1, 0, "Caetegoty 1"));
	ichart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 2, 0, "Caetegoty 3"));
	ichart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 3, 0, "Caetegoty 5"));
	ichart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 4, 0, "Caetegoty 7"));
	ichart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 5, 0, "Caetegoty 9"));
	ichart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 6, 0, "Caetegoty 11"));
	// Nieuwe serie toevoegen
	ichart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 1, "Series 1"), ichart.getType());
	ichart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 2, "Series 2"), ichart.getType());
	// Vult nu seriegegevens in
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
	//Nu worden er nog een reeks gegevens ingevuld
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
	// Teksteigenschappen voor categorie-as instellen
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
	// Teksteigenschappen van waarde-as instellen
	IChartPortionFormat txtVal = ichart.getAxes().getVerticalAxis().getTextFormat().getPortionFormat();
	txtVal.setFontBold(NullableBool.True);
	txtVal.setFontHeight(10);
	txtVal.getFillFormat().setFillType(FillType.Solid);
	txtVal.getFillFormat().getSolidFillColor().setColor(new Color(PresetColor.DimGray));
	txtVal.setLatinFont(new FontData("Calibri"));
	// Formaat waarde-asnummer instellen
	ichart.getAxes().getVerticalAxis().setNumberFormatLinkedToSource(false);
	ichart.getAxes().getVerticalAxis().setNumberFormat("\"$\"#,##0.00");
	// Instelling van de belangrijkste eenheidswaarde van het diagram
	ichart.getAxes().getVerticalAxis().setAutomaticMajorUnit(false);
	ichart.getAxes().getVerticalAxis().setMajorUnit(1.25f);
	// Bewaar de gegenereerde presentatie
	pres.save(outPath, SaveFormat.Pptx);
}
finally
{
	if (pres != null) pres.dispose();
}
```

## Conclusie

In deze zelfstudie hebt u geleerd hoe u een radardiagram in een PowerPoint-presentatie kunt maken met Aspose.Slides voor Java. U kunt deze concepten toepassen om uw gegevens effectief te visualiseren en presenteren in uw Java-applicaties.

## Veelgestelde vragen

### Hoe kan ik de diagramtitel wijzigen?

Om de diagramtitel te wijzigen, wijzigt u de volgende regel:
```java
ichart.getChartTitle().addTextFrameForOverriding("Radar Chart");
```

### Kan ik meer gegevensreeksen toevoegen aan de radarkaart?

Ja, u kunt meer gegevensreeksen toevoegen door de stappen in "Stap 3" en "Stap 4" te volgen voor elke extra reeks die u wilt opnemen.

### Hoe pas ik de diagramkleuren aan?

 U kunt de kleuren van de serie aanpassen door de lijnen te wijzigen die de kleur instellen`SolidFillColor` eigenschap voor elke serie. Bijvoorbeeld:
```java
series.getFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.RED);
```

### Hoe kan ik de aslabels en opmaak wijzigen?

Raadpleeg "Stap 5" om de aslabels en opmaak aan te passen, inclusief lettergrootte en kleur.

### Hoe sla ik het diagram op in een ander bestandsformaat?

 kunt het uitvoerformaat wijzigen door de bestandsextensie in het`outPath` variabele en gebruik de juiste`SaveFormat` . Als u bijvoorbeeld als PDF wilt opslaan, gebruikt u`SaveFormat.Pdf`.