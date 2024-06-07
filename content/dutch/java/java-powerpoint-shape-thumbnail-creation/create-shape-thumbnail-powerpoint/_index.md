---
title: Maak een vormminiatuur in PowerPoint
linktitle: Maak een vormminiatuur in PowerPoint
second_title: Aspose.Slides Java PowerPoint-verwerkings-API
description: Leer hoe u vormminiaturen kunt genereren in PowerPoint-presentaties met Aspose.Slides voor Java. Stap-voor-stap handleiding meegeleverd.
type: docs
weight: 14
url: /nl/java/java-powerpoint-shape-thumbnail-creation/create-shape-thumbnail-powerpoint/
---
## Invoering
In deze zelfstudie gaan we dieper in op het maken van vormminiaturen in PowerPoint-presentaties met behulp van Aspose.Slides voor Java. Aspose.Slides is een krachtige bibliotheek waarmee ontwikkelaars programmatisch met PowerPoint-bestanden kunnen werken, waardoor verschillende taken kunnen worden geautomatiseerd, waaronder het genereren van vormminiaturen.
## Vereisten
Voordat we beginnen, zorg ervoor dat u aan de volgende vereisten voldoet:
- Basiskennis van Java-programmeren.
- Java Development Kit (JDK) op uw systeem geïnstalleerd.
-  Aspose.Slides voor Java-bibliotheek gedownload en ingesteld in uw project. Je kunt het downloaden van[hier](https://releases.aspose.com/slides/java/).

## Pakketten importeren
Ten eerste moet u de benodigde pakketten in uw Java-code importeren om de functionaliteiten van Aspose.Slides te kunnen gebruiken. Voeg de volgende importinstructies toe aan het begin van uw Java-bestand:
```java
import com.aspose.slides.Presentation;
import com.aspose.slides.examples.RunExamples;
import javax.imageio.ImageIO;
import java.awt.image.BufferedImage;
import java.io.File;
import java.io.IOException;
```
## Stap 1: Definieer de documentmap
```java
String dataDir = "Your Document Directory";
```
 Vervangen`"Your Document Directory"` met het pad naar de map met uw PowerPoint-bestand.
## Stap 2: Presentatieobject instantiëren
```java
Presentation presentation = new Presentation(dataDir + "HelloWorld.pptx");
```
 Maak een nieuw exemplaar van de`Presentation` class, waarbij u het pad naar uw PowerPoint-bestand als parameter doorgeeft.
## Stap 3: Genereer vormminiatuur
```java
BufferedImage bitmap = presentation.getSlides().get_Item(0).getShapes().get_Item(0).getThumbnail();
```
Haal de miniatuur van de gewenste vorm op uit de eerste dia van de presentatie.
## Stap 4: Bewaar miniatuurafbeelding
```java
ImageIO.write(bitmap, ".png", new File(dataDir + "Shape_thumbnail_out.png"));
```
Sla de gegenereerde miniatuurafbeelding op schijf op in PNG-indeling met de opgegeven bestandsnaam.

## Conclusie
Concluderend heeft deze tutorial gedemonstreerd hoe u vormminiaturen kunt maken in PowerPoint-presentaties met behulp van Aspose.Slides voor Java. Door de stapsgewijze handleiding te volgen en de meegeleverde codefragmenten te gebruiken, kunt u programmatisch vormminiaturen efficiënt genereren.

## Veelgestelde vragen
### Kan ik miniaturen maken voor vormen op elke dia in de presentatie?
Ja, u kunt de code aanpassen om vormen op elke dia te targeten door de dia-index dienovereenkomstig aan te passen.
### Ondersteunt Aspose.Slides andere afbeeldingsformaten voor het opslaan van miniaturen?
Ja, naast PNG ondersteunt Aspose.Slides het opslaan van miniaturen in verschillende afbeeldingsformaten zoals JPEG, GIF en BMP.
### Is Aspose.Slides geschikt voor commercieel gebruik?
Ja, Aspose.Slides biedt commerciële licenties voor bedrijven en organisaties. U kunt een licentie kopen bij[hier](https://purchase.aspose.com/buy).
### Kan ik Aspose.Slides uitproberen voordat ik een aankoop doe?
 Absoluut! U kunt een gratis proefversie van Aspose.Slides downloaden van[hier](https://releases.aspose.com/) om de kenmerken en mogelijkheden ervan te evalueren.
### Waar kan ik ondersteuning vinden voor Aspose.Slides?
 Als u vragen heeft of hulp nodig heeft met Aspose.Slides, kunt u terecht op de[Aspose.Slides-forum](https://forum.aspose.com/c/slides/11) Voor ondersteuning.