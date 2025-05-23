---
"description": "Verbeter je PowerPoint-presentaties met Aspose.Slides voor Java. Leer bestaande grafieken programmatisch aan te passen. Stapsgewijze handleiding met broncode voor het aanpassen van grafieken."
"linktitle": "Bestaande grafiek in Java-dia's"
"second_title": "Aspose.Slides Java PowerPoint-verwerkings-API"
"title": "Bestaande grafiek in Java-dia's"
"url": "/nl/java/chart-elements/existing-chart-java-slides/"
"weight": 12
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Bestaande grafiek in Java-dia's


## Inleiding tot bestaande grafieken in Java-dia's met Aspose.Slides voor Java

In deze tutorial laten we zien hoe je een bestaande grafiek in een PowerPoint-presentatie kunt aanpassen met Aspose.Slides voor Java. We doorlopen de stappen om grafiekgegevens, categorienamen en reeksnamen te wijzigen en een nieuwe reeks aan de grafiek toe te voegen. Zorg ervoor dat je Aspose.Slides voor Java in je project hebt ingesteld.

## Vereisten

Voordat we beginnen, moet u ervoor zorgen dat u aan de volgende vereisten voldoet:

1. Aspose.Slides voor de Java-bibliotheek is opgenomen in uw project.
2. Een bestaande PowerPoint-presentatie met een grafiek die u wilt wijzigen.
3. Java-ontwikkelomgeving instellen.

## Stap 1: Laad de presentatie

```java
// Het pad naar de documentenmap.
String dataDir = "Your Document Directory";

// Instantieer presentatieklasse die PPTX-bestand vertegenwoordigt
Presentation pres = new Presentation(dataDir + "ExistingChart.pptx");
```

## Stap 2: Toegang tot de dia en grafiek

```java
// Toegang tot de eerste dia
ISlide sld = pres.getSlides().get_Item(0);

// Toegang tot de grafiek op de dia
IChart chart = (IChart) sld.getShapes().get_Item(0);
```

## Stap 3: Wijzig grafiekgegevens en categorienamen

```java
// De index van het grafiekgegevensblad instellen
int defaultWorksheetIndex = 0;

// Het werkblad met grafiekgegevens ophalen
IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();

// Wijzig de namen van grafiekcategorieën
fact.getCell(defaultWorksheetIndex, 1, 0, "Modified Category 1");
fact.getCell(defaultWorksheetIndex, 2, 0, "Modified Category 2");
```

## Stap 4: Eerste grafiekserie bijwerken

```java
// Neem de eerste grafiekserie
IChartSeries series = chart.getChartData().getSeries().get_Item(0);

// Serienaam bijwerken
fact.getCell(defaultWorksheetIndex, 0, 1, "New_Series1");

// Seriegegevens bijwerken
series.getDataPoints().get_Item(0).getValue().setData(90);
series.getDataPoints().get_Item(1).getValue().setData(123);
series.getDataPoints().get_Item(2).getValue().setData(44);
```

## Stap 5: Tweede grafiekreeks bijwerken

```java
// Neem de tweede grafiekserie
series = chart.getChartData().getSeries().get_Item(1);

// Serienaam bijwerken
fact.getCell(defaultWorksheetIndex, 0, 2, "New_Series2");

// Seriegegevens bijwerken
series.getDataPoints().get_Item(0).getValue().setData(23);
series.getDataPoints().get_Item(1).getValue().setData(67);
series.getDataPoints().get_Item(2).getValue().setData(99);
```

## Stap 6: Een nieuwe serie toevoegen aan de grafiek

```java
// Een nieuwe serie toevoegen
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 3, "Series 3"), chart.getType());

// Neem de derde grafiekserie
series = chart.getChartData().getSeries().get_Item(2);

// Vul reeksgegevens in
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 3, 20));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 3, 50));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 3, 30));
```

## Stap 7: Wijzig het grafiektype

```java
// Wijzig het diagramtype naar Geclusterde cilinder
chart.setType(ChartType.ClusteredCylinder);
```

## Stap 8: De gewijzigde presentatie opslaan

```java
// Sla de presentatie op met de aangepaste grafiek
pres.save(dataDir + "AsposeChartModified_out.pptx", SaveFormat.Pptx);
```

Gefeliciteerd! Je hebt met succes een bestaande grafiek in een PowerPoint-presentatie aangepast met Aspose.Slides voor Java. Je kunt deze code nu gebruiken om grafieken in je PowerPoint-presentaties programmatisch aan te passen.

## Volledige broncode voor bestaande grafiek in Java-dia's

```java
// Het pad naar de documentenmap.
String dataDir = "Your Document Directory";
// Instantieer presentatieklasse die PPTX-bestand vertegenwoordigt // Instantieer presentatieklasse die PPTX-bestand vertegenwoordigt
Presentation pres = new Presentation(dataDir + "ExistingChart.pptx");
// Toegang tot eerste diaMarker
ISlide sld = pres.getSlides().get_Item(0);
// Grafiek toevoegen met standaardgegevens
IChart chart = (IChart) sld.getShapes().get_Item(0);
// De index van het grafiekgegevensblad instellen
int defaultWorksheetIndex = 0;
// Het werkblad met grafiekgegevens ophalen
IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
// Wijzigen van grafiekcategorienaam
fact.getCell(defaultWorksheetIndex, 1, 0, "Modified Category 1");
fact.getCell(defaultWorksheetIndex, 2, 0, "Modified Category 2");
// Neem de eerste grafiekserie
IChartSeries series = chart.getChartData().getSeries().get_Item(0);
// Seriegegevens worden nu bijgewerkt
fact.getCell(defaultWorksheetIndex, 0, 1, "New_Series1");// Serienaam wijzigen
series.getDataPoints().get_Item(0).getValue().setData(90);
series.getDataPoints().get_Item(1).getValue().setData(123);
series.getDataPoints().get_Item(2).getValue().setData(44);
// Neem de tweede grafiekserie
series = chart.getChartData().getSeries().get_Item(1);
// Seriegegevens worden nu bijgewerkt
fact.getCell(defaultWorksheetIndex, 0, 2, "New_Series2");// Serienaam wijzigen
series.getDataPoints().get_Item(0).getValue().setData(23);
series.getDataPoints().get_Item(1).getValue().setData(67);
series.getDataPoints().get_Item(2).getValue().setData(99);
// Nu, een nieuwe serie toevoegen
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 3, "Series 3"), chart.getType());
// Neem de 3e grafiekserie
series = chart.getChartData().getSeries().get_Item(2);
// Nu worden reeksgegevens ingevuld
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 3, 20));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 3, 50));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 3, 30));
chart.setType(ChartType.ClusteredCylinder);
// Presentatie met grafiek opslaan
pres.save(dataDir + "AsposeChartModified_out.pptx", SaveFormat.Pptx);
```
## Conclusie

In deze uitgebreide tutorial hebben we geleerd hoe je een bestaande grafiek in een PowerPoint-presentatie kunt aanpassen met Aspose.Slides voor Java. Door de stapsgewijze handleiding te volgen en broncodevoorbeelden te gebruiken, kun je grafieken eenvoudig aanpassen en bijwerken om aan je specifieke eisen te voldoen. Hier is een samenvatting van wat we hebben behandeld:

## Veelgestelde vragen

### Hoe kan ik het grafiektype wijzigen?

U kunt het grafiektype wijzigen met behulp van de `chart.setType(ChartType.ChartTypeHere)` methode. Vervangen `ChartTypeHere` met het gewenste grafiektype, zoals `ChartType.ClusteredCylinder` in ons voorbeeld.

### Kan ik meer datapunten aan een reeks toevoegen?

Ja, u kunt meer datapunten aan een reeks toevoegen met behulp van de `series.getDataPoints().addDataPointForBarSeries(cell)` methode. Zorg ervoor dat u de juiste celgegevens verstrekt.

### Hoe kan ik de categorienamen bijwerken?

U kunt categorienamen bijwerken met behulp van `fact.getCell(worksheetIndex, columnIndex, rowIndex, newValue)` om de nieuwe categorienamen in te stellen.

### Hoe wijzig ik serienamen?

Om serienamen te wijzigen, gebruikt u `fact.getCell(worksheetIndex, columnIndex, rowIndex, newValue)` om de nieuwe serienamen in te stellen.

### Is er een manier om een reeks uit de grafiek te verwijderen?

Ja, u kunt een reeks uit de grafiek verwijderen met behulp van de `chart.getChartData().getSeries().removeAt(index)` methode, waarbij `index` is de index van de reeks die u wilt verwijderen.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}