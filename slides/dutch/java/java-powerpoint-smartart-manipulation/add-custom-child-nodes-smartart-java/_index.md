---
"description": "Leer hoe u aangepaste onderliggende knooppunten toevoegt aan SmartArt in PowerPoint-presentaties met behulp van Java en Aspose.Slides. Verfraai uw dia's moeiteloos met professionele afbeeldingen."
"linktitle": "Aangepaste onderliggende knooppunten toevoegen in SmartArt met behulp van Java"
"second_title": "Aspose.Slides Java PowerPoint-verwerkings-API"
"title": "Aangepaste onderliggende knooppunten toevoegen in SmartArt met behulp van Java"
"url": "/nl/java/java-powerpoint-smartart-manipulation/add-custom-child-nodes-smartart-java/"
"weight": 11
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Aangepaste onderliggende knooppunten toevoegen in SmartArt met behulp van Java

## Invoering
SmartArt is een krachtige functie in PowerPoint waarmee gebruikers snel en eenvoudig professioneel ogende afbeeldingen kunnen maken. In deze tutorial leren we hoe je aangepaste onderliggende knooppunten aan SmartArt kunt toevoegen met behulp van Java en Aspose.Slides.
## Vereisten
Voordat we beginnen, zorg ervoor dat u het volgende heeft:
1. Java Development Kit (JDK): Zorg ervoor dat Java op uw systeem is geïnstalleerd.
2. Aspose.Slides voor Java: Download en installeer Aspose.Slides voor Java van [hier](https://releases.aspose.com/slides/java/).

## Pakketten importeren
Om te beginnen importeert u de benodigde pakketten in uw Java-project:
```java
import com.aspose.slides.*;
```
## Stap 1: Laad de presentatie
Laad de PowerPoint-presentatie waaraan u aangepaste onderliggende knooppunten aan de SmartArt wilt toevoegen:
```java
String dataDir = "Your Document Directory";
// Laad de gewenste presentatie
Presentation pres = new Presentation(dataDir + "YourPresentation.pptx");
```
## Stap 2: SmartArt toevoegen aan dia
Laten we nu SmartArt aan de dia toevoegen:
```java
ISmartArt smart = pres.getSlides().get_Item(0).getShapes().addSmartArt(20, 20, 600, 500, SmartArtLayoutType.OrganizationChart);
```
## Stap 3: SmartArt-vorm verplaatsen
Verplaats de SmartArt-vorm naar een nieuwe positie:
```java
ISmartArtNode node = smart.getAllNodes().get_Item(1);
ISmartArtShape shape = node.getShapes().get_Item(1);
shape.setX(shape.getX() + (shape.getWidth() * 2));
shape.setY(shape.getY() - (shape.getHeight() / 2));
```
## Stap 4: Wijzig de vormbreedte
De breedte van de SmartArt-vorm wijzigen:
```java
node = smart.getAllNodes().get_Item(2);
shape = node.getShapes().get_Item(1);
shape.setWidth(shape.getWidth() + (shape.getWidth() / 2));
```
## Stap 5: Verander de vormhoogte
De hoogte van de SmartArt-vorm wijzigen:
```java
node = smart.getAllNodes().get_Item(3);
shape = node.getShapes().get_Item(1);
shape.setHeight(shape.getHeight() + (shape.getHeight() / 2));
```
## Stap 6: Draai de vorm
De SmartArt-vorm roteren:
```java
node = smart.getAllNodes().get_Item(4);
shape = node.getShapes().get_Item(1);
shape.setRotation(90);
```
## Stap 7: Sla de presentatie op
Sla ten slotte de gewijzigde presentatie op:
```java
pres.save(dataDir + "ModifiedPresentation.pptx", SaveFormat.Pptx);
```

## Conclusie
In deze tutorial hebben we geleerd hoe je aangepaste onderliggende knooppunten aan SmartArt kunt toevoegen met behulp van Java en Aspose.Slides. Door deze stappen te volgen, kun je je presentaties verbeteren met aangepaste afbeeldingen, waardoor ze aantrekkelijker en professioneler worden.
## Veelgestelde vragen
### Kan ik verschillende soorten SmartArt-lay-outs toevoegen met Aspose.Slides voor Java?
Ja, Aspose.Slides voor Java ondersteunt verschillende SmartArt-layouts, zodat u de lay-out kunt kiezen die het beste bij uw presentatiebehoeften past.
### Is Aspose.Slides voor Java compatibel met verschillende versies van PowerPoint?
Aspose.Slides voor Java is ontworpen om naadloos te werken met verschillende versies van PowerPoint, waardoor compatibiliteit en consistentie op alle platforms wordt gegarandeerd.
### Kan ik het uiterlijk van SmartArt-vormen programmatisch aanpassen?
Absoluut! Met Aspose.Slides voor Java kunt u het uiterlijk, de grootte, de kleur en de lay-out van SmartArt-vormen programmatisch aanpassen aan uw ontwerpvoorkeuren.
### Biedt Aspose.Slides voor Java documentatie en ondersteuning?
Ja, u kunt uitgebreide documentatie en toegang tot community-ondersteuningsforums vinden op de Aspose-website.
### Is er een proefversie beschikbaar voor Aspose.Slides voor Java?
Ja, u kunt een gratis proefversie van Aspose.Slides voor Java downloaden van de website om de functies en mogelijkheden ervan te verkennen voordat u een aankoop doet. [hier](https://releases.aspose.com/slides/java/).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}