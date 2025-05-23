---
"description": "Leer hoe u formules voor grafiekgegevenscellen in Java PowerPoint-presentaties instelt met Aspose.Slides voor Java. Maak dynamische grafieken met formules."
"linktitle": "Formules voor diagramgegevenscellen in Java-dia's"
"second_title": "Aspose.Slides Java PowerPoint-verwerkings-API"
"title": "Formules voor diagramgegevenscellen in Java-dia's"
"url": "/nl/java/data-manipulation/chart-data-cell-formulas-java-slides/"
"weight": 11
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Formules voor diagramgegevenscellen in Java-dia's


## Inleiding tot formules voor diagramgegevenscellen in Aspose.Slides voor Java

In deze tutorial laten we zien hoe je met formules voor diagramgegevenscellen kunt werken met Aspose.Slides voor Java. Met Aspose.Slides kun je diagrammen in PowerPoint-presentaties maken en bewerken, inclusief het instellen van formules voor gegevenscellen.

## Vereisten

Voordat u begint, moet u ervoor zorgen dat u de Aspose.Slides voor Java-bibliotheek hebt geïnstalleerd. U kunt deze downloaden van [hier](https://releases.aspose.com/slides/java/).

## Stap 1: Maak een PowerPoint-presentatie

Laten we eerst een nieuwe PowerPoint-presentatie maken en er een grafiek aan toevoegen.

```java
String outpptxFile = "Your Output Directory" + File.separator + "ChartDataCell_Formulas_out.pptx";
Presentation presentation = new Presentation();
try
{
    // Voeg een grafiek toe aan de eerste dia
    IChart chart = presentation.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 150, 150, 500, 300);
    
    // Download de werkmap voor grafiekgegevens
    IChartDataWorkbook workbook = chart.getChartData().getChartDataWorkbook();
    
    // Ga door met de bewerkingen van de gegevenscel
    // ...
    
    // Sla de presentatie op
    presentation.save(outpptxFile, SaveFormat.Pptx);
}
finally
{
    if (presentation != null) presentation.dispose();
}
```

## Stap 2: Formules instellen voor gegevenscellen

Laten we nu formules instellen voor specifieke gegevenscellen in de grafiek. In dit voorbeeld stellen we formules in voor twee verschillende cellen.

### Cel 1: A1-notatie gebruiken

```java
IChartDataCell cell1 = workbook.getCell(0, "B2");
cell1.setFormula("1 + SUM(F2:H5)");
```

In de bovenstaande code stellen we een formule in voor cel B2 met de A1-notatie. De formule berekent de som van de cellen F2 tot en met H5 en telt 1 op bij het resultaat.

### Cel 2: R1C1-notatie gebruiken

```java
IChartDataCell cell2 = workbook.getCell(0, "C2");
cell2.setR1C1Formula("MAX(R2C6:R5C8) / 3");
```

We gebruiken hier een formule voor cel C2 met de R1C1-notatie. De formule berekent de maximumwaarde binnen het bereik R2C6 tot en met R5C8 en deelt deze vervolgens door 3.

## Stap 3: Formules berekenen

Nadat u de formules hebt ingesteld, is het belangrijk om ze te berekenen met behulp van de volgende code:

```java
workbook.calculateFormulas();
```

Met deze stap wordt ervoor gezorgd dat de grafiek de bijgewerkte waarden op basis van de formules weerspiegelt.

## Stap 4: Sla de presentatie op

Sla ten slotte de gewijzigde presentatie op in een bestand.

```java
presentation.save(outpptxFile, SaveFormat.Pptx);
```

## Volledige broncode voor grafiekgegevenscelformules in Java-dia's

```java
String outpptxFile = "Your Output Directory" + File.pathSeparator + "ChartDataCell_Formulas_out.pptx";
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

In deze tutorial hebben we onderzocht hoe je met formules voor diagramgegevenscellen in Aspose.Slides voor Java kunt werken. We hebben het maken van een PowerPoint-presentatie, het toevoegen van een grafiek, het instellen van formules voor gegevenscellen, het berekenen van de formules en het opslaan van de presentatie behandeld. Je kunt deze mogelijkheden nu gebruiken om dynamische en datagestuurde grafieken in je presentaties te maken.

## Veelgestelde vragen

### Hoe voeg ik een grafiek toe aan een specifieke dia?

Om een grafiek aan een specifieke dia toe te voegen, kunt u de `getSlides().get_Item(slideIndex)` methode om toegang te krijgen tot de gewenste dia en gebruik vervolgens de `addChart` Methode om de grafiek toe te voegen.

### Kan ik verschillende soorten formules gebruiken in gegevenscellen?

Ja, u kunt verschillende typen formules gebruiken in formules voor gegevenscellen, waaronder wiskundige bewerkingen, functies en verwijzingen naar andere cellen.

### Hoe verander ik het grafiektype?

U kunt het grafiektype wijzigen met behulp van de `setChartType` methode op de `IChart` object en het gewenste specificeren `ChartType`.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}