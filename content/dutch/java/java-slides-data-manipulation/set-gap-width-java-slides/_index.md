---
title: Stel de tussenruimte in Java-dia's in
linktitle: Stel de tussenruimte in Java-dia's in
second_title: Aspose.Slides Java PowerPoint-verwerkings-API
description: Leer hoe u de tussenruimte in Java-dia's instelt met Aspose.Slides voor Java. Verbeter de diagrambeelden voor uw PowerPoint-presentaties.
type: docs
weight: 21
url: /nl/java/data-manipulation/set-gap-width-java-slides/
---

## Inleiding tot het instellen van de tussenruimte in Aspose.Slides voor Java

In deze zelfstudie begeleiden we u bij het instellen van de tussenruimte voor een diagram in een PowerPoint-presentatie met behulp van Aspose.Slides voor Java. Tussenruimte bepaalt de afstand tussen de kolommen of staven in een diagram, zodat u de visuele weergave van het diagram kunt bepalen.

## Vereisten

 Voordat u begint, moet u ervoor zorgen dat de Aspose.Slides voor Java-bibliotheek is geïnstalleerd. U kunt het downloaden van de Aspose-website[hier](https://releases.aspose.com/slides/java/).

## Stapsgewijze handleiding

Volg deze stappen om de tussenruimte in een diagram in te stellen met Aspose.Slides voor Java:

### 1. Maak een lege presentatie

```java
// Het pad naar de documentenmap.
String dataDir = "Your Document Directory";

// Een lege presentatie maken
Presentation presentation = new Presentation();
```

### 2. Ga naar de eerste dia

```java
// Toegang tot de eerste dia
ISlide slide = presentation.getSlides().get_Item(0);
```

### 3. Voeg een diagram met standaardgegevens toe

```java
// Voeg een diagram met standaardgegevens toe
IChart chart = slide.getShapes().addChart(ChartType.StackedColumn, 0, 0, 500, 500);
```

### 4. Stel de index van het diagramgegevensblad in

```java
// De index van het kaartgegevensblad instellen
int defaultWorksheetIndex = 0;
```

### 5. Download de werkmap Diagramgegevens

```java
// Het werkblad met diagramgegevens ophalen
IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
```

### 6. Voeg reeksen toe aan het diagram

```java
// Voeg reeksen toe aan het diagram
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 1, "Series 1"), chart.getType());
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 2, "Series 2"), chart.getType());
```

### 7. Voeg categorieën toe aan het diagram

```java
// Voeg categorieën toe aan het diagram
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 1, 0, "Category 1"));
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 2, 0, "Category 2"));
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 3, 0, "Category 3"));
```

### 8. Reeksgegevens invullen

```java
// Reeksgegevens invullen
IChartSeries series = chart.getChartData().getSeries().get_Item(1);

// Gegevenspunten van reeksen vullen
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 1, 20));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 50));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 30));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 2, 30));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 2, 10));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 2, 60));
```

### 9. Stel de tussenruimte in

```java
// Stel de waarde voor de tussenruimte in
series.getParentSeriesGroup().setGapWidth(50);
```

### 10. Sla de presentatie op

```java
// Sla de presentatie met het diagram op
presentation.save(dataDir + "GapWidth_out.pptx", SaveFormat.Pptx);
```

## Volledige broncode voor ingestelde tussenruimte in Java-dia's

```java
// Het pad naar de documentenmap.
String dataDir = "Your Document Directory";
// Lege presentatie maken
Presentation presentation = new Presentation();
// Toegang tot de eerste dia
ISlide slide = presentation.getSlides().get_Item(0);
// Diagram met standaardgegevens toevoegen
IChart chart = slide.getShapes().addChart(ChartType.StackedColumn, 0, 0, 500, 500);
// De index van het kaartgegevensblad instellen
int defaultWorksheetIndex = 0;
// Het werkblad met diagramgegevens ophalen
IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
// Serie toevoegen
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 1, "Series 1"), chart.getType());
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 2, "Series 2"), chart.getType());
// Categorieën toevoegen
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 1, 0, "Caetegoty 1"));
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 2, 0, "Caetegoty 2"));
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 3, 0, "Caetegoty 3"));
// Neem de tweede kaartenserie
IChartSeries series = chart.getChartData().getSeries().get_Item(1);
//Vult nu seriegegevens in
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 1, 20));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 50));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 30));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 2, 30));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 2, 10));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 2, 60));
// Stel de GapWidth-waarde in
series.getParentSeriesGroup().setGapWidth(50);
// Presentatie opslaan met grafiek
presentation.save(dataDir + "GapWidth_out.pptx", SaveFormat.Pptx);
```

## Conclusie

In deze zelfstudie hebt u geleerd hoe u de tussenruimte instelt voor een diagram in een PowerPoint-presentatie met behulp van Aspose.Slides voor Java. Door de tussenruimte aan te passen, kunt u de afstand tussen kolommen of staven in uw diagram bepalen, waardoor de visuele weergave van uw gegevens wordt verbeterd.

## Veelgestelde vragen

### Hoe wijzig ik de waarde van de tussenruimte?

 Om de tussenruimte te wijzigen, gebruikt u de`setGapWidth` methode op de`ParentSeriesGroup`van de kaartenreeks. In het gegeven voorbeeld stellen we de tussenruimte in op 50, maar u kunt deze waarde aanpassen aan de gewenste afstand.

### Kan ik andere diagrameigenschappen aanpassen?

Ja, Aspose.Slides voor Java biedt uitgebreide mogelijkheden voor het aanpassen van diagrammen. U kunt verschillende diagrameigenschappen wijzigen, zoals kleuren, labels, titels en meer. Raadpleeg de API-referentie voor gedetailleerde informatie over de aanpassingsopties voor diagrammen.

### Waar kan ik meer bronnen en documentatie vinden?

 Uitgebreide documentatie en aanvullende bronnen over Aspose.Slides voor Java vindt u op de website[Aspose-website](https://reference.aspose.com/slides/java/).