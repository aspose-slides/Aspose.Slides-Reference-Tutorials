---
title: Beheer eigenschappengrafieken in Java-dia's
linktitle: Beheer eigenschappengrafieken in Java-dia's
second_title: Aspose.Slides Java PowerPoint-verwerkings-API
description: Leer verbluffende grafieken maken en eigenschappen beheren in Java-dia's met Aspose.Slides. Stap-voor-stap handleiding met broncode voor krachtige presentaties.
type: docs
weight: 13
url: /nl/java/data-manipulation/manage-properties-charts-java-slides/
---

## Inleiding tot het beheren van eigenschappen en diagrammen in Java Slides met Aspose.Slides

In deze zelfstudie onderzoeken we hoe u eigenschappen kunt beheren en grafieken kunt maken in Java-dia's met behulp van Aspose.Slides. Aspose.Slides is een krachtige Java API voor het werken met PowerPoint-presentaties. We zullen het stapsgewijze proces doorlopen, inclusief broncodevoorbeelden.

## Vereisten

 Voordat we beginnen, moet u ervoor zorgen dat de Aspose.Slides-bibliotheek voor Java in uw project is geïnstalleerd en ingesteld. Je kunt het downloaden van[hier](https://releases.aspose.com/slides/java/).

## Een diagram aan een dia toevoegen

Volg deze stappen om een diagram aan een dia toe te voegen:

1. Importeer de benodigde klassen en maak een exemplaar van de klasse Presentation.

```java
// Maak een exemplaar van de presentatieklasse
Presentation presentation = new Presentation();
```

2. Ga naar de dia waaraan u het diagram wilt toevoegen. In dit voorbeeld hebben we toegang tot de eerste dia.

```java
// Toegang tot de eerste dia
ISlide slide = presentation.getSlides().get_Item(0);
```

3. Voeg een diagram met standaardgegevens toe. In dit geval voegen we een StackedColumn3D-diagram toe.

```java
// Diagram met standaardgegevens toevoegen
IChart chart = slide.getShapes().addChart(ChartType.StackedColumn3D, 0, 0, 500, 500);
```

## Grafiekgegevens instellen

Om de diagramgegevens in te stellen, moeten we een werkmap met diagramgegevens maken en series en categorieën toevoegen. Volg deze stappen:

4. Stel de index van het kaartgegevensblad in.

```java
// De index van het kaartgegevensblad instellen
int defaultWorksheetIndex = 0;
```

5. Haal de diagramgegevenswerkmap op.

```java
// Het werkblad met diagramgegevens ophalen
IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
```

6. Voeg reeksen toe aan het diagram. In dit voorbeeld voegen we twee series toe met de namen 'Serie 1' en 'Serie 2'.

```java
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 1, "Series 1"), chart.getType());
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 2, "Series 2"), chart.getType());
```

7. Voeg categorieën toe aan het diagram. Hier voegen we drie categorieën toe.

```java
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 1, 0, "Category 1"));
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 2, 0, "Category 2"));
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 3, 0, "Category 3"));
```

## 3D-rotatie-eigenschappen instellen

Laten we nu de 3D-rotatie-eigenschappen voor het diagram instellen:

8. Stel de rechte hoekassen in.

```java
chart.getRotation3D().setRightAngleAxes(true);
```

9. Stel de rotatiehoeken voor de X- en Y-assen in. In dit voorbeeld draaien we X 40 graden en Y 270 graden.

```java
chart.getRotation3D().setRotationX((byte) 40);
chart.getRotation3D().setRotationY(270);
```

10. Stel het dieptepercentage in op 150.

```java
chart.getRotation3D().setDepthPercents(150);
```

## Reeksgegevens invullen

11. Neem de tweede diagramreeks en vul deze met gegevenspunten.

```java
IChartSeries series = chart.getChartData().getSeries().get_Item(1);

// Reeksgegevens invullen
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 1, 20));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 50));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 30));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 2, 30));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 2, 10));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 2, 60));
```

## Overlapping aanpassen

12. Stel de overlapwaarde voor reeksen in. U kunt dit bijvoorbeeld instellen op 100, zodat er geen overlap is.

```java
series.getParentSeriesGroup().setOverlap((byte) 100);
```

## De presentatie opslaan

Sla ten slotte de presentatie op schijf op.

```java
presentation.save(dataDir + "Rotation3D_out.pptx", SaveFormat.Pptx);
```

Dat is het! U hebt met succes een 3D-gestapeld kolomdiagram met aangepaste eigenschappen gemaakt met behulp van Aspose.Slides in Java.

## Volledige broncode voor het beheren van eigenschappengrafieken in Java-dia's

```java
// Het pad naar de documentenmap.
String dataDir = "Your Document Directory";
// Maak een exemplaar van de presentatieklasse
Presentation presentation = new Presentation();
// Toegang tot de eerste dia
ISlide slide = presentation.getSlides().get_Item(0);
// Diagram met standaardgegevens toevoegen
IChart chart = slide.getShapes().addChart(ChartType.StackedColumn3D, 0, 0, 500, 500);
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
// Stel Rotatie3D-eigenschappen in
chart.getRotation3D().setRightAngleAxes(true);
chart.getRotation3D().setRotationX((byte) 40);
chart.getRotation3D().setRotationY(270);
chart.getRotation3D().setDepthPercents(150);
// Neem de tweede kaartenserie
IChartSeries series = chart.getChartData().getSeries().get_Item(1);
//Vult nu seriegegevens in
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 1, 20));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 50));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 30));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 2, 30));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 2, 10));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 2, 60));
// Stel de OverLap-waarde in
series.getParentSeriesGroup().setOverlap((byte) 100);
// Presentatie naar schijf schrijven
presentation.save(dataDir + "Rotation3D_out.pptx", SaveFormat.Pptx);
```

## Conclusie

In deze zelfstudie hebben we ons verdiept in de wereld van het beheren van eigenschappen en het maken van diagrammen in Java-dia's met behulp van Aspose.Slides. Aspose.Slides is een robuuste Java API waarmee ontwikkelaars efficiënt met PowerPoint-presentaties kunnen werken. We hebben de essentiële stappen besproken en broncodevoorbeelden gegeven om u door het proces te begeleiden.

## Veelgestelde vragen

### Hoe kan ik het diagramtype wijzigen?

 U kunt het diagramtype wijzigen door het`ChartType`parameter bij het toevoegen van het diagram. Raadpleeg de Aspose.Slides-documentatie voor beschikbare diagramtypen.

### Kan ik de grafiekkleuren aanpassen?

Ja, u kunt de diagramkleuren aanpassen door de vuleigenschappen van reeksgegevenspunten of categorieën in te stellen.

### Hoe voeg ik meer gegevenspunten toe aan een reeks?

 U kunt meer gegevenspunten aan een reeks toevoegen met behulp van de`series.getDataPoints().addDataPointForBarSeries()` methode en specificeert de cel die de gegevenswaarde bevat.

### Hoe kan ik een andere rotatiehoek instellen?

 Gebruik om een andere rotatiehoek voor de X- en Y-assen in te stellen`chart.getRotation3D().setRotationX()` En`chart.getRotation3D().setRotationY()` met de gewenste hoekwaarden.

### Welke andere 3D-eigenschappen kan ik aanpassen?

U kunt andere 3D-eigenschappen van het diagram verkennen, zoals diepte, perspectief en belichting, door de Aspose.Slides-documentatie te raadplegen.