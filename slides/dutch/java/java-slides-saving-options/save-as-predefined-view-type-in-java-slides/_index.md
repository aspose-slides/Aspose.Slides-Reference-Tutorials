---
title: Opslaan als vooraf gedefinieerd weergavetype in Java-dia's
linktitle: Opslaan als vooraf gedefinieerd weergavetype in Java-dia's
second_title: Aspose.Slides Java PowerPoint-verwerkings-API
description: Leer hoe u vooraf gedefinieerde weergavetypen in Java Slides instelt met behulp van Aspose.Slides voor Java. Stapsgewijze handleiding met codevoorbeelden en veelgestelde vragen.
weight: 10
url: /nl/java/saving-options/save-as-predefined-view-type-in-java-slides/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Opslaan als vooraf gedefinieerd weergavetype in Java-dia's


## Inleiding tot opslaan als vooraf gedefinieerd weergavetype in Java-dia's

In deze stapsgewijze handleiding onderzoeken we hoe u een presentatie met een vooraf gedefinieerd weergavetype kunt opslaan met behulp van Aspose.Slides voor Java. We zullen u voorzien van de benodigde code en uitleg om deze taak met succes uit te voeren.

## Vereisten

Voordat we beginnen, zorg ervoor dat u over het volgende beschikt:

- Basiskennis van Java-programmeren.
- Aspose.Slides voor Java-bibliotheek geïnstalleerd.
- Geïntegreerde ontwikkelomgeving (IDE) naar keuze.

## Uw omgeving instellen

Om aan de slag te gaan, volgt u deze stappen om uw ontwikkelomgeving in te stellen:

1. Maak een nieuw Java-project in uw IDE.
2. Voeg de Aspose.Slides voor Java-bibliotheek als afhankelijkheid toe aan uw project.

Nu uw omgeving is ingesteld, gaan we verder met de code.

## Stap 1: Een presentatie maken

Om te demonstreren hoe u een presentatie opslaat met een vooraf gedefinieerd weergavetype, maken we eerst een nieuwe presentatie. Hier is de code om een presentatie te maken:

```java
// Het pad naar de documentenmap.
String dataDir = "Your Document Directory";
// Het presentatiebestand openen
Presentation presentation = new Presentation();
```

 In deze code maken we een nieuw`Presentation` object, dat onze PowerPoint-presentatie vertegenwoordigt.

## Stap 2: Het weergavetype instellen

Vervolgens stellen we het weergavetype voor onze presentatie in. Weergavetypen bepalen hoe de presentatie wordt weergegeven wanneer deze wordt geopend. In dit voorbeeld stellen we dit in op 'Diamodelweergave'. Hier is de code:

```java
// Weergavetype instellen
presentation.getViewProperties().setLastView(ViewType.SlideMasterView);
```

 In de bovenstaande code gebruiken we de`setLastView` werkwijze van de`ViewProperties` klasse om het weergavetype op in te stellen`SlideMasterView`. U kunt indien nodig andere weergavetypen kiezen.

## Stap 3: De presentatie opslaan

Nu we onze presentatie hebben gemaakt en het weergavetype hebben ingesteld, is het tijd om de presentatie op te slaan. We slaan het op in PPTX-formaat. Hier is de code:

```java
// Presentatie opslaan
presentation.save(dataDir + "SetViewType_out.pptx", SaveFormat.Pptx);
```

 In deze code gebruiken we de`save` werkwijze van de`Presentation` class om de presentatie op te slaan met de opgegeven bestandsnaam en indeling.

## Volledige broncode voor opslaan als vooraf gedefinieerd weergavetype in Java-dia's

```java
// Het pad naar de documentenmap.
String dataDir = "Your Document Directory";
// Het presentatiebestand openen
Presentation presentation = new Presentation();
try
{
	// Weergavetype instellen
	presentation.getViewProperties().setLastView(ViewType.SlideMasterView);
	// Presentatie opslaan
	presentation.save(dataDir + "SetViewType_out.pptx", SaveFormat.Pptx);
}
finally
{
	if (presentation != null) presentation.dispose();
}
```

## Conclusie

In deze zelfstudie hebben we geleerd hoe u een presentatie met een vooraf gedefinieerd weergavetype in Java kunt opslaan met behulp van Aspose.Slides voor Java. Door de meegeleverde code en stappen te volgen, kunt u eenvoudig het weergavetype van uw presentaties instellen en deze in het gewenste formaat opslaan.

## Veelgestelde vragen

### Hoe wijzig ik het weergavetype in iets anders dan "Diamodelweergave"?

 Als u het weergavetype wilt wijzigen in iets anders dan 'Diamodelweergave', hoeft u alleen maar te vervangen`ViewType.SlideMasterView` met het gewenste weergavetype, zoals`ViewType.NormalView` of`ViewType.SlideSorterView`, in de code waarin we het weergavetype instellen.

### Kan ik weergave-eigenschappen instellen voor afzonderlijke dia's in de presentatie?

Ja, u kunt weergave-eigenschappen voor afzonderlijke dia's instellen met Aspose.Slides voor Java. U kunt de eigenschappen van elke dia afzonderlijk openen en bewerken door de dia's in de presentatie te doorlopen.

### In welke andere formaten kan ik mijn presentatie opslaan?

Aspose.Slides voor Java ondersteunt verschillende uitvoerformaten, waaronder PPTX, PDF, TIFF, HTML en meer. U kunt bij het opslaan van uw presentatie het gewenste formaat opgeven met behulp van het daarvoor bestemde bestand`SaveFormat` enum-waarde.

### Is Aspose.Slides voor Java geschikt voor batchverwerking van presentaties?

Ja, Aspose.Slides voor Java is zeer geschikt voor batchverwerkingstaken. U kunt de verwerking van meerdere presentaties automatiseren, wijzigingen aanbrengen en deze in bulk opslaan met behulp van Java-code.

### Waar kan ik meer informatie en documentatie vinden voor Aspose.Slides voor Java?

 Bezoek de documentatiewebsite voor uitgebreide documentatie en referenties met betrekking tot Aspose.Slides voor Java:[Aspose.Slides voor Java-documentatie](https://reference.aspose.com/slides/java/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
