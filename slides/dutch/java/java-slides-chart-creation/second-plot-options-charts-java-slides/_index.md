---
"description": "Leer hoe je grafieken in Java Slides kunt aanpassen met Aspose.Slides voor Java. Ontdek de opties voor een tweede plot en verbeter je presentaties."
"linktitle": "Tweede plotopties voor grafieken in Java-dia's"
"second_title": "Aspose.Slides Java PowerPoint-verwerkings-API"
"title": "Tweede plotopties voor grafieken in Java-dia's"
"url": "/nl/java/chart-creation/second-plot-options-charts-java-slides/"
"weight": 12
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Tweede plotopties voor grafieken in Java-dia's


## Inleiding tot tweede plotopties voor grafieken in Java-dia's

In deze tutorial laten we zien hoe je tweede plotopties aan grafieken kunt toevoegen met Aspose.Slides voor Java. Met tweede plotopties kun je het uiterlijk en gedrag van grafieken aanpassen, met name in scenario's zoals cirkeldiagrammen. We geven stapsgewijze instructies en broncodevoorbeelden om dit te bereiken. 

## Vereisten
Voordat we beginnen, moet u ervoor zorgen dat u Aspose.Slides voor Java hebt geïnstalleerd en ingesteld in uw Java-project.

## Stap 1: Een presentatie maken
Laten we beginnen met het maken van een nieuwe presentatie:

```java
// Het pad naar de documentenmap.
String dataDir = "Your Document Directory";
// Een exemplaar van de presentatieklasse maken
Presentation presentation = new Presentation();
```

## Stap 2: Een grafiek toevoegen aan een dia
Vervolgens voegen we een grafiek toe aan een dia. In dit voorbeeld maken we een cirkeldiagram:

```java
// Grafiek toevoegen aan dia
IChart chart = presentation.getSlides().get_Item(0).getShapes().addChart(ChartType.PieOfPie, 50, 50, 500, 400);
```

## Stap 3: Grafiekeigenschappen aanpassen
Laten we nu verschillende eigenschappen voor de grafiek instellen, waaronder opties voor het tweede diagram:

```java
// Gegevenslabels weergeven voor de eerste reeks
chart.getChartData().getSeries().get_Item(0).getLabels().getDefaultDataLabelFormat().setShowValue(true);

// Stel de grootte van de tweede taart in (in procenten)
chart.getChartData().getSeries().get_Item(0).getParentSeriesGroup().setSecondPieSize(149);

// Verdeel de taart in procenten
chart.getChartData().getSeries().get_Item(0).getParentSeriesGroup().setPieSplitBy(PieSplitType.ByPercentage);

// De positie van de splitsing instellen
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
// Een exemplaar van de presentatieklasse maken
Presentation presentation = new Presentation();
// Grafiek toevoegen aan dia
IChart chart = presentation.getSlides().get_Item(0).getShapes().addChart(ChartType.PieOfPie, 50, 50, 500, 400);
// Verschillende eigenschappen instellen
chart.getChartData().getSeries().get_Item(0).getLabels().getDefaultDataLabelFormat().setShowValue(true);
chart.getChartData().getSeries().get_Item(0).getParentSeriesGroup().setSecondPieSize(149);
chart.getChartData().getSeries().get_Item(0).getParentSeriesGroup().setPieSplitBy(PieSplitType.ByPercentage);
chart.getChartData().getSeries().get_Item(0).getParentSeriesGroup().setPieSplitPosition(53);
// Presentatie naar schijf schrijven
presentation.save(dataDir + "SecondPlotOptionsforCharts_out.pptx", SaveFormat.Pptx);
```

## Conclusie

In deze tutorial hebben we geleerd hoe je met Aspose.Slides voor Java tweede plotopties kunt toevoegen aan grafieken in Java Slides. Je kunt verschillende eigenschappen aanpassen om het uiterlijk en de functionaliteit van je grafieken te verbeteren, waardoor je presentaties informatiever en visueel aantrekkelijker worden.

## Veelgestelde vragen

### Hoe kan ik de grootte van de tweede cirkel in een cirkeldiagram wijzigen?

Om de grootte van de tweede cirkel in een cirkeldiagram te wijzigen, gebruikt u de `setSecondPieSize` Methode zoals weergegeven in het bovenstaande codevoorbeeld. Pas de waarde aan om de grootte in percentage op te geven.

### Wat betekent `PieSplitBy` controle in een cirkeldiagram?

De `PieSplitBy` De eigenschap bepaalt hoe het cirkeldiagram wordt gesplitst. U kunt het instellen op: `PieSplitType.ByPercentage` of `PieSplitType.ByValue` om de grafiek respectievelijk op een percentage of op een specifieke waarde te splitsen.

### Hoe stel ik de positie van de splitsing in een cirkeldiagram in?

U kunt de positie van de splitsing in een cirkeldiagram instellen met behulp van de `setPieSplitPosition` methode. Pas de waarde aan om de gewenste positie op te geven.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}