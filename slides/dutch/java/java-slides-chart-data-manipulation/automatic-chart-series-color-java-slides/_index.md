---
"description": "Leer hoe u dynamische grafieken met automatische reekskleuring in PowerPoint-presentaties maakt met Aspose.Slides voor Java. Verbeter uw datavisualisaties moeiteloos."
"linktitle": "Automatische kleur van grafiekreeksen in Java-dia's"
"second_title": "Aspose.Slides Java PowerPoint-verwerkings-API"
"title": "Automatische kleur van grafiekreeksen in Java-dia's"
"url": "/nl/java/chart-data-manipulation/automatic-chart-series-color-java-slides/"
"weight": 14
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Automatische kleur van grafiekreeksen in Java-dia's


## Inleiding tot automatische kleuring van grafiekreeksen in Aspose.Slides voor Java

In deze tutorial laten we zien hoe je een PowerPoint-presentatie met een grafiek maakt met Aspose.Slides voor Java en hoe je automatische opvulkleuren instelt voor grafiekreeksen. Automatische opvulkleuren kunnen je grafieken visueel aantrekkelijker maken en je tijd besparen doordat de bibliotheek de kleuren voor je kiest.

## Vereisten

Voordat u begint, moet u ervoor zorgen dat de Aspose.Slides voor Java-bibliotheek in uw project is geïnstalleerd. U kunt deze downloaden van [hier](https://releases.aspose.com/slides/java/).

## Stap 1: Een nieuwe presentatie maken

Eerst maken we een nieuwe PowerPoint-presentatie en voegen we er een dia aan toe.

```java
// Het pad naar de documentenmap.
String dataDir = "Your Document Directory";
// Een exemplaar van de presentatieklasse maken
Presentation presentation = new Presentation();
```

## Stap 2: Voeg een grafiek toe aan de dia

Vervolgens voegen we een geclusterde kolomgrafiek toe aan de dia. We stellen de eerste reeks ook in om waarden weer te geven.

```java
// Toegang tot eerste dia
ISlide slide = presentation.getSlides().get_Item(0);
// Grafiek toevoegen met standaardgegevens
IChart chart = slide.getShapes().addChart(ChartType.ClusteredColumn, 0, 0, 500, 500);
// Stel de eerste reeks in op Waarden weergeven
chart.getChartData().getSeries().get_Item(0).getLabels().getDefaultDataLabelFormat().setShowValue(true);
```

## Stap 3: Grafiekgegevens invullen

Nu vullen we de grafiek met gegevens. We beginnen met het verwijderen van de standaard gegenereerde reeksen en categorieën en voegen vervolgens nieuwe reeksen en categorieën toe.

```java
// De index van het grafiekgegevensblad instellen
int defaultWorksheetIndex = 0;
// Het werkblad met grafiekgegevens ophalen
IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
// Standaard gegenereerde series en categorieën verwijderen
chart.getChartData().getSeries().clear();
chart.getChartData().getCategories().clear();

// Nieuwe series toevoegen
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 1, "Series 1"), chart.getType());
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 2, "Series 2"), chart.getType());

// Nieuwe categorieën toevoegen
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 1, 0, "Category 1"));
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 2, 0, "Category 2"));
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 3, 0, "Category 3"));
```

## Stap 4: Vul reeksgegevens in

We vullen de reeksgegevens voor zowel Reeks 1 als Reeks 2 in.

```java
// Neem de eerste grafiekserie
IChartSeries series = chart.getChartData().getSeries().get_Item(0);
// Nu worden reeksgegevens ingevuld
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 1, 20));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 50));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 30));

// Neem de tweede grafiekserie
series = chart.getChartData().getSeries().get_Item(1);
// Nu worden reeksgegevens ingevuld
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 2, 30));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 2, 10));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 2, 60));
```

## Stap 5: Automatische opvulkleur voor series instellen

Laten we nu automatische vulkleuren voor de grafiekreeks instellen. Dit zorgt ervoor dat de bibliotheek kleuren voor ons kiest.

```java
// Automatische opvulkleur voor series instellen
series.getFormat().getFill().setFillType(FillType.NotDefined);
```

## Stap 6: Sla de presentatie op

Ten slotte slaan we de presentatie met de grafiek op in een PowerPoint-bestand.

```java
// Presentatie met grafiek opslaan
presentation.save(dataDir + "AutomaticColor_out.pptx", SaveFormat.Pptx);
```

## Volledige broncode voor automatische kleuring van grafiekreeksen in Java-dia's

```java
// Het pad naar de documentenmap.
String dataDir = "Your Document Directory";
// Een exemplaar van de presentatieklasse maken
Presentation presentation = new Presentation();
try
{
	// Toegang tot eerste dia
	ISlide slide = presentation.getSlides().get_Item(0);
	// Grafiek toevoegen met standaardgegevens
	IChart chart = slide.getShapes().addChart(ChartType.ClusteredColumn, 0, 0, 500, 500);
	// Stel de eerste reeks in op Waarden weergeven
	chart.getChartData().getSeries().get_Item(0).getLabels().getDefaultDataLabelFormat().setShowValue(true);
	// De index van het grafiekgegevensblad instellen
	int defaultWorksheetIndex = 0;
	// Het werkblad met grafiekgegevens ophalen
	IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
	// Standaard gegenereerde series en categorieën verwijderen
	chart.getChartData().getSeries().clear();
	chart.getChartData().getCategories().clear();
	int s = chart.getChartData().getSeries().size();
	s = chart.getChartData().getCategories().size();
	// Nieuwe series toevoegen
	chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 1, "Series 1"), chart.getType());
	chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 2, "Series 2"), chart.getType());
	// Nieuwe categorieën toevoegen
	chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 1, 0, "Caetegoty 1"));
	chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 2, 0, "Caetegoty 2"));
	chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 3, 0, "Caetegoty 3"));
	// Neem de eerste grafiekserie
	IChartSeries series = chart.getChartData().getSeries().get_Item(0);
	// Nu worden reeksgegevens ingevuld
	series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 1, 20));
	series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 50));
	series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 30));
	// Automatische opvulkleur voor series instellen
	series.getFormat().getFill().setFillType(FillType.NotDefined);
	// Neem de tweede grafiekserie
	series = chart.getChartData().getSeries().get_Item(1);
	// Nu worden reeksgegevens ingevuld
	series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 2, 30));
	series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 2, 10));
	series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 2, 60));
	// Vulkleur instellen voor reeksen
	series.getFormat().getFill().setFillType(FillType.Solid);
	series.getFormat().getFill().getSolidFillColor().setColor(Color.GRAY);
	// Presentatie met grafiek opslaan
	presentation.save(dataDir + "AutomaticColor_out.pptx", SaveFormat.Pptx);
}
finally
{
	if (presentation != null) presentation.dispose();
}
```

## Conclusie

In deze tutorial hebben we geleerd hoe je een PowerPoint-presentatie met een grafiek maakt met Aspose.Slides voor Java en hoe je automatische opvulkleuren instelt voor grafiekreeksen. Automatische kleuren kunnen de visuele aantrekkingskracht van je grafieken vergroten en je presentaties aantrekkelijker maken. Je kunt de grafiek naar wens verder aanpassen aan je specifieke wensen.

## Veelgestelde vragen

### Hoe stel ik automatische opvulkleuren in voor grafiekreeksen in Aspose.Slides voor Java?

Gebruik de volgende code om automatische opvulkleuren voor grafiekreeksen in Aspose.Slides voor Java in te stellen:

```java
// Automatische opvulkleur voor series instellen
series.getFormat().getFill().setFillType(FillType.NotDefined);
```

Met deze code kan de bibliotheek automatisch kleuren kiezen voor de grafiekserie.

### Kan ik de kleuren van het diagram aanpassen indien nodig?

Ja, u kunt de kleuren van de grafiek naar wens aanpassen. In het voorbeeld hebben we automatische vulkleuren gebruikt, maar u kunt specifieke kleuren instellen door de `FillType` En `SolidFillColor` Eigenschappen van het formaat van de serie.

### Hoe kan ik extra series of categorieën aan de grafiek toevoegen?

Om extra series of categorieën aan de grafiek toe te voegen, gebruikt u de `getSeries()` En `getCategories()` methoden van de grafiek `ChartData` object. U kunt nieuwe series en categorieën toevoegen door hun gegevens en labels op te geven.

### Is het mogelijk om de grafiek en labels verder op te maken?

Ja, u kunt de grafiek, reeksen en labels naar wens verder opmaken. Aspose.Slides voor Java biedt uitgebreide opmaakopties voor grafieken, waaronder lettertypen, kleuren, stijlen en meer. Raadpleeg de documentatie voor meer informatie over opmaakopties.

### Waar kan ik meer informatie vinden over het werken met Aspose.Slides voor Java?

Voor meer informatie en gedetailleerde documentatie over Aspose.Slides voor Java kunt u de referentiedocumentatie raadplegen [hier](https://reference.aspose.com/slides/java/).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}