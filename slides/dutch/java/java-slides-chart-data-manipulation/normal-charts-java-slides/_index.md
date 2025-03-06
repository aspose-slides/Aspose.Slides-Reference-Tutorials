---
title: Normale grafieken in Java-dia's
linktitle: Normale grafieken in Java-dia's
second_title: Aspose.Slides Java PowerPoint-verwerkings-API
description: Maak normale grafieken in Java-dia's met Aspose.Slides voor Java. Stapsgewijze handleiding en broncode voor het maken, aanpassen en opslaan van diagrammen in PowerPoint-presentaties.
weight: 21
url: /nl/java/chart-data-manipulation/normal-charts-java-slides/
---

{< blocks/products/pf/main-wrap-class >}
{< blocks/products/pf/main-container >}
{< blocks/products/pf/tutorial-page-section >}


## Inleiding tot normale diagrammen in Java-dia's

In deze zelfstudie doorlopen we het proces van het maken van normale diagrammen in Java Slides met behulp van de Aspose.Slides voor Java API. We zullen stapsgewijze instructies samen met de broncode gebruiken om te demonstreren hoe u een geclusterd kolomdiagram in een PowerPoint-presentatie kunt maken.

## Vereisten

Voordat u begint, moet u ervoor zorgen dat u aan de volgende vereisten voldoet:

1. Aspose.Slides voor Java API geïnstalleerd.
2. Er is een Java-ontwikkelomgeving opgezet.
3. Basiskennis van Java-programmeren.

## Stap 1: Het project opzetten

Zorg ervoor dat u een map voor uw project hebt. Laten we het "Uw documentenmap" noemen, zoals vermeld in de code. U kunt dit vervangen door het daadwerkelijke pad naar uw projectmap.

```java
// Het pad naar de documentenmap.
String dataDir = "Your Document Directory";
// Maak een directory aan als deze nog niet aanwezig is.
boolean IsExists = new File(dataDir).exists();
if (!IsExists)
    new File(dataDir).mkdirs();
```

## Stap 2: Een presentatie maken

Laten we nu een PowerPoint-presentatie maken en de eerste dia openen.

```java
// Instantieer de presentatieklasse die het PPTX-bestand vertegenwoordigt
Presentation pres = new Presentation();
// Toegang tot de eerste dia
ISlide sld = pres.getSlides().get_Item(0);
```

## Stap 3: Een diagram toevoegen

We voegen een geclusterd kolomdiagram toe aan de dia en stellen de titel in.

```java
// Diagram met standaardgegevens toevoegen
IChart chart = sld.getShapes().addChart(ChartType.ClusteredColumn, 0, 0, 500, 500);
// Instelschema Titel
chart.getChartTitle().addTextFrameForOverriding("Sample Title");
chart.getChartTitle().getTextFrameForOverriding().getTextFrameFormat().setCenterText(NullableBool.True);
chart.getChartTitle().setHeight(20);
chart.setTitle(true);
```

## Stap 4: Grafiekgegevens instellen

Vervolgens zullen we de grafiekgegevens instellen door series en categorieën te definiëren.

```java
// Stel de eerste reeks in op Waarden tonen
chart.getChartData().getSeries().get_Item(0).getLabels().getDefaultDataLabelFormat().setShowValue(true);

// De index van het kaartgegevensblad instellen
int defaultWorksheetIndex = 0;

// Het werkblad met diagramgegevens ophalen
IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();

// Verwijder standaard gegenereerde series en categorieën
chart.getChartData().getSeries().clear();
chart.getChartData().getCategories().clear();

// Nieuwe serie toevoegen
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 1, "Series 1"), chart.getType());
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 2, "Series 2"), chart.getType());

// Nieuwe categorieën toevoegen
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 1, 0, "Category 1"));
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 2, 0, "Category 2"));
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 3, 0, "Category 3"));
```

## Stap 5: Seriegegevens invullen

Laten we nu de reeksgegevenspunten voor het diagram invullen.

```java
// Neem de eerste kaartenreeks
IChartSeries series = chart.getChartData().getSeries().get_Item(0);

// Reeksgegevens invullen
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 1, 20));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 50));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 30));

// Vulkleur voor series instellen
series.getFormat().getFill().setFillType(FillType.Solid);
series.getFormat().getFill().getSolidFillColor().setColor(Color.RED);

// Neem de tweede kaartenreeks
series = chart.getChartData().getSeries().get_Item(1);

// Reeksgegevens invullen
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 2, 30));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 2, 10));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 2, 60));

// Vulkleur voor series instellen
series.getFormat().getFill().setFillType(FillType.Solid);
series.getFormat().getFill().getSolidFillColor().setColor(Color.GREEN);
```

## Stap 6: Etiketten aanpassen

Laten we de gegevenslabels voor de diagramreeksen aanpassen.

```java
// Het eerste label toont de categorienaam
IDataLabel lbl = series.getDataPoints().get_Item(0).getLabel();
lbl.getDataLabelFormat().setShowCategoryName(true);

lbl = series.getDataPoints().get_Item(1).getLabel();
lbl.getDataLabelFormat().setShowSeriesName(true);

// Toon waarde voor het derde label met serienaam en scheidingsteken
lbl = series.getDataPoints().get_Item(2).getLabel();
lbl.getDataLabelFormat().setShowValue(true);
lbl.getDataLabelFormat().setShowSeriesName(true);
lbl.getDataLabelFormat().setSeparator("/");
```

## Stap 7: De presentatie opslaan

Sla ten slotte de presentatie met het diagram op in uw projectmap.

```java
pres.save(dataDir + "AsposeChart_out.pptx", SaveFormat.Pptx);
```

Dat is het! U hebt met succes een geclusterd kolomdiagram gemaakt in een PowerPoint-presentatie met Aspose.Slides voor Java. U kunt dit diagram verder aanpassen aan uw wensen.

## Volledige broncode voor normale grafieken in Java-dia's

```java
// Het pad naar de documentenmap.
String dataDir = "Your Document Directory";
// Maak een directory aan als deze nog niet aanwezig is.
boolean IsExists = new File(dataDir).exists();
if (!IsExists)
	new File(dataDir).mkdirs();
// Instantieer de presentatieklasse die het PPTX-bestand vertegenwoordigt
Presentation pres = new Presentation();
// Toegang tot de eerste dia
ISlide sld = pres.getSlides().get_Item(0);
// Diagram met standaardgegevens toevoegen
IChart chart = sld.getShapes().addChart(ChartType.ClusteredColumn, 0, 0, 500, 500);
// Instelschema Titel
// Chart.getChartTitle().getTextFrameForOverriding().setText("Voorbeeldtitel");
chart.getChartTitle().addTextFrameForOverriding("Sample Title");
chart.getChartTitle().getTextFrameForOverriding().getTextFrameFormat().setCenterText(NullableBool.True);
chart.getChartTitle().setHeight(20);
chart.setTitle(true);
// Stel de eerste reeks in op Waarden tonen
chart.getChartData().getSeries().get_Item(0).getLabels().getDefaultDataLabelFormat().setShowValue(true);
// De index van het kaartgegevensblad instellen
int defaultWorksheetIndex = 0;
// Het werkblad met diagramgegevens ophalen
IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
// Verwijder standaard gegenereerde series en categorieën
chart.getChartData().getSeries().clear();
chart.getChartData().getCategories().clear();
int s = chart.getChartData().getSeries().size();
s = chart.getChartData().getCategories().size();
// Nieuwe serie toevoegen
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 1, "Series 1"), chart.getType());
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 2, "Series 2"), chart.getType());
// Nieuwe categorieën toevoegen
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 1, 0, "Caetegoty 1"));
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 2, 0, "Caetegoty 2"));
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 3, 0, "Caetegoty 3"));
// Neem de eerste kaartenreeks
IChartSeries series = chart.getChartData().getSeries().get_Item(0);
// Vult nu seriegegevens in
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 1, 20));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 50));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 30));
// Vulkleur voor series instellen
series.getFormat().getFill().setFillType(FillType.Solid);
series.getFormat().getFill().getSolidFillColor().setColor(Color.RED);
// Neem de tweede kaartenreeks
series = chart.getChartData().getSeries().get_Item(1);
// Vult nu seriegegevens in
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 2, 30));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 2, 10));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 2, 60));
// Vulkleur voor series instellen
series.getFormat().getFill().setFillType(FillType.Solid);
series.getFormat().getFill().getSolidFillColor().setColor(Color.GREEN);
// Het eerste label is de categorienaam
IDataLabel lbl = series.getDataPoints().get_Item(0).getLabel();
lbl.getDataLabelFormat().setShowCategoryName(true);
lbl = series.getDataPoints().get_Item(1).getLabel();
lbl.getDataLabelFormat().setShowSeriesName(true);
// Toon waarde voor derde label
lbl = series.getDataPoints().get_Item(2).getLabel();
lbl.getDataLabelFormat().setShowValue(true);
lbl.getDataLabelFormat().setShowSeriesName(true);
lbl.getDataLabelFormat().setSeparator("/");
// Presentatie opslaan met grafiek
pres.save(dataDir + "AsposeChart_out.pptx", SaveFormat.Pptx);
```
# Conclusie

In deze zelfstudie hebben we geleerd hoe u normale diagrammen in Java Slides kunt maken met behulp van de Aspose.Slides voor Java API. We hebben een stapsgewijze handleiding met broncode doorlopen om een geclusterd kolomdiagram in een PowerPoint-presentatie te maken.

## Veelgestelde vragen

### Hoe kan ik het diagramtype wijzigen?

 Als u het diagramtype wilt wijzigen, wijzigt u het`ChartType`parameter bij het toevoegen van het diagram met behulp van`sld.getShapes().addChart()`. U kunt kiezen uit verschillende diagramtypen die beschikbaar zijn in Aspose.Slides.

### Kan ik de kleuren van de kaartenserie wijzigen?

 Ja, u kunt de kleuren van de diagramreeksen wijzigen door de vulkleur voor elke reeks in te stellen met behulp van`series.getFormat().getFill().getSolidFillColor().setColor(Color.YOUR_COLOR)`.

### Hoe voeg ik meer categorieën of series toe aan het diagram?

 U kunt meer categorieën of reeksen aan het diagram toevoegen door nieuwe gegevenspunten en labels toe te voegen met behulp van de`chart.getChartData().getCategories().add()` En`chart.getChartData().getSeries().add()` methoden.

### Hoe kan ik de diagramtitel verder aanpassen?

 U kunt de diagramtitel verder aanpassen door de eigenschappen van te wijzigen`chart.getChartTitle()` zoals tekstuitlijning, lettergrootte en kleur.

### Hoe sla ik het diagram op in een ander bestandsformaat?

 Om het diagram in een ander bestandsformaat op te slaan, wijzigt u de`SaveFormat` parameter in de`pres.save()` methode naar het gewenste formaat (bijvoorbeeld PDF, PNG, JPEG).
{< /blocks/products/pf/tutorial-page-section >}

{< /blocks/products/pf/main-container >}
{< /blocks/products/pf/main-wrap-class >}

{< blocks/products/products-backtop-button >}
