---
"description": "Maak normale grafieken in Java Slides met Aspose.Slides voor Java. Stapsgewijze handleiding en broncode voor het maken, aanpassen en opslaan van grafieken in PowerPoint-presentaties."
"linktitle": "Normale grafieken in Java-dia's"
"second_title": "Aspose.Slides Java PowerPoint-verwerkings-API"
"title": "Normale grafieken in Java-dia's"
"url": "/nl/java/chart-data-manipulation/normal-charts-java-slides/"
"weight": 21
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Normale grafieken in Java-dia's


## Inleiding tot normale grafieken in Java-dia's

In deze tutorial doorlopen we het proces voor het maken van normale grafieken in Java Slides met behulp van de Aspose.Slides voor Java API. We gebruiken stapsgewijze instructies en broncode om te laten zien hoe je een geclusterde kolomgrafiek maakt in een PowerPoint-presentatie.

## Vereisten

Voordat u begint, moet u ervoor zorgen dat aan de volgende vereisten is voldaan:

1. Aspose.Slides voor Java API geïnstalleerd.
2. Er is een Java-ontwikkelomgeving opgezet.
3. Basiskennis van Java-programmering.

## Stap 1: Het project opzetten

Zorg ervoor dat je een map voor je project hebt. Laten we deze "Je Documentenmap" noemen, zoals vermeld in de code. Je kunt dit vervangen door het daadwerkelijke pad naar je projectmap.

```java
// Het pad naar de documentenmap.
String dataDir = "Your Document Directory";
// Maak een map aan als deze nog niet bestaat.
boolean IsExists = new File(dataDir).exists();
if (!IsExists)
    new File(dataDir).mkdirs();
```

## Stap 2: Een presentatie maken

Laten we nu een PowerPoint-presentatie maken en de eerste dia openen.

```java
// Instantieer presentatieklasse die PPTX-bestand vertegenwoordigt
Presentation pres = new Presentation();
// Toegang tot eerste dia
ISlide sld = pres.getSlides().get_Item(0);
```

## Stap 3: Een grafiek toevoegen

We voegen een geclusterde kolomgrafiek aan de dia toe en stellen de titel ervan in.

```java
// Grafiek toevoegen met standaardgegevens
IChart chart = sld.getShapes().addChart(ChartType.ClusteredColumn, 0, 0, 500, 500);
// Titel van de instellingsgrafiek
chart.getChartTitle().addTextFrameForOverriding("Sample Title");
chart.getChartTitle().getTextFrameForOverriding().getTextFrameFormat().setCenterText(NullableBool.True);
chart.getChartTitle().setHeight(20);
chart.setTitle(true);
```

## Stap 4: Grafiekgegevens instellen

Vervolgens stellen we de grafiekgegevens in door reeksen en categorieën te definiëren.

```java
// Stel de eerste reeks in op Waarden weergeven
chart.getChartData().getSeries().get_Item(0).getLabels().getDefaultDataLabelFormat().setShowValue(true);

// De index van het grafiekgegevensblad instellen
int defaultWorksheetIndex = 0;

// Het werkblad met grafiekgegevens ophalen
IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();

// Standaard gegenereerde series en categorieën verwijderen
chart.getChartData().getSeries().clear();
chart.getChartData().getCategories().clear();

// Nieuwe series toevoegen
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 1, "Series 1"), chart.getType());
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 2, "Series 2"), chart.getType());

// Nieuwe categorieën toevoegen
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 1, 0, "Category 1"));
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 2, 0, "Category 2"));
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 3, 0, "Category 3"));
```

## Stap 5: Reeksgegevens vullen

Laten we nu de reeksgegevenspunten voor de grafiek invullen.

```java
// Neem de eerste grafiekserie
IChartSeries series = chart.getChartData().getSeries().get_Item(0);

// Het vullen van reeksgegevens
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 1, 20));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 50));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 30));

// Vulkleur instellen voor reeksen
series.getFormat().getFill().setFillType(FillType.Solid);
series.getFormat().getFill().getSolidFillColor().setColor(Color.RED);

// Neem de tweede grafiekserie
series = chart.getChartData().getSeries().get_Item(1);

// Het vullen van reeksgegevens
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 2, 30));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 2, 10));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 2, 60));

// Vulkleur instellen voor reeksen
series.getFormat().getFill().setFillType(FillType.Solid);
series.getFormat().getFill().getSolidFillColor().setColor(Color.GREEN);
```

## Stap 6: Labels aanpassen

Laten we de gegevenslabels voor de diagramreeks aanpassen.

```java
// Het eerste label toont de categorienaam
IDataLabel lbl = series.getDataPoints().get_Item(0).getLabel();
lbl.getDataLabelFormat().setShowCategoryName(true);

lbl = series.getDataPoints().get_Item(1).getLabel();
lbl.getDataLabelFormat().setShowSeriesName(true);

// Toon waarde voor het derde label met reeksnaam en scheidingsteken
lbl = series.getDataPoints().get_Item(2).getLabel();
lbl.getDataLabelFormat().setShowValue(true);
lbl.getDataLabelFormat().setShowSeriesName(true);
lbl.getDataLabelFormat().setSeparator("/");
```

## Stap 7: De presentatie opslaan

Sla ten slotte de presentatie met de grafiek op in uw projectmap.

```java
pres.save(dataDir + "AsposeChart_out.pptx", SaveFormat.Pptx);
```

Dat is alles! Je hebt met succes een geclusterde kolomgrafiek gemaakt in een PowerPoint-presentatie met Aspose.Slides voor Java. Je kunt deze grafiek verder naar wens aanpassen.

## Volledige broncode voor normale grafieken in Java-dia's

```java
// Het pad naar de documentenmap.
String dataDir = "Your Document Directory";
// Maak een map aan als deze nog niet bestaat.
boolean IsExists = new File(dataDir).exists();
if (!IsExists)
	new File(dataDir).mkdirs();
// Instantieer presentatieklasse die PPTX-bestand vertegenwoordigt
Presentation pres = new Presentation();
// Toegang tot eerste dia
ISlide sld = pres.getSlides().get_Item(0);
// Grafiek toevoegen met standaardgegevens
IChart chart = sld.getShapes().addChart(ChartType.ClusteredColumn, 0, 0, 500, 500);
// Titel van de instellingsgrafiek
// Chart.getChartTitle().getTextFrameForOverriding().setText("Voorbeeldtitel");
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
int s = chart.getChartData().getSeries().size();
s = chart.getChartData().getCategories().size();
// Nieuwe series toevoegen
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 1, "Series 1"), chart.getType());
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 2, "Series 2"), chart.getType());
// Nieuwe categorieën toevoegen
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 1, 0, "Caetegoty 1"));
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 2, 0, "Caetegoty 2"));
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 3, 0, "Caetegoty 3"));
// Neem de eerste grafiekserie
IChartSeries series = chart.getChartData().getSeries().get_Item(0);
// Nu worden reeksgegevens ingevuld
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 1, 20));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 50));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 30));
// Vulkleur instellen voor reeksen
series.getFormat().getFill().setFillType(FillType.Solid);
series.getFormat().getFill().getSolidFillColor().setColor(Color.RED);
// Neem de tweede grafiekserie
series = chart.getChartData().getSeries().get_Item(1);
// Nu worden reeksgegevens ingevuld
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 2, 30));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 2, 10));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 2, 60));
// Vulkleur instellen voor reeksen
series.getFormat().getFill().setFillType(FillType.Solid);
series.getFormat().getFill().getSolidFillColor().setColor(Color.GREEN);
// Het eerste label zal de categorienaam weergeven
IDataLabel lbl = series.getDataPoints().get_Item(0).getLabel();
lbl.getDataLabelFormat().setShowCategoryName(true);
lbl = series.getDataPoints().get_Item(1).getLabel();
lbl.getDataLabelFormat().setShowSeriesName(true);
// Toon waarde voor derde label
lbl = series.getDataPoints().get_Item(2).getLabel();
lbl.getDataLabelFormat().setShowValue(true);
lbl.getDataLabelFormat().setShowSeriesName(true);
lbl.getDataLabelFormat().setSeparator("/");
// Presentatie met grafiek opslaan
pres.save(dataDir + "AsposeChart_out.pptx", SaveFormat.Pptx);
```
# Conclusie

In deze tutorial hebben we geleerd hoe je normale grafieken maakt in Java Slides met behulp van de Aspose.Slides voor Java API. We hebben een stapsgewijze handleiding met broncode doorlopen om een geclusterde kolomgrafiek te maken in een PowerPoint-presentatie.

## Veelgestelde vragen

### Hoe kan ik het grafiektype wijzigen?

Om het grafiektype te wijzigen, wijzigt u de `ChartType` parameter bij het toevoegen van de grafiek met behulp van `sld.getShapes().addChart()`U kunt kiezen uit verschillende grafiektypen die beschikbaar zijn in Aspose.Slides.

### Kan ik de kleuren van de diagramserie wijzigen?

Ja, u kunt de kleuren van de grafiekserie wijzigen door de vulkleur voor elke serie in te stellen met `series.getFormat().getFill().getSolidFillColor().setColor(Color.YOUR_COLOR)`.

### Hoe voeg ik meer categorieën of series toe aan de grafiek?

U kunt meer categorieën of reeksen aan de grafiek toevoegen door nieuwe gegevenspunten en labels toe te voegen met behulp van de `chart.getChartData().getCategories().add()` En `chart.getChartData().getSeries().add()` methoden.

### Hoe kan ik de grafiektitel verder aanpassen?

U kunt de grafiektitel verder aanpassen door de eigenschappen van `chart.getChartTitle()` zoals tekstuitlijning, lettergrootte en kleur.

### Hoe kan ik de grafiek opslaan in een ander bestandsformaat?

Om de grafiek in een ander bestandsformaat op te slaan, wijzigt u de `SaveFormat` parameter in de `pres.save()` methode naar het gewenste formaat (bijv. PDF, PNG, JPEG).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}