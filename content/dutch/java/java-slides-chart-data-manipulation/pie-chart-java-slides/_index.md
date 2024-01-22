---
title: Cirkeldiagram in Java-dia's
linktitle: Cirkeldiagram in Java-dia's
second_title: Aspose.Slides Java PowerPoint-verwerkings-API
description: Leer hoe u verbluffende cirkeldiagrammen kunt maken in PowerPoint-presentaties met Aspose.Slides voor Java. Stap-voor-stap handleiding met broncode voor Java-ontwikkelaars.
type: docs
weight: 23
url: /nl/java/chart-data-manipulation/pie-chart-java-slides/
---

## Inleiding tot het maken van een cirkeldiagram in Java-dia's met Aspose.Slides

In deze zelfstudie laten we zien hoe u een cirkeldiagram maakt in een PowerPoint-presentatie met behulp van Aspose.Slides voor Java. We geven u stapsgewijze instructies en Java-broncode om u op weg te helpen. In deze handleiding wordt ervan uitgegaan dat u uw ontwikkelomgeving al hebt ingesteld met Aspose.Slides voor Java.

## Vereisten

 Voordat u begint, moet u ervoor zorgen dat de Aspose.Slides voor Java-bibliotheek in uw project is geïnstalleerd en geconfigureerd. Je kunt het downloaden van[hier](https://releases.aspose.com/slides/java/).

## Stap 1: Importeer de vereiste bibliotheken

```java
import com.aspose.slides.*;
import com.aspose.slides.charts.*;
```

Zorg ervoor dat u de benodigde klassen uit de Aspose.Slides-bibliotheek importeert.

## Stap 2: Initialiseer de presentatie

```java
// Het pad naar de documentenmap.
String dataDir = "Your Document Directory";

// Instantieer de presentatieklasse die het PPTX-bestand vertegenwoordigt
Presentation presentation = new Presentation();
```

 Maak een nieuw presentatieobject om uw PowerPoint-bestand weer te geven. Vervangen`"Your Document Directory"` met het daadwerkelijke pad waar u de presentatie wilt opslaan.

## Stap 3: Voeg een dia toe

```java
// Toegang tot de eerste dia
ISlide slide = presentation.getSlides().get_Item(0);
```

Haal de eerste dia van de presentatie op waar u het cirkeldiagram wilt toevoegen.

## Stap 4: Voeg een cirkeldiagram toe

```java
// Voeg een cirkeldiagram met standaardgegevens toe
IChart chart = slide.getShapes().addChart(ChartType.Pie, 100, 100, 400, 400);
```

Voeg een cirkeldiagram toe aan de dia op de opgegeven positie en grootte.

## Stap 5: Stel de diagramtitel in

```java
// Diagramtitel instellen
chart.getChartTitle().addTextFrameForOverriding("Sample Title");
chart.getChartTitle().getTextFrameForOverriding().getTextFrameFormat().setCenterText(NullableBool.True);
chart.getChartTitle().setHeight(20);
chart.setTitle(true);
```

Stel een titel in voor het cirkeldiagram. U kunt de titel indien nodig aanpassen.

## Stap 6: Grafiekgegevens aanpassen

```java
// Stel de eerste reeks in om waarden weer te geven
chart.getChartData().getSeries().get_Item(0).getLabels().getDefaultDataLabelFormat().setShowValue(true);

// Instellen van de index van het kaartgegevensblad
int defaultWorksheetIndex = 0;

//Het werkblad met diagramgegevens ophalen
IChartDataWorkbook workbook = chart.getChartData().getChartDataWorkbook();

// Verwijder standaard gegenereerde series en categorieën
chart.getChartData().getSeries().clear();
chart.getChartData().getCategories().clear();

// Nieuwe categorieën toevoegen
chart.getChartData().getCategories().add(workbook.getCell(0, 1, 0, "First Qtr"));
chart.getChartData().getCategories().add(workbook.getCell(0, 2, 0, "2nd Qtr"));
chart.getChartData().getCategories().add(workbook.getCell(0, 3, 0, "3rd Qtr"));

// Nieuwe serie toevoegen
IChartSeries series = chart.getChartData().getSeries().add(workbook.getCell(0, 0, 1, "Series 1"), chart.getType());

// Reeksgegevens invullen
series.getDataPoints().addDataPointForPieSeries(workbook.getCell(defaultWorksheetIndex, 1, 1, 20));
series.getDataPoints().addDataPointForPieSeries(workbook.getCell(defaultWorksheetIndex, 2, 1, 50));
series.getDataPoints().addDataPointForPieSeries(workbook.getCell(defaultWorksheetIndex, 3, 1, 30));
```

Pas de diagramgegevens aan door categorieën en reeksen toe te voegen en hun waarden in te stellen. In dit voorbeeld hebben we drie categorieën en één reeks met bijbehorende gegevenspunten.

## Stap 7: Pas cirkeldiagramsectoren aan

```java
// Sectorkleuren instellen
chart.getChartData().getSeriesGroups().get_Item(0).setColorVaried(true);

// Pas het uiterlijk van elke sector aan
IChartDataPoint point1 = series.getDataPoints().get_Item(0);
point1.getFormat().getFill().setFillType(FillType.Solid);
point1.getFormat().getFill().getSolidFillColor().setColor(new Color(PresetColor.Cyan));
// Pas de sectorrand aan
point1.getFormat().getLine().getFillFormat().setFillType(FillType.Solid);
point1.getFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.GRAY);
point1.getFormat().getLine().setWidth(3.0);
point1.getFormat().getLine().setStyle(LineStyle.ThinThick);
point1.getFormat().getLine().setDashStyle(LineDashStyle.DashDot);

//Pas andere sectoren op een vergelijkbare manier aan
```

Pas het uiterlijk van elke sector in het cirkeldiagram aan. U kunt de kleuren, randstijlen en andere visuele eigenschappen wijzigen.

## Stap 8: Gegevenslabels aanpassen

```java
// Pas gegevenslabels aan
IDataLabel lbl1 = series.getDataPoints().get_Item(0).getLabel();
lbl1.getDataLabelFormat().setShowValue(true);

// Pas gegevenslabels voor andere gegevenspunten op een vergelijkbare manier aan
```

Pas gegevenslabels aan voor elk gegevenspunt in het cirkeldiagram. U kunt bepalen welke waarden in het diagram worden weergegeven.

## Stap 9: Toon aanhaallijnen

```java
// Toon aanhaallijnen voor het diagram
series.getLabels().getDefaultDataLabelFormat().setShowLeaderLines(true);
```

Schakel aanlooplijnen in om gegevenslabels te verbinden met de overeenkomstige sectoren.

## Stap 10: Stel de rotatiehoek van het cirkeldiagram in

```java
// Stel de rotatiehoek voor cirkeldiagramsectoren in
chart.getChartData().getSeriesGroups().get_Item(0).setFirstSliceAngle(180);
```

Stel de rotatiehoek in voor de cirkeldiagramsectoren. In dit voorbeeld stellen we deze in op 180 graden.

## Stap 11: Sla de presentatie op

```java
// Sla de presentatie op met het cirkeldiagram
presentation.save(dataDir + "PieChart_out.pptx", SaveFormat.Pptx);
```

Sla de presentatie met het cirkeldiagram op in de opgegeven map.

## Volledige broncode voor cirkeldiagram in Java-dia's

```java
// Het pad naar de documentenmap.
String dataDir = "Your Document Directory";
// Instantieer de presentatieklasse die het PPTX-bestand vertegenwoordigt
Presentation presentation = new Presentation();
// Toegang tot de eerste dia
ISlide slides = presentation.getSlides().get_Item(0);
// Diagram met standaardgegevens toevoegen
IChart chart = slides.getShapes().addChart(ChartType.Pie, 100, 100, 400, 400);
// Instelschema Titel
chart.getChartTitle().addTextFrameForOverriding("Sample Title");
chart.getChartTitle().getTextFrameForOverriding().getTextFrameFormat().setCenterText(NullableBool.True);
chart.getChartTitle().setHeight(20);
chart.setTitle(true);
// Stel de eerste reeks in op Waarden tonen
chart.getChartData().getSeries().get_Item(0).getLabels().getDefaultDataLabelFormat().setShowValue(true);
// De index van het kaartgegevensblad instellen
int defaultWorksheetIndex = 0;
//Het werkblad met diagramgegevens ophalen
IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
// Verwijder standaard gegenereerde series en categorieën
chart.getChartData().getSeries().clear();
chart.getChartData().getCategories().clear();
// Nieuwe categorieën toevoegen
chart.getChartData().getCategories().add(fact.getCell(0, 1, 0, "First Qtr"));
chart.getChartData().getCategories().add(fact.getCell(0, 2, 0, "2nd Qtr"));
chart.getChartData().getCategories().add(fact.getCell(0, 3, 0, "3rd Qtr"));
// Nieuwe serie toevoegen
IChartSeries series = chart.getChartData().getSeries().add(fact.getCell(0, 0, 1, "Series 1"), chart.getType());
// Vult nu seriegegevens in
series.getDataPoints().addDataPointForPieSeries(fact.getCell(defaultWorksheetIndex, 1, 1, 20));
series.getDataPoints().addDataPointForPieSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 50));
series.getDataPoints().addDataPointForPieSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 30));
//Werkt niet in nieuwe versie
// Nieuwe punten toevoegen en sectorkleur instellen
// series.IsColorVaried = waar;
chart.getChartData().getSeriesGroups().get_Item(0).setColorVaried(true);
IChartDataPoint point = series.getDataPoints().get_Item(0);
point.getFormat().getFill().setFillType(FillType.Solid);
point.getFormat().getFill().getSolidFillColor().setColor(new Color(PresetColor.Cyan));
// Sectorgrens instellen
point.getFormat().getLine().getFillFormat().setFillType(FillType.Solid);
point.getFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.GRAY);
point.getFormat().getLine().setWidth(3.0);
point.getFormat().getLine().setStyle(LineStyle.ThinThick);
point.getFormat().getLine().setDashStyle(LineDashStyle.DashDot);
IChartDataPoint point1 = series.getDataPoints().get_Item(1);
point1.getFormat().getFill().setFillType(FillType.Solid);
point1.getFormat().getFill().getSolidFillColor().setColor(new Color(PresetColor.Brown));
// Sectorgrens instellen
point1.getFormat().getLine().getFillFormat().setFillType(FillType.Solid);
point1.getFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.BLUE);
point1.getFormat().getLine().setWidth(3.0);
point1.getFormat().getLine().setStyle(LineStyle.Single);
point1.getFormat().getLine().setDashStyle(LineDashStyle.LargeDashDot);
IChartDataPoint point2 = series.getDataPoints().get_Item(2);
point2.getFormat().getFill().setFillType(FillType.Solid);
point2.getFormat().getFill().getSolidFillColor().setColor(new Color(PresetColor.Coral));
// Sectorgrens instellen
point2.getFormat().getLine().getFillFormat().setFillType(FillType.Solid);
point2.getFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.RED);
point2.getFormat().getLine().setWidth(2.0);
point2.getFormat().getLine().setStyle(LineStyle.ThinThin);
point2.getFormat().getLine().setDashStyle(LineDashStyle.LargeDashDotDot);
// Maak aangepaste labels voor elk van de categorieën voor nieuwe series
IDataLabel lbl1 = series.getDataPoints().get_Item(0).getLabel();
// lbl.setShowCategoryName(waar);
lbl1.getDataLabelFormat().setShowValue(true);
IDataLabel lbl2 = series.getDataPoints().get_Item(1).getLabel();
lbl2.getDataLabelFormat().setShowValue(true);
lbl2.getDataLabelFormat().setShowLegendKey(true);
lbl2.getDataLabelFormat().setShowPercentage(true);
IDataLabel lbl3 = series.getDataPoints().get_Item(2).getLabel();
lbl3.getDataLabelFormat().setShowSeriesName(true);
lbl3.getDataLabelFormat().setShowPercentage(true);
// Toont aanhaallijnen voor diagram
series.getLabels().getDefaultDataLabelFormat().setShowLeaderLines(true);
// Rotatiehoek voor cirkeldiagramsectoren instellen
chart.getChartData().getSeriesGroups().get_Item(0).setFirstSliceAngle(180);
// Presentatie opslaan met grafiek
presentation.save(dataDir + "PieChart_out.pptx", SaveFormat.Pptx);
```

## Conclusie

U hebt met succes een cirkeldiagram gemaakt in een PowerPoint-presentatie met Aspose.Slides voor Java. U kunt het uiterlijk en de gegevenslabels van het diagram aanpassen aan uw specifieke vereisten. Deze zelfstudie geeft een basisvoorbeeld en u kunt uw diagrammen indien nodig verder verbeteren en aanpassen.

## Veelgestelde vragen

### Hoe kan ik de kleuren van individuele sectoren in het cirkeldiagram wijzigen?

 Als u de kleuren van afzonderlijke sectoren in het cirkeldiagram wilt wijzigen, kunt u de vulkleur voor elk gegevenspunt aanpassen. In het meegeleverde codevoorbeeld hebben we gedemonstreerd hoe u de vulkleur voor elke sector kunt instellen met behulp van de`getSolidFillColor().setColor()`methode. U kunt de kleurwaarden wijzigen om het gewenste uiterlijk te bereiken.

### Kan ik meer categorieën en gegevensreeksen toevoegen aan het cirkeldiagram?

 Ja, u kunt extra categorieën en gegevensreeksen toevoegen aan het cirkeldiagram. Om dit te doen, kunt u gebruik maken van de`getChartData().getCategories().add()` En`getChartData().getSeries().add()` methoden, zoals weergegeven in het voorbeeld. Geef eenvoudigweg de juiste gegevens en labels op voor de nieuwe categorieën en series om uw diagram uit te breiden.

### Hoe pas ik het uiterlijk van gegevenslabels aan?

 U kunt het uiterlijk van gegevenslabels aanpassen met behulp van de`getDataLabelFormat()` methode op het label van elk gegevenspunt. In het voorbeeld hebben we gedemonstreerd hoe u de waarde op gegevenslabels kunt weergeven met behulp van`getDataLabelFormat().setShowValue(true)`. U kunt gegevenslabels verder aanpassen door te bepalen welke waarden worden weergegeven, legendasleutels weer te geven en andere opmaakopties aan te passen.

### Kan ik de titel van het cirkeldiagram wijzigen?

 Ja, u kunt de titel van het cirkeldiagram wijzigen. In de meegeleverde code stellen we de diagramtitel in met behulp van`chart.getChartTitle().addTextFrameForOverriding("Sample Title")` . Je kunt vervangen`"Sample Title"` met uw gewenste titeltekst.

### Hoe sla ik de gegenereerde presentatie met het cirkeldiagram op?

 Om de presentatie met het cirkeldiagram op te slaan, gebruikt u de`presentation.save()` methode. Geef het gewenste bestandspad en de gewenste naam op, samen met het formaat waarin u de presentatie wilt opslaan. Bijvoorbeeld:
```java
presentation.save(dataDir + "PieChart_out.pptx", SaveFormat.Pptx);
```

Zorg ervoor dat u het juiste bestandspad en de juiste indeling opgeeft.

### Kan ik andere typen diagrammen maken met Aspose.Slides voor Java?

 Ja, Aspose.Slides voor Java ondersteunt verschillende diagramtypen, waaronder staafdiagrammen, lijndiagrammen en meer. U kunt verschillende typen diagrammen maken door de`ChartType` bij het toevoegen van een diagram. Raadpleeg de Aspose.Slides-documentatie voor meer informatie over het maken van verschillende soorten diagrammen.

### Hoe kan ik meer informatie en voorbeelden vinden voor het werken met Aspose.Slides voor Java?

 Voor meer informatie, gedetailleerde documentatie en aanvullende voorbeelden kunt u terecht op de website[Aspose.Slides voor Java-documentatie](https://reference.aspose.com/slides/java/). Het biedt uitgebreide hulpmiddelen waarmee u de bibliotheek effectief kunt gebruiken.