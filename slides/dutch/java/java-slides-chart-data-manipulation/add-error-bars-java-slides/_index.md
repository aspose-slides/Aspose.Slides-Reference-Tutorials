---
title: Voeg foutbalken toe aan Java-dia's
linktitle: Voeg foutbalken toe aan Java-dia's
second_title: Aspose.Slides Java PowerPoint-verwerkings-API
description: Leer hoe u foutbalken kunt toevoegen aan PowerPoint-diagrammen in Java met behulp van Aspose.Slides. Stapsgewijze handleiding met broncode voor het aanpassen van foutbalken.
type: docs
weight: 13
url: /nl/java/chart-data-manipulation/add-error-bars-java-slides/
---

## Inleiding tot het toevoegen van foutbalken in Java-dia's met behulp van Aspose.Slides

In deze zelfstudie laten we zien hoe u foutbalken aan een diagram in een PowerPoint-dia kunt toevoegen met behulp van Aspose.Slides voor Java. Foutbalken bieden waardevolle informatie over de variabiliteit of onzekerheid van gegevenspunten in een diagram. We gaan een bellendiagram maken en er foutbalken aan toevoegen. Laten we beginnen!

## Vereisten

Voordat u begint, moet u ervoor zorgen dat de Aspose.Slides voor Java-bibliotheek is geïnstalleerd en ingesteld in uw Java-project. U kunt de bibliotheek downloaden via de[Aspose-website](https://downloads.aspose.com/slides/java).

## Stap 1: Maak een lege presentatie

```java
// Het pad naar de documentenmap.
String dataDir = "Your Document Directory";
// Lege presentatie maken
Presentation presentation = new Presentation();
```

In deze stap maken we een lege presentatie waarin we ons diagram met foutbalken toevoegen.

## Stap 2: Maak een bellendiagram

```java
// Een bellendiagram maken
IChart chart = presentation.getSlides().get_Item(0).getShapes().addChart(ChartType.Bubble, 50, 50, 400, 300, true);
```

Hier maken we een bellendiagram en specificeren we de positie en afmetingen ervan op de dia.

## Stap 3: Foutbalken toevoegen en het formaat instellen

```java
// Foutbalken toevoegen en het formaat ervan instellen
IErrorBarsFormat errBarX = chart.getChartData().getSeries().get_Item(0).getErrorBarsXFormat();
IErrorBarsFormat errBarY = chart.getChartData().getSeries().get_Item(0).getErrorBarsYFormat();
errBarX.setVisible(true);
errBarY.setVisible(true);
errBarX.setValueType(ErrorBarValueType.Fixed);
errBarX.setValue(0.1f);
errBarY.setValueType(ErrorBarValueType.Percentage);
errBarY.setValue(5);
errBarX.setType(ErrorBarType.Plus);
errBarY.getFormat().getLine().setWidth(2);
errBarX.setEndCap(true);
```

In deze stap voegen we foutbalken toe aan het diagram en stellen we het formaat ervan in. U kunt foutbalken aanpassen door waarden, typen en andere eigenschappen te wijzigen.

- `errBarX` vertegenwoordigt foutbalken langs de X-as.
- `errBarY` vertegenwoordigt foutbalken langs de Y-as.
- We maken zowel X- als Y-foutbalken zichtbaar.
- `setValueType` specificeert het waardetype voor foutbalken (bijvoorbeeld Vast of Percentage).
- `setValue` stelt de waarde voor foutbalken in.
- `setType` definieert het type foutbalken (bijvoorbeeld Plus of Min).
-  We stellen de breedte van de foutbalklijnen in met behulp van`getFormat().getLine().setWidth(2)`.
- `setEndCap`specificeert of einddoppen op de foutbalken moeten worden opgenomen.

## Stap 4: Sla de presentatie op

```java
// Presentatie opslaan
presentation.save(dataDir + "ErrorBars_out.pptx", SaveFormat.Pptx);
```

Ten slotte slaan we de presentatie met de toegevoegde foutbalken op een opgegeven locatie op.

Dat is het! U hebt met succes foutbalken toegevoegd aan een diagram in een PowerPoint-dia met behulp van Aspose.Slides voor Java.

## Volledige broncode voor het toevoegen van foutbalken in Java-dia's

```java
// Het pad naar de documentenmap.
String dataDir = "Your Document Directory";
// Lege presentatie maken
Presentation presentation = new Presentation();
try
{
	// Een bellendiagram maken
	IChart chart = presentation.getSlides().get_Item(0).getShapes().addChart(ChartType.Bubble, 50, 50, 400, 300, true);
	// Foutbalken toevoegen en het formaat ervan instellen
	IErrorBarsFormat errBarX = chart.getChartData().getSeries().get_Item(0).getErrorBarsXFormat();
	IErrorBarsFormat errBarY = chart.getChartData().getSeries().get_Item(0).getErrorBarsYFormat();
	errBarX.setVisible(true);
	errBarY.setVisible(true);
	errBarX.setValueType(ErrorBarValueType.Fixed);
	errBarX.setValue(0.1f);
	errBarY.setValueType(ErrorBarValueType.Percentage);
	errBarY.setValue(5);
	errBarX.setType(ErrorBarType.Plus);
	errBarY.getFormat().getLine().setWidth(2);
	errBarX.setEndCap(true);
	// Presentatie opslaan
	presentation.save(dataDir + "ErrorBars_out.pptx", SaveFormat.Pptx);
}
finally
{
	if (presentation != null) presentation.dispose();
}
```

## Conclusie

In deze zelfstudie hebben we onderzocht hoe u uw PowerPoint-presentaties kunt verbeteren door foutbalken aan diagrammen toe te voegen met behulp van Aspose.Slides voor Java. Foutbalken bieden waardevolle inzichten in de variabiliteit en onzekerheden van gegevens, waardoor uw presentaties informatiever en visueel aantrekkelijker worden.

## Veelgestelde vragen

### Hoe kan ik de weergave van foutbalken verder aanpassen?

U kunt foutbalken aanpassen door hun eigenschappen, zoals lijnstijl, kleur en breedte, te wijzigen, zoals gedemonstreerd in stap 3.

### Kan ik foutbalken toevoegen aan verschillende diagramtypen?

Ja, u kunt foutbalken toevoegen aan verschillende diagramtypen die worden ondersteund door Aspose.Slides voor Java. Maak eenvoudig het gewenste diagramtype en volg dezelfde stappen voor het aanpassen van de foutbalk.

### Hoe kan ik de positie en grootte van het diagram op de dia aanpassen?

 U kunt de positie en afmetingen van het diagram bepalen door de parameters in het diagram aan te passen`addChart` methode, zoals weergegeven in stap 2.

### Waar kan ik meer informatie vinden over Aspose.Slides voor Java?

 U kunt verwijzen naar de[Aspose.Slides voor Java-documentatie](https://reference.aspose.com/slides/java/) voor gedetailleerde informatie over het gebruik van de bibliotheek.