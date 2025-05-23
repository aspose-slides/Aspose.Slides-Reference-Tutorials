---
"description": "Leer hoe u verbluffende grafieken maakt en eigenschappen beheert in Java-dia's met Aspose.Slides. Stapsgewijze handleiding met broncode voor krachtige presentaties."
"linktitle": "Eigenschappengrafieken beheren in Java-dia's"
"second_title": "Aspose.Slides Java PowerPoint-verwerkings-API"
"title": "Eigenschappengrafieken beheren in Java-dia's"
"url": "/nl/java/data-manipulation/manage-properties-charts-java-slides/"
"weight": 13
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Eigenschappengrafieken beheren in Java-dia's


## Inleiding tot het beheren van eigenschappen en grafieken in Java-dia's met Aspose.Slides

In deze tutorial laten we zien hoe je eigenschappen kunt beheren en grafieken kunt maken in Java-dia's met Aspose.Slides. Aspose.Slides is een krachtige Java API voor het werken met PowerPoint-presentaties. We doorlopen het proces stapsgewijs, inclusief broncodevoorbeelden.

## Vereisten

Voordat we beginnen, zorg ervoor dat je de Aspose.Slides-bibliotheek voor Java hebt geïnstalleerd en ingesteld in je project. Je kunt deze downloaden van [hier](https://releases.aspose.com/slides/java/).

## Een grafiek aan een dia toevoegen

Om een grafiek aan een dia toe te voegen, volgt u deze stappen:

1. Importeer de benodigde klassen en maak een exemplaar van de Presentation-klasse.

```java
// Een exemplaar van de presentatieklasse maken
Presentation presentation = new Presentation();
```

2. Ga naar de dia waaraan u de grafiek wilt toevoegen. In dit voorbeeld gaan we naar de eerste dia.

```java
// Toegang tot eerste dia
ISlide slide = presentation.getSlides().get_Item(0);
```

3. Voeg een grafiek toe met standaardgegevens. In dit geval voegen we een StackedColumn3D-grafiek toe.

```java
// Grafiek toevoegen met standaardgegevens
IChart chart = slide.getShapes().addChart(ChartType.StackedColumn3D, 0, 0, 500, 500);
```

## Grafiekgegevens instellen

Om de grafiekgegevens in te stellen, moeten we een grafiekwerkmap maken en reeksen en categorieën toevoegen. Volg deze stappen:

4. Stel de index van het grafiekgegevensblad in.

```java
// De index van het grafiekgegevensblad instellen
int defaultWorksheetIndex = 0;
```

5. Download het werkboek met grafiekgegevens.

```java
// Het werkblad met grafiekgegevens ophalen
IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
```

6. Voeg series toe aan de grafiek. In dit voorbeeld voegen we twee series toe, genaamd "Serie 1" en "Serie 2".

```java
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 1, "Series 1"), chart.getType());
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 2, "Series 2"), chart.getType());
```

7. Voeg categorieën toe aan de grafiek. Hier voegen we drie categorieën toe.

```java
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 1, 0, "Category 1"));
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 2, 0, "Category 2"));
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 3, 0, "Category 3"));
```

## 3D-rotatie-eigenschappen instellen

Laten we nu de 3D-rotatie-eigenschappen voor de grafiek instellen:

8. Stel de assen in met een rechte hoek.

```java
chart.getRotation3D().setRightAngleAxes(true);
```

9. Stel de rotatiehoeken voor de X- en Y-as in. In dit voorbeeld roteren we X met 40 graden en Y met 270 graden.

```java
chart.getRotation3D().setRotationX((byte) 40);
chart.getRotation3D().setRotationY(270);
```

10. Stel het dieptepercentage in op 150.

```java
chart.getRotation3D().setDepthPercents(150);
```

## Het vullen van reeksgegevens

11. Neem de tweede grafiekserie en vul deze met datapunten.

```java
IChartSeries series = chart.getChartData().getSeries().get_Item(1);

// Vul reeksgegevens in
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 1, 20));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 50));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 30));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 2, 30));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 2, 10));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 2, 60));
```

## Overlap aanpassen

12. Stel de overlappingswaarde voor series in. U kunt deze bijvoorbeeld op 100 zetten voor geen overlapping.

```java
series.getParentSeriesGroup().setOverlap((byte) 100);
```

## De presentatie opslaan

Sla ten slotte de presentatie op schijf op.

```java
presentation.save(dataDir + "Rotation3D_out.pptx", SaveFormat.Pptx);
```

Dat is alles! Je hebt met succes een 3D-gestapelde kolomgrafiek met aangepaste eigenschappen gemaakt met Aspose.Slides in Java.

## Volledige broncode voor het beheren van eigenschappengrafieken in Java-dia's

```java
// Het pad naar de documentenmap.
String dataDir = "Your Document Directory";
// Een exemplaar van de presentatieklasse maken
Presentation presentation = new Presentation();
// Toegang tot eerste dia
ISlide slide = presentation.getSlides().get_Item(0);
// Grafiek toevoegen met standaardgegevens
IChart chart = slide.getShapes().addChart(ChartType.StackedColumn3D, 0, 0, 500, 500);
// De index van het grafiekgegevensblad instellen
int defaultWorksheetIndex = 0;
// Het werkblad met grafiekgegevens ophalen
IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
// Serie toevoegen
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 1, "Series 1"), chart.getType());
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 2, "Series 2"), chart.getType());
// Categorieën toevoegen
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 1, 0, "Caetegoty 1"));
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 2, 0, "Caetegoty 2"));
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 3, 0, "Caetegoty 3"));
// Rotation3D-eigenschappen instellen
chart.getRotation3D().setRightAngleAxes(true);
chart.getRotation3D().setRotationX((byte) 40);
chart.getRotation3D().setRotationY(270);
chart.getRotation3D().setDepthPercents(150);
// Neem de tweede grafiekserie
IChartSeries series = chart.getChartData().getSeries().get_Item(1);
// Nu worden reeksgegevens ingevuld
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 1, 20));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 50));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 30));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 2, 30));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 2, 10));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 2, 60));
// OverLap-waarde instellen
series.getParentSeriesGroup().setOverlap((byte) 100);
// Presentatie naar schijf schrijven
presentation.save(dataDir + "Rotation3D_out.pptx", SaveFormat.Pptx);
```

## Conclusie

In deze tutorial hebben we ons verdiept in de wereld van het beheren van eigenschappen en het maken van grafieken in Java-dia's met Aspose.Slides. Aspose.Slides is een robuuste Java API waarmee ontwikkelaars efficiënt met PowerPoint-presentaties kunnen werken. We hebben de essentiële stappen behandeld en broncodevoorbeelden gegeven om je door het proces te leiden.

## Veelgestelde vragen

### Hoe kan ik het grafiektype wijzigen?

U kunt het grafiektype wijzigen door de `ChartType` parameter bij het toevoegen van de grafiek. Raadpleeg de Aspose.Slides-documentatie voor beschikbare grafiektypen.

### Kan ik de kleuren van het diagram aanpassen?

Ja, u kunt de kleuren van het diagram aanpassen door de vuleigenschappen van reeksen gegevenspunten of categorieën in te stellen.

### Hoe voeg ik meer datapunten toe aan een reeks?

U kunt meer datapunten aan een reeks toevoegen door de `series.getDataPoints().addDataPointForBarSeries()` methode en het opgeven van de cel die de gegevenswaarde bevat.

### Hoe kan ik een andere rotatiehoek instellen?

Om een andere rotatiehoek voor de X- en Y-as in te stellen, gebruikt u `chart.getRotation3D().setRotationX()` En `chart.getRotation3D().setRotationY()` met de gewenste hoekwaarden.

### Welke andere 3D-eigenschappen kan ik aanpassen?

U kunt andere 3D-eigenschappen van de grafiek, zoals diepte, perspectief en belichting, bekijken door de documentatie van Aspose.Slides te raadplegen.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}