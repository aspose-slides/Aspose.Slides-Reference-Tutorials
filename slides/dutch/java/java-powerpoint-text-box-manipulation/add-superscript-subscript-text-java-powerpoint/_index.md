---
title: Voeg superscript- en subscripttekst toe in Java PowerPoint
linktitle: Voeg superscript- en subscripttekst toe in Java PowerPoint
second_title: Aspose.Slides Java PowerPoint-verwerkings-API
description: Leer hoe u superscript- en subscript-tekst kunt toevoegen aan Java PowerPoint-presentaties met Aspose.Slides voor Java. Perfect voor het verbeteren van uw dia's.
weight: 13
url: /nl/java/java-powerpoint-text-box-manipulation/add-superscript-subscript-text-java-powerpoint/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

## Invoering
Het maken van boeiende en informatieve PowerPoint-presentaties vereist vaak het gebruik van opmaakfuncties zoals superscript- en subscript-tekst. Deze tutorial leidt u door het proces van het opnemen van superscript- en subscript-tekst in uw Java PowerPoint-presentaties met behulp van Aspose.Slides voor Java.
## Vereisten
Zorg ervoor dat u over het volgende beschikt voordat u begint:
- Java Development Kit (JDK) op uw systeem geïnstalleerd.
-  Aspose.Slides voor Java-bibliotheek. Je kunt het downloaden van[hier](https://releases.aspose.com/slides/java/).
- Een Integrated Development Environment (IDE), zoals IntelliJ IDEA of Eclipse, opgezet voor Java-ontwikkeling.
- Basiskennis van programmeren in Java en PowerPoint-presentaties.

## Pakketten importeren
Importeer eerst de benodigde pakketten uit Aspose.Slides voor Java:
```java
import com.aspose.slides.*;
```
## Stap 1: Stel de presentatie in
```java
// Het pad naar de documentenmap.
String dataDir = "Your Document Directory";
Presentation presentation = new Presentation();
```
## Stap 2: Toegang tot de dia
```java
// Haal de eerste dia
ISlide slide = presentation.getSlides().get_Item(0);
```
## Stap 3: Maak een tekstvak
```java
// Maak een AutoVorm die als tekstvak kan dienen
IAutoShape shape = slide.getShapes().addAutoShape(ShapeType.Rectangle, 100, 100, 200, 100);
ITextFrame textFrame = shape.getTextFrame();
textFrame.getParagraphs().clear();
```
## Stap 4: Superscript-tekst toevoegen
```java
// Maak een alinea voor de hoofdtekst
IParagraph mainParagraph = new Paragraph();
IPortion mainPortion = new Portion();
mainPortion.setText("SlideTitle");
mainParagraph.getPortions().add(mainPortion);
// Maak een gedeelte voor de superscripttekst
IPortion superPortion = new Portion();
superPortion.getPortionFormat().setEscapement(30); // Stel het echappement in voor superscript
superPortion.setText("TM");
mainParagraph.getPortions().add(superPortion);
//Voeg de hoofdparagraaf met superscript toe aan het tekstvak
textFrame.getParagraphs().add(mainParagraph);
```
## Stap 5: Voeg subscripttekst toe
```java
// Maak nog een alinea voor subscripttekst
IParagraph subscriptParagraph = new Paragraph();
IPortion subscriptPortion = new Portion();
subscriptPortion.setText("a");
subscriptParagraph.getPortions().add(subscriptPortion);
// Maak een gedeelte voor de subscripttekst
IPortion subPortion = new Portion();
subPortion.getPortionFormat().setEscapement(-25); // Stel het echappement in voor subscript
subPortion.setText("i");
subscriptParagraph.getPortions().add(subPortion);
// Voeg de subscriptparagraaf toe aan het tekstvak
textFrame.getParagraphs().add(subscriptParagraph);
```
## Stap 6: Sla de presentatie op
```java
// Bewaar de presentatie
presentation.save(dataDir + "TestOut.pptx", SaveFormat.Pptx);
```

## Conclusie
In deze zelfstudie hebben we onderzocht hoe u uw Java PowerPoint-presentaties kunt verbeteren met superscript- en subscript-tekst met behulp van Aspose.Slides voor Java. Door deze stappen te volgen, kunt u visueel aantrekkelijkere en informatieve dia's maken die uw inhoud effectief overbrengen.

## Veelgestelde vragen
### Wat is Aspose.Slides voor Java?
Aspose.Slides voor Java is een robuuste bibliotheek waarmee ontwikkelaars PowerPoint-presentaties programmatisch kunnen maken, manipuleren en converteren.
### Waar kan ik meer documentatie vinden over Aspose.Slides voor Java?
 Gedetailleerde documentatie is te vinden[hier](https://reference.aspose.com/slides/java/).
### Hoe kan ik een tijdelijke licentie verkrijgen voor Aspose.Slides voor Java?
 U kunt een tijdelijke licentie krijgen[hier](https://purchase.aspose.com/temporary-license/).
### Kan ik Aspose.Slides voor Java gratis uitproberen?
 Ja, u kunt een gratis proefversie downloaden van[hier](https://releases.aspose.com/).
### Waar kan ik ondersteuning krijgen voor Aspose.Slides voor Java?
 Voor ondersteuning en discussies kunt u terecht op de[Aspose.Slides-forum](https://forum.aspose.com/c/slides/11).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
