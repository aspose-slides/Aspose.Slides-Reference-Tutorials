---
title: Schaalfactorminiatuur maken
linktitle: Schaalfactorminiatuur maken
second_title: Aspose.Slides Java PowerPoint-verwerkings-API
description: Leer hoe u schaalfactorminiaturen kunt maken in Java met behulp van Aspose.Slides voor Java. Eenvoudig te volgen handleiding met stapsgewijze instructies.
type: docs
weight: 12
url: /nl/java/java-powerpoint-shape-thumbnail-creation/create-scaling-factor-thumbnail/
---
## Invoering
In deze zelfstudie begeleiden we u bij het maken van een schaalfactorminiatuur met Aspose.Slides voor Java. Volg deze stapsgewijze instructies om het gewenste resultaat te bereiken.
## Vereisten
Voordat u begint, moet u ervoor zorgen dat u aan de volgende vereisten voldoet:
- Java Development Kit (JDK) op uw systeem geïnstalleerd.
- Aspose.Slides voor Java-bibliotheek gedownload en ingesteld in uw Java-project.
- Basiskennis van de Java-programmeertaal.

## Pakketten importeren
Importeer eerst de benodigde pakketten die nodig zijn om met Aspose.Slides te werken in uw Java-code. 
```java
import com.aspose.slides.Presentation;
import com.aspose.slides.ShapeThumbnailBounds;
import com.aspose.slides.examples.RunExamples;
import javax.imageio.ImageIO;
import java.awt.image.BufferedImage;
import java.io.File;
import java.io.IOException;
```

Laten we het gegeven voorbeeld nu in meerdere stappen opsplitsen:
## Stap 1: Stel de documentmap in
Definieer het pad naar uw documentmap waar het PowerPoint-presentatiebestand zich bevindt.
```java
String dataDir = "Your Document Directory";
```
 Vervangen`"Your Document Directory"` met het pad naar uw daadwerkelijke documentmap.
## Stap 2: Instantie van het presentatieobject
Maak een exemplaar van de klasse Presentation om het PowerPoint-presentatiebestand weer te geven.
```java
Presentation p = new Presentation(dataDir + "HelloWorld.pptx");
```
 Zorg ervoor dat u deze vervangt`"HelloWorld.pptx"` met de naam van uw PowerPoint-presentatiebestand.
## Stap 3: Maak een afbeelding op volledige schaal
Genereer een afbeelding op volledige schaal van de gewenste dia uit de presentatie.
```java
BufferedImage bitmap = p.getSlides().get_Item(0).getShapes().get_Item(0).getThumbnail(ShapeThumbnailBounds.Shape, 1, 1);
```
Deze code haalt de miniatuur op van de eerste vorm op de eerste dia van de presentatie.
## Stap 4: Sla de afbeelding op
Sla de gegenereerde afbeelding op schijf op in PNG-indeling.
```java
ImageIO.write(bitmap, ".png", new File(dataDir + "Scaling Factor Thumbnail_out.png"));
```
 Zorg ervoor dat u deze vervangt`"Scaling Factor Thumbnail_out.png"` met de gewenste uitvoerbestandsnaam.

## Conclusie
Kortom, u hebt met succes een schaalfactorminiatuur gemaakt met Aspose.Slides voor Java. Door de aangegeven stappen te volgen, kunt u deze functionaliteit eenvoudig in uw Java-applicaties integreren.
## Veelgestelde vragen
### Kan ik Aspose.Slides voor Java gebruiken met elke Java IDE?
Ja, Aspose.Slides voor Java kan worden gebruikt met elke Java Integrated Development Environment (IDE), zoals Eclipse, IntelliJ IDEA of NetBeans.
### Is er een gratis proefversie beschikbaar voor Aspose.Slides voor Java?
 Ja, u kunt profiteren van een gratis proefversie van Aspose.Slides voor Java door naar de[website](https://releases.aspose.com/).
### Waar kan ik ondersteuning vinden voor Aspose.Slides voor Java?
 Ondersteuning voor Aspose.Slides voor Java vindt u op de[Aspose.Slides-forum](https://forum.aspose.com/c/slides/11).
### Hoe kan ik Aspose.Slides voor Java kopen?
 U kunt Aspose.Slides voor Java kopen bij de[aankooppagina](https://purchase.aspose.com/buy).
### Heb ik een tijdelijke licentie nodig voor het gebruik van Aspose.Slides voor Java?
 Ja, u kunt een tijdelijke licentie verkrijgen bij de[tijdelijke licentiepagina](https://purchase.aspose.com/temporary-license/).