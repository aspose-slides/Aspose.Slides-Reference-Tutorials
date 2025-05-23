---
"description": "Ontdek hoe je knooppunten op specifieke posities in SmartArt kunt toevoegen met behulp van Java en Aspose.Slides. Maak moeiteloos dynamische presentaties."
"linktitle": "Knooppunten op specifieke posities toevoegen in SmartArt met behulp van Java"
"second_title": "Aspose.Slides Java PowerPoint-verwerkings-API"
"title": "Knooppunten op specifieke posities toevoegen in SmartArt met behulp van Java"
"url": "/nl/java/java-powerpoint-smartart-manipulation/add-nodes-specific-position-smartart-java/"
"weight": 16
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Knooppunten op specifieke posities toevoegen in SmartArt met behulp van Java

## Invoering
In deze tutorial begeleiden we je door het proces van het toevoegen van knooppunten op specifieke posities in SmartArt met behulp van Java en Aspose.Slides. SmartArt is een functie in PowerPoint waarmee je visueel aantrekkelijke diagrammen en grafieken kunt maken.
## Vereisten
Voordat u begint, moet u ervoor zorgen dat u het volgende heeft:
1. Java Development Kit (JDK) op uw systeem geïnstalleerd.
2. Aspose.Slides voor Java-bibliotheek gedownload. Je kunt het downloaden van [hier](https://releases.aspose.com/slides/java/).
3. Basiskennis van de programmeertaal Java.

## Pakketten importeren
Laten we eerst de benodigde pakketten in onze Java-code importeren:
```java
import com.aspose.slides.*;
import java.io.File;
```
## Stap 1: Een presentatie-instantie maken
Begin met het maken van een exemplaar van de Presentation-klasse:
```java
Presentation pres = new Presentation();
```
## Stap 2: Toegang tot de presentatieslide
Ga naar de dia waaraan u de SmartArt wilt toevoegen:
```java
ISlide slide = pres.getSlides().get_Item(0);
```
## Stap 3: SmartArt-vorm toevoegen
Voeg een SmartArt-vorm toe aan de dia:
```java
ISmartArt smart = slide.getShapes().addSmartArt(0, 0, 400, 400, SmartArtLayoutType.StackedList);
```
## Stap 4: Toegang tot SmartArt Node
Ga naar het SmartArt-knooppunt op de gewenste index:
```java
ISmartArtNode node = smart.getAllNodes().get_Item(0);
```
## Stap 5: Voeg een onderliggend knooppunt toe op een specifieke positie
Voeg een nieuw onderliggend knooppunt toe op een specifieke positie in het bovenliggende knooppunt:
```java
SmartArtNode chNode = (SmartArtNode) ((SmartArtNodeCollection) node.getChildNodes()).addNodeByPosition(2);
```
## Stap 6: Tekst toevoegen aan het knooppunt
Stel de tekst in voor het nieuw toegevoegde knooppunt:
```java
chNode.getTextFrame().setText("Sample Text Added");
```
## Stap 7: Sla de presentatie op
Sla de gewijzigde presentatie op:
```java
pres.save(dataDir + "AddSmartArtNodeByPosition_out.pptx", SaveFormat.Pptx);
```

## Conclusie
In deze tutorial heb je geleerd hoe je knooppunten op specifieke posities in SmartArt kunt toevoegen met behulp van Java en Aspose.Slides. Door deze stappen te volgen, kun je SmartArt-vormen programmatisch manipuleren om dynamische presentaties te maken.
## Veelgestelde vragen
### Kan ik meerdere knooppunten tegelijk toevoegen?
Ja, u kunt programmatisch meerdere knooppunten toevoegen door over de gewenste posities te itereren.
### Is Aspose.Slides compatibel met alle versies van PowerPoint?
Aspose.Slides ondersteunt verschillende PowerPoint-formaten en is daarom compatibel met de meeste versies.
### Kan ik het uiterlijk van SmartArt-knooppunten aanpassen?
Ja, u kunt het uiterlijk van knooppunten aanpassen, waaronder de grootte, kleur en stijl.
### Biedt Aspose.Slides ondersteuning voor andere programmeertalen?
Ja, Aspose.Slides biedt bibliotheken voor meerdere programmeertalen, waaronder .NET en Python.
### Is er een proefversie beschikbaar voor Aspose.Slides?
Ja, u kunt een gratis proefversie downloaden van [hier](https://releases.aspose.com/).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}