---
"description": "Maak grafieken met meerdere categorieën in Java Slides met Aspose.Slides voor Java. Stapsgewijze handleiding met broncode voor indrukwekkende datavisualisatie in presentaties."
"linktitle": "Grafiek met meerdere categorieën in Java-dia's"
"second_title": "Aspose.Slides Java PowerPoint-verwerkings-API"
"title": "Grafiek met meerdere categorieën in Java-dia's"
"url": "/nl/java/chart-data-manipulation/multi-category-chart-java-slides/"
"weight": 20
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Grafiek met meerdere categorieën in Java-dia's


## Inleiding tot multi-categorie diagrammen in Java-dia's met Aspose.Slides

In deze tutorial leren we hoe je een grafiek met meerdere categorieën in Java Slides maakt met behulp van de Aspose.Slides voor Java API. Deze handleiding biedt stapsgewijze instructies en broncode om je te helpen bij het maken van een geclusterde kolomgrafiek met meerdere categorieën en reeksen.

## Vereisten
Voordat u begint, moet u ervoor zorgen dat u de Aspose.Slides voor Java-bibliotheek hebt geïnstalleerd en ingesteld in uw Java-ontwikkelomgeving.

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
Verwijder alle bestaande gegevens uit de grafiek.

```java
ch.getChartData().getSeries().clear();
ch.getChartData().getCategories().clear();
```

## Stap 4: Gegevenscategorieën instellen
Laten we nu gegevenscategorieën voor de grafiek instellen. We maken meerdere categorieën aan en groeperen ze.

```java
IChartDataWorkbook fact = ch.getChartData().getChartDataWorkbook();
fact.clear(0);

int defaultWorksheetIndex = 0;

// Categorieën toevoegen en groeperen
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
Laten we nu een reeks aan de grafiek toevoegen, samen met datapunten.

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
Sla ten slotte de presentatie met de grafiek op.

```java
pres.save(dataDir + "AsposeChart_out.pptx", SaveFormat.Pptx);
```

Dat is alles! Je hebt met succes een grafiek met meerdere categorieën in een Java-dia gemaakt met Aspose.Slides. Je kunt deze grafiek verder aanpassen aan je specifieke wensen.

## Volledige broncode voor multi-categorie grafiek in Java-dia's

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
//            Serie toevoegen
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
// Presentatie met grafiek opslaan
pres.save(dataDir + "AsposeChart_out.pptx", SaveFormat.Pptx);
```

## Conclusie

In deze tutorial hebben we geleerd hoe je een grafiek met meerdere categorieën in Java Slides maakt met behulp van de Aspose.Slides voor Java API. We hebben een stapsgewijze handleiding met broncode doorgenomen om een geclusterde kolomgrafiek met meerdere categorieën en reeksen te maken.

## Veelgestelde vragen

### Hoe kan ik het uiterlijk van de grafiek aanpassen?

U kunt de weergave van de grafiek aanpassen door eigenschappen zoals kleuren, lettertypen en stijlen aan te passen. Raadpleeg de Aspose.Slides-documentatie voor gedetailleerde aanpassingsopties.

### Kan ik meer series aan de grafiek toevoegen?

Ja, u kunt extra series aan de grafiek toevoegen door een soortgelijk proces te volgen als getoond in stap 5.

### Hoe verander ik het grafiektype?

Om het grafiektype te wijzigen, vervangt u `ChartType.ClusteredColumn` met het gewenste grafiektype wanneer u de grafiek toevoegt in stap 2.

### Hoe kan ik een titel aan de grafiek toevoegen?

U kunt een titel aan de grafiek toevoegen met behulp van de `ch.getChartTitle().getTextFrame().setText("Chart Title");` methode.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}