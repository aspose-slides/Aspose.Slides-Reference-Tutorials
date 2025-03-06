---
title: Stel een externe werkmap in met het bijwerken van grafiekgegevens in Java-dia's
linktitle: Stel een externe werkmap in met het bijwerken van grafiekgegevens in Java-dia's
second_title: Aspose.Slides Java PowerPoint-verwerkings-API
description: Leer hoe u externe werkmappen instelt en diagramgegevens bijwerkt in Java Slides met behulp van Aspose.Slides voor Java. Verbeter uw PowerPoint-automatiseringsvaardigheden.
weight: 20
url: /nl/java/data-manipulation/set-external-workbook-update-chart-data-java-slides/
---

{< blocks/products/pf/main-wrap-class >}
{< blocks/products/pf/main-container >}
{< blocks/products/pf/tutorial-page-section >}


## Inleiding tot het instellen van een externe werkmap met het bijwerken van grafiekgegevens in Java-dia's

In deze uitgebreide handleiding leiden we u door het proces van het instellen van een externe werkmap met bijgewerkte grafiekgegevens in Java Slides met behulp van de Aspose.Slides voor Java API. Met deze krachtige bibliotheek kunt u PowerPoint-presentaties programmatisch manipuleren, waardoor u eenvoudig taken kunt automatiseren, zoals het bijwerken van diagramgegevens vanuit een externe bron. Aan het einde van deze tutorial begrijpt u duidelijk hoe u deze taak kunt uitvoeren met stapsgewijze instructies en bijbehorende Java-code.

## Vereisten

Voordat we ingaan op de implementatie, moet u ervoor zorgen dat u aan de volgende vereisten voldoet:

1.  Aspose.Slides voor Java: De Aspose.Slides voor Java-bibliotheek moet geïnstalleerd zijn. Je kunt het downloaden van[hier](https://releases.aspose.com/slides/java/).

2. Java-ontwikkelomgeving: Zorg ervoor dat er een Java-ontwikkelomgeving op uw systeem is geïnstalleerd.

## Stap 1: Maak een nieuwe presentatie

Laten we om te beginnen een nieuwe PowerPoint-presentatie maken met Aspose.Slides voor Java. Hier is de Java-code om dat te doen:

```java
// Het pad naar de documentenmap.
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
```

## Stap 2: Voeg een diagram toe

Laten we nu een diagram aan onze presentatie toevoegen. In dit voorbeeld maken we een cirkeldiagram:

```java
IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.Pie, 50, 50, 400, 600, true);
```

## Stap 3: Stel de externe werkmap in

Hier stellen we de externe werkmap in als gegevensbron voor ons diagram. U moet de URL naar de externe werkmap opgeven, zelfs als deze momenteel niet bestaat:

```java
IChartData chartData = chart.getChartData();
chartData.setExternalWorkbook("http://pad/bestaat niet/bestaat", false);
```

## Stap 4: Sla de presentatie op

Sla ten slotte de presentatie op met de bijgewerkte grafiekgegevens:

```java
pres.save(dataDir + "SetExternalWorkbookWithUpdateChartData.pptx", SaveFormat.Pptx);
```

## Volledige broncode voor externe werkmap instellen met diagramgegevens bijwerken in Java-dia's

```java
// Het pad naar de documentenmap.
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
try
{
	IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.Pie, 50, 50, 400, 600, true);
	IChartData chartData = chart.getChartData();
	chartData.setExternalWorkbook("http://pad/bestaat niet/bestaat", false);
	pres.save(dataDir + "SetExternalWorkbookWithUpdateChartData.pptx", SaveFormat.Pptx);
}
finally
{
	if (pres != null) pres.dispose();
}
```

## Conclusie

Gefeliciteerd! U hebt geleerd hoe u een externe werkmap kunt instellen met bijgewerkte diagramgegevens in Java Slides met behulp van Aspose.Slides voor Java. Dit kan ongelooflijk handig zijn voor het dynamisch bijwerken van diagrammen in uw PowerPoint-presentaties vanuit externe gegevensbronnen.

## Veelgestelde vragen

### Hoe kan ik de externe werkmapgegevens voor het diagram bijwerken?

Om de externe werkmapgegevens voor het diagram bij te werken, hoeft u alleen maar de gegevens in de externe werkmap op de opgegeven URL te wijzigen. De volgende keer dat u de presentatie opent, haalt Aspose.Slides voor Java de bijgewerkte gegevens op uit de externe werkmap en werkt het diagram dienovereenkomstig bij.

### Kan ik een lokaal bestand als externe werkmap gebruiken?

Ja, u kunt een lokaal bestand als externe werkmap gebruiken door het bestandspad op te geven in plaats van een URL. Zorg ervoor dat het bestandspad correct is en toegankelijk is vanuit uw Java-toepassing.

### Zijn er beperkingen voor het gebruik van externe werkmappen met Aspose.Slides voor Java?

Hoewel het gebruik van externe werkmappen een krachtige functie is, moet u er rekening mee houden dat de beschikbaarheid van de gegevens van de externe werkmap afhankelijk is van de toegankelijkheid ervan via de opgegeven URL of het opgegeven bestandspad. Zorg ervoor dat de externe gegevensbron beschikbaar is wanneer u de presentatie opent om problemen met het ophalen van gegevens te voorkomen.

### Kan ik het uiterlijk van het diagram aanpassen nadat ik de externe werkmap heb ingesteld?

Ja, u kunt het uiterlijk van het diagram aanpassen, inclusief de titel, labels, kleuren en meer, zelfs nadat u de externe werkmap hebt ingesteld. Aspose.Slides voor Java biedt uitgebreide opmaakopties voor diagrammen om aan uw behoeften te voldoen.

### Waar kan ik meer documentatie en bronnen vinden voor Aspose.Slides voor Java?

 Voor gedetailleerde documentatie en aanvullende bronnen gaat u naar de Aspose.Slides voor Java-documentatie op[hier](https://reference.aspose.com/slides/java/).
{< /blocks/products/pf/tutorial-page-section >}

{< /blocks/products/pf/main-container >}
{< /blocks/products/pf/main-wrap-class >}

{< blocks/products/products-backtop-button >}
