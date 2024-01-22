---
title: Boxdiagram in Java-dia's
linktitle: Boxdiagram in Java-dia's
second_title: Aspose.Slides Java PowerPoint-verwerkings-API
description: Leer hoe u boxdiagrammen maakt in Java-presentaties met Aspose.Slides. Inclusief stapsgewijze handleiding en broncode voor effectieve datavisualisatie.
type: docs
weight: 10
url: /nl/java/chart-elements/box-chart-java-slides/
---

## Inleiding tot Box Chart in Aspose.Slides voor Java

In deze zelfstudie begeleiden we u bij het maken van een boxdiagram met Aspose.Slides voor Java. Boxdiagrammen zijn handig voor het visualiseren van statistische gegevens met verschillende kwartielen en uitschieters. We bieden stapsgewijze instructies samen met de broncode om u op weg te helpen.

## Vereisten

Zorg ervoor dat u over het volgende beschikt voordat u begint:

- Aspose.Slides voor Java-bibliotheek geïnstalleerd en geconfigureerd.
- Er is een Java-ontwikkelomgeving opgezet.

## Stap 1: Initialiseer de presentatie

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "test.pptx");
```

In deze stap initialiseren we een presentatieobject met behulp van het pad naar een bestaand PowerPoint-bestand ("test.pptx" in dit voorbeeld).

## Stap 2: Maak het boxdiagram

```java
try {
    IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.BoxAndWhisker, 50, 50, 500, 400);
    chart.getChartData().getCategories().clear();
    chart.getChartData().getSeries().clear();
```

In deze stap maken we een boxdiagramvorm op de eerste dia van de presentatie. We verwijderen ook eventuele bestaande categorieën en series uit het diagram.

## Stap 3: Definieer categorieën

```java
    IChartDataWorkbook wb = chart.getChartData().getChartDataWorkbook();
    wb.clear(0);
    chart.getChartData().getCategories().add(wb.getCell(0, "A1", "Category 1"));
    chart.getChartData().getCategories().add(wb.getCell(0, "A2", "Category 1"));
    chart.getChartData().getCategories().add(wb.getCell(0, "A3", "Category 1"));
    chart.getChartData().getCategories().add(wb.getCell(0, "A4", "Category 1"));
    chart.getChartData().getCategories().add(wb.getCell(0, "A5", "Category 1"));
    chart.getChartData().getCategories().add(wb.getCell(0, "A6", "Category 1"));
```

 In deze stap definiëren we de categorieën voor het boxdiagram. Wij gebruiken de`IChartDataWorkbook`om categorieën toe te voegen en deze dienovereenkomstig te labelen.

## Stap 4: Maak de serie

```java
    IChartSeries series = chart.getChartData().getSeries().add(ChartType.BoxAndWhisker);
    series.setQuartileMethod(QuartileMethodType.Exclusive);
    series.setShowMeanLine(true);
    series.setShowMeanMarkers(true);
    series.setShowInnerPoints(true);
    series.setShowOutlierPoints(true);
```

Hier maken we een BoxAndWhisker-reeks voor het diagram en configureren we verschillende opties, zoals de kwartielmethode, gemiddelde lijn, gemiddelde markeringen, binnenste punten en uitschieters.

## Stap 5: Voeg gegevenspunten toe

```java
    series.getDataPoints().addDataPointForBoxAndWhiskerSeries(wb.getCell(0, "B1", 15));
    series.getDataPoints().addDataPointForBoxAndWhiskerSeries(wb.getCell(0, "B2", 41));
    series.getDataPoints().addDataPointForBoxAndWhiskerSeries(wb.getCell(0, "B3", 16));
    series.getDataPoints().addDataPointForBoxAndWhiskerSeries(wb.getCell(0, "B4", 10));
    series.getDataPoints().addDataPointForBoxAndWhiskerSeries(wb.getCell(0, "B5", 23));
    series.getDataPoints().addDataPointForBoxAndWhiskerSeries(wb.getCell(0, "B6", 16));
```

In deze stap voegen we gegevenspunten toe aan de BoxAndWhisker-reeks. Deze gegevenspunten vertegenwoordigen de statistische gegevens voor het diagram.

## Stap 6: Sla de presentatie op

```java
    pres.save("BoxAndWhisker.pptx", SaveFormat.Pptx);
} finally {
    if (pres != null) pres.dispose();
}
```

Ten slotte slaan we de presentatie met de Box Chart op in een nieuw PowerPoint-bestand met de naam 'BoxAndWhisker.pptx'.

Gefeliciteerd! U hebt met succes een boxdiagram gemaakt met Aspose.Slides voor Java. U kunt het diagram verder aanpassen door verschillende eigenschappen aan te passen en indien nodig meer gegevenspunten toe te voegen.

## Volledige broncode voor boxdiagram in Java-dia's

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "test.pptx");
try
{
	IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.BoxAndWhisker, 50, 50, 500, 400);
	chart.getChartData().getCategories().clear();
	chart.getChartData().getSeries().clear();
	IChartDataWorkbook wb = chart.getChartData().getChartDataWorkbook();
	wb.clear(0);
	chart.getChartData().getCategories().add(wb.getCell(0, "A1", "Category 1"));
	chart.getChartData().getCategories().add(wb.getCell(0, "A2", "Category 1"));
	chart.getChartData().getCategories().add(wb.getCell(0, "A3", "Category 1"));
	chart.getChartData().getCategories().add(wb.getCell(0, "A4", "Category 1"));
	chart.getChartData().getCategories().add(wb.getCell(0, "A5", "Category 1"));
	chart.getChartData().getCategories().add(wb.getCell(0, "A6", "Category 1"));
	IChartSeries series = chart.getChartData().getSeries().add(ChartType.BoxAndWhisker);
	series.setQuartileMethod(QuartileMethodType.Exclusive);
	series.setShowMeanLine(true);
	series.setShowMeanMarkers(true);
	series.setShowInnerPoints(true);
	series.setShowOutlierPoints(true);
	series.getDataPoints().addDataPointForBoxAndWhiskerSeries(wb.getCell(0, "B1", 15));
	series.getDataPoints().addDataPointForBoxAndWhiskerSeries(wb.getCell(0, "B2", 41));
	series.getDataPoints().addDataPointForBoxAndWhiskerSeries(wb.getCell(0, "B3", 16));
	series.getDataPoints().addDataPointForBoxAndWhiskerSeries(wb.getCell(0, "B4", 10));
	series.getDataPoints().addDataPointForBoxAndWhiskerSeries(wb.getCell(0, "B5", 23));
	series.getDataPoints().addDataPointForBoxAndWhiskerSeries(wb.getCell(0, "B6", 16));
	pres.save("BoxAndWhisker.pptx", SaveFormat.Pptx);
}
finally
{
	if (pres != null) pres.dispose();
}
```

## Conclusie

In deze zelfstudie hebben we geleerd hoe u een boxdiagram kunt maken met Aspose.Slides voor Java. Boxdiagrammen zijn waardevolle hulpmiddelen voor het visualiseren van statistische gegevens, inclusief kwartielen en uitschieters. We hebben een stapsgewijze handleiding samen met de broncode geleverd om u op weg te helpen met het maken van Box Charts in uw Java-toepassingen.

## Veelgestelde vragen

### Hoe kan ik het uiterlijk van het boxdiagram wijzigen?

U kunt het uiterlijk van het boxdiagram aanpassen door eigenschappen zoals lijnstijlen, kleuren en lettertypen te wijzigen. Raadpleeg de Aspose.Slides voor Java-documentatie voor meer informatie over het aanpassen van diagrammen.

### Kan ik extra gegevensreeksen toevoegen aan het boxdiagram?

 Ja, u kunt meerdere gegevensreeksen aan het boxdiagram toevoegen door er meerdere te maken`IChartSeries` objecten en voegt er gegevenspunten aan toe.

### Wat betekent QuartileMethodType.Exclusive?

 De`QuartileMethodType.Exclusive` De instelling specificeert dat de kwartielberekeningen moeten worden uitgevoerd met behulp van de exclusieve methode. U kunt verschillende kwartielberekeningsmethoden kiezen, afhankelijk van uw gegevens en vereisten.