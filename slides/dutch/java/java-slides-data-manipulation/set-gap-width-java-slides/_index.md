---
"description": "Leer hoe u de tussenruimte in Java Slides instelt met Aspose.Slides voor Java. Verbeter de grafiekweergave in uw PowerPoint-presentaties."
"linktitle": "Gapbreedte instellen in Java-dia's"
"second_title": "Aspose.Slides Java PowerPoint-verwerkings-API"
"title": "Gapbreedte instellen in Java-dia's"
"url": "/nl/java/data-manipulation/set-gap-width-java-slides/"
"weight": 21
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Gapbreedte instellen in Java-dia's


## Inleiding tot het instellen van de spleetbreedte in Aspose.Slides voor Java

In deze tutorial begeleiden we je door het proces van het instellen van de tussenruimte voor een grafiek in een PowerPoint-presentatie met behulp van Aspose.Slides voor Java. De tussenruimte bepaalt de afstand tussen de kolommen of balken in een grafiek, zodat je de visuele weergave van de grafiek kunt bepalen.

## Vereisten

Voordat u begint, moet u ervoor zorgen dat de Aspose.Slides for Java-bibliotheek is geïnstalleerd. U kunt deze downloaden van de Aspose-website. [hier](https://releases.aspose.com/slides/java/).

## Stapsgewijze handleiding

Volg deze stappen om de tussenruimtebreedte in een grafiek in te stellen met Aspose.Slides voor Java:

### 1. Maak een lege presentatie

```java
// Het pad naar de documentenmap.
String dataDir = "Your Document Directory";

// Een lege presentatie maken 
Presentation presentation = new Presentation();
```

### 2. Toegang tot de eerste dia

```java
// Toegang tot de eerste dia
ISlide slide = presentation.getSlides().get_Item(0);
```

### 3. Voeg een grafiek toe met standaardgegevens

```java
// Een grafiek met standaardgegevens toevoegen
IChart chart = slide.getShapes().addChart(ChartType.StackedColumn, 0, 0, 500, 500);
```

### 4. Stel de index van het grafiekgegevensblad in

```java
// De index van het grafiekgegevensblad instellen
int defaultWorksheetIndex = 0;
```

### 5. Download het werkboek met grafiekgegevens

```java
// Het werkblad met grafiekgegevens ophalen
IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
```

### 6. Voeg series toe aan de grafiek

```java
// Serie toevoegen aan de grafiek
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 1, "Series 1"), chart.getType());
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 2, "Series 2"), chart.getType());
```

### 7. Categorieën toevoegen aan de grafiek

```java
// Categorieën toevoegen aan de grafiek
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 1, 0, "Category 1"));
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 2, 0, "Category 2"));
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 3, 0, "Category 3"));
```

### 8. Vul reeksgegevens in

```java
// Vul reeksgegevens in
IChartSeries series = chart.getChartData().getSeries().get_Item(1);

// Het vullen van reeksgegevenspunten
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 1, 20));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 50));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 30));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 2, 30));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 2, 10));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 2, 60));
```

### 9. Stel de spleetbreedte in

```java
// Stel de waarde voor de tussenruimtebreedte in
series.getParentSeriesGroup().setGapWidth(50);
```

### 10. Sla de presentatie op

```java
// Sla de presentatie met de grafiek op
presentation.save(dataDir + "GapWidth_out.pptx", SaveFormat.Pptx);
```

## Volledige broncode voor het instellen van de breedte van de tussenruimte in Java-dia's

```java
// Het pad naar de documentenmap.
String dataDir = "Your Document Directory";
// Lege presentatie maken 
Presentation presentation = new Presentation();
// Toegang tot eerste dia
ISlide slide = presentation.getSlides().get_Item(0);
// Grafiek toevoegen met standaardgegevens
IChart chart = slide.getShapes().addChart(ChartType.StackedColumn, 0, 0, 500, 500);
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
// Neem de tweede grafiekserie
IChartSeries series = chart.getChartData().getSeries().get_Item(1);
// Nu worden reeksgegevens ingevuld
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 1, 20));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 50));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 30));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 2, 30));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 2, 10));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 2, 60));
// GapWidth-waarde instellen
series.getParentSeriesGroup().setGapWidth(50);
// Presentatie met grafiek opslaan
presentation.save(dataDir + "GapWidth_out.pptx", SaveFormat.Pptx);
```

## Conclusie

In deze tutorial heb je geleerd hoe je de tussenruimte voor een grafiek in een PowerPoint-presentatie instelt met Aspose.Slides voor Java. Door de tussenruimte aan te passen, kun je de afstand tussen kolommen of balken in je grafiek bepalen, wat de visuele weergave van je gegevens verbetert.

## Veelgestelde vragen

### Hoe verander ik de waarde van de Gap Width?

Om de tussenruimtebreedte te wijzigen, gebruikt u de `setGapWidth` methode op de `ParentSeriesGroup` van de grafiekreeks. In het gegeven voorbeeld stellen we de tussenruimte in op 50, maar u kunt deze waarde aanpassen naar uw gewenste afstand.

### Kan ik andere grafiekeigenschappen aanpassen?

Ja, Aspose.Slides voor Java biedt uitgebreide mogelijkheden voor het aanpassen van grafieken. U kunt verschillende grafiekeigenschappen aanpassen, zoals kleuren, labels, titels en meer. Raadpleeg de API-referentie voor gedetailleerde informatie over de opties voor het aanpassen van grafieken.

### Waar kan ik meer bronnen en documentatie vinden?

Uitgebreide documentatie en aanvullende bronnen vindt u op Aspose.Slides voor Java op de [Aspose-website](https://reference.aspose.com/slides/java/).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}