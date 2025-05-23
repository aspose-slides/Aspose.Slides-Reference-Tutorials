---
"description": "Leer hoe je verbluffende cirkeldiagrammen maakt in PowerPoint-presentaties met Aspose.Slides voor Java. Stapsgewijze handleiding met broncode voor Java-ontwikkelaars."
"linktitle": "Cirkeldiagram in Java-dia's"
"second_title": "Aspose.Slides Java PowerPoint-verwerkings-API"
"title": "Cirkeldiagram in Java-dia's"
"url": "/nl/java/chart-data-manipulation/pie-chart-java-slides/"
"weight": 23
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Cirkeldiagram in Java-dia's


## Inleiding tot het maken van een cirkeldiagram in Java Slides met Aspose.Slides

In deze tutorial laten we zien hoe je een cirkeldiagram maakt in een PowerPoint-presentatie met Aspose.Slides voor Java. We geven je stapsgewijze instructies en Java-broncode om je op weg te helpen. Deze handleiding gaat ervan uit dat je je ontwikkelomgeving al hebt ingesteld met Aspose.Slides voor Java.

## Vereisten

Voordat u begint, moet u ervoor zorgen dat de Aspose.Slides voor Java-bibliotheek in uw project is geïnstalleerd en geconfigureerd. U kunt deze downloaden van [hier](https://releases.aspose.com/slides/java/).

## Stap 1: Vereiste bibliotheken importeren

```java
import com.aspose.slides.*;
import com.aspose.slides.charts.*;
```

Zorg ervoor dat u de benodigde klassen uit de Aspose.Slides-bibliotheek importeert.

## Stap 2: Initialiseer de presentatie

```java
// Het pad naar de documentenmap.
String dataDir = "Your Document Directory";

// Instantieer presentatieklasse die PPTX-bestand vertegenwoordigt
Presentation presentation = new Presentation();
```

Maak een nieuw presentatieobject om uw PowerPoint-bestand te vertegenwoordigen. Vervang `"Your Document Directory"` met het daadwerkelijke pad waar u de presentatie wilt opslaan.

## Stap 3: Een dia toevoegen

```java
// Toegang tot de eerste dia
ISlide slide = presentation.getSlides().get_Item(0);
```

Selecteer de eerste dia van de presentatie waaraan u het cirkeldiagram wilt toevoegen.

## Stap 4: Voeg een cirkeldiagram toe

```java
// Voeg een cirkeldiagram met standaardgegevens toe
IChart chart = slide.getShapes().addChart(ChartType.Pie, 100, 100, 400, 400);
```

Voeg een cirkeldiagram toe aan de dia op de opgegeven positie en grootte.

## Stap 5: Stel de grafiektitel in

```java
// Titel van grafiek instellen
chart.getChartTitle().addTextFrameForOverriding("Sample Title");
chart.getChartTitle().getTextFrameForOverriding().getTextFrameFormat().setCenterText(NullableBool.True);
chart.getChartTitle().setHeight(20);
chart.setTitle(true);
```

Geef een titel op voor het cirkeldiagram. U kunt de titel naar wens aanpassen.

## Stap 6: Grafiekgegevens aanpassen

```java
// Stel de eerste reeks in om waarden weer te geven
chart.getChartData().getSeries().get_Item(0).getLabels().getDefaultDataLabelFormat().setShowValue(true);

// De index van het grafiekgegevensblad instellen
int defaultWorksheetIndex = 0;

// Het werkblad met grafiekgegevens ophalen
IChartDataWorkbook workbook = chart.getChartData().getChartDataWorkbook();

// Standaard gegenereerde series en categorieën verwijderen
chart.getChartData().getSeries().clear();
chart.getChartData().getCategories().clear();

// Nieuwe categorieën toevoegen
chart.getChartData().getCategories().add(workbook.getCell(0, 1, 0, "First Qtr"));
chart.getChartData().getCategories().add(workbook.getCell(0, 2, 0, "2nd Qtr"));
chart.getChartData().getCategories().add(workbook.getCell(0, 3, 0, "3rd Qtr"));

// Nieuwe series toevoegen
IChartSeries series = chart.getChartData().getSeries().add(workbook.getCell(0, 0, 1, "Series 1"), chart.getType());

// Het vullen van reeksgegevens
series.getDataPoints().addDataPointForPieSeries(workbook.getCell(defaultWorksheetIndex, 1, 1, 20));
series.getDataPoints().addDataPointForPieSeries(workbook.getCell(defaultWorksheetIndex, 2, 1, 50));
series.getDataPoints().addDataPointForPieSeries(workbook.getCell(defaultWorksheetIndex, 3, 1, 30));
```

Pas de grafiekgegevens aan door categorieën en reeksen toe te voegen en hun waarden in te stellen. In dit voorbeeld hebben we drie categorieën en één reeks met bijbehorende datapunten.

## Stap 7: Sectoren van cirkeldiagrammen aanpassen

```java
// Sectorkleuren instellen
chart.getChartData().getSeriesGroups().get_Item(0).setColorVaried(true);

// Pas het uiterlijk van elke sector aan
IChartDataPoint point1 = series.getDataPoints().get_Item(0);
point1.getFormat().getFill().setFillType(FillType.Solid);
point1.getFormat().getFill().getSolidFillColor().setColor(new Color(PresetColor.Cyan));
// Sectorgrens aanpassen
point1.getFormat().getLine().getFillFormat().setFillType(FillType.Solid);
point1.getFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.GRAY);
point1.getFormat().getLine().setWidth(3.0);
point1.getFormat().getLine().setStyle(LineStyle.ThinThick);
point1.getFormat().getLine().setDashStyle(LineDashStyle.DashDot);

// Pas andere sectoren op een vergelijkbare manier aan
```

Pas het uiterlijk van elke sector in het cirkeldiagram aan. U kunt de kleuren, randstijlen en andere visuele eigenschappen wijzigen.

## Stap 8: Gegevenslabels aanpassen

```java
// Gegevenslabels aanpassen
IDataLabel lbl1 = series.getDataPoints().get_Item(0).getLabel();
lbl1.getDataLabelFormat().setShowValue(true);

// Pas op een vergelijkbare manier gegevenslabels aan voor andere datapunten
```

Pas de gegevenslabels voor elk gegevenspunt in het cirkeldiagram aan. U kunt bepalen welke waarden in het diagram worden weergegeven.

## Stap 9: Toon leiderlijnen

```java
// Toon leiderlijnen voor de grafiek
series.getLabels().getDefaultDataLabelFormat().setShowLeaderLines(true);
```

Schakel leiderlijnen in om gegevenslabels te verbinden met de bijbehorende sectoren.

## Stap 10: Stel de rotatiehoek van het cirkeldiagram in

```java
// Stel de rotatiehoek in voor cirkeldiagramsectoren
chart.getChartData().getSeriesGroups().get_Item(0).setFirstSliceAngle(180);
```

Stel de rotatiehoek voor de cirkeldiagramsectoren in. In dit voorbeeld stellen we deze in op 180 graden.

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
// Instantieer presentatieklasse die PPTX-bestand vertegenwoordigt
Presentation presentation = new Presentation();
// Toegang tot eerste dia
ISlide slides = presentation.getSlides().get_Item(0);
// Grafiek toevoegen met standaardgegevens
IChart chart = slides.getShapes().addChart(ChartType.Pie, 100, 100, 400, 400);
// Titel van de instellingsgrafiek
chart.getChartTitle().addTextFrameForOverriding("Sample Title");
chart.getChartTitle().getTextFrameForOverriding().getTextFrameFormat().setCenterText(NullableBool.True);
chart.getChartTitle().setHeight(20);
chart.setTitle(true);
// Stel de eerste reeks in op Waarden weergeven
chart.getChartData().getSeries().get_Item(0).getLabels().getDefaultDataLabelFormat().setShowValue(true);
// De index van het grafiekgegevensblad instellen
int defaultWorksheetIndex = 0;
// Het werkblad met grafiekgegevens ophalen
IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
// Standaard gegenereerde series en categorieën verwijderen
chart.getChartData().getSeries().clear();
chart.getChartData().getCategories().clear();
// Nieuwe categorieën toevoegen
chart.getChartData().getCategories().add(fact.getCell(0, 1, 0, "First Qtr"));
chart.getChartData().getCategories().add(fact.getCell(0, 2, 0, "2nd Qtr"));
chart.getChartData().getCategories().add(fact.getCell(0, 3, 0, "3rd Qtr"));
// Nieuwe series toevoegen
IChartSeries series = chart.getChartData().getSeries().add(fact.getCell(0, 0, 1, "Series 1"), chart.getType());
// Nu worden reeksgegevens ingevuld
series.getDataPoints().addDataPointForPieSeries(fact.getCell(defaultWorksheetIndex, 1, 1, 20));
series.getDataPoints().addDataPointForPieSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 50));
series.getDataPoints().addDataPointForPieSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 30));
// Werkt niet in nieuwe versie
// Nieuwe punten toevoegen en sectorkleur instellen
// serie.IsColorVaried = true;
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
// Maak aangepaste labels voor elke categorie voor nieuwe series
IDataLabel lbl1 = series.getDataPoints().get_Item(0).getLabel();
// lbl.setShowCategoryName(true);
lbl1.getDataLabelFormat().setShowValue(true);
IDataLabel lbl2 = series.getDataPoints().get_Item(1).getLabel();
lbl2.getDataLabelFormat().setShowValue(true);
lbl2.getDataLabelFormat().setShowLegendKey(true);
lbl2.getDataLabelFormat().setShowPercentage(true);
IDataLabel lbl3 = series.getDataPoints().get_Item(2).getLabel();
lbl3.getDataLabelFormat().setShowSeriesName(true);
lbl3.getDataLabelFormat().setShowPercentage(true);
// Leiderlijnen voor grafiek weergeven
series.getLabels().getDefaultDataLabelFormat().setShowLeaderLines(true);
// Rotatiehoek instellen voor cirkeldiagramsectoren
chart.getChartData().getSeriesGroups().get_Item(0).setFirstSliceAngle(180);
// Presentatie met grafiek opslaan
presentation.save(dataDir + "PieChart_out.pptx", SaveFormat.Pptx);
```

## Conclusie

U hebt met succes een cirkeldiagram gemaakt in een PowerPoint-presentatie met Aspose.Slides voor Java. U kunt het uiterlijk en de gegevenslabels van het diagram aanpassen aan uw specifieke wensen. Deze tutorial geeft een eenvoudig voorbeeld; u kunt uw diagrammen naar wens verder verbeteren en aanpassen.

## Veelgestelde vragen

### Hoe kan ik de kleuren van afzonderlijke sectoren in het cirkeldiagram wijzigen?

Om de kleuren van individuele sectoren in het cirkeldiagram te wijzigen, kunt u de opvulkleur voor elk gegevenspunt aanpassen. In het meegeleverde codevoorbeeld laten we zien hoe u de opvulkleur voor elke sector instelt met behulp van de `getSolidFillColor().setColor()` methode. U kunt de kleurwaarden wijzigen om het gewenste uiterlijk te bereiken.

### Kan ik meer categorieën en gegevensreeksen toevoegen aan het cirkeldiagram?

Ja, u kunt extra categorieën en gegevensreeksen toevoegen aan de cirkeldiagram. Hiervoor kunt u de `getChartData().getCategories().add()` En `getChartData().getSeries().add()` Methoden, zoals weergegeven in het voorbeeld. Geef eenvoudig de juiste gegevens en labels op voor de nieuwe categorieën en reeksen om uw grafiek uit te breiden.

### Hoe pas ik het uiterlijk van gegevenslabels aan?

U kunt het uiterlijk van gegevenslabels aanpassen met behulp van de `getDataLabelFormat()` methode op het label van elk datapunt. In het voorbeeld hebben we laten zien hoe je de waarde op datalabels kunt weergeven met behulp van `getDataLabelFormat().setShowValue(true)`U kunt gegevenslabels verder aanpassen door te bepalen welke waarden worden weergegeven, legendasleutels weer te geven en andere opmaakopties aan te passen.

### Kan ik de titel van het cirkeldiagram wijzigen?

Ja, u kunt de titel van het cirkeldiagram wijzigen. In de meegeleverde code stellen we de titel van het diagram in met `chart.getChartTitle().addTextFrameForOverriding("Sample Title")`. Je kunt vervangen `"Sample Title"` met de gewenste titeltekst.

### Hoe sla ik de gegenereerde presentatie met het cirkeldiagram op?

Om de presentatie met het cirkeldiagram op te slaan, gebruikt u de `presentation.save()` Methode. Geef het gewenste bestandspad en de gewenste bestandsnaam op, samen met het formaat waarin u de presentatie wilt opslaan. Bijvoorbeeld:
```java
presentation.save(dataDir + "PieChart_out.pptx", SaveFormat.Pptx);
```

Zorg ervoor dat u het juiste bestandspad en de juiste indeling opgeeft.

### Kan ik andere soorten grafieken maken met Aspose.Slides voor Java?

Ja, Aspose.Slides voor Java ondersteunt verschillende grafiektypen, waaronder staafdiagrammen, lijndiagrammen en meer. U kunt verschillende soorten grafieken maken door de `ChartType` Bij het toevoegen van een grafiek. Raadpleeg de Aspose.Slides-documentatie voor meer informatie over het maken van verschillende typen grafieken.

### Waar kan ik meer informatie en voorbeelden vinden over het werken met Aspose.Slides voor Java?

Voor meer informatie, gedetailleerde documentatie en extra voorbeelden kunt u terecht op de [Aspose.Slides voor Java-documentatie](https://reference.aspose.com/slides/java/)Het biedt uitgebreide bronnen om u te helpen de bibliotheek effectief te gebruiken.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}