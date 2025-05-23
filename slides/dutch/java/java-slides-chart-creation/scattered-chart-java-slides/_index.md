---
"description": "Leer hoe u spreidingsdiagrammen maakt in Java met Aspose.Slides. Stapsgewijze handleiding met Java-broncode voor datavisualisatie in presentaties."
"linktitle": "Spreidingsdiagram in Java-dia's"
"second_title": "Aspose.Slides Java PowerPoint-verwerkings-API"
"title": "Spreidingsdiagram in Java-dia's"
"url": "/nl/java/chart-creation/scattered-chart-java-slides/"
"weight": 11
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Spreidingsdiagram in Java-dia's


## Inleiding tot spreidingsdiagram in Aspose.Slides voor Java

In deze tutorial begeleiden we je door het proces van het maken van een spreidingsdiagram met Aspose.Slides voor Java. Spreidingsdiagrammen zijn handig voor het visualiseren van datapunten op een tweedimensionaal vlak. We geven stapsgewijze instructies en voegen Java-broncode toe voor jouw gemak.

## Vereisten

Voordat u begint, moet u ervoor zorgen dat aan de volgende vereisten is voldaan:

1. [Aspose.Slides voor Java](https://products.aspose.com/slides/java) geïnstalleerd.
2. Er is een Java-ontwikkelomgeving opgezet.

## Stap 1: Initialiseer de presentatie

Importeer eerst de benodigde bibliotheken en maak een nieuwe presentatie.

```java
// Het pad naar de documentenmap.
String dataDir = "Your Document Directory";

// Maak een map aan als deze nog niet bestaat.
boolean IsExists = new File(dataDir).exists();
if (!IsExists)
    new File(dataDir).mkdirs();

// Een nieuwe presentatie maken
Presentation pres = new Presentation();
```

## Stap 2: Voeg een dia toe en maak het spreidingsdiagram

Voeg vervolgens een dia toe en maak daarop het spreidingsdiagram. We gebruiken de `ScatterWithSmoothLines` grafiektype in dit voorbeeld.

```java
// Ontvang de eerste dia
ISlide slide = pres.getSlides().get_Item(0);

// Het spreidingsdiagram maken
IChart chart = slide.getShapes().addChart(ChartType.ScatterWithSmoothLines, 0, 0, 400, 400);
```

## Stap 3: Grafiekgegevens voorbereiden

Laten we nu de gegevens voor onze spreidingsgrafiek voorbereiden. We voegen twee reeksen toe, elk met meerdere datapunten.

```java
// De standaardindex voor grafiekgegevens ophalen
int defaultWorksheetIndex = 0;

// Het werkblad met grafiekgegevens ophalen
IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();

// Demoserie verwijderen
chart.getChartData().getSeries().clear();

// Voeg de eerste serie toe
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 1, 1, "Series 1"), chart.getType());
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 1, 3, "Series 2"), chart.getType());

// Neem de eerste grafiekserie
IChartSeries series = chart.getChartData().getSeries().get_Item(0);

// Voeg datapunten toe aan de eerste reeks
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 1), fact.getCell(defaultWorksheetIndex, 2, 2, 3));
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 2), fact.getCell(defaultWorksheetIndex, 3, 2, 10));

// Bewerk het type serie
series.setType(ChartType.ScatterWithStraightLinesAndMarkers);
series.getMarker().setSize(10); // Markeergrootte wijzigen
series.getMarker().setSymbol(MarkerStyleType.Star); // Wijzig markeringssymbool

// Neem de tweede grafiekserie
series = chart.getChartData().getSeries().get_Item(1);

// Voeg datapunten toe aan de tweede reeks
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 2, 3, 5), fact.getCell(defaultWorksheetIndex, 2, 4, 2));
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 3, 3, 3), fact.getCell(defaultWorksheetIndex, 3, 4, 1));
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 4, 3, 2), fact.getCell(defaultWorksheetIndex, 4, 4, 2));
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 5, 3, 5), fact.getCell(defaultWorksheetIndex, 5, 4, 1));

// Wijzig de markeringstijl voor de tweede reeks
series.getMarker().setSize(10);
series.getMarker().setSymbol(MarkerStyleType.Circle);
```

## Stap 4: Sla de presentatie op

Sla ten slotte de presentatie met het spreidingsdiagram op in een PPTX-bestand.

```java
pres.save(dataDir + "AsposeChart_out.pptx", SaveFormat.Pptx);
```

Dat is alles! Je hebt met succes een spreidingsdiagram gemaakt met Aspose.Slides voor Java. Je kunt dit voorbeeld nu verder aanpassen aan je specifieke gegevens- en ontwerpvereisten.

## Volledige broncode voor spreidingsdiagram in Java-dia's
```java
// Het pad naar de documentenmap.
String dataDir = "Your Document Directory";
// Maak een map aan als deze nog niet bestaat.
boolean IsExists = new File(dataDir).exists();
if (!IsExists)
	new File(dataDir).mkdirs();
Presentation pres = new Presentation();
ISlide slide = pres.getSlides().get_Item(0);
// Het standaarddiagram maken
IChart chart = slide.getShapes().addChart(ChartType.ScatterWithSmoothLines, 0, 0, 400, 400);
// De standaardindex voor grafiekgegevens ophalen
int defaultWorksheetIndex = 0;
// Het werkblad met grafiekgegevens ophalen
IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
// Demoserie verwijderen
chart.getChartData().getSeries().clear();
// Nieuwe serie toevoegen
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 1, 1, "Series 1"), chart.getType());
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 1, 3, "Series 2"), chart.getType());
// Neem de eerste grafiekserie
IChartSeries series = chart.getChartData().getSeries().get_Item(0);
// Voeg daar een nieuw punt (1:3) toe.
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 1), fact.getCell(defaultWorksheetIndex, 2, 2, 3));
// Nieuw punt toevoegen (2:10)
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 2), fact.getCell(defaultWorksheetIndex, 3, 2, 10));
// Bewerk het type serie
series.setType(ChartType.ScatterWithStraightLinesAndMarkers);
// Het wijzigen van de grafiekreeksmarkering
series.getMarker().setSize(10);
series.getMarker().setSymbol(MarkerStyleType.Star);
// Neem de tweede grafiekserie
series = chart.getChartData().getSeries().get_Item(1);
// Voeg daar een nieuw punt (5:2) toe.
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 2, 3, 5), fact.getCell(defaultWorksheetIndex, 2, 4, 2));
// Nieuw punt toevoegen (3:1)
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 3, 3, 3), fact.getCell(defaultWorksheetIndex, 3, 4, 1));
// Nieuw punt toevoegen (2:2)
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 4, 3, 2), fact.getCell(defaultWorksheetIndex, 4, 4, 2));
// Nieuw punt toevoegen (5:1)
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 5, 3, 5), fact.getCell(defaultWorksheetIndex, 5, 4, 1));
// Het wijzigen van de grafiekreeksmarkering
series.getMarker().setSize(10);
series.getMarker().setSymbol(MarkerStyleType.Circle);
pres.save(dataDir + "AsposeChart_out.pptx", SaveFormat.Pptx);
```

## Conclusie

In deze tutorial hebben we je door het proces geleid van het maken van een spreidingsdiagram met Aspose.Slides voor Java. Spreidingsdiagrammen zijn krachtige tools voor het visualiseren van datapunten in een tweedimensionale ruimte, waardoor het eenvoudiger wordt om complexe datarelaties te analyseren en te begrijpen.

## Veelgestelde vragen

### Hoe kan ik het grafiektype wijzigen?

Om het grafiektype te wijzigen, gebruikt u de `setType` methode op de grafiekreeks en geef het gewenste grafiektype op. Bijvoorbeeld, `series.setType(ChartType.Line)` zou de reeks veranderen in een lijndiagram.

### Hoe pas ik de grootte en stijl van de marker aan?

U kunt de grootte en stijl van de markering wijzigen met behulp van de `getMarker` methode op de reeks en stel vervolgens de grootte en symbooleigenschappen in. Bijvoorbeeld:

```java
series.getMarker().setSize(10);
series.getMarker().setSymbol(MarkerStyleType.Circle);
```

U kunt nog meer aanpassingsopties verkennen in de documentatie van Aspose.Slides voor Java.

Vergeet niet te vervangen `"Your Document Directory"` met het daadwerkelijke pad waar u de presentatie wilt opslaan.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}