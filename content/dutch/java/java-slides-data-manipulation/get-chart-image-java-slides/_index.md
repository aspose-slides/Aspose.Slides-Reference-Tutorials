---
title: Grafiekafbeelding ophalen in Java-dia's
linktitle: Grafiekafbeelding ophalen in Java-dia's
second_title: Aspose.Slides Java PowerPoint-verwerkings-API
description: Leer hoe u diagramafbeeldingen kunt verkrijgen in Java Slides met behulp van Aspose.Slides voor Java. Deze stapsgewijze handleiding biedt broncode en tips voor een naadloze integratie.
type: docs
weight: 19
url: /nl/java/data-manipulation/get-chart-image-java-slides/
---

## Inleiding tot het verkrijgen van een grafiekafbeelding in Java-dia's

Aspose.Slides voor Java is een krachtige bibliotheek waarmee u programmatisch met PowerPoint-presentaties kunt werken. Met deze bibliotheek kunt u verschillende elementen uit presentaties, inclusief diagrammen, maken, manipuleren en extraheren. Een veel voorkomende vereiste is het verkrijgen van diagramafbeeldingen uit dia's. In deze handleiding laten we u zien hoe u dat precies doet.

## Vereisten

Voordat we in de code duiken, moet je ervoor zorgen dat je aan de volgende vereisten voldoet:

- Java Development Kit (JDK) op uw systeem geïnstalleerd.
-  Aspose.Slides voor Java-bibliotheek gedownload en geconfigureerd in uw project. Je kunt het downloaden van[hier](https://releases.aspose.com/slides/java/).

## Stap 1: Stel uw project in

Begin met het maken van een Java-project in de Integrated Development Environment (IDE) van uw voorkeur. Zorg ervoor dat u de Aspose.Slides voor Java-bibliotheek hebt toegevoegd aan de afhankelijkheden van uw project.

## Stap 2: Initialiseer de presentatie

Om te beginnen moet u een PowerPoint-presentatie initialiseren. In dit voorbeeld gaan we ervan uit dat u een PowerPoint-bestand met de naam 'test.pptx' in uw documentmap hebt staan.

```java
// Het pad naar de documentenmap.
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "test.pptx");
```

## Stap 3: Voeg een diagram toe en haal de afbeelding op

Vervolgens kunt u een diagram aan een dia toevoegen en de afbeelding ervan verkrijgen. In dit voorbeeld voegen we een geclusterd kolomdiagram toe.

```java
try {
    IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 50, 50, 600, 400);
    BufferedImage img = chart.getThumbnail();
    ImageIO.write(img, ".png", new File(dataDir + "image.png"));
} finally {
    if (pres != null) pres.dispose();
}
```

In dit codefragment maken we een geclusterd kolomdiagram op de eerste dia van de presentatie en verkrijgen vervolgens de miniatuurafbeelding ervan. De afbeelding wordt opgeslagen als "image.png" in de opgegeven map.

## Volledige broncode voor het verkrijgen van een grafiekafbeelding in Java-dia's

```java
// Het pad naar de documentenmap.
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "test.pptx");
try
{
	IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 50, 50, 600, 400);
	BufferedImage img = chart.getThumbnail();
	ImageIO.write(img, ".png", new File(dataDir + "image.png"));
}
finally
{
	if (pres != null) pres.dispose();
}
```

## Conclusie

Het verkrijgen van diagramafbeeldingen uit Java Slides met Aspose.Slides voor Java is een eenvoudig proces. Met de meegeleverde code kunt u deze functionaliteit eenvoudig integreren in uw Java-applicaties, waardoor u effectief met PowerPoint-presentaties kunt werken.

## Veelgestelde vragen

### Hoe installeer ik Aspose.Slides voor Java?

 Het installeren van Aspose.Slides voor Java is eenvoudig. U kunt de bibliotheek downloaden van[hier](https://releases.aspose.com/slides/java/)en volg de installatie-instructies in de documentatie.

### Kan ik het diagram aanpassen voordat ik de afbeelding verkrijg?

Ja, u kunt het uiterlijk, de gegevens en andere eigenschappen van het diagram aanpassen voordat u de afbeelding ervan verkrijgt. Aspose.Slides voor Java biedt uitgebreide opties voor het aanpassen van diagrammen.

### Welke andere functies biedt Aspose.Slides voor Java?

Aspose.Slides voor Java biedt een breed scala aan functies voor het werken met PowerPoint-presentaties, waaronder het maken van dia's, tekstmanipulatie, vormbewerking en nog veel meer. U kunt de documentatie raadplegen voor gedetailleerde informatie.

### Is Aspose.Slides voor Java geschikt voor commercieel gebruik?

Ja, Aspose.Slides voor Java kan voor commerciële doeleinden worden gebruikt. Het biedt licentieopties die geschikt zijn voor zowel individuele ontwikkelaars als ondernemingen.

### Kan ik de kaartafbeelding in een ander formaat opslaan?

Zeker! U kunt de kaartafbeelding in verschillende formaten opslaan, zoals JPEG of GIF, door de juiste bestandsextensie op te geven in het`ImageIO.write` methode.