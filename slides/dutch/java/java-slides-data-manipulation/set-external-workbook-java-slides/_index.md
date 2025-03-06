---
title: Stel een externe werkmap in in Java-dia's
linktitle: Stel een externe werkmap in in Java-dia's
second_title: Aspose.Slides Java PowerPoint-verwerkings-API
description: Leer hoe u externe werkmappen in Java Slides instelt met Aspose.Slides voor Java. Creëer dynamische presentaties met Excel-gegevensintegratie.
weight: 19
url: /nl/java/data-manipulation/set-external-workbook-java-slides/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}


## Inleiding tot het instellen van een externe werkmap in Java-dia's

In deze zelfstudie onderzoeken we hoe u een externe werkmap in Java Slides kunt instellen met behulp van Aspose.Slides. U leert hoe u een PowerPoint-presentatie maakt met een diagram dat verwijst naar gegevens uit een externe Excel-werkmap. Aan het einde van deze handleiding heeft u een duidelijk inzicht in hoe u externe gegevens kunt integreren in uw Java Slides-presentaties.

## Vereisten

Voordat we ingaan op de implementatie, moet u ervoor zorgen dat u aan de volgende vereisten voldoet:

- Java Development Kit (JDK) op uw systeem geïnstalleerd.
- Aspose.Slides voor Java-bibliotheek toegevoegd aan uw project.
- Een Excel-werkmap met de gegevens waarnaar u in uw presentatie wilt verwijzen.

## Stap 1: Maak een nieuwe presentatie

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
```

We beginnen met het maken van een nieuwe PowerPoint-presentatie met Aspose.Slides.

## Stap 2: Voeg een diagram toe

```java
IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.Pie, 50, 50, 400, 600, false);
```

Vervolgens voegen we een cirkeldiagram in de presentatie. U kunt het diagramtype en de positie indien nodig aanpassen.

## Stap 3: Toegang tot externe werkmap

```java
IChartData chartData = chart.getChartData();
chartData.setExternalWorkbook(dataDir + "externalWorkbook.xlsx");
```

 Om toegang te krijgen tot de externe werkmap gebruiken we de`setExternalWorkbook` methode en geef het pad op naar de Excel-werkmap die de gegevens bevat.

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

We binden het diagram aan gegevens uit de externe werkmap door de celverwijzingen voor reeksen en categorieën op te geven.

## Stap 5: Sla de presentatie op

```java
pres.save(dataDir + "Presentation_with_externalWorkbook.pptx", SaveFormat.Pptx);
```

Ten slotte slaan we de presentatie met de externe werkmapreferentie op als PowerPoint-bestand.

## Volledige broncode voor externe werkmap instellen in Java-dia's

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

In deze zelfstudie hebben we geleerd hoe u een externe werkmap in Java Slides kunt instellen met Aspose.Slides. U kunt nu presentaties maken die dynamisch verwijzen naar gegevens uit Excel-werkmappen, waardoor de flexibiliteit en interactiviteit van uw dia's wordt vergroot.

## Veelgestelde vragen

### Hoe installeer ik Aspose.Slides voor Java?

Aspose.Slides voor Java kan worden geïnstalleerd door de bibliotheek aan uw Java-project toe te voegen. U kunt de bibliotheek downloaden van de Aspose-website en de installatie-instructies volgen die in de documentatie staan.

### Kan ik verschillende diagramtypen gebruiken met externe werkmappen?

Ja, u kunt verschillende diagramtypen gebruiken die door Aspose.Slides worden ondersteund en deze koppelen aan gegevens uit externe werkmappen. Het proces kan enigszins variëren, afhankelijk van het diagramtype dat u kiest.

### Wat moet ik doen als de gegevensstructuur van mijn externe werkmap verandert?

Als de structuur van de gegevens van uw externe werkmap verandert, moet u mogelijk de celverwijzingen in uw Java-code bijwerken om ervoor te zorgen dat de diagramgegevens accuraat blijven.

### Is Aspose.Slides compatibel met de nieuwste Java-versies?

Aspose.Slides voor Java wordt regelmatig bijgewerkt om compatibiliteit met de nieuwste Java-versies te garanderen. Zorg ervoor dat u controleert op updates en gebruik de nieuwste versie van de bibliotheek voor optimale prestaties en compatibiliteit.

### Kan ik meerdere diagrammen toevoegen die verwijzen naar dezelfde externe werkmap?

Ja, u kunt meerdere diagrammen aan uw presentatie toevoegen, die allemaal naar dezelfde externe werkmap verwijzen. Herhaal eenvoudigweg de stappen die in deze zelfstudie worden beschreven voor elk diagram dat u wilt maken.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
