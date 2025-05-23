---
"description": "Leer hoe u met Aspose.Slides SmartArt-miniaturen voor onderliggende notities in Java kunt maken, waarmee u uw PowerPoint-presentaties moeiteloos kunt verbeteren."
"linktitle": "Miniatuur van SmartArt-kindnotitie maken"
"second_title": "Aspose.Slides Java PowerPoint-verwerkings-API"
"title": "Miniatuur van SmartArt-kindnotitie maken"
"url": "/nl/java/java-powerpoint-shape-thumbnail-creation/create-smartart-child-note-thumbnail/"
"weight": 15
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Miniatuur van SmartArt-kindnotitie maken

## Invoering
In deze tutorial laten we zien hoe je SmartArt-miniaturen voor onderliggende notities in Java kunt maken met Aspose.Slides. Aspose.Slides is een krachtige Java API waarmee ontwikkelaars programmatisch met PowerPoint-presentaties kunnen werken, waardoor ze eenvoudig dia's kunnen maken, wijzigen en manipuleren.
## Vereisten
Voordat we beginnen, zorg ervoor dat u het volgende heeft:
1. Java Development Kit (JDK) op uw systeem geïnstalleerd.
2. Aspose.Slides voor Java-bibliotheek gedownload en geconfigureerd in uw project. U kunt de bibliotheek downloaden van [hier](https://releases.aspose.com/slides/java/).

## Pakketten importeren
Zorg ervoor dat u de benodigde pakketten in uw Java-klasse importeert:
```java
import com.aspose.slides.ISmartArt;
import com.aspose.slides.ISmartArtNode;
import com.aspose.slides.Presentation;
import com.aspose.slides.SmartArtLayoutType;

import javax.imageio.ImageIO;
import java.awt.image.BufferedImage;
import java.io.File;
import java.io.IOException;
```
## Stap 1: Stel uw project in
Zorg ervoor dat u een Java-project hebt ingesteld en geconfigureerd met de Aspose.Slides-bibliotheek.
## Stap 2: Een presentatie maken
Instantieer de `Presentation` klasse om het PPTX-bestand te vertegenwoordigen:
```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
```
## Stap 3: SmartArt toevoegen
SmartArt toevoegen aan uw presentatieslide:
```java
ISmartArt smart = pres.getSlides().get_Item(0).getShapes().addSmartArt(10, 10, 400, 300, SmartArtLayoutType.BasicCycle);
```
## Stap 4: Een knooppuntreferentie verkrijgen
De referentie van een knooppunt verkrijgen door de index ervan te gebruiken:
```java
ISmartArtNode node = smart.getNodes().get_Item(1);
```
## Stap 5: Miniatuur verkrijgen
Haal de miniatuurafbeelding van het SmartArt-knooppunt op:
```java
BufferedImage bmp = node.getShapes().get_Item(0).getThumbnail();
```
## Stap 6: Miniatuur opslaan
Sla de miniatuurafbeelding op in een bestand:
```java
ImageIO.write(bmp, "jpeg", new File(dataDir + "SmartArt_ChildNote_Thumbnail_out.jpeg"));
```
Herhaal deze stappen indien nodig voor elk SmartArt-knooppunt in uw presentatie.

## Conclusie
In deze tutorial hebben we geleerd hoe je met behulp van Aspose.Slides SmartArt-miniaturen voor onderliggende notities in Java kunt maken. Met deze kennis kun je je PowerPoint-presentaties programmatisch verbeteren en eenvoudig visueel aantrekkelijke elementen toevoegen.
## Veelgestelde vragen
### Kan ik Aspose.Slides gebruiken om bestaande PowerPoint-bestanden te bewerken?
Ja, met Aspose.Slides kunt u bestaande PowerPoint-bestanden wijzigen. U kunt onder andere dia's en hun inhoud toevoegen, verwijderen of bewerken.
### Ondersteunt Aspose.Slides het exporteren van dia's naar verschillende bestandsindelingen?
Absoluut! Aspose.Slides ondersteunt het exporteren van dia's naar verschillende formaten, waaronder PDF, afbeeldingen en HTML.
### Is Aspose.Slides geschikt voor PowerPoint-automatisering op ondernemingsniveau?
Ja, Aspose.Slides is ontworpen om PowerPoint-automatiseringstaken op ondernemingsniveau efficiënt en betrouwbaar uit te voeren.
### Kan ik programmatisch complexe SmartArt-diagrammen maken met Aspose.Slides?
Zeker! Aspose.Slides biedt uitgebreide ondersteuning voor het maken en bewerken van SmartArt-diagrammen van verschillende complexiteiten.
### Biedt Aspose.Slides technische ondersteuning voor ontwikkelaars?
Ja, Aspose.Slides biedt toegewijde technische ondersteuning voor ontwikkelaars via hun [forum](https://forum.aspose.com/c/slides/11) en andere kanalen.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}