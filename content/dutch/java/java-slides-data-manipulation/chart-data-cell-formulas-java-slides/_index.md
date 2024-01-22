---
title: Grafiekgegevenscelformules in Java-dia's
linktitle: Grafiekgegevenscelformules in Java-dia's
second_title: Aspose.Slides Java PowerPoint-verwerkings-API
description: Leer hoe u celformules voor diagramgegevens instelt in Java PowerPoint-presentaties met behulp van Aspose.Slides voor Java. Maak dynamische grafieken met formules.
type: docs
weight: 11
url: /nl/java/data-manipulation/chart-data-cell-formulas-java-slides/
---

## Inleiding tot diagramgegevenscelformules in Aspose.Slides voor Java

In deze zelfstudie onderzoeken we hoe u met grafiekgegevenscelformules kunt werken met behulp van Aspose.Slides voor Java. Met Aspose.Slides kunt u diagrammen in PowerPoint-presentaties maken en manipuleren, inclusief het instellen van formules voor gegevenscellen.

## Vereisten

 Voordat u begint, moet u ervoor zorgen dat de Aspose.Slides voor Java-bibliotheek is geïnstalleerd. Je kunt het downloaden van[hier](https://releases.aspose.com/slides/java/).

## Stap 1: Maak een PowerPoint-presentatie

Laten we eerst een nieuwe PowerPoint-presentatie maken en er een diagram aan toevoegen.

```java
String outpptxFile = RunExamples.getOutPath() + File.separator + "ChartDataCell_Formulas_out.pptx";
Presentation presentation = new Presentation();
try
{
    // Voeg een diagram toe aan de eerste dia
    IChart chart = presentation.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 150, 150, 500, 300);
    
    // Download de werkmap voor diagramgegevens
    IChartDataWorkbook workbook = chart.getChartData().getChartDataWorkbook();
    
    // Ga door met datacelbewerkingen
    // ...
    
    // Bewaar de presentatie
    presentation.save(outpptxFile, SaveFormat.Pptx);
}
finally
{
    if (presentation != null) presentation.dispose();
}
```

## Stap 2: Formules instellen voor gegevenscellen

Laten we nu formules instellen voor specifieke gegevenscellen in het diagram. In dit voorbeeld stellen we formules in voor twee verschillende cellen.

### Cel 1: A1-notatie gebruiken

```java
IChartDataCell cell1 = workbook.getCell(0, "B2");
cell1.setFormula("1 + SUM(F2:H5)");
```

In de bovenstaande code stellen we een formule in voor cel B2 met behulp van de A1-notatie. De formule berekent de som van de cellen F2 tot en met H5 en telt 1 op bij het resultaat.

### Cel 2: R1C1-notatie gebruiken

```java
IChartDataCell cell2 = workbook.getCell(0, "C2");
cell2.setR1C1Formula("MAX(R2C6:R5C8) / 3");
```

Hier stellen we een formule in voor cel C2 met behulp van de R1C1-notatie. De formule berekent de maximale waarde binnen het bereik R2C6 tot en met R5C8 en deelt deze vervolgens door 3.

## Stap 3: Bereken formules

Nadat u de formules heeft ingesteld, is het essentieel om ze te berekenen met behulp van de volgende code:

```java
workbook.calculateFormulas();
```

Deze stap zorgt ervoor dat het diagram de bijgewerkte waarden weergeeft op basis van de formules.

## Stap 4: Sla de presentatie op

Sla ten slotte de gewijzigde presentatie op in een bestand.

```java
presentation.save(outpptxFile, SaveFormat.Pptx);
```

## Volledige broncode voor diagramgegevenscelformules in Java-dia's

```java
String outpptxFile = RunExamples.getOutPath() + File.pathSeparator + "ChartDataCell_Formulas_out.pptx";
Presentation presentation = new Presentation();
try
{
	IChart chart = presentation.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 150, 150, 500, 300);
	IChartDataWorkbook workbook = chart.getChartData().getChartDataWorkbook();
	IChartDataCell cell1 = workbook.getCell(0, "B2");
	cell1.setFormula("1 + SUM(F2:H5)");
	IChartDataCell cell2 = workbook.getCell(0, "C2");
	cell2.setR1C1Formula("MAX(R2C6:R5C8) / 3");
	workbook.calculateFormulas();
	presentation.save(outpptxFile, SaveFormat.Pptx);
}
finally
{
	if (presentation != null) presentation.dispose();
}
```

## Conclusie

In deze zelfstudie hebben we onderzocht hoe u kunt werken met celformules voor diagramgegevens in Aspose.Slides voor Java. We hebben het gehad over het maken van een PowerPoint-presentatie, het toevoegen van een diagram, het instellen van formules voor gegevenscellen, het berekenen van de formules en het opslaan van de presentatie. U kunt deze mogelijkheden nu benutten om dynamische en gegevensgestuurde grafieken in uw presentaties te maken.

## Veelgestelde vragen

### Hoe voeg ik een diagram toe aan een specifieke dia?

 Om een diagram aan een specifieke dia toe te voegen, kunt u de`getSlides().get_Item(slideIndex)` methode om toegang te krijgen tot de gewenste dia en gebruik vervolgens de`addChart` methode om het diagram toe te voegen.

### Kan ik verschillende soorten formules in gegevenscellen gebruiken?

Ja, u kunt in gegevenscelformules verschillende typen formules gebruiken, waaronder wiskundige bewerkingen, functies en verwijzingen naar andere cellen.

### Hoe wijzig ik het diagramtype?

 U kunt het diagramtype wijzigen met behulp van de`setChartType` methode op de`IChart` object en specificeer het gewenste`ChartType`.