---
title: Gegevenslabels instellen Percentage Aanmelden in Java-dia's
linktitle: Gegevenslabels instellen Percentage Aanmelden in Java-dia's
second_title: Aspose.Slides Java PowerPoint-verwerkings-API
description: Leer hoe u gegevenslabels met procenttekens instelt in PowerPoint-presentaties met Aspose.Slides voor Java. Maak boeiende grafieken met stapsgewijze begeleiding en broncode.
weight: 17
url: /nl/java/data-manipulation/set-data-labels-percentage-sign-java-slides/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}


## Inleiding tot het instellen van gegevenslabels Percentage-aanmelding in Aspose.Slides voor Java

In deze handleiding begeleiden we u door het proces van het instellen van gegevenslabels met een percentageteken met behulp van Aspose.Slides voor Java. We gaan een PowerPoint-presentatie maken met een gestapeld kolomdiagram en gegevenslabels configureren om percentages weer te geven.

## Vereisten

 Voordat u begint, moet u ervoor zorgen dat de Aspose.Slides voor Java-bibliotheek aan uw project is toegevoegd. Je kunt het downloaden van[hier](https://releases.aspose.com/slides/java/).

## Stap 1: Maak een nieuwe presentatie

Eerst maken we een nieuwe PowerPoint-presentatie met Aspose.Slides.

```java
// Het pad naar de documentenmap.
String dataDir = "Your Document Directory";
// Maak een exemplaar van de presentatieklasse
Presentation presentation = new Presentation();
```

## Stap 2: Voeg een dia en grafiek toe

Vervolgens voegen we een dia en een gestapeld kolomdiagram toe aan de presentatie.

```java
// Referentie van de dia opvragen
ISlide slide = presentation.getSlides().get_Item(0);

// Voeg PercentsStackedColumn-diagram toe aan een dia
IChart chart = slide.getShapes().addChart(ChartType.PercentsStackedColumn, 20, 20, 500, 400);
```

## Stap 3: Configureer het asnummerformaat

Om percentages weer te geven, moeten we de getalnotatie voor de verticale as van het diagram configureren.

```java
// Stel NumberFormatLinkedToSource in op false
chart.getAxes().getVerticalAxis().setNumberFormatLinkedToSource(false);
chart.getAxes().getVerticalAxis().setNumberFormat("0.00%");
```

## Stap 4: Voeg grafiekgegevens toe

We voegen gegevens aan het diagram toe door reeksen en gegevenspunten te maken. In dit voorbeeld voegen we twee reeksen toe met hun respectievelijke gegevenspunten.

```java
// Het werkblad met diagramgegevens ophalen
IChartDataWorkbook workbook = chart.getChartData().getChartDataWorkbook();

// Nieuwe serie toevoegen
IChartSeries series = chart.getChartData().getSeries().add(workbook.getCell(defaultWorksheetIndex, 0, 1, "Reds"), chart.getType());
series.getDataPoints().addDataPointForBarSeries(workbook.getCell(defaultWorksheetIndex, 1, 1, 0.30));
series.getDataPoints().addDataPointForBarSeries(workbook.getCell(defaultWorksheetIndex, 2, 1, 0.50));
series.getDataPoints().addDataPointForBarSeries(workbook.getCell(defaultWorksheetIndex, 3, 1, 0.80));
series.getDataPoints().addDataPointForBarSeries(workbook.getCell(defaultWorksheetIndex, 4, 1, 0.65));

// Nieuwe serie toevoegen
IChartSeries series2 = chart.getChartData().getSeries().add(workbook.getCell(defaultWorksheetIndex, 0, 2, "Blues"), chart.getType());
series2.getDataPoints().addDataPointForBarSeries(workbook.getCell(defaultWorksheetIndex, 1, 2, 0.70));
series2.getDataPoints().addDataPointForBarSeries(workbook.getCell(defaultWorksheetIndex, 2, 2, 0.50));
series2.getDataPoints().addDataPointForBarSeries(workbook.getCell(defaultWorksheetIndex, 3, 2, 0.20));
series2.getDataPoints().addDataPointForBarSeries(workbook.getCell(defaultWorksheetIndex, 4, 2, 0.35));
```

## Stap 5: Gegevenslabels aanpassen

Laten we nu het uiterlijk van de gegevenslabels aanpassen.

```java
// LabelFormat-eigenschappen instellen
series.getLabels().getDefaultDataLabelFormat().setShowValue(true);
series.getLabels().getDefaultDataLabelFormat().setNumberFormatLinkedToSource(false);
series.getLabels().getDefaultDataLabelFormat().setNumberFormat("0.0%");
series.getLabels().getDefaultDataLabelFormat().getTextFormat().getPortionFormat().setFontHeight(10);
series.getLabels().getDefaultDataLabelFormat().getTextFormat().getPortionFormat().getFillFormat().setFillType(FillType.Solid);
series.getLabels().getDefaultDataLabelFormat().getTextFormat().getPortionFormat().getFillFormat().getSolidFillColor().setColor(Color.WHITE);
series.getLabels().getDefaultDataLabelFormat().setShowValue(true);

series2.getLabels().getDefaultDataLabelFormat().setShowValue(true);
series2.getLabels().getDefaultDataLabelFormat().setNumberFormatLinkedToSource(false);
series2.getLabels().getDefaultDataLabelFormat().setNumberFormat("0.0%");
series2.getLabels().getDefaultDataLabelFormat().getTextFormat().getPortionFormat().setFontHeight(10);
series2.getLabels().getDefaultDataLabelFormat().getTextFormat().getPortionFormat().getFillFormat().setFillType(FillType.Solid);
series2.getLabels().getDefaultDataLabelFormat().getTextFormat().getPortionFormat().getFillFormat().getSolidFillColor().setColor(Color.WHITE);
```

## Stap 6: Sla de presentatie op

Ten slotte slaan we de presentatie op in een PowerPoint-bestand.

```java
// Presentatie naar schijf schrijven
presentation.save(dataDir + "SetDataLabelsPercentageSign_out.pptx", SaveFormat.Pptx);
```

Dat is het! U hebt met succes een PowerPoint-presentatie gemaakt met een gestapeld kolomdiagram en gegevenslabels geconfigureerd om percentages weer te geven met behulp van Aspose.Slides voor Java.

## Volledige broncode voor ingestelde gegevenslabels Percentage aanmelden in Java-dia's

```java
// Het pad naar de documentenmap.
String dataDir = "Your Document Directory";
// Maak een exemplaar van de presentatieklasse
Presentation presentation = new Presentation();
// Referentie van de dia opvragen
ISlide slide = presentation.getSlides().get_Item(0);
// Voeg PercentsStackedColumn-diagram toe aan een dia
IChart chart = slide.getShapes().addChart(ChartType.PercentsStackedColumn, 20, 20, 500, 400);
// Stel NumberFormatLinkedToSource in op false
chart.getAxes().getVerticalAxis().setNumberFormatLinkedToSource(false);
chart.getAxes().getVerticalAxis().setNumberFormat("0.00%");
chart.getChartData().getSeries().clear();
int defaultWorksheetIndex = 0;
// Het werkblad met diagramgegevens ophalen
IChartDataWorkbook workbook = chart.getChartData().getChartDataWorkbook();
// Nieuwe serie toevoegen
IChartSeries series = chart.getChartData().getSeries().add(workbook.getCell(defaultWorksheetIndex, 0, 1, "Reds"), chart.getType());
series.getDataPoints().addDataPointForBarSeries(workbook.getCell(defaultWorksheetIndex, 1, 1, 0.30));
series.getDataPoints().addDataPointForBarSeries(workbook.getCell(defaultWorksheetIndex, 2, 1, 0.50));
series.getDataPoints().addDataPointForBarSeries(workbook.getCell(defaultWorksheetIndex, 3, 1, 0.80));
series.getDataPoints().addDataPointForBarSeries(workbook.getCell(defaultWorksheetIndex, 4, 1, 0.65));
// De vulkleur van series instellen
series.getFormat().getFill().setFillType(FillType.Solid);
series.getFormat().getFill().getSolidFillColor().setColor(Color.RED);
// LabelFormat-eigenschappen instellen
series.getLabels().getDefaultDataLabelFormat().setShowValue(true);
series.getLabels().getDefaultDataLabelFormat().setNumberFormatLinkedToSource(false);
series.getLabels().getDefaultDataLabelFormat().setNumberFormat("0.0%");
series.getLabels().getDefaultDataLabelFormat().getTextFormat().getPortionFormat().setFontHeight(10);
series.getLabels().getDefaultDataLabelFormat().getTextFormat().getPortionFormat().getFillFormat().setFillType(FillType.Solid);
series.getLabels().getDefaultDataLabelFormat().getTextFormat().getPortionFormat().getFillFormat().getSolidFillColor().setColor(Color.WHITE);
series.getLabels().getDefaultDataLabelFormat().setShowValue(true);
// Nieuwe serie toevoegen
IChartSeries series2 = chart.getChartData().getSeries().add(workbook.getCell(defaultWorksheetIndex, 0, 2, "Blues"), chart.getType());
series2.getDataPoints().addDataPointForBarSeries(workbook.getCell(defaultWorksheetIndex, 1, 2, 0.70));
series2.getDataPoints().addDataPointForBarSeries(workbook.getCell(defaultWorksheetIndex, 2, 2, 0.50));
series2.getDataPoints().addDataPointForBarSeries(workbook.getCell(defaultWorksheetIndex, 3, 2, 0.20));
series2.getDataPoints().addDataPointForBarSeries(workbook.getCell(defaultWorksheetIndex, 4, 2, 0.35));
// Vultype en kleur instellen
series2.getFormat().getFill().setFillType(FillType.Solid);
series2.getFormat().getFill().getSolidFillColor().setColor(Color.BLUE);
series2.getLabels().getDefaultDataLabelFormat().setShowValue(true);
series2.getLabels().getDefaultDataLabelFormat().setNumberFormatLinkedToSource(false);
series2.getLabels().getDefaultDataLabelFormat().setNumberFormat("0.0%");
series2.getLabels().getDefaultDataLabelFormat().getTextFormat().getPortionFormat().setFontHeight(10);
series2.getLabels().getDefaultDataLabelFormat().getTextFormat().getPortionFormat().getFillFormat().setFillType(FillType.Solid);
series2.getLabels().getDefaultDataLabelFormat().getTextFormat().getPortionFormat().getFillFormat().getSolidFillColor().setColor(Color.WHITE);
// Presentatie naar schijf schrijven
presentation.save(dataDir + "SetDataLabelsPercentageSign_out.pptx", SaveFormat.Pptx);
```

## Conclusie

Door deze handleiding te volgen, heeft u geleerd hoe u boeiende presentaties kunt maken met op percentages gebaseerde gegevenslabels, wat vooral handig kan zijn voor het effectief overbrengen van informatie in bedrijfsrapporten, educatief materiaal en meer.

## Veelgestelde vragen

### Hoe kan ik de kleuren van de kaartenserie wijzigen?

 U kunt de vulkleur van diagramreeksen wijzigen met behulp van de`setFill` methode zoals weergegeven in het voorbeeld.

### Kan ik de lettergrootte van de gegevenslabels aanpassen?

Ja, u kunt de lettergrootte van gegevenslabels aanpassen door de`setFontHeight` eigenschap zoals gedemonstreerd in de code.

### Hoe kan ik meer series aan het diagram toevoegen?

 U kunt extra reeksen aan het diagram toevoegen met behulp van de`add` methode op de`IChartSeriesCollection` voorwerp.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
