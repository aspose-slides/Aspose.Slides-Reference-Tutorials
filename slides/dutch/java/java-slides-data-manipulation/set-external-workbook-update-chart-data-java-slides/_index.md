---
"description": "Leer hoe u externe werkmappen instelt en grafiekgegevens bijwerkt in Java Slides met Aspose.Slides voor Java. Verbeter uw vaardigheden in PowerPoint-automatisering."
"linktitle": "Externe werkmap instellen met bijgewerkte grafiekgegevens in Java-dia's"
"second_title": "Aspose.Slides Java PowerPoint-verwerkings-API"
"title": "Externe werkmap instellen met bijgewerkte grafiekgegevens in Java-dia's"
"url": "/nl/java/data-manipulation/set-external-workbook-update-chart-data-java-slides/"
"weight": 20
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Externe werkmap instellen met bijgewerkte grafiekgegevens in Java-dia's


## Inleiding tot het instellen van een externe werkmap met bijgewerkte grafiekgegevens in Java-dia's

In deze uitgebreide handleiding leiden we je door het proces van het instellen van een externe werkmap met bijgewerkte grafiekgegevens in Java Slides met behulp van de Aspose.Slides voor Java API. Met deze krachtige bibliotheek kun je PowerPoint-presentaties programmatisch bewerken, waardoor je taken zoals het bijwerken van grafiekgegevens vanuit een externe bron eenvoudig kunt automatiseren. Aan het einde van deze tutorial heb je een duidelijk begrip van hoe je deze taak kunt uitvoeren met stapsgewijze instructies en bijbehorende Java-code.

## Vereisten

Voordat we met de implementatie beginnen, moet u ervoor zorgen dat de volgende vereisten aanwezig zijn:

1. Aspose.Slides voor Java: U dient de Aspose.Slides voor Java-bibliotheek geïnstalleerd te hebben. U kunt deze downloaden van [hier](https://releases.aspose.com/slides/java/).

2. Java-ontwikkelomgeving: zorg ervoor dat u een Java-ontwikkelomgeving op uw systeem hebt ingesteld.

## Stap 1: Een nieuwe presentatie maken

Om te beginnen maken we een nieuwe PowerPoint-presentatie met Aspose.Slides voor Java. Hier is de Java-code om dat te doen:

```java
// Het pad naar de documentenmap.
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
```

## Stap 2: Een grafiek toevoegen

Laten we nu een grafiek aan onze presentatie toevoegen. In dit voorbeeld maken we een cirkeldiagram:

```java
IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.Pie, 50, 50, 400, 600, true);
```

## Stap 3: Externe werkmap instellen

Hier stellen we de externe werkmap in als gegevensbron voor onze grafiek. U moet de URL naar de externe werkmap opgeven, ook al bestaat deze momenteel niet:

```java
IChartData chartData = chart.getChartData();
chartData.setExternalWorkbook("http://pad/bestaat/niet", false);
```

## Stap 4: Sla de presentatie op

Sla ten slotte de presentatie op met de bijgewerkte grafiekgegevens:

```java
pres.save(dataDir + "SetExternalWorkbookWithUpdateChartData.pptx", SaveFormat.Pptx);
```

## Volledige broncode voor het instellen van een externe werkmap met bijgewerkte grafiekgegevens in Java-dia's

```java
// Het pad naar de documentenmap.
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
try
{
	IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.Pie, 50, 50, 400, 600, true);
	IChartData chartData = chart.getChartData();
	chartData.setExternalWorkbook("http://pad/bestaat/niet", false);
	pres.save(dataDir + "SetExternalWorkbookWithUpdateChartData.pptx", SaveFormat.Pptx);
}
finally
{
	if (pres != null) pres.dispose();
}
```

## Conclusie

Gefeliciteerd! Je hebt geleerd hoe je een externe werkmap met bijgewerkte grafiekgegevens in Java Slides kunt instellen met Aspose.Slides voor Java. Dit kan ontzettend handig zijn voor het dynamisch bijwerken van grafieken in je PowerPoint-presentaties vanuit externe gegevensbronnen.

## Veelgestelde vragen

### Hoe kan ik de externe werkmapgegevens voor de grafiek bijwerken?

Om de gegevens in de externe werkmap voor de grafiek bij te werken, hoeft u alleen de gegevens in de externe werkmap op de opgegeven URL aan te passen. De volgende keer dat u de presentatie opent, haalt Aspose.Slides voor Java de bijgewerkte gegevens op uit de externe werkmap en werkt de grafiek dienovereenkomstig bij.

### Kan ik een lokaal bestand gebruiken als externe werkmap?

Ja, u kunt een lokaal bestand als externe werkmap gebruiken door het bestandspad op te geven in plaats van een URL. Zorg er wel voor dat het bestandspad correct is en toegankelijk is vanuit uw Java-applicatie.

### Zijn er beperkingen voor het gebruik van externe werkmappen met Aspose.Slides voor Java?

Hoewel het gebruik van externe werkmappen een krachtige functie is, moet u er rekening mee houden dat de beschikbaarheid van de gegevens in de externe werkmap afhankelijk is van de toegankelijkheid via de opgegeven URL of het opgegeven bestandspad. Zorg ervoor dat de externe gegevensbron beschikbaar is wanneer u de presentatie opent om problemen met het ophalen van gegevens te voorkomen.

### Kan ik het uiterlijk van de grafiek aanpassen nadat ik de externe werkmap heb ingesteld?

Ja, u kunt het uiterlijk van de grafiek aanpassen, inclusief de titel, labels, kleuren en meer, zelfs nadat u de externe werkmap hebt ingesteld. Aspose.Slides voor Java biedt uitgebreide opties voor het opmaken van grafieken om aan uw wensen te voldoen.

### Waar kan ik meer documentatie en bronnen vinden voor Aspose.Slides voor Java?

Voor gedetailleerde documentatie en aanvullende bronnen, bezoek de Aspose.Slides voor Java-documentatie op [hier](https://reference.aspose.com/slides/java/).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}