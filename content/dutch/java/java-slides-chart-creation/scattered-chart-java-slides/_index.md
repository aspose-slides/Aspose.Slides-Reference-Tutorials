---
title: Verspreid diagram in Java-dia's
linktitle: Verspreid diagram in Java-dia's
second_title: Aspose.Slides Java PowerPoint-verwerkings-API
description: Leer hoe u spreidingsdiagrammen maakt in Java met behulp van Aspose.Slides. Stap-voor-stap handleiding met Java-broncode voor datavisualisatie in presentaties.
type: docs
weight: 11
url: /nl/java/chart-creation/scattered-chart-java-slides/
---

## Inleiding tot het spreidingsdiagram in Aspose.Slides voor Java

In deze zelfstudie begeleiden we u bij het maken van een spreidingsdiagram met Aspose.Slides voor Java. Spreidingsdiagrammen zijn handig voor het visualiseren van gegevenspunten op een tweedimensionaal vlak. We geven u stapsgewijze instructies en voegen voor uw gemak de Java-broncode toe.

## Vereisten

Voordat u begint, moet u ervoor zorgen dat u aan de volgende vereisten voldoet:

1. [Aspose.Slides voor Java](https://products.aspose.com/slides/java) geïnstalleerd.
2. Er is een Java-ontwikkelomgeving opgezet.

## Stap 1: Initialiseer de presentatie

Importeer eerst de benodigde bibliotheken en maak een nieuwe presentatie.

```java
// Het pad naar de documentenmap.
String dataDir = "Your Document Directory";

// Maak een directory aan als deze nog niet aanwezig is.
boolean IsExists = new File(dataDir).exists();
if (!IsExists)
    new File(dataDir).mkdirs();

// Maak een nieuwe presentatie
Presentation pres = new Presentation();
```

## Stap 2: Voeg een dia toe en maak het spreidingsdiagram

 Voeg vervolgens een dia toe en maak er het spreidingsdiagram op. Wij gebruiken de`ScatterWithSmoothLines`grafiektype in dit voorbeeld.

```java
// Haal de eerste dia
ISlide slide = pres.getSlides().get_Item(0);

// Het spreidingsdiagram maken
IChart chart = slide.getShapes().addChart(ChartType.ScatterWithSmoothLines, 0, 0, 400, 400);
```

## Stap 3: Bereid grafiekgegevens voor

Laten we nu de gegevens voor ons spreidingsdiagram voorbereiden. We voegen twee reeksen toe, elk met meerdere gegevenspunten.

```java
// De standaard werkbladindex voor diagramgegevens ophalen
int defaultWorksheetIndex = 0;

// Het werkblad met diagramgegevens ophalen
IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();

// Demoserie verwijderen
chart.getChartData().getSeries().clear();

// Voeg de eerste serie toe
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 1, 1, "Series 1"), chart.getType());
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 1, 3, "Series 2"), chart.getType());

// Neem de eerste kaartenserie
IChartSeries series = chart.getChartData().getSeries().get_Item(0);

// Voeg gegevenspunten toe aan de eerste reeks
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 1), fact.getCell(defaultWorksheetIndex, 2, 2, 3));
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 2), fact.getCell(defaultWorksheetIndex, 3, 2, 10));

// Bewerk het type serie
series.setType(ChartType.ScatterWithStraightLinesAndMarkers);
series.getMarker().setSize(10); // Wijzig de markeringsgrootte
series.getMarker().setSymbol(MarkerStyleType.Star); // Markeringssymbool wijzigen

// Neem de tweede kaartenreeks
series = chart.getChartData().getSeries().get_Item(1);

// Voeg gegevenspunten toe aan de tweede reeks
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 2, 3, 5), fact.getCell(defaultWorksheetIndex, 2, 4, 2));
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 3, 3, 3), fact.getCell(defaultWorksheetIndex, 3, 4, 1));
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 4, 3, 2), fact.getCell(defaultWorksheetIndex, 4, 4, 2));
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 5, 3, 5), fact.getCell(defaultWorksheetIndex, 5, 4, 1));

// Wijzig de markeringsstijl voor de tweede serie
series.getMarker().setSize(10);
series.getMarker().setSymbol(MarkerStyleType.Circle);
```

## Stap 4: Sla de presentatie op

Sla ten slotte de presentatie met het spreidingsdiagram op in een PPTX-bestand.

```java
pres.save(dataDir + "AsposeChart_out.pptx", SaveFormat.Pptx);
```

Dat is het! U hebt met succes een spreidingsdiagram gemaakt met Aspose.Slides voor Java. U kunt dit voorbeeld nu verder aanpassen aan uw specifieke gegevens- en ontwerpvereisten.

## Volledige broncode voor verspreide grafiek in Java-dia's
```java
// Het pad naar de documentenmap.
String dataDir = "Your Document Directory";
// Maak een directory aan als deze nog niet aanwezig is.
boolean IsExists = new File(dataDir).exists();
if (!IsExists)
	new File(dataDir).mkdirs();
Presentation pres = new Presentation();
ISlide slide = pres.getSlides().get_Item(0);
//Het standaarddiagram maken
IChart chart = slide.getShapes().addChart(ChartType.ScatterWithSmoothLines, 0, 0, 400, 400);
// De standaard werkbladindex voor diagramgegevens ophalen
int defaultWorksheetIndex = 0;
// Het werkblad met diagramgegevens ophalen
IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
// Demoserie verwijderen
chart.getChartData().getSeries().clear();
// Nieuwe serie toevoegen
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 1, 1, "Series 1"), chart.getType());
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 1, 3, "Series 2"), chart.getType());
// Neem de eerste kaartenreeks
IChartSeries series = chart.getChartData().getSeries().get_Item(0);
// Voeg daar een nieuw punt (1:3) toe.
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 1), fact.getCell(defaultWorksheetIndex, 2, 2, 3));
// Nieuw punt toevoegen (2:10)
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 2), fact.getCell(defaultWorksheetIndex, 3, 2, 10));
// Bewerk het type serie
series.setType(ChartType.ScatterWithStraightLinesAndMarkers);
// De kaartreeksmarkering wijzigen
series.getMarker().setSize(10);
series.getMarker().setSymbol(MarkerStyleType.Star);
// Neem de tweede kaartenreeks
series = chart.getChartData().getSeries().get_Item(1);
// Voeg daar een nieuw punt (5:2) toe.
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 2, 3, 5), fact.getCell(defaultWorksheetIndex, 2, 4, 2));
// Nieuw punt toevoegen (3:1)
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 3, 3, 3), fact.getCell(defaultWorksheetIndex, 3, 4, 1));
// Nieuw punt toevoegen (2:2)
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 4, 3, 2), fact.getCell(defaultWorksheetIndex, 4, 4, 2));
// Nieuw punt toevoegen (5:1)
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 5, 3, 5), fact.getCell(defaultWorksheetIndex, 5, 4, 1));
// De kaartreeksmarkering wijzigen
series.getMarker().setSize(10);
series.getMarker().setSymbol(MarkerStyleType.Circle);
pres.save(dataDir + "AsposeChart_out.pptx", SaveFormat.Pptx);
```

## Conclusie

In deze zelfstudie hebben we u door het proces geleid van het maken van een spreidingsdiagram met Aspose.Slides voor Java. Spreidingsdiagrammen zijn krachtige hulpmiddelen voor het visualiseren van gegevenspunten in een tweedimensionale ruimte, waardoor het gemakkelijker wordt om complexe gegevensrelaties te analyseren en te begrijpen.

## Veelgestelde vragen

### Hoe kan ik het diagramtype wijzigen?

 Om het diagramtype te wijzigen, gebruikt u de`setType` methode voor de kaartserie en geef het gewenste kaarttype op. Bijvoorbeeld,`series.setType(ChartType.Line)` zou de reeks veranderen in een lijndiagram.

### Hoe pas ik de grootte en stijl van de marker aan?

 U kunt de grootte en stijl van de markering wijzigen met behulp van de`getMarker` methode op de reeks en stel vervolgens de grootte- en symbooleigenschappen in. Bijvoorbeeld:

```java
series.getMarker().setSize(10);
series.getMarker().setSymbol(MarkerStyleType.Circle);
```

Voel je vrij om meer aanpassingsopties te verkennen in de Aspose.Slides voor Java-documentatie.

 Vergeet niet te vervangen`"Your Document Directory"` met het daadwerkelijke pad waar u de presentatie wilt opslaan.