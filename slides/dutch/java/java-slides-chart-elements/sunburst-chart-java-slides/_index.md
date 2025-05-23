---
"description": "Maak verbluffende sunburst-grafieken in Java Slides met Aspose.Slides. Leer stapsgewijs hoe je grafieken maakt en gegevens bewerkt."
"linktitle": "Zonnestraaldiagram in Java-dia's"
"second_title": "Aspose.Slides Java PowerPoint-verwerkings-API"
"title": "Zonnestraaldiagram in Java-dia's"
"url": "/nl/java/chart-elements/sunburst-chart-java-slides/"
"weight": 16
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Zonnestraaldiagram in Java-dia's


## Inleiding tot Sunburst-diagrammen in Java-dia's met Aspose.Slides

In deze tutorial leer je hoe je een Sunburst-grafiek maakt in een PowerPoint-presentatie met behulp van de Aspose.Slides voor Java API. Een Sunburst-grafiek is een radiaaldiagram dat wordt gebruikt om hiërarchische gegevens weer te geven. We geven stapsgewijze instructies en broncode.

## Vereisten

Voordat u begint, moet u ervoor zorgen dat de Aspose.Slides voor Java-bibliotheek is geïnstalleerd en geconfigureerd in uw Java-project. U kunt de bibliotheek downloaden van [hier](https://releases.aspose.com/slides/java/).

## Stap 1: Vereiste bibliotheken importeren

Importeer eerst de benodigde bibliotheken om met Aspose.Slides te werken en maak een Sunburst-grafiek in uw Java-toepassing.

```java
import com.aspose.slides.*;
```

## Stap 2: Initialiseer de presentatie

Initialiseer een PowerPoint-presentatie en geef de map op waar uw presentatiebestand moet worden opgeslagen.

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "test.pptx");
```

## Stap 3: Maak de Sunburst-grafiek

Maak een Sunburst-grafiek op een dia. We specificeren de positie (X, Y) en afmetingen (breedte, hoogte) van de grafiek.

```java
IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.Sunburst, 50, 50, 500, 400);
```

## Stap 4: Grafiekgegevens voorbereiden

Verwijder alle bestaande categorieën en reeksgegevens uit de grafiek en maak een gegevenswerkmap voor de grafiek.

```java
chart.getChartData().getCategories().clear();
chart.getChartData().getSeries().clear();
IChartDataWorkbook wb = chart.getChartData().getChartDataWorkbook();
wb.clear(0);
```

## Stap 5: Definieer de grafiekhiërarchie

Definieer de hiërarchische structuur van de Sunburst-grafiek. U kunt takken, stengels en bladeren als categorieën toevoegen.

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

## Stap 6: Gegevens toevoegen aan de grafiek

Voeg datapunten toe aan de Sunburst-grafiekreeks.

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

Sla ten slotte de presentatie met het Sunburst-diagram op.

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

In deze tutorial heb je geleerd hoe je een Sunburst-grafiek maakt in een PowerPoint-presentatie met behulp van de Aspose.Slides voor Java API. Je hebt gezien hoe je de presentatie initialiseert, de grafiek aanmaakt, de hiërarchie definieert, datapunten toevoegt en de presentatie opslaat. Je kunt deze kennis nu gebruiken om interactieve en informatieve Sunburst-grafieken te maken in je Java-applicaties.

## Veelgestelde vragen

### Hoe pas ik het uiterlijk van het Sunburst-diagram aan?

U kunt het uiterlijk van de Sunburst-grafiek aanpassen door eigenschappen zoals kleuren, labels en stijlen aan te passen. Raadpleeg de Aspose.Slides-documentatie voor gedetailleerde aanpassingsopties.

### Kan ik meer datapunten aan de grafiek toevoegen?

Ja, u kunt meer datapunten aan de grafiek toevoegen met behulp van de `series.getDataPoints().addDataPointForSunburstSeries()` Selecteer een methode voor elk gegevenspunt dat u wilt opnemen.

### Hoe kan ik tooltips toevoegen aan het Sunburst-diagram?

Om tooltips aan het Sunburst-diagram toe te voegen, kunt u de indeling van het gegevenslabel zo instellen dat er extra informatie wordt weergegeven, zoals waarden of beschrijvingen, wanneer u de muisaanwijzer op diagramsegmenten plaatst.

### Is het mogelijk om interactieve Sunburst-grafieken met hyperlinks te maken?

Ja, u kunt interactieve Sunburst-grafieken met hyperlinks maken door hyperlinks toe te voegen aan specifieke grafiekelementen of segmenten. Raadpleeg de Aspose.Slides-documentatie voor meer informatie over het toevoegen van hyperlinks.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}