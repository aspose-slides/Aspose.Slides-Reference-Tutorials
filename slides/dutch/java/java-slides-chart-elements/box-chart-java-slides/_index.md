---
"description": "Leer hoe u boxdiagrammen maakt in Java-presentaties met Aspose.Slides. Inclusief stapsgewijze handleiding en broncode voor effectieve datavisualisatie."
"linktitle": "Boxdiagram in Java-dia's"
"second_title": "Aspose.Slides Java PowerPoint-verwerkings-API"
"title": "Boxdiagram in Java-dia's"
"url": "/nl/java/chart-elements/box-chart-java-slides/"
"weight": 10
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Boxdiagram in Java-dia's


## Inleiding tot boxdiagram in Aspose.Slides voor Java

In deze tutorial leiden we je door het proces van het maken van een boxdiagram met Aspose.Slides voor Java. Boxdiagrammen zijn handig voor het visualiseren van statistische gegevens met verschillende kwartielen en uitschieters. We bieden stapsgewijze instructies en broncode om je op weg te helpen.

## Vereisten

Voordat u begint, moet u ervoor zorgen dat u het volgende heeft:

- Aspose.Slides voor Java-bibliotheek geïnstalleerd en geconfigureerd.
- Er is een Java-ontwikkelomgeving opgezet.

## Stap 1: Initialiseer de presentatie

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "test.pptx");
```

In deze stap initialiseren we een presentatieobject met behulp van het pad naar een bestaand PowerPoint-bestand (in dit voorbeeld 'test.pptx').

## Stap 2: Maak het boxdiagram

```java
try {
    IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.BoxAndWhisker, 50, 50, 500, 400);
    chart.getChartData().getCategories().clear();
    chart.getChartData().getSeries().clear();
```

In deze stap maken we een boxdiagram op de eerste dia van de presentatie. We verwijderen ook alle bestaande categorieën en reeksen uit het diagram.

## Stap 3: Categorieën definiëren

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

In deze stap definiëren we de categorieën voor de boxgrafiek. We gebruiken de `IChartDataWorkbook` om categorieën toe te voegen en ze van de juiste labels te voorzien.

## Stap 4: De serie maken

```java
    IChartSeries series = chart.getChartData().getSeries().add(ChartType.BoxAndWhisker);
    series.setQuartileMethod(QuartileMethodType.Exclusive);
    series.setShowMeanLine(true);
    series.setShowMeanMarkers(true);
    series.setShowInnerPoints(true);
    series.setShowOutlierPoints(true);
```

Hier maken we een BoxAndWhisker-serie voor de grafiek en configureren we verschillende opties, zoals kwartielmethode, gemiddelde lijn, gemiddelde markeringen, binnenste punten en uitschieters.

## Stap 5: Gegevenspunten toevoegen

```java
    series.getDataPoints().addDataPointForBoxAndWhiskerSeries(wb.getCell(0, "B1", 15));
    series.getDataPoints().addDataPointForBoxAndWhiskerSeries(wb.getCell(0, "B2", 41));
    series.getDataPoints().addDataPointForBoxAndWhiskerSeries(wb.getCell(0, "B3", 16));
    series.getDataPoints().addDataPointForBoxAndWhiskerSeries(wb.getCell(0, "B4", 10));
    series.getDataPoints().addDataPointForBoxAndWhiskerSeries(wb.getCell(0, "B5", 23));
    series.getDataPoints().addDataPointForBoxAndWhiskerSeries(wb.getCell(0, "B6", 16));
```

In deze stap voegen we datapunten toe aan de BoxAndWhisker-reeks. Deze datapunten vertegenwoordigen de statistische gegevens voor de grafiek.

## Stap 6: Sla de presentatie op

```java
    pres.save("BoxAndWhisker.pptx", SaveFormat.Pptx);
} finally {
    if (pres != null) pres.dispose();
}
```

Ten slotte slaan we de presentatie met het Box Chart op in een nieuw PowerPoint-bestand met de naam "BoxAndWhisker.pptx."

Gefeliciteerd! Je hebt met succes een boxdiagram gemaakt met Aspose.Slides voor Java. Je kunt het diagram verder aanpassen door verschillende eigenschappen aan te passen en indien nodig meer datapunten toe te voegen.

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

In deze tutorial hebben we geleerd hoe je een boxdiagram maakt met Aspose.Slides voor Java. Boxdiagrammen zijn waardevolle tools voor het visualiseren van statistische gegevens, inclusief kwartielen en uitschieters. We hebben een stapsgewijze handleiding en broncode toegevoegd om je op weg te helpen met het maken van boxdiagrammen in je Java-applicaties.

## Veelgestelde vragen

### Hoe kan ik het uiterlijk van het boxdiagram wijzigen?

U kunt het uiterlijk van het boxdiagram aanpassen door eigenschappen zoals lijnstijlen, kleuren en lettertypen aan te passen. Raadpleeg de documentatie van Aspose.Slides voor Java voor meer informatie over het aanpassen van diagrammen.

### Kan ik extra gegevensreeksen toevoegen aan het boxdiagram?

Ja, u kunt meerdere gegevensreeksen toevoegen aan het boxdiagram door extra gegevensreeksen te maken. `IChartSeries` objecten en het toevoegen van datapunten daaraan.

### Wat betekent QuartileMethodType.Exclusive?

De `QuartileMethodType.Exclusive` De instelling specificeert dat de kwartielberekeningen moeten worden uitgevoerd met behulp van de exclusieve methode. U kunt verschillende kwartielberekeningsmethoden kiezen, afhankelijk van uw gegevens en vereisten.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}