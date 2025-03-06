---
title: Grafiek met meerdere categorieën in Java-dia's
linktitle: Grafiek met meerdere categorieën in Java-dia's
second_title: Aspose.Slides Java PowerPoint-verwerkings-API
description: Maak diagrammen met meerdere categorieën in Java-dia's met Aspose.Slides voor Java. Stap-voor-stap handleiding met broncode voor indrukwekkende datavisualisatie in presentaties.
weight: 20
url: /nl/java/chart-data-manipulation/multi-category-chart-java-slides/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}


## Inleiding tot diagrammen met meerdere categorieën in Java-dia's met Aspose.Slides

In deze zelfstudie leren we hoe u een diagram met meerdere categorieën in Java-dia's kunt maken met behulp van de Aspose.Slides voor Java API. Deze handleiding biedt stapsgewijze instructies samen met de broncode om u te helpen een geclusterd kolomdiagram met meerdere categorieën en reeksen te maken.

## Vereisten
Voordat we beginnen, moet u ervoor zorgen dat de Aspose.Slides voor Java-bibliotheek is geïnstalleerd en ingesteld in uw Java-ontwikkelomgeving.

## Stap 1: De omgeving instellen
Importeer eerst de benodigde klassen en maak een nieuw presentatieobject om met dia's te werken.

```java
// Het pad naar de documentenmap.
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
```

## Stap 2: Een dia en grafiek toevoegen
Maak vervolgens een dia en voeg er een geclusterd kolomdiagram aan toe.

```java
ISlide slide = pres.getSlides().get_Item(0);
IChart ch = slide.getShapes().addChart(ChartType.ClusteredColumn, 100, 100, 600, 450);
```

## Stap 3: Bestaande gegevens wissen
Wis alle bestaande gegevens uit het diagram.

```java
ch.getChartData().getSeries().clear();
ch.getChartData().getCategories().clear();
```

## Stap 4: Gegevenscategorieën instellen
Laten we nu gegevenscategorieën voor het diagram instellen. We zullen meerdere categorieën maken en deze groeperen.

```java
IChartDataWorkbook fact = ch.getChartData().getChartDataWorkbook();
fact.clear(0);

int defaultWorksheetIndex = 0;

// Voeg categorieën toe en groepeer ze
IChartCategory category = ch.getChartData().getCategories().add(fact.getCell(0, "c2", "A"));
category.getGroupingLevels().setGroupingItem(1, "Group1");

category = ch.getChartData().getCategories().add(fact.getCell(0, "c3", "B"));

category = ch.getChartData().getCategories().add(fact.getCell(0, "c4", "C"));
category.getGroupingLevels().setGroupingItem(1, "Group2");

category = ch.getChartData().getCategories().add(fact.getCell(0, "c5", "D"));

category = ch.getChartData().getCategories().add(fact.getCell(0, "c6", "E"));
category.getGroupingLevels().setGroupingItem(1, "Group3");

category = ch.getChartData().getCategories().add(fact.getCell(0, "c7", "F"));

category = ch.getChartData().getCategories().add(fact.getCell(0, "c8", "G"));
category.getGroupingLevels().setGroupingItem(1, "Group4");

category = ch.getChartData().getCategories().add(fact.getCell(0, "c9", "H"));
```

## Stap 5: Serie toevoegen
Laten we nu een reeks aan het diagram toevoegen, samen met gegevenspunten.

```java
IChartSeries series = ch.getChartData().getSeries().add(fact.getCell(0, "D1", "Series 1"), ChartType.ClusteredColumn);

series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, "D2", 10));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, "D3", 20));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, "D4", 30));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, "D5", 40));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, "D6", 50));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, "D7", 60));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, "D8", 70));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, "D9", 80));
```

## Stap 6: De presentatie opslaan
Sla ten slotte de presentatie op met het diagram.

```java
pres.save(dataDir + "AsposeChart_out.pptx", SaveFormat.Pptx);
```

Dat is het! U hebt met succes een diagram met meerdere categorieën gemaakt in een Java-dia met behulp van Aspose.Slides. U kunt dit diagram verder aanpassen aan uw specifieke vereisten.

## Volledige broncode voor diagram met meerdere categorieën in Java-dia's

```java
// Het pad naar de documentenmap.
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
ISlide slide = pres.getSlides().get_Item(0);
IChart ch = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 100, 100, 600, 450);
ch.getChartData().getSeries().clear();
ch.getChartData().getCategories().clear();
IChartDataWorkbook fact = ch.getChartData().getChartDataWorkbook();
fact.clear(0);
int defaultWorksheetIndex = 0;
IChartCategory category = ch.getChartData().getCategories().add(fact.getCell(0, "c2", "A"));
category.getGroupingLevels().setGroupingItem(1, "Group1");
category = ch.getChartData().getCategories().add(fact.getCell(0, "c3", "B"));
category = ch.getChartData().getCategories().add(fact.getCell(0, "c4", "C"));
category.getGroupingLevels().setGroupingItem(1, "Group2");
category = ch.getChartData().getCategories().add(fact.getCell(0, "c5", "D"));
category = ch.getChartData().getCategories().add(fact.getCell(0, "c6", "E"));
category.getGroupingLevels().setGroupingItem(1, "Group3");
category = ch.getChartData().getCategories().add(fact.getCell(0, "c7", "F"));
category = ch.getChartData().getCategories().add(fact.getCell(0, "c8", "G"));
category.getGroupingLevels().setGroupingItem(1, "Group4");
category = ch.getChartData().getCategories().add(fact.getCell(0, "c9", "H"));
// Serie toevoegen
IChartSeries series = ch.getChartData().getSeries().add(fact.getCell(0, "D1", "Series 1"),
		ChartType.ClusteredColumn);
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, "D2", 10));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, "D3", 20));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, "D4", 30));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, "D5", 40));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, "D6", 50));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, "D7", 60));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, "D8", 70));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, "D9", 80));
// Presentatie opslaan met grafiek
pres.save(dataDir + "AsposeChart_out.pptx", SaveFormat.Pptx);
```

## Conclusie

In deze zelfstudie hebben we geleerd hoe u een diagram met meerdere categorieën in Java-dia's kunt maken met behulp van de Aspose.Slides voor Java API. We hebben een stapsgewijze handleiding met broncode doorlopen om een geclusterd kolomdiagram met meerdere categorieën en reeksen te maken.

## Veelgestelde vragen

### Hoe kan ik de weergave van het diagram aanpassen?

kunt het uiterlijk van het diagram aanpassen door eigenschappen zoals kleuren, lettertypen en stijlen te wijzigen. Raadpleeg de Aspose.Slides-documentatie voor gedetailleerde aanpassingsopties.

### Kan ik meer series aan het diagram toevoegen?

Ja, u kunt extra reeksen aan het diagram toevoegen door een soortgelijk proces te volgen als weergegeven in stap 5.

### Hoe wijzig ik het diagramtype?

 Als u het diagramtype wilt wijzigen, vervangt u`ChartType.ClusteredColumn` met het gewenste diagramtype bij het toevoegen van het diagram in stap 2.

### Hoe kan ik een titel aan het diagram toevoegen?

 U kunt een titel aan het diagram toevoegen met behulp van de`ch.getChartTitle().getTextFrame().setText("Chart Title");` methode.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
