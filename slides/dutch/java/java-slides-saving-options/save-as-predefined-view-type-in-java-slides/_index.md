---
"description": "Leer hoe u vooraf gedefinieerde weergavetypen in Java Slides instelt met Aspose.Slides voor Java. Stapsgewijze handleiding met codevoorbeelden en veelgestelde vragen."
"linktitle": "Opslaan als vooraf gedefinieerd weergavetype in Java-dia's"
"second_title": "Aspose.Slides Java PowerPoint-verwerkings-API"
"title": "Opslaan als vooraf gedefinieerd weergavetype in Java-dia's"
"url": "/nl/java/saving-options/save-as-predefined-view-type-in-java-slides/"
"weight": 10
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Opslaan als vooraf gedefinieerd weergavetype in Java-dia's


## Inleiding tot Opslaan als vooraf gedefinieerd weergavetype in Java-dia's

In deze stapsgewijze handleiding leggen we uit hoe je een presentatie met een vooraf gedefinieerd weergavetype kunt opslaan met Aspose.Slides voor Java. We geven je de benodigde code en uitleg om deze taak succesvol uit te voeren.

## Vereisten

Voordat we beginnen, zorg ervoor dat u het volgende heeft:

- Basiskennis van Java-programmering.
- Aspose.Slides voor Java-bibliotheek geïnstalleerd.
- Geïntegreerde ontwikkelomgeving (IDE) van uw keuze.

## Uw omgeving instellen

Om te beginnen volgt u deze stappen om uw ontwikkelomgeving in te stellen:

1. Maak een nieuw Java-project in uw IDE.
2. Voeg de Aspose.Slides voor Java-bibliotheek als afhankelijkheid toe aan uw project.

Nu uw omgeving is ingesteld, kunnen we verdergaan met de code.

## Stap 1: Een presentatie maken

Om te laten zien hoe je een presentatie met een vooraf gedefinieerd weergavetype kunt opslaan, maken we eerst een nieuwe presentatie. Hier is de code om een presentatie te maken:

```java
// Het pad naar de documentenmap.
String dataDir = "Your Document Directory";
// Het presentatiebestand openen
Presentation presentation = new Presentation();
```

In deze code maken we een nieuwe `Presentation` object, dat onze PowerPoint-presentatie vertegenwoordigt.

## Stap 2: Het weergavetype instellen

Vervolgens stellen we het weergavetype voor onze presentatie in. Weergavetypen bepalen hoe de presentatie wordt weergegeven wanneer deze wordt geopend. In dit voorbeeld stellen we dit in op 'Diamodelweergave'. Hier is de code:

```java
// Weergavetype instellen
presentation.getViewProperties().setLastView(ViewType.SlideMasterView);
```

In de bovenstaande code gebruiken we de `setLastView` methode van de `ViewProperties` klasse om het weergavetype in te stellen `SlideMasterView`U kunt indien nodig andere weergavetypen kiezen.

## Stap 3: De presentatie opslaan

Nu we onze presentatie hebben gemaakt en het weergavetype hebben ingesteld, is het tijd om de presentatie op te slaan. We slaan hem op in PPTX-formaat. Hier is de code:

```java
// Presentatie opslaan
presentation.save(dataDir + "SetViewType_out.pptx", SaveFormat.Pptx);
```

In deze code gebruiken we de `save` methode van de `Presentation` klasse om de presentatie op te slaan met de opgegeven bestandsnaam en indeling.

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

In deze tutorial hebben we geleerd hoe je een presentatie met een vooraf gedefinieerd weergavetype in Java kunt opslaan met Aspose.Slides voor Java. Door de meegeleverde code en stappen te volgen, kun je eenvoudig het weergavetype van je presentaties instellen en ze in het gewenste formaat opslaan.

## Veelgestelde vragen

### Hoe kan ik het weergavetype wijzigen naar iets anders dan 'Diamasterweergave'?

Om het weergavetype te wijzigen naar iets anders dan 'Diamasterweergave', vervangt u eenvoudigweg `ViewType.SlideMasterView` met het gewenste weergavetype, zoals `ViewType.NofmalView` or `ViewType.SlideSorterView`, in de code waar we het weergave type instellen.

### Kan ik weergave-eigenschappen instellen voor afzonderlijke dia's in de presentatie?

Ja, u kunt weergave-eigenschappen voor individuele dia's instellen met Aspose.Slides voor Java. U kunt de eigenschappen voor elke dia afzonderlijk openen en bewerken door door de dia's in de presentatie te itereren.

### In welke andere formaten kan ik mijn presentatie opslaan?

Aspose.Slides voor Java ondersteunt verschillende uitvoerformaten, waaronder PPTX, PDF, TIFF, HTML en meer. U kunt het gewenste formaat opgeven bij het opslaan van uw presentatie met behulp van de juiste `SaveFormat` enum-waarde.

### Is Aspose.Slides voor Java geschikt voor batchverwerking van presentaties?

Ja, Aspose.Slides voor Java is zeer geschikt voor batchverwerking. U kunt de verwerking van meerdere presentaties automatiseren, wijzigingen toepassen en ze in bulk opslaan met Java-code.

### Waar kan ik meer informatie en documentatie vinden over Aspose.Slides voor Java?

Voor uitgebreide documentatie en referenties met betrekking tot Aspose.Slides voor Java kunt u terecht op de documentatiewebsite: [Aspose.Slides voor Java-documentatie](https://reference.aspose.com/slides/java/).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}