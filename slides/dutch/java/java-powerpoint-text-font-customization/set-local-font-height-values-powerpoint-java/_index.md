---
title: Stel lokale lettertypehoogtewaarden in PowerPoint in met behulp van Java
linktitle: Stel lokale lettertypehoogtewaarden in PowerPoint in met behulp van Java
second_title: Aspose.Slides Java PowerPoint-verwerkings-API
description: Leer hoe u de letterhoogten in PowerPoint-presentaties kunt aanpassen met Java met Aspose.Slides. Verbeter moeiteloos de tekstopmaak in uw dia's.
weight: 17
url: /nl/java/java-powerpoint-text-font-customization/set-local-font-height-values-powerpoint-java/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Stel lokale lettertypehoogtewaarden in PowerPoint in met behulp van Java

## Invoering
In deze zelfstudie leert u hoe u de letterhoogten op verschillende niveaus in PowerPoint-presentaties kunt manipuleren met Aspose.Slides voor Java. Het beheersen van de lettergroottes is cruciaal voor het creëren van visueel aantrekkelijke en gestructureerde presentaties. We zullen stapsgewijze voorbeelden doornemen om te illustreren hoe u de letterhoogten voor verschillende tekstelementen kunt instellen.
## Vereisten
Zorg ervoor dat u over het volgende beschikt voordat u begint:
- Java Development Kit (JDK) op uw systeem geïnstalleerd
-  Aspose.Slides voor Java-bibliotheek. Je kunt het downloaden[hier](https://releases.aspose.com/slides/java/).
- Een basiskennis van Java-programmeren en PowerPoint-presentaties
## Pakketten importeren
Zorg ervoor dat u de benodigde Aspose.Slides-pakketten in uw Java-bestand opneemt:
```java
import com.aspose.slides.*;
```
## Stap 1: Initialiseer een presentatieobject
Maak eerst een nieuw PowerPoint-presentatieobject:
```java
Presentation pres = new Presentation();
```
## Stap 2: Voeg een vorm en tekstkader toe
Voeg een automatische vorm met een tekstkader toe aan de eerste dia:
```java
IAutoShape newShape = pres.getSlides().get_Item(0).getShapes().addAutoShape(ShapeType.Rectangle, 100, 100, 400, 75, false);
newShape.addTextFrame("");
```
## Stap 3: Maak tekstgedeelten
Definieer tekstgedeelten met verschillende lettertypehoogtes:
```java
IPortion portion0 = new Portion("Sample text with first portion");
IPortion portion1 = new Portion(" and second portion.");
newShape.getTextFrame().getParagraphs().get_Item(0).getPortions().add(portion0);
newShape.getTextFrame().getParagraphs().get_Item(0).getPortions().add(portion1);
```
## Stap 4: Stel de letterhoogte in
Stel letterhoogten in op verschillende niveaus:
```java
pres.getDefaultTextStyle().getLevel(0).getDefaultPortionFormat().setFontHeight(24);
newShape.getTextFrame().getParagraphs().get_Item(0).getParagraphFormat().getDefaultPortionFormat().setFontHeight(40);
newShape.getTextFrame().getParagraphs().get_Item(0).getPortions().get_Item(0).getPortionFormat().setFontHeight(55);
newShape.getTextFrame().getParagraphs().get_Item(0).getPortions().get_Item(1).getPortionFormat().setFontHeight(18);
```
## Stap 5: Sla de presentatie op
Sla de gewijzigde presentatie op in een bestand:
```java
pres.save("YourOutputDirectory/SetLocalFontHeightValues.pptx", SaveFormat.Pptx);
```

## Conclusie
In deze zelfstudie werd gedemonstreerd hoe u de letterhoogten in PowerPoint-dia's programmatisch kunt aanpassen met Aspose.Slides voor Java. Door de lettergroottes op verschillende niveaus (voor de hele presentatie, alinea's en gedeelten) te manipuleren, kunt u nauwkeurige controle krijgen over de tekstopmaak in uw presentaties.
## Veelgestelde vragen
### Wat is Aspose.Slides voor Java?
Aspose.Slides voor Java is een krachtige API voor het programmatisch manipuleren van PowerPoint-presentaties.
### Waar kan ik documentatie vinden voor Aspose.Slides voor Java?
 U kunt de documentatie vinden[hier](https://reference.aspose.com/slides/java/).
### Kan ik Aspose.Slides voor Java uitproberen voordat ik een aankoop doe?
 Ja, u kunt een gratis proefperiode krijgen[hier](https://releases.aspose.com/).
### Hoe kan ik ondersteuning krijgen voor Aspose.Slides voor Java?
 Voor ondersteuning kunt u terecht op de[Aspose.Slides-forum](https://forum.aspose.com/c/slides/11).
### Waar kan ik een licentie kopen voor Aspose.Slides voor Java?
 U kunt een licentie kopen[hier](https://purchase.aspose.com/buy).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
