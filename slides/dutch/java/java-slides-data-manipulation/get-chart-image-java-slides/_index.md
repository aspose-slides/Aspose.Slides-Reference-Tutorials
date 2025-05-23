---
"description": "Leer hoe u grafiekafbeeldingen in Java Slides kunt verkrijgen met Aspose.Slides voor Java. Deze stapsgewijze handleiding biedt broncode en tips voor naadloze integratie."
"linktitle": "Grafiekafbeelding ophalen in Java-dia's"
"second_title": "Aspose.Slides Java PowerPoint-verwerkings-API"
"title": "Grafiekafbeelding ophalen in Java-dia's"
"url": "/nl/java/data-manipulation/get-chart-image-java-slides/"
"weight": 19
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Grafiekafbeelding ophalen in Java-dia's


## Inleiding tot het verkrijgen van grafiekafbeeldingen in Java-dia's

Aspose.Slides voor Java is een krachtige bibliotheek waarmee u programmatisch met PowerPoint-presentaties kunt werken. Met deze bibliotheek kunt u verschillende elementen uit presentaties maken, bewerken en extraheren, waaronder grafieken. Een veelvoorkomende vereiste is het verkrijgen van grafiekafbeeldingen uit dia's, en in deze handleiding laten we zien hoe u dat kunt doen.

## Vereisten

Voordat we in de code duiken, moet u ervoor zorgen dat de volgende vereisten aanwezig zijn:

- Java Development Kit (JDK) op uw systeem geïnstalleerd.
- Aspose.Slides voor Java-bibliotheek gedownload en geconfigureerd in uw project. U kunt het downloaden van [hier](https://releases.aspose.com/slides/java/).

## Stap 1: Stel uw project in

Begin met het maken van een Java-project in je favoriete Integrated Development Environment (IDE). Zorg ervoor dat je de Aspose.Slides for Java-bibliotheek hebt toegevoegd aan de afhankelijkheden van je project.

## Stap 2: Initialiseer de presentatie

Om te beginnen moet u een PowerPoint-presentatie initialiseren. In dit voorbeeld gaan we ervan uit dat u een PowerPoint-bestand met de naam 'test.pptx' in uw documentmap hebt staan.

```java
// Het pad naar de documentenmap.
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "test.pptx");
```

## Stap 3: Voeg een grafiek toe en ontvang de afbeelding

Vervolgens kun je een grafiek aan een dia toevoegen en de afbeelding ervan bekijken. In dit voorbeeld voegen we een geclusterde kolomgrafiek toe.

```java
try {
    IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 50, 50, 600, 400);
    BufferedImage img = chart.getThumbnail();
    ImageIO.write(img, ".png", new File(dataDir + "image.png"));
} finally {
    if (pres != null) pres.dispose();
}
```

In dit codefragment maken we een geclusterde kolomgrafiek op de eerste dia van de presentatie en verkrijgen we vervolgens de bijbehorende miniatuurafbeelding. De afbeelding wordt opgeslagen als "image.png" in de opgegeven map.

## Volledige broncode voor het ophalen van grafiekafbeeldingen in Java-dia's

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

Het verkrijgen van grafiekafbeeldingen uit Java Slides met Aspose.Slides voor Java is een eenvoudig proces. Met de meegeleverde code kunt u deze functionaliteit eenvoudig integreren in uw Java-applicaties, zodat u effectief met PowerPoint-presentaties kunt werken.

## Veelgestelde vragen

### Hoe installeer ik Aspose.Slides voor Java?

Het installeren van Aspose.Slides voor Java is eenvoudig. U kunt de bibliotheek downloaden van [hier](https://releases.aspose.com/slides/java/) en volg de installatie-instructies in de documentatie.

### Kan ik de grafiek aanpassen voordat ik de afbeelding ervan ontvang?

Ja, u kunt het uiterlijk, de gegevens en andere eigenschappen van de grafiek aanpassen voordat u de afbeelding ophaalt. Aspose.Slides voor Java biedt uitgebreide opties voor het aanpassen van de grafiek.

### Welke andere functies biedt Aspose.Slides voor Java?

Aspose.Slides voor Java biedt een breed scala aan functies voor het werken met PowerPoint-presentaties, waaronder het maken van dia's, tekstmanipulatie, vormbewerking en nog veel meer. Raadpleeg de documentatie voor gedetailleerde informatie.

### Is Aspose.Slides voor Java geschikt voor commercieel gebruik?

Ja, Aspose.Slides voor Java kan voor commerciële doeleinden worden gebruikt. Het biedt licentieopties die geschikt zijn voor zowel individuele ontwikkelaars als bedrijven.

### Kan ik de grafiekafbeelding in een ander formaat opslaan?

Zeker! U kunt de grafiekafbeelding in verschillende formaten opslaan, zoals JPEG of GIF, door de juiste bestandsextensie in het bestand op te geven. `ImageIO.write` methode.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}