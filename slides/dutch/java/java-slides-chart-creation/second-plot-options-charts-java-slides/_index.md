---
title: Tweede plotopties voor grafieken in Java-dia's
linktitle: Tweede plotopties voor grafieken in Java-dia's
second_title: Aspose.Slides Java PowerPoint-verwerkings-API
description: Leer hoe u diagrammen in Java Slides kunt aanpassen met Aspose.Slides voor Java. Ontdek tweede plotopties en verbeter uw presentaties.
weight: 12
url: /nl/java/chart-creation/second-plot-options-charts-java-slides/
---

{< blocks/products/pf/main-wrap-class >}
{< blocks/products/pf/main-container >}
{< blocks/products/pf/tutorial-page-section >}


## Inleiding tot tweede plotopties voor diagrammen in Java-dia's

In deze zelfstudie onderzoeken we hoe u tweede plotopties aan diagrammen kunt toevoegen met behulp van Aspose.Slides voor Java. Met tweede plotopties kunt u het uiterlijk en het gedrag van diagrammen aanpassen, vooral in scenario's zoals cirkeldiagrammen. We zullen stapsgewijze instructies en broncodevoorbeelden geven om dit te bereiken. 

## Vereisten
Voordat we beginnen, zorg ervoor dat Aspose.Slides voor Java is geïnstalleerd en ingesteld in uw Java-project.

## Stap 1: Maak een presentatie
Laten we beginnen met het maken van een nieuwe presentatie:

```java
// Het pad naar de documentenmap.
String dataDir = "Your Document Directory";
// Maak een exemplaar van de presentatieklasse
Presentation presentation = new Presentation();
```

## Stap 2: Voeg een diagram toe aan een dia
Vervolgens voegen we een diagram aan een dia toe. In dit voorbeeld maken we een cirkeldiagram:

```java
// Voeg een diagram toe aan de dia
IChart chart = presentation.getSlides().get_Item(0).getShapes().addChart(ChartType.PieOfPie, 50, 50, 500, 400);
```

## Stap 3: Pas de diagrameigenschappen aan
Laten we nu verschillende eigenschappen voor het diagram instellen, inclusief tweede plotopties:

```java
// Toon gegevenslabels voor de eerste serie
chart.getChartData().getSeries().get_Item(0).getLabels().getDefaultDataLabelFormat().setShowValue(true);

// Stel de grootte van de tweede taart in (in percentage)
chart.getChartData().getSeries().get_Item(0).getParentSeriesGroup().setSecondPieSize(149);

// Verdeel de taart op percentage
chart.getChartData().getSeries().get_Item(0).getParentSeriesGroup().setPieSplitBy(PieSplitType.ByPercentage);

// Stel de positie van de splitsing in
chart.getChartData().getSeries().get_Item(0).getParentSeriesGroup().setPieSplitPosition(53);
```

## Stap 4: Sla de presentatie op
Sla ten slotte de presentatie op met de grafiek- en tweede plotopties:

```java
// Presentatie naar schijf schrijven
presentation.save(dataDir + "SecondPlotOptionsforCharts_out.pptx", SaveFormat.Pptx);
```

## Volledige broncode voor tweede plotopties

```java
// Het pad naar de documentenmap.
String dataDir = "Your Document Directory";
// Maak een exemplaar van de presentatieklasse
Presentation presentation = new Presentation();
// Voeg een diagram toe aan de dia
IChart chart = presentation.getSlides().get_Item(0).getShapes().addChart(ChartType.PieOfPie, 50, 50, 500, 400);
// Stel verschillende eigenschappen in
chart.getChartData().getSeries().get_Item(0).getLabels().getDefaultDataLabelFormat().setShowValue(true);
chart.getChartData().getSeries().get_Item(0).getParentSeriesGroup().setSecondPieSize(149);
chart.getChartData().getSeries().get_Item(0).getParentSeriesGroup().setPieSplitBy(PieSplitType.ByPercentage);
chart.getChartData().getSeries().get_Item(0).getParentSeriesGroup().setPieSplitPosition(53);
// Presentatie naar schijf schrijven
presentation.save(dataDir + "SecondPlotOptionsforCharts_out.pptx", SaveFormat.Pptx);
```

## Conclusie

In deze zelfstudie hebben we geleerd hoe u tweede plotopties kunt toevoegen aan diagrammen in Java Slides met behulp van Aspose.Slides voor Java. U kunt verschillende eigenschappen aanpassen om het uiterlijk en de functionaliteit van uw diagrammen te verbeteren, waardoor uw presentaties informatiever en visueel aantrekkelijker worden.

## Veelgestelde vragen

### Hoe kan ik de grootte van de tweede cirkel in een cirkeldiagram wijzigen?

Als u de grootte van de tweede cirkel in een cirkeldiagram wilt wijzigen, gebruikt u de`setSecondPieSize` methode zoals weergegeven in het bovenstaande codevoorbeeld. Pas de waarde aan om de grootte in procenten op te geven.

###  Wat doet`PieSplitBy` control in a Pie of Pie chart?

 De`PieSplitBy` eigenschap bepaalt hoe het cirkeldiagram wordt gesplitst. Je kunt het op beide instellen`PieSplitType.ByPercentage` of`PieSplitType.ByValue` om het diagram respectievelijk op percentage of op een specifieke waarde te splitsen.

### Hoe stel ik de positie van de splitsing in een cirkeldiagram in?

 U kunt de positie van de splitsing in een cirkeldiagram instellen met behulp van de`setPieSplitPosition` methode. Pas de waarde aan om de gewenste positie op te geven.
{< /blocks/products/pf/tutorial-page-section >}

{< /blocks/products/pf/main-container >}
{< /blocks/products/pf/main-wrap-class >}

{< blocks/products/products-backtop-button >}
