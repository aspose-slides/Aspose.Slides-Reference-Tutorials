---
title: Wijzig tekst op SmartArt Node met Java
linktitle: Wijzig tekst op SmartArt Node met Java
second_title: Aspose.Slides Java PowerPoint-verwerkings-API
description: Ontdek hoe u SmartArt-knooppunttekst in PowerPoint kunt bijwerken met behulp van Java met Aspose.Slides, waardoor de aanpassing van presentaties wordt verbeterd.
type: docs
weight: 22
url: /nl/java/java-powerpoint-smartart-manipulation/change-text-smartart-node-java/
---
## Invoering
SmartArt in PowerPoint is een krachtige functie voor het maken van visueel aantrekkelijke diagrammen. Aspose.Slides voor Java biedt uitgebreide ondersteuning voor het programmatisch manipuleren van SmartArt-elementen. In deze zelfstudie begeleiden we u bij het proces van het wijzigen van tekst op een SmartArt-knooppunt met behulp van Java.
## Vereisten
Zorg ervoor dat u over het volgende beschikt voordat u begint:
- Java Development Kit (JDK) op uw systeem geïnstalleerd.
- Aspose.Slides voor Java-bibliotheek gedownload en waarnaar wordt verwezen in uw Java-project.
- Basiskennis van Java-programmeren.

## Pakketten importeren
Importeer eerst de benodigde pakketten om toegang te krijgen tot de Aspose.Slides-functionaliteit binnen uw Java-code.
```java
import com.aspose.slides.*;
```
Laten we het voorbeeld in meerdere stappen opsplitsen:
## Stap 1: Initialiseer het presentatieobject
```java
Presentation presentation = new Presentation();
```
 Maak een nieuw exemplaar van de`Presentation` klas aan de slag met een PowerPoint-presentatie.
## Stap 2: SmartArt toevoegen aan dia
```java
ISmartArt smart = presentation.getSlides().get_Item(0).getShapes().addSmartArt(10, 10, 400, 300, SmartArtLayoutType.BasicCycle);
```
 Voeg SmartArt toe aan de eerste dia. In dit voorbeeld gebruiken we de`BasicCycle` indeling.
## Stap 3: Open SmartArt Node
```java
ISmartArtNode node = smart.getNodes().get_Item(1);
```
Krijg een verwijzing naar het tweede hoofdknooppunt van de SmartArt.
## Stap 4: Stel tekst in op knooppunt
```java
node.getTextFrame().setText("Second root node");
```
Stel de tekst in voor het geselecteerde SmartArt-knooppunt.
## Stap 5: Presentatie opslaan
```java
presentation.save(dataDir + "ChangeText_On_SmartArt_Node_out.pptx", SaveFormat.Pptx);
```
Sla de gewijzigde presentatie op een opgegeven locatie op.

## Conclusie
In deze zelfstudie hebben we gedemonstreerd hoe u tekst op een SmartArt-knooppunt kunt wijzigen met behulp van Java en Aspose.Slides. Met deze kennis kunt u SmartArt-elementen in uw PowerPoint-presentaties dynamisch manipuleren, waardoor hun visuele aantrekkingskracht en helderheid wordt verbeterd.
## Veelgestelde vragen
### Kan ik de lay-out van de SmartArt wijzigen nadat ik deze aan de dia heb toegevoegd?
 Ja, u kunt de lay-out wijzigen door naar het`SmartArt.setAllNodes(LayoutType)` methode.
### Is Aspose.Slides compatibel met Java 11?
Ja, Aspose.Slides voor Java is compatibel met Java 11 en nieuwere versies.
### Kan ik het uiterlijk van SmartArt-knooppunten programmatisch aanpassen?
U kunt zeker verschillende eigenschappen, zoals kleur, grootte en vorm, wijzigen met de Aspose.Slides API.
### Ondersteunt Aspose.Slides andere typen SmartArt-lay-outs?
Ja, Aspose.Slides ondersteunt een breed scala aan SmartArt-lay-outs, zodat u degene kunt kiezen die het beste bij uw presentatiebehoeften past.
### Waar kan ik meer bronnen en ondersteuning vinden voor Aspose.Slides?
 U kunt een bezoek brengen aan de[Aspose.Slides-documentatie](https://reference.aspose.com/slides/java/) voor gedetailleerde API-referenties en tutorials. Daarnaast kunt u hulp zoeken bij de[Aspose.Slides-forum](https://forum.aspose.com/c/slides/11) of overweeg de aanschaf van een[tijdelijke licentie](https://purchase.aspose.com/temporary-license/) voor professionele ondersteuning.