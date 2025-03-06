---
title: Voeg knooppunten op specifieke posities toe in SmartArt met behulp van Java
linktitle: Voeg knooppunten op specifieke posities toe in SmartArt met behulp van Java
second_title: Aspose.Slides Java PowerPoint-verwerkings-API
description: Ontdek hoe u knooppunten op specifieke posities in SmartArt kunt toevoegen met behulp van Java met Aspose.Slides. Creëer moeiteloos dynamische presentaties.
weight: 16
url: /nl/java/java-powerpoint-smartart-manipulation/add-nodes-specific-position-smartart-java/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Voeg knooppunten op specifieke posities toe in SmartArt met behulp van Java

## Invoering
In deze zelfstudie begeleiden we u bij het toevoegen van knooppunten op specifieke posities in SmartArt met behulp van Java met Aspose.Slides. SmartArt is een functie in PowerPoint waarmee u visueel aantrekkelijke diagrammen en diagrammen kunt maken.
## Vereisten
Zorg ervoor dat u over het volgende beschikt voordat u begint:
1. Java Development Kit (JDK) op uw systeem geïnstalleerd.
2.  Aspose.Slides voor Java-bibliotheek gedownload. Je kunt het downloaden van[hier](https://releases.aspose.com/slides/java/).
3. Basiskennis van de programmeertaal Java.

## Pakketten importeren
Laten we eerst de benodigde pakketten in onze Java-code importeren:
```java
import com.aspose.slides.*;
import java.io.File;
```
## Stap 1: Maak een presentatie-instantie
Begin met het maken van een exemplaar van de klasse Presentation:
```java
Presentation pres = new Presentation();
```
## Stap 2: Open de presentatiedia
Ga naar de dia waaraan u de SmartArt wilt toevoegen:
```java
ISlide slide = pres.getSlides().get_Item(0);
```
## Stap 3: Voeg SmartArt-vorm toe
Voeg een SmartArt-vorm toe aan de dia:
```java
ISmartArt smart = slide.getShapes().addSmartArt(0, 0, 400, 400, SmartArtLayoutType.StackedList);
```
## Stap 4: Open SmartArt Node
Ga naar het SmartArt-knooppunt op de gewenste index:
```java
ISmartArtNode node = smart.getAllNodes().get_Item(0);
```
## Stap 5: Voeg een onderliggend knooppunt toe op een specifieke positie
Voeg een nieuw onderliggend knooppunt toe op een specifieke positie in het bovenliggende knooppunt:
```java
SmartArtNode chNode = (SmartArtNode) ((SmartArtNodeCollection) node.getChildNodes()).addNodeByPosition(2);
```
## Stap 6: Voeg tekst toe aan het knooppunt
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
In deze zelfstudie hebt u geleerd hoe u knooppunten op specifieke posities in SmartArt kunt toevoegen met behulp van Java met Aspose.Slides. Door deze stappen te volgen, kunt u SmartArt-vormen programmatisch manipuleren om dynamische presentaties te maken.
## Veelgestelde vragen
### Kan ik meerdere knooppunten tegelijk toevoegen?
Ja, u kunt programmatisch meerdere knooppunten toevoegen door de gewenste posities te herhalen.
### Is Aspose.Slides compatibel met alle versies van PowerPoint?
Aspose.Slides ondersteunt verschillende PowerPoint-formaten, waardoor compatibiliteit met de meeste versies wordt gegarandeerd.
### Kan ik het uiterlijk van SmartArt-knooppunten aanpassen?
Ja, u kunt het uiterlijk van knooppunten aanpassen, inclusief hun grootte, kleur en stijl.
### Biedt Aspose.Slides ondersteuning voor andere programmeertalen?
Ja, Aspose.Slides biedt bibliotheken voor meerdere programmeertalen, waaronder .NET en Python.
### Is er een proefversie beschikbaar voor Aspose.Slides?
 Ja, u kunt een gratis proefversie downloaden van[hier](https://releases.aspose.com/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
