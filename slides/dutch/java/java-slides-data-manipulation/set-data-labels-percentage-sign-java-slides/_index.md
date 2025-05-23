---
"description": "Leer hoe u gegevenslabels met procenttekens instelt in PowerPoint-presentaties met Aspose.Slides voor Java. Maak boeiende grafieken met stapsgewijze instructies en broncode."
"linktitle": "Gegevenslabels instellen Percentageteken in Java-dia's"
"second_title": "Aspose.Slides Java PowerPoint-verwerkings-API"
"title": "Gegevenslabels instellen Percentageteken in Java-dia's"
"url": "/nl/java/data-manipulation/set-data-labels-percentage-sign-java-slides/"
"weight": 17
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Gegevenslabels instellen Percentageteken in Java-dia's


## Inleiding tot het instellen van gegevenslabels met percentagetekens in Aspose.Slides voor Java

In deze handleiding leiden we je door het proces van het instellen van gegevenslabels met een percentageteken met behulp van Aspose.Slides voor Java. We maken een PowerPoint-presentatie met een gestapelde kolomgrafiek en configureren gegevenslabels om percentages weer te geven.

## Vereisten

Voordat u begint, moet u ervoor zorgen dat u de Aspose.Slides voor Java-bibliotheek aan uw project hebt toegevoegd. U kunt deze downloaden van [hier](https://releases.aspose.com/slides/java/).

## Stap 1: Een nieuwe presentatie maken

Eerst maken we een nieuwe PowerPoint-presentatie met behulp van Aspose.Slides.

```java
// Het pad naar de documentenmap.
String dataDir = "Your Document Directory";
// Een exemplaar van de presentatieklasse maken
Presentation presentation = new Presentation();
```

## Stap 2: Voeg een dia en grafiek toe

Vervolgens voegen we een dia en een gestapeld kolomdiagram toe aan de presentatie.

```java
// Verkrijg een referentie van de dia
ISlide slide = presentation.getSlides().get_Item(0);

// PercentsStackedColumn-diagram toevoegen aan een dia
IChart chart = slide.getShapes().addChart(ChartType.PercentsStackedColumn, 20, 20, 500, 400);
```

## Stap 3: Asnummerformaat configureren

Om percentages weer te geven, moeten we de getalnotatie voor de verticale as van de grafiek configureren.

```java
// Stel NumberFormatLinkedToSource in op false
chart.getAxes().getVerticalAxis().setNumberFormatLinkedToSource(false);
chart.getAxes().getVerticalAxis().setNumberFormat("0.00%");
```

## Stap 4: Grafiekgegevens toevoegen

We voegen gegevens toe aan de grafiek door reeksen en datapunten te creëren. In dit voorbeeld voegen we twee reeksen toe met hun bijbehorende datapunten.

```java
// Het werkblad met grafiekgegevens ophalen
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

Dat is alles! U hebt met succes een PowerPoint-presentatie gemaakt met een gestapelde kolomgrafiek en geconfigureerde gegevenslabels om percentages weer te geven met behulp van Aspose.Slides voor Java.

## Volledige broncode voor het instellen van gegevenslabels met percentagetekens in Java-dia's

```java
// Het pad naar de documentenmap.
String dataDir = "Your Document Directory";
// Een exemplaar van de presentatieklasse maken
Presentation presentation = new Presentation();
// Verkrijg een referentie van de dia
ISlide slide = presentation.getSlides().get_Item(0);
// PercentsStackedColumn-diagram toevoegen aan een dia
IChart chart = slide.getShapes().addChart(ChartType.PercentsStackedColumn, 20, 20, 500, 400);
// Stel NumberFormatLinkedToSource in op false
chart.getAxes().getVerticalAxis().setNumberFormatLinkedToSource(false);
chart.getAxes().getVerticalAxis().setNumberFormat("0.00%");
chart.getChartData().getSeries().clear();
int defaultWorksheetIndex = 0;
// Het werkblad met grafiekgegevens ophalen
IChartDataWorkbook workbook = chart.getChartData().getChartDataWorkbook();
// Nieuwe serie toevoegen
IChartSeries series = chart.getChartData().getSeries().add(workbook.getCell(defaultWorksheetIndex, 0, 1, "Reds"), chart.getType());
series.getDataPoints().addDataPointForBarSeries(workbook.getCell(defaultWorksheetIndex, 1, 1, 0.30));
series.getDataPoints().addDataPointForBarSeries(workbook.getCell(defaultWorksheetIndex, 2, 1, 0.50));
series.getDataPoints().addDataPointForBarSeries(workbook.getCell(defaultWorksheetIndex, 3, 1, 0.80));
series.getDataPoints().addDataPointForBarSeries(workbook.getCell(defaultWorksheetIndex, 4, 1, 0.65));
// De vulkleur van een reeks instellen
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

Met behulp van deze handleiding hebt u geleerd hoe u aantrekkelijke presentaties kunt maken met op percentages gebaseerde gegevenslabels. Deze presentaties zijn vooral handig om informatie op een effectieve manier over te brengen in bedrijfsrapporten, educatieve materialen en meer.

## Veelgestelde vragen

### Hoe kan ik de kleuren van de grafiekserie wijzigen?

U kunt de vulkleur van diagramreeksen wijzigen met behulp van de `setFill` methode zoals getoond in het voorbeeld.

### Kan ik de lettergrootte van de gegevenslabels aanpassen?

Ja, u kunt de lettergrootte van gegevenslabels aanpassen door de `setFontHeight` eigenschap zoals gedemonstreerd in de code.

### Hoe kan ik meer series aan de grafiek toevoegen?

U kunt extra series aan de grafiek toevoegen met behulp van de `add` methode op de `IChartSeriesCollection` voorwerp.


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}