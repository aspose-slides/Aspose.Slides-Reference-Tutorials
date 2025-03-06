---
title: Automatische grafiekreekskleur in Java-dia's
linktitle: Automatische grafiekreekskleur in Java-dia's
second_title: Aspose.Slides Java PowerPoint-verwerkings-API
description: Leer hoe u dynamische grafieken met automatische reekskleuren kunt maken in PowerPoint-presentaties met Aspose.Slides voor Java. Verbeter moeiteloos uw datavisualisaties.
weight: 14
url: /nl/java/chart-data-manipulation/automatic-chart-series-color-java-slides/
---

{< blocks/products/pf/main-wrap-class >}
{< blocks/products/pf/main-container >}
{< blocks/products/pf/tutorial-page-section >}


## Inleiding tot automatische kleurreeksen in Aspose.Slides voor Java

In deze zelfstudie onderzoeken we hoe u een PowerPoint-presentatie met een diagram kunt maken met Aspose.Slides voor Java en hoe u automatische vulkleuren voor diagramseries kunt instellen. Automatische opvulkleuren kunnen uw diagrammen visueel aantrekkelijker maken en u tijd besparen doordat u de bibliotheek de kleuren voor u laat kiezen.

## Vereisten

 Voordat u begint, moet u ervoor zorgen dat de Aspose.Slides voor Java-bibliotheek in uw project is geïnstalleerd. Je kunt het downloaden van[hier](https://releases.aspose.com/slides/java/).

## Stap 1: Maak een nieuwe presentatie

Eerst maken we een nieuwe PowerPoint-presentatie en voegen we er een dia aan toe.

```java
// Het pad naar de documentenmap.
String dataDir = "Your Document Directory";
// Maak een exemplaar van de presentatieklasse
Presentation presentation = new Presentation();
```

## Stap 2: Voeg een diagram toe aan de dia

Vervolgens voegen we een geclusterd kolomdiagram toe aan de dia. We zullen ook instellen dat de eerste reeks waarden weergeeft.

```java
// Toegang tot de eerste dia
ISlide slide = presentation.getSlides().get_Item(0);
// Diagram met standaardgegevens toevoegen
IChart chart = slide.getShapes().addChart(ChartType.ClusteredColumn, 0, 0, 500, 500);
// Stel de eerste reeks in op Waarden tonen
chart.getChartData().getSeries().get_Item(0).getLabels().getDefaultDataLabelFormat().setShowValue(true);
```

## Stap 3: Grafiekgegevens invullen

Nu vullen we het diagram met gegevens. We beginnen met het verwijderen van de standaard gegenereerde series en categorieën en voegen vervolgens nieuwe series en categorieën toe.

```java
// De index van het kaartgegevensblad instellen
int defaultWorksheetIndex = 0;
// Het werkblad met diagramgegevens ophalen
IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
// Verwijder standaard gegenereerde series en categorieën
chart.getChartData().getSeries().clear();
chart.getChartData().getCategories().clear();

// Nieuwe serie toevoegen
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 1, "Series 1"), chart.getType());
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 2, "Series 2"), chart.getType());

// Nieuwe categorieën toevoegen
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 1, 0, "Category 1"));
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 2, 0, "Category 2"));
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 3, 0, "Category 3"));
```

## Stap 4: Reeksgegevens invullen

We vullen de seriegegevens in voor zowel Serie 1 als Serie 2.

```java
// Neem de eerste kaartenreeks
IChartSeries series = chart.getChartData().getSeries().get_Item(0);
// Vult nu seriegegevens in
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 1, 20));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 50));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 30));

// Neem de tweede kaartenreeks
series = chart.getChartData().getSeries().get_Item(1);
// Vult nu seriegegevens in
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 2, 30));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 2, 10));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 2, 60));
```

## Stap 5: Stel de automatische vulkleur voor series in

Laten we nu automatische opvulkleuren instellen voor de diagramserie. Hierdoor kiest de bibliotheek kleuren voor ons.

```java
// Automatische vulkleur instellen voor series
series.getFormat().getFill().setFillType(FillType.NotDefined);
```

## Stap 6: Sla de presentatie op

Ten slotte slaan we de presentatie met het diagram op in een PowerPoint-bestand.

```java
// Presentatie opslaan met grafiek
presentation.save(dataDir + "AutomaticColor_out.pptx", SaveFormat.Pptx);
```

## Volledige broncode voor automatische kleurreeksen in Java-dia's

```java
// Het pad naar de documentenmap.
String dataDir = "Your Document Directory";
// Maak een exemplaar van de presentatieklasse
Presentation presentation = new Presentation();
try
{
	// Toegang tot de eerste dia
	ISlide slide = presentation.getSlides().get_Item(0);
	// Diagram met standaardgegevens toevoegen
	IChart chart = slide.getShapes().addChart(ChartType.ClusteredColumn, 0, 0, 500, 500);
	// Stel de eerste reeks in op Waarden tonen
	chart.getChartData().getSeries().get_Item(0).getLabels().getDefaultDataLabelFormat().setShowValue(true);
	// De index van het kaartgegevensblad instellen
	int defaultWorksheetIndex = 0;
	// Het werkblad met diagramgegevens ophalen
	IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
	// Verwijder standaard gegenereerde series en categorieën
	chart.getChartData().getSeries().clear();
	chart.getChartData().getCategories().clear();
	int s = chart.getChartData().getSeries().size();
	s = chart.getChartData().getCategories().size();
	// Nieuwe serie toevoegen
	chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 1, "Series 1"), chart.getType());
	chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 2, "Series 2"), chart.getType());
	// Nieuwe categorieën toevoegen
	chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 1, 0, "Caetegoty 1"));
	chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 2, 0, "Caetegoty 2"));
	chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 3, 0, "Caetegoty 3"));
	// Neem de eerste kaartenreeks
	IChartSeries series = chart.getChartData().getSeries().get_Item(0);
	// Vult nu seriegegevens in
	series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 1, 20));
	series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 50));
	series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 30));
	// Automatische vulkleur instellen voor series
	series.getFormat().getFill().setFillType(FillType.NotDefined);
	// Neem de tweede kaartenreeks
	series = chart.getChartData().getSeries().get_Item(1);
	// Vult nu seriegegevens in
	series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 2, 30));
	series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 2, 10));
	series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 2, 60));
	// Vulkleur voor series instellen
	series.getFormat().getFill().setFillType(FillType.Solid);
	series.getFormat().getFill().getSolidFillColor().setColor(Color.GRAY);
	// Presentatie opslaan met grafiek
	presentation.save(dataDir + "AutomaticColor_out.pptx", SaveFormat.Pptx);
}
finally
{
	if (presentation != null) presentation.dispose();
}
```

## Conclusie

In deze zelfstudie hebben we geleerd hoe u een PowerPoint-presentatie met een diagram kunt maken met behulp van Aspose.Slides voor Java en hoe u automatische vulkleuren kunt instellen voor diagramseries. Automatische kleuren kunnen de visuele aantrekkingskracht van uw diagrammen vergroten en uw presentaties aantrekkelijker maken. U kunt het diagram indien nodig verder aanpassen aan uw specifieke vereisten.

## Veelgestelde vragen

### Hoe stel ik automatische opvulkleuren in voor diagramseries in Aspose.Slides voor Java?

Gebruik de volgende code om automatische opvulkleuren voor diagramseries in Aspose.Slides voor Java in te stellen:

```java
// Automatische vulkleur instellen voor series
series.getFormat().getFill().setFillType(FillType.NotDefined);
```

Met deze code kan de bibliotheek automatisch kleuren kiezen voor de kaartenreeks.

### Kan ik de kaartkleuren indien nodig aanpassen?

 Ja, u kunt de kaartkleuren indien nodig aanpassen. In het gegeven voorbeeld hebben we automatische opvulkleuren gebruikt, maar u kunt specifieke kleuren instellen door de`FillType` En`SolidFillColor` eigenschappen van het serieformaat.

### Hoe kan ik extra series of categorieën aan het diagram toevoegen?

 Om extra series of categorieën aan het diagram toe te voegen, gebruikt u de`getSeries()` En`getCategories()` methoden van de grafiek`ChartData` voorwerp. U kunt nieuwe series en categorieën toevoegen door hun gegevens en labels op te geven.

### Is het mogelijk om het diagram en de labels verder op te maken?

Ja, u kunt het diagram, de reeksen en de labels indien nodig verder opmaken. Aspose.Slides voor Java biedt uitgebreide opmaakopties voor diagrammen, inclusief lettertypen, kleuren, stijlen en meer. U kunt de documentatie raadplegen voor meer informatie over opmaakopties.

### Waar kan ik meer informatie vinden over het werken met Aspose.Slides voor Java?

 Voor meer informatie en gedetailleerde documentatie over Aspose.Slides voor Java kunt u de referentiedocumentatie raadplegen[hier](https://reference.aspose.com/slides/java/).
{< /blocks/products/pf/tutorial-page-section >}

{< /blocks/products/pf/main-container >}
{< /blocks/products/pf/main-wrap-class >}

{< blocks/products/products-backtop-button >}
