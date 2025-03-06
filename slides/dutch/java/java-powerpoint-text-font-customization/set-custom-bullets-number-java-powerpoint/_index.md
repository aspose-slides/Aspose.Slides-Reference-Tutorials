---
title: Stel een aangepast opsommingstekennummer in Java PowerPoint in
linktitle: Stel een aangepast opsommingstekennummer in Java PowerPoint in
second_title: Aspose.Slides Java PowerPoint-verwerkings-API
description: Leer hoe u aangepaste opsommingstekens kunt instellen in Java PowerPoint met Aspose.Slides, waardoor de helderheid en structuur van presentaties programmatisch wordt verbeterd.
weight: 15
url: /nl/java/java-powerpoint-text-font-customization/set-custom-bullets-number-java-powerpoint/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Stel een aangepast opsommingstekennummer in Java PowerPoint in

## Invoering
In het huidige digitale tijdperk is het creëren van dynamische presentaties cruciaal voor het effectief communiceren van ideeën en gegevens. Aspose.Slides voor Java biedt een krachtige toolkit om PowerPoint-presentaties programmatisch te manipuleren en biedt uitgebreide functies om uw presentatieopbouwproces te verbeteren. In dit artikel wordt dieper ingegaan op het instellen van aangepaste opsommingstekens in Java PowerPoint-presentaties met behulp van Aspose.Slides. Of u nu een doorgewinterde ontwikkelaar of een nieuwkomer bent, deze tutorial begeleidt u stap voor stap door het proces, zodat u deze mogelijkheid efficiënt kunt benutten.
## Vereisten
Voordat u in de zelfstudie duikt, moet u ervoor zorgen dat u aan de volgende vereisten voldoet in uw ontwikkelomgeving:
- Java Development Kit (JDK) geïnstalleerd
- Integrated Development Environment (IDE), zoals IntelliJ IDEA of Eclipse
-  Aspose.Slides voor Java-bibliotheek. Je kunt het downloaden van[hier](https://releases.aspose.com/slides/java/)
- Basiskennis van Java-programmeertaal en objectgeoriënteerde concepten

## Pakketten importeren
Importeer eerst de benodigde Aspose.Slides-klassen en andere Java-standaardbibliotheken:
```java
import com.aspose.slides.*;
```
## Stap 1: Maak een presentatieobject
Begin met het maken van een nieuwe PowerPoint-presentatie met Aspose.Slides.
```java
String dataDir = "Your Document Directory";
Presentation presentation = new Presentation();
```
## Stap 2: Voeg een AutoVorm met tekst toe
Voeg een AutoVorm (rechthoek) in op de dia en open het tekstkader.
```java
IAutoShape shape = presentation.getSlides().get_Item(0).getShapes().addAutoShape(ShapeType.Rectangle, 200, 200, 400, 200);
ITextFrame textFrame = shape.getTextFrame();
```
## Stap 3: verwijder de standaardparagraaf
Verwijder de standaard bestaande alinea uit het tekstkader.
```java
textFrame.getParagraphs().removeAt(0);
```
## Stap 4: Voeg genummerde opsommingstekens toe
Voeg alinea's toe met aangepaste genummerde opsommingstekens, beginnend bij specifieke cijfers.
```java
// Voorbeeldparagraaf met opsommingsteken vanaf 2
Paragraph paragraph1 = new Paragraph();
paragraph1.setText("bullet 2");
paragraph1.getParagraphFormat().setDepth((short) 4);
paragraph1.getParagraphFormat().getBullet().setNumberedBulletStartWith((short) 2);
paragraph1.getParagraphFormat().getBullet().setType(BulletType.Numbered);
textFrame.getParagraphs().add(paragraph1);
// Voorbeeldparagraaf met opsommingsteken vanaf 3
Paragraph paragraph2 = new Paragraph();
paragraph2.setText("bullet 3");
paragraph2.getParagraphFormat().setDepth((short) 4);
paragraph2.getParagraphFormat().getBullet().setNumberedBulletStartWith((short) 3);
paragraph2.getParagraphFormat().getBullet().setType(BulletType.Numbered);
textFrame.getParagraphs().add(paragraph2);
// Voorbeeldparagraaf met opsommingsteken vanaf 7
Paragraph paragraph3 = new Paragraph();
paragraph3.setText("bullet 7");
paragraph3.getParagraphFormat().setDepth((short) 4);
paragraph3.getParagraphFormat().getBullet().setNumberedBulletStartWith((short) 7);
paragraph3.getParagraphFormat().getBullet().setType(BulletType.Numbered);
textFrame.getParagraphs().add(paragraph3);
```
## Stap 5: Sla de presentatie op
Sla ten slotte de gewijzigde presentatie op de door u gewenste locatie op.
```java
presentation.save(dataDir + "SetCustomBulletsNumber-slides.pptx", SaveFormat.Pptx);
```

## Conclusie
Concluderend vereenvoudigt Aspose.Slides voor Java het proces van het programmatisch instellen van aangepaste opsommingstekens in PowerPoint-presentaties. Door de stappen in deze zelfstudie te volgen, kunt u de visuele helderheid en structuur van uw presentaties efficiënt verbeteren.
## Veelgestelde vragen
### Kan ik het uiterlijk van kogels verder aanpassen?
Ja, Aspose.Slides biedt uitgebreide opties om het type, de grootte, de kleur en meer van het opsommingsteken aan te passen.
### Is Aspose.Slides compatibel met alle versies van PowerPoint?
Aspose.Slides ondersteunt PowerPoint-formaten van 97-2003 tot de nieuwste versies.
### Hoe kan ik technische ondersteuning krijgen voor Aspose.Slides?
 Bezoek[Aspose.Slides-forum](https://forum.aspose.com/c/slides/11) voor technische assistentie.
### Kan ik Aspose.Slides uitproberen voordat ik een aankoop doe?
 Ja, u kunt een gratis proefversie downloaden van[hier](https://releases.aspose.com/).
### Waar kan ik Aspose.Slides kopen?
 U kunt Aspose.Slides kopen bij[hier](https://purchase.aspose.com/buy).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
