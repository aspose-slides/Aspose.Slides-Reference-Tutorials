---
"description": "Leer hoe u de letterhoogte in PowerPoint-presentaties kunt aanpassen met behulp van Java met Aspose.Slides. Verbeter moeiteloos de tekstopmaak in uw dia's."
"linktitle": "Lokale letterhoogtewaarden instellen in PowerPoint met behulp van Java"
"second_title": "Aspose.Slides Java PowerPoint-verwerkings-API"
"title": "Lokale letterhoogtewaarden instellen in PowerPoint met behulp van Java"
"url": "/nl/java/java-powerpoint-text-font-customization/set-local-font-height-values-powerpoint-java/"
"weight": 17
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Lokale letterhoogtewaarden instellen in PowerPoint met behulp van Java

## Invoering
In deze tutorial leer je hoe je de letterhoogte op verschillende niveaus in PowerPoint-presentaties kunt aanpassen met Aspose.Slides voor Java. Het aanpassen van de lettergrootte is cruciaal voor het maken van visueel aantrekkelijke en gestructureerde presentaties. We laten je stapsgewijze voorbeelden zien om te laten zien hoe je de letterhoogte voor verschillende tekstelementen kunt instellen.
## Vereisten
Voordat u begint, moet u ervoor zorgen dat u het volgende heeft:
- Java Development Kit (JDK) op uw systeem geïnstalleerd
- Aspose.Slides voor Java-bibliotheek. Je kunt het downloaden. [hier](https://releases.aspose.com/slides/java/).
- Een basiskennis van Java-programmering en PowerPoint-presentaties
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
## Stap 2: Een vorm en tekstkader toevoegen
Voeg een automatische vorm met een tekstkader toe aan de eerste dia:
```java
IAutoShape newShape = pres.getSlides().get_Item(0).getShapes().addAutoShape(ShapeType.Rectangle, 100, 100, 400, 75, false);
newShape.addTextFrame("");
```
## Stap 3: Tekstgedeelten maken
Definieer tekstgedeelten met verschillende letterhoogten:
```java
IPortion portion0 = new Portion("Sample text with first portion");
IPortion portion1 = new Portion(" and second portion.");
newShape.getTextFrame().getParagraphs().get_Item(0).getPortions().add(portion0);
newShape.getTextFrame().getParagraphs().get_Item(0).getPortions().add(portion1);
```
## Stap 4: Letterhoogtes instellen
Stel de letterhoogte in op verschillende niveaus:
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
Deze tutorial laat zien hoe je de letterhoogte in PowerPoint-dia's programmatisch kunt aanpassen met Aspose.Slides voor Java. Door de lettergrootte op verschillende niveaus (presentatiebreed, alinea en gedeelte) te manipuleren, krijg je nauwkeurige controle over de tekstopmaak in je presentaties.
## Veelgestelde vragen
### Wat is Aspose.Slides voor Java?
Aspose.Slides voor Java is een krachtige API voor het programmatisch bewerken van PowerPoint-presentaties.
### Waar kan ik documentatie vinden voor Aspose.Slides voor Java?
De documentatie vindt u hier [hier](https://reference.aspose.com/slides/java/).
### Kan ik Aspose.Slides voor Java uitproberen voordat ik het koop?
Ja, u kunt een gratis proefperiode krijgen [hier](https://releases.aspose.com/).
### Hoe kan ik ondersteuning krijgen voor Aspose.Slides voor Java?
Voor ondersteuning, bezoek de [Aspose.Slides forum](https://forum.aspose.com/c/slides/11).
### Waar kan ik een licentie voor Aspose.Slides voor Java kopen?
U kunt een licentie kopen [hier](https://purchase.aspose.com/buy).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}