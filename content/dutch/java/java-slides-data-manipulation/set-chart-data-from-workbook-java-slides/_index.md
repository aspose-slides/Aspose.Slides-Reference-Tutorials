---
title: Stel grafiekgegevens uit de werkmap in Java-dia's in
linktitle: Stel grafiekgegevens uit de werkmap in Java-dia's in
second_title: Aspose.Slides Java PowerPoint-verwerkings-API
description: Leer hoe u diagramgegevens vanuit een Excel-werkmap in Java Slides instelt met behulp van Aspose.Slides. Stapsgewijze handleiding met codevoorbeelden voor dynamische presentaties.
type: docs
weight: 15
url: /nl/java/data-manipulation/set-chart-data-from-workbook-java-slides/
---

## Inleiding tot het instellen van diagramgegevens uit de werkmap in Java-dia's

Aspose.Slides voor Java is een krachtige bibliotheek waarmee ontwikkelaars programmatisch met PowerPoint-presentaties kunnen werken. Het biedt uitgebreide functies voor het maken, manipuleren en beheren van PowerPoint-dia's. Een veel voorkomende vereiste bij het werken met presentaties is het dynamisch instellen van diagramgegevens vanuit een externe gegevensbron, zoals een Excel-werkmap. In deze tutorial laten we zien hoe u dit kunt bereiken met behulp van Java.

## Vereisten

Voordat we ingaan op de implementatie, moet u ervoor zorgen dat u aan de volgende vereisten voldoet:

- Java Development Kit (JDK) op uw systeem geïnstalleerd.
- Aspose.Slides voor Java-bibliotheek toegevoegd aan uw project.
- Een Excel-werkmap met de gegevens die u voor het diagram wilt gebruiken.

## Stap 1: Maak een presentatie

```java
String outPath = "Your Output Directory" + "response2.pptx";
Presentation pres = new Presentation();
```

We beginnen met het maken van een nieuwe PowerPoint-presentatie met Aspose.Slides voor Java.

## Stap 2: Voeg een diagram toe

```java
IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.Pie, 50, 50, 500, 400);
```

Vervolgens voegen we een diagram toe aan een van de dia's in de presentatie. In dit voorbeeld voegen we een cirkeldiagram toe, maar u kunt het diagramtype kiezen dat bij uw behoeften past.

## Stap 3: Wis grafiekgegevens

```java
chart.getChartData().getChartDataWorkbook().clear(0);
```

We verwijderen alle bestaande gegevens uit het diagram om deze voor te bereiden op nieuwe gegevens uit de Excel-werkmap.

## Stap 4: Excel-werkmap laden

```java
Workbook workbook = new Workbook("Your Document Directory";
```

 We laden de Excel-werkmap die de gegevens bevat die we voor het diagram willen gebruiken. Vervangen`"book1.xlsx"` met het pad naar uw Excel-bestand.

## Stap 5: Schrijf werkmapstream naar diagramgegevens

```java
ByteArrayOutputStream mem = new ByteArrayOutputStream();
workbook.save(mem, com.aspose.cells.SaveFormat.XLSX);
mem.flush();
chart.getChartData().writeWorkbookStream(mem.toByteArray());
```

We converteren de Excel-werkmapgegevens naar een stream en schrijven deze naar de diagramgegevens.

## Stap 6: Stel het diagramgegevensbereik in

```java
chart.getChartData().setRange("Sheet2!$A$1:$B$3");
```

We specificeren het cellenbereik uit de Excel-werkmap dat moet worden gebruikt als gegevens voor het diagram. Pas het bereik indien nodig aan voor uw gegevens.

## Stap 7: Pas de grafiekreeks aan

```java
IChartSeries series = chart.getChartData().getSeries().get_Item(0);
series.getParentSeriesGroup().setColorVaried(true);
```

U kunt verschillende eigenschappen van de diagramreeks aanpassen aan uw vereisten. In dit voorbeeld schakelen we gevarieerde kleuren in voor de diagramreeksen.

## Stap 8: Sla de presentatie op

```java
pres.save(outPath, SaveFormat.Pptx);
```

Ten slotte slaan we de presentatie met de bijgewerkte grafiekgegevens op in het opgegeven uitvoerpad.

## Volledige broncode voor ingestelde grafiekgegevens uit de werkmap in Java-dia's

```java
String outPath = "Your Output Directory" + "response2.pptx";
Presentation pres = new Presentation();
try {
	IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.Pie, 50, 50, 500, 400);
	chart.getChartData().getChartDataWorkbook().clear(0);
	Workbook workbook = null;
	try {
		workbook = new Workbook("Your Document Directory";
	} catch (Exception ex) {
		System.out.println(ex);
	}
	ByteArrayOutputStream mem = new ByteArrayOutputStream();
	workbook.save(mem, com.aspose.cells.SaveFormat.XLSX);
	mem.flush();
	chart.getChartData().writeWorkbookStream(mem.toByteArray());
	chart.getChartData().setRange("Sheet2!$A$1:$B$3");
	IChartSeries series = chart.getChartData().getSeries().get_Item(0);
	series.getParentSeriesGroup().setColorVaried(true);
	pres.save(outPath, SaveFormat.Pptx);
} catch(Exception e) {
} finally {
	if (pres != null) pres.dispose();
}
```

## Conclusie

In deze zelfstudie hebben we geleerd hoe u diagramgegevens uit een Excel-werkmap in Java Slides kunt instellen met behulp van de Aspose.Slides voor Java-bibliotheek. Door de stapsgewijze handleiding te volgen en de meegeleverde broncodevoorbeelden te gebruiken, kunt u eenvoudig dynamische grafiekgegevens in uw PowerPoint-presentaties integreren.

## Veelgestelde vragen

### Hoe kan ik de weergave van het diagram in mijn presentatie aanpassen?

U kunt het uiterlijk van het diagram aanpassen door eigenschappen zoals kleuren, lettertypen, labels en meer te wijzigen. Raadpleeg de Aspose.Slides voor Java-documentatie voor gedetailleerde informatie over aanpassingsopties voor diagrammen.

### Kan ik gegevens uit een ander Excel-bestand gebruiken voor het diagram?

Ja, u kunt gegevens uit elk Excel-bestand gebruiken door het juiste bestandspad op te geven bij het laden van de werkmap in de code.

### Welke andere soorten diagrammen kan ik maken met Aspose.Slides voor Java?

Aspose.Slides voor Java ondersteunt verschillende diagramtypen, waaronder staafdiagrammen, lijndiagrammen, spreidingsdiagrammen en meer. U kunt het diagramtype kiezen dat het beste past bij uw behoeften op het gebied van gegevensweergave.

### Is het mogelijk om de grafiekgegevens dynamisch bij te werken in een lopende presentatie?

Ja, u kunt diagramgegevens dynamisch bijwerken in een presentatie door de onderliggende werkmap te wijzigen en vervolgens de diagramgegevens te vernieuwen.

### Waar kan ik meer voorbeelden en bronnen vinden voor het werken met Aspose.Slides voor Java?

 U kunt aanvullende voorbeelden en bronnen bekijken op de[Aspose-website](https://www.aspose.com/). Bovendien biedt de Aspose.Slides voor Java-documentatie uitgebreide richtlijnen voor het werken met de bibliotheek.