---
"description": "Leer hoe u externe werkmappen in Java Slides instelt met Aspose.Slides voor Java. Maak dynamische presentaties met Excel-data-integratie."
"linktitle": "Externe werkmap instellen in Java-dia's"
"second_title": "Aspose.Slides Java PowerPoint-verwerkings-API"
"title": "Externe werkmap instellen in Java-dia's"
"url": "/nl/java/data-manipulation/set-external-workbook-java-slides/"
"weight": 19
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Externe werkmap instellen in Java-dia's


## Inleiding tot het instellen van externe werkboeken in Java-dia's

In deze tutorial laten we zien hoe je een externe werkmap in Java Slides kunt instellen met Aspose.Slides. Je leert hoe je een PowerPoint-presentatie maakt met een grafiek die verwijst naar gegevens uit een externe Excel-werkmap. Aan het einde van deze handleiding heb je een duidelijk begrip van hoe je externe gegevens in je Java Slides-presentaties kunt integreren.

## Vereisten

Voordat we met de implementatie beginnen, moet u ervoor zorgen dat u aan de volgende vereisten voldoet:

- Java Development Kit (JDK) op uw systeem geïnstalleerd.
- Aspose.Slides voor Java-bibliotheek toegevoegd aan uw project.
- Een Excel-werkmap met de gegevens waarnaar u wilt verwijzen in uw presentatie.

## Stap 1: Een nieuwe presentatie maken

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
```

We beginnen met het maken van een nieuwe PowerPoint-presentatie met behulp van Aspose.Slides.

## Stap 2: Een grafiek toevoegen

```java
IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.Pie, 50, 50, 400, 600, false);
```

Vervolgens voegen we een cirkeldiagram toe aan de presentatie. U kunt het diagramtype en de positie naar wens aanpassen.

## Stap 3: Toegang tot externe werkmap

```java
IChartData chartData = chart.getChartData();
chartData.setExternalWorkbook(dataDir + "externalWorkbook.xlsx");
```

Om toegang te krijgen tot de externe werkmap gebruiken we de `setExternalWorkbook` en geef het pad op naar de Excel-werkmap met de gegevens.

## Stap 4: Grafiekgegevens binden

```java
chartData.getSeries().add(chartData.getChartDataWorkbook().getCell(0, "B1"), ChartType.Pie);
chartData.getSeries().get_Item(0).getDataPoints().addDataPointForPieSeries(chartData.getChartDataWorkbook().getCell(0, "B2"));
chartData.getSeries().get_Item(0).getDataPoints().addDataPointForPieSeries(chartData.getChartDataWorkbook().getCell(0, "B3"));
chartData.getSeries().get_Item(0).getDataPoints().addDataPointForPieSeries(chartData.getChartDataWorkbook().getCell(0, "B4"));
chartData.getCategories().add(chartData.getChartDataWorkbook().getCell(0, "A2"));
chartData.getCategories().add(chartData.getChartDataWorkbook().getCell(0, "A3"));
chartData.getCategories().add(chartData.getChartDataWorkbook().getCell(0, "A4"));
```

We koppelen de grafiek aan gegevens uit de externe werkmap door de celverwijzingen voor reeksen en categorieën op te geven.

## Stap 5: Sla de presentatie op

```java
pres.save(dataDir + "Presentation_with_externalWorkbook.pptx", SaveFormat.Pptx);
```

Tot slot slaan we de presentatie met de externe werkmapreferentie op als een PowerPoint-bestand.

## Volledige broncode voor het instellen van een externe werkmap in Java-dia's

```java
// Het pad naar de documentenmap.
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
try
{
	IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.Pie, 50, 50, 400, 600, false);
	IChartData chartData = chart.getChartData();
	chartData.setExternalWorkbook(dataDir + "externalWorkbook.xlsx");
	chartData.getSeries().add(chartData.getChartDataWorkbook().getCell(0, "B1"), ChartType.Pie);
	chartData.getSeries().get_Item(0).getDataPoints().addDataPointForPieSeries(chartData.getChartDataWorkbook().getCell(0, "B2"));
	chartData.getSeries().get_Item(0).getDataPoints().addDataPointForPieSeries(chartData.getChartDataWorkbook().getCell(0, "B3"));
	chartData.getSeries().get_Item(0).getDataPoints().addDataPointForPieSeries(chartData.getChartDataWorkbook().getCell(0, "B4"));
	chartData.getCategories().add(chartData.getChartDataWorkbook().getCell(0, "A2"));
	chartData.getCategories().add(chartData.getChartDataWorkbook().getCell(0, "A3"));
	chartData.getCategories().add(chartData.getChartDataWorkbook().getCell(0, "A4"));
	pres.save(dataDir + "Presentation_with_externalWorkbook.pptx", SaveFormat.Pptx);
}
finally
{
	if (pres != null) pres.dispose();
}
```

## Conclusie

In deze tutorial hebben we geleerd hoe je een externe werkmap in Java Slides kunt instellen met Aspose.Slides. Je kunt nu presentaties maken die dynamisch verwijzen naar gegevens uit Excel-werkmappen, wat de flexibiliteit en interactiviteit van je slides vergroot.

## Veelgestelde vragen

### Hoe installeer ik Aspose.Slides voor Java?

Aspose.Slides voor Java kan worden geïnstalleerd door de bibliotheek aan uw Java-project toe te voegen. U kunt de bibliotheek downloaden van de Aspose-website en de installatie-instructies in de documentatie volgen.

### Kan ik verschillende grafiektypen gebruiken met externe werkmappen?

Ja, u kunt verschillende diagramtypen gebruiken die door Aspose.Slides worden ondersteund en deze koppelen aan gegevens uit externe werkmappen. Het proces kan enigszins variëren, afhankelijk van het diagramtype dat u kiest.

### Wat moet ik doen als de gegevensstructuur van mijn externe werkmap verandert?

Als de structuur van de gegevens in uw externe werkmap verandert, moet u mogelijk de celverwijzingen in uw Java-code bijwerken om ervoor te zorgen dat de grafiekgegevens nauwkeurig blijven.

### Is Aspose.Slides compatibel met de nieuwste Java-versies?

Aspose.Slides voor Java wordt regelmatig bijgewerkt om compatibiliteit met de nieuwste Java-versies te garanderen. Controleer regelmatig op updates en gebruik de nieuwste versie van de bibliotheek voor optimale prestaties en compatibiliteit.

### Kan ik meerdere grafieken toevoegen die naar dezelfde externe werkmap verwijzen?

Ja, u kunt meerdere grafieken aan uw presentatie toevoegen, die allemaal naar dezelfde externe werkmap verwijzen. Herhaal hiervoor de stappen in deze tutorial voor elke grafiek die u wilt maken.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}