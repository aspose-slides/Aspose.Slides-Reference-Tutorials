---
title: Bestaand diagram in Java-dia's
linktitle: Bestaand diagram in Java-dia's
second_title: Aspose.Slides Java PowerPoint-verwerkings-API
description: Verbeter uw PowerPoint-presentaties met Aspose.Slides voor Java. Leer hoe u bestaande diagrammen programmatisch kunt wijzigen. Stapsgewijze handleiding met broncode voor het aanpassen van diagrammen.
type: docs
weight: 12
url: /nl/java/chart-elements/existing-chart-java-slides/
---

## Inleiding tot bestaande grafieken in Java-dia's met behulp van Aspose.Slides voor Java

In deze zelfstudie laten we zien hoe u een bestaand diagram in een PowerPoint-presentatie kunt wijzigen met Aspose.Slides voor Java. We doorlopen de stappen om diagramgegevens, categorienamen en serienamen te wijzigen en een nieuwe serie aan het diagram toe te voegen. Zorg ervoor dat Aspose.Slides voor Java in uw project is ingesteld.

## Vereisten

Voordat we beginnen, zorg ervoor dat u aan de volgende vereisten voldoet:

1. Aspose.Slides voor Java-bibliotheek opgenomen in uw project.
2. Een bestaande PowerPoint-presentatie met een diagram dat u wilt wijzigen.
3. Java-ontwikkelomgeving opgezet.

## Stap 1: Laad de presentatie

```java
// Het pad naar de documentenmap.
String dataDir = "Your Document Directory";

// Instantieer de presentatieklasse die het PPTX-bestand vertegenwoordigt
Presentation pres = new Presentation(dataDir + "ExistingChart.pptx");
```

## Stap 2: Open de dia en het diagram

```java
// Toegang tot de eerste dia
ISlide sld = pres.getSlides().get_Item(0);

// Open het diagram op de dia
IChart chart = (IChart) sld.getShapes().get_Item(0);
```

## Stap 3: Wijzig grafiekgegevens en categorienamen

```java
// Instellen van de index van het kaartgegevensblad
int defaultWorksheetIndex = 0;

// Het werkblad met diagramgegevens ophalen
IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();

// Wijzig de namen van diagramcategorieën
fact.getCell(defaultWorksheetIndex, 1, 0, "Modified Category 1");
fact.getCell(defaultWorksheetIndex, 2, 0, "Modified Category 2");
```

## Stap 4: Update de eerste kaartserie

```java
// Neem de eerste kaartenserie
IChartSeries series = chart.getChartData().getSeries().get_Item(0);

// Serienaam bijwerken
fact.getCell(defaultWorksheetIndex, 0, 1, "New_Series1");

// Seriegegevens bijwerken
series.getDataPoints().get_Item(0).getValue().setData(90);
series.getDataPoints().get_Item(1).getValue().setData(123);
series.getDataPoints().get_Item(2).getValue().setData(44);
```

## Stap 5: Update de tweede kaartreeks

```java
// Neem de tweede kaartenreeks
series = chart.getChartData().getSeries().get_Item(1);

// Serienaam bijwerken
fact.getCell(defaultWorksheetIndex, 0, 2, "New_Series2");

// Seriegegevens bijwerken
series.getDataPoints().get_Item(0).getValue().setData(23);
series.getDataPoints().get_Item(1).getValue().setData(67);
series.getDataPoints().get_Item(2).getValue().setData(99);
```

## Stap 6: Voeg een nieuwe reeks toe aan de grafiek

```java
// Een nieuwe serie toevoegen
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 3, "Series 3"), chart.getType());

// Neem de derde kaartenreeks
series = chart.getChartData().getSeries().get_Item(2);

// Reeksgegevens invullen
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 3, 20));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 3, 50));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 3, 30));
```

## Stap 7: Wijzig het diagramtype

```java
//Wijzig het diagramtype in Geclusterde cilinder
chart.setType(ChartType.ClusteredCylinder);
```

## Stap 8: Sla de aangepaste presentatie op

```java
// Sla de presentatie op met het gewijzigde diagram
pres.save(dataDir + "AsposeChartModified_out.pptx", SaveFormat.Pptx);
```

Gefeliciteerd! U hebt met succes een bestaand diagram in een PowerPoint-presentatie gewijzigd met Aspose.Slides voor Java. U kunt deze code nu gebruiken om diagrammen in uw PowerPoint-presentaties programmatisch aan te passen.

## Volledige broncode voor bestaand diagram in Java-dia's

```java
// Het pad naar de documentenmap.
String dataDir = "Your Document Directory";
// Instantieer presentatieklasse die het PPTX-bestand vertegenwoordigt// Instantieer presentatieklasse die het PPTX-bestand vertegenwoordigt
Presentation pres = new Presentation(dataDir + "ExistingChart.pptx");
// Toegang tot de eerste slideMarker
ISlide sld = pres.getSlides().get_Item(0);
// Diagram met standaardgegevens toevoegen
IChart chart = (IChart) sld.getShapes().get_Item(0);
// De index van het kaartgegevensblad instellen
int defaultWorksheetIndex = 0;
// Het werkblad met diagramgegevens ophalen
IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
// Categorienaam van diagram wijzigen
fact.getCell(defaultWorksheetIndex, 1, 0, "Modified Category 1");
fact.getCell(defaultWorksheetIndex, 2, 0, "Modified Category 2");
// Neem de eerste kaartenreeks
IChartSeries series = chart.getChartData().getSeries().get_Item(0);
// Seriegegevens worden nu bijgewerkt
fact.getCell(defaultWorksheetIndex, 0, 1, "New_Series1");// Serienaam wijzigen
series.getDataPoints().get_Item(0).getValue().setData(90);
series.getDataPoints().get_Item(1).getValue().setData(123);
series.getDataPoints().get_Item(2).getValue().setData(44);
// Neem de tweede kaartenreeks
series = chart.getChartData().getSeries().get_Item(1);
// Seriegegevens worden nu bijgewerkt
fact.getCell(defaultWorksheetIndex, 0, 2, "New_Series2");// Serienaam wijzigen
series.getDataPoints().get_Item(0).getValue().setData(23);
series.getDataPoints().get_Item(1).getValue().setData(67);
series.getDataPoints().get_Item(2).getValue().setData(99);
// Nu wordt er een nieuwe serie toegevoegd
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 3, "Series 3"), chart.getType());
// Neem de derde kaartserie
series = chart.getChartData().getSeries().get_Item(2);
// Vult nu seriegegevens in
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 3, 20));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 3, 50));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 3, 30));
chart.setType(ChartType.ClusteredCylinder);
// Presentatie opslaan met grafiek
pres.save(dataDir + "AsposeChartModified_out.pptx", SaveFormat.Pptx);
```
## Conclusie

In deze uitgebreide zelfstudie hebben we geleerd hoe u een bestaand diagram in een PowerPoint-presentatie kunt wijzigen met Aspose.Slides voor Java. Door de stapsgewijze handleiding te volgen en broncodevoorbeelden te gebruiken, kunt u diagrammen eenvoudig aanpassen en bijwerken om aan uw specifieke vereisten te voldoen. Hier is een samenvatting van wat we hebben besproken:

## Veelgestelde vragen

### Hoe kan ik het diagramtype wijzigen?

 U kunt het diagramtype wijzigen met behulp van de`chart.setType(ChartType.ChartTypeHere)` methode. Vervangen`ChartTypeHere` met het gewenste diagramtype, zoals`ChartType.ClusteredCylinder` in ons voorbeeld.

### Kan ik meer gegevenspunten aan een reeks toevoegen?

 Ja, u kunt meer gegevenspunten aan een reeks toevoegen met behulp van de`series.getDataPoints().addDataPointForBarSeries(cell)` methode. Zorg ervoor dat u de juiste celgegevens opgeeft.

### Hoe update ik de categorienamen?

 U kunt categorienamen bijwerken met behulp van`fact.getCell(worksheetIndex, columnIndex, rowIndex, newValue)` om de nieuwe categorienamen in te stellen.

### Hoe wijzig ik serienamen?

 Om serienamen te wijzigen, gebruikt u`fact.getCell(worksheetIndex, columnIndex, rowIndex, newValue)` om de nieuwe serienamen in te stellen.

### Is er een manier om een reeks uit het diagram te verwijderen?

 Ja, u kunt een reeks uit het diagram verwijderen met behulp van de`chart.getChartData().getSeries().removeAt(index)` methode, waar`index`is de index van de reeks die u wilt verwijderen.