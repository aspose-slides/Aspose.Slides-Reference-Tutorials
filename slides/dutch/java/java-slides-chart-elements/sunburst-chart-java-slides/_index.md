---
title: Sunburst-grafiek in Java-dia's
linktitle: Sunburst-grafiek in Java-dia's
second_title: Aspose.Slides Java PowerPoint-verwerkings-API
description: Maak verbluffende Sunburst-grafieken in Java-dia's met Aspose.Slides. Leer stapsgewijze diagrammen maken en gegevensmanipulatie.
type: docs
weight: 16
url: /nl/java/chart-elements/sunburst-chart-java-slides/
---

## Inleiding tot Sunburst Chart in Java-dia's met Aspose.Slides

In deze zelfstudie leert u hoe u een Sunburst-diagram maakt in een PowerPoint-presentatie met behulp van de Aspose.Slides voor Java API. Een Sunburst-diagram is een radiaaldiagram dat wordt gebruikt om hiërarchische gegevens weer te geven. We bieden stapsgewijze instructies samen met de broncode.

## Vereisten

 Voordat u begint, moet u ervoor zorgen dat de Aspose.Slides voor Java-bibliotheek in uw Java-project is geïnstalleerd en geconfigureerd. U kunt de bibliotheek downloaden van[hier](https://releases.aspose.com/slides/java/).

## Stap 1: Importeer de vereiste bibliotheken

Importeer eerst de benodigde bibliotheken om met Aspose.Slides te werken en maak een Sunburst-diagram in uw Java-toepassing.

```java
import com.aspose.slides.*;
```

## Stap 2: Initialiseer de presentatie

Initialiseer een PowerPoint-presentatie en geef de map op waar uw presentatiebestand zal worden opgeslagen.

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "test.pptx");
```

## Stap 3: Maak de Sunburst-grafiek

Maak een Sunburst-diagram op een dia. We specificeren de positie (X, Y) en afmetingen (breedte, hoogte) van de grafiek.

```java
IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.Sunburst, 50, 50, 500, 400);
```

## Stap 4: Bereid grafiekgegevens voor

Wis alle bestaande categorieën en reeksgegevens uit het diagram en maak een gegevenswerkmap voor het diagram.

```java
chart.getChartData().getCategories().clear();
chart.getChartData().getSeries().clear();
IChartDataWorkbook wb = chart.getChartData().getChartDataWorkbook();
wb.clear(0);
```

## Stap 5: Definieer de diagramhiërarchie

Definieer de hiërarchische structuur van het Sunburst-diagram. U kunt takken, stengels en bladeren als categorieën toevoegen.

```java
// Tak 1
IChartCategory leaf = chart.getChartData().getCategories().add(wb.getCell(0, "C1", "Leaf1"));
leaf.getGroupingLevels().setGroupingItem(1, "Stem1");
leaf.getGroupingLevels().setGroupingItem(2, "Branch1");
chart.getChartData().getCategories().add(wb.getCell(0, "C2", "Leaf2"));
leaf = chart.getChartData().getCategories().add(wb.getCell(0, "C3", "Leaf3"));
leaf.getGroupingLevels().setGroupingItem(1, "Stem2");
chart.getChartData().getCategories().add(wb.getCell(0, "C4", "Leaf4"));

// Tak 2
leaf = chart.getChartData().getCategories().add(wb.getCell(0, "C5", "Leaf5"));
leaf.getGroupingLevels().setGroupingItem(1, "Stem3");
leaf.getGroupingLevels().setGroupingItem(2, "Branch2");
chart.getChartData().getCategories().add(wb.getCell(0, "C6", "Leaf6"));
leaf = chart.getChartData().getCategories().add(wb.getCell(0, "C7", "Leaf7"));
leaf.getGroupingLevels().setGroupingItem(1, "Stem4");
chart.getChartData().getCategories().add(wb.getCell(0, "C8", "Leaf8"));
```

## Stap 6: Voeg gegevens toe aan het diagram

Voeg gegevenspunten toe aan de Sunburst-diagramreeks.

```java
IChartSeries series = chart.getChartData().getSeries().add(ChartType.Sunburst);
series.getLabels().getDefaultDataLabelFormat().setShowCategoryName(true);
series.getDataPoints().addDataPointForSunburstSeries(wb.getCell(0, "D1", 4));
series.getDataPoints().addDataPointForSunburstSeries(wb.getCell(0, "D2", 5));
series.getDataPoints().addDataPointForSunburstSeries(wb.getCell(0, "D3", 3));
series.getDataPoints().addDataPointForSunburstSeries(wb.getCell(0, "D4", 6));
series.getDataPoints().addDataPointForSunburstSeries(wb.getCell(0, "D5", 9));
series.getDataPoints().addDataPointForSunburstSeries(wb.getCell(0, "D6", 9));
series.getDataPoints().addDataPointForSunburstSeries(wb.getCell(0, "D7", 4));
series.getDataPoints().addDataPointForSunburstSeries(wb.getCell(0, "D8", 3));
```

## Stap 7: Sla de presentatie op

Sla ten slotte de presentatie op met het Sunburst-diagram.

```java
pres.save("Sunburst.pptx", SaveFormat.Pptx);
```

## Volledige broncode voor Sunburst-grafiek in Java-dia's

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "test.pptx");
try
{
	IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.Sunburst, 50, 50, 500, 400);
	chart.getChartData().getCategories().clear();
	chart.getChartData().getSeries().clear();
	IChartDataWorkbook wb = chart.getChartData().getChartDataWorkbook();
	wb.clear(0);
	//tak 1
	IChartCategory leaf = chart.getChartData().getCategories().add(wb.getCell(0, "C1", "Leaf1"));
	leaf.getGroupingLevels().setGroupingItem(1, "Stem1");
	leaf.getGroupingLevels().setGroupingItem(2, "Branch1");
	chart.getChartData().getCategories().add(wb.getCell(0, "C2", "Leaf2"));
	leaf = chart.getChartData().getCategories().add(wb.getCell(0, "C3", "Leaf3"));
	leaf.getGroupingLevels().setGroupingItem(1, "Stem2");
	chart.getChartData().getCategories().add(wb.getCell(0, "C4", "Leaf4"));
	//tak 2
	leaf = chart.getChartData().getCategories().add(wb.getCell(0, "C5", "Leaf5"));
	leaf.getGroupingLevels().setGroupingItem(1, "Stem3");
	leaf.getGroupingLevels().setGroupingItem(2, "Branch2");
	chart.getChartData().getCategories().add(wb.getCell(0, "C6", "Leaf6"));
	leaf = chart.getChartData().getCategories().add(wb.getCell(0, "C7", "Leaf7"));
	leaf.getGroupingLevels().setGroupingItem(1, "Stem4");
	chart.getChartData().getCategories().add(wb.getCell(0, "C8", "Leaf8"));
	IChartSeries series = chart.getChartData().getSeries().add(ChartType.Sunburst);
	series.getLabels().getDefaultDataLabelFormat().setShowCategoryName(true);
	series.getDataPoints().addDataPointForSunburstSeries(wb.getCell(0, "D1", 4));
	series.getDataPoints().addDataPointForSunburstSeries(wb.getCell(0, "D2", 5));
	series.getDataPoints().addDataPointForSunburstSeries(wb.getCell(0, "D3", 3));
	series.getDataPoints().addDataPointForSunburstSeries(wb.getCell(0, "D4", 6));
	series.getDataPoints().addDataPointForSunburstSeries(wb.getCell(0, "D5", 9));
	series.getDataPoints().addDataPointForSunburstSeries(wb.getCell(0, "D6", 9));
	series.getDataPoints().addDataPointForSunburstSeries(wb.getCell(0, "D7", 4));
	series.getDataPoints().addDataPointForSunburstSeries(wb.getCell(0, "D8", 3));
	pres.save("Sunburst.pptx", SaveFormat.Pptx);
}
finally
{
	if (pres != null) pres.dispose();
}
```

## Conclusie

In deze zelfstudie hebt u geleerd hoe u een Sunburst-grafiek kunt maken in een PowerPoint-presentatie met behulp van de Aspose.Slides voor Java API. U hebt gezien hoe u de presentatie kunt initialiseren, het diagram kunt maken, de diagramhiërarchie kunt definiëren, gegevenspunten kunt toevoegen en de presentatie kunt opslaan. U kunt deze kennis nu gebruiken om interactieve en informatieve Sunburst-grafieken te maken in uw Java-applicaties.

## Veelgestelde vragen

### Hoe pas ik het uiterlijk van het Sunburst-diagram aan?

U kunt het uiterlijk van het Sunburst-diagram aanpassen door eigenschappen zoals kleuren, labels en stijlen te wijzigen. Raadpleeg de Aspose.Slides-documentatie voor gedetailleerde aanpassingsopties.

### Kan ik meer gegevenspunten aan het diagram toevoegen?

 Ja, u kunt meer gegevenspunten aan het diagram toevoegen met behulp van de`series.getDataPoints().addDataPointForSunburstSeries()` methode voor elk gegevenspunt dat u wilt opnemen.

### Hoe kan ik tooltips toevoegen aan het Sunburst-diagram?

Als u knopinfo aan het Sunburst-diagram wilt toevoegen, kunt u de indeling van het gegevenslabel zo instellen dat aanvullende informatie, zoals waarden of beschrijvingen, wordt weergegeven wanneer u de muisaanwijzer over diagramsegmenten beweegt.

### Is het mogelijk om interactieve Sunburst-grafieken met hyperlinks te maken?

Ja, u kunt interactieve Sunburst-diagrammen met hyperlinks maken door hyperlinks toe te voegen aan specifieke diagramelementen of segmenten. Raadpleeg de Aspose.Slides-documentatie voor meer informatie over het toevoegen van hyperlinks.