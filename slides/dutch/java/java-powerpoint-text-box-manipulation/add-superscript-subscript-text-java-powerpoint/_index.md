---
"description": "Leer hoe je superscript en subscript toevoegt aan Java PowerPoint-presentaties met Aspose.Slides voor Java. Perfect om je dia's te verfraaien."
"linktitle": "Superscript en subscripttekst toevoegen in Java PowerPoint"
"second_title": "Aspose.Slides Java PowerPoint-verwerkings-API"
"title": "Superscript en subscripttekst toevoegen in Java PowerPoint"
"url": "/nl/java/java-powerpoint-text-box-manipulation/add-superscript-subscript-text-java-powerpoint/"
"weight": 13
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Superscript en subscripttekst toevoegen in Java PowerPoint

## Invoering
Het maken van boeiende en informatieve PowerPoint-presentaties vereist vaak opmaakfuncties zoals superscript en subscript. Deze tutorial begeleidt je bij het integreren van superscript en subscript in je Java PowerPoint-presentaties met behulp van Aspose.Slides voor Java.
## Vereisten
Voordat u begint, moet u ervoor zorgen dat u het volgende heeft:
- Java Development Kit (JDK) op uw systeem geïnstalleerd.
- Aspose.Slides voor Java-bibliotheek. Je kunt het downloaden van [hier](https://releases.aspose.com/slides/java/).
- Een Integrated Development Environment (IDE) zoals IntelliJ IDEA of Eclipse, ingesteld voor Java-ontwikkeling.
- Basiskennis van Java-programmering en PowerPoint-presentaties.

## Pakketten importeren
Importeer eerst de benodigde pakketten uit Aspose.Slides voor Java:
```java
import com.aspose.slides.*;
```
## Stap 1: De presentatie instellen
```java
// Het pad naar de documentenmap.
String dataDir = "Your Document Directory";
Presentation presentation = new Presentation();
```
## Stap 2: Toegang tot de dia
```java
// Ontvang de eerste dia
ISlide slide = presentation.getSlides().get_Item(0);
```
## Stap 3: Een tekstvak maken
```java
// Maak een AutoVorm die als tekstvak dient
IAutoShape shape = slide.getShapes().addAutoShape(ShapeType.Rectangle, 100, 100, 200, 100);
ITextFrame textFrame = shape.getTextFrame();
textFrame.getParagraphs().clear();
```
## Stap 4: Superscripttekst toevoegen
```java
// Maak een alinea voor de hoofdtekst
IParagraph mainParagraph = new Paragraph();
IPortion mainPortion = new Portion();
mainPortion.setText("SlideTitle");
mainParagraph.getPortions().add(mainPortion);
// Maak een gedeelte voor de superscripttekst
IPortion superPortion = new Portion();
superPortion.getPortionFormat().setEscapement(30); // Stel echappement in voor superscript
superPortion.setText("TM");
mainParagraph.getPortions().add(superPortion);
// Voeg de hoofdalinea met superscript toe aan het tekstvak
textFrame.getParagraphs().add(mainParagraph);
```
## Stap 5: Subscripttekst toevoegen
```java
// Maak een andere alinea voor subscripttekst
IParagraph subscriptParagraph = new Paragraph();
IPortion subscriptPortion = new Portion();
subscriptPortion.setText("a");
subscriptParagraph.getPortions().add(subscriptPortion);
// Maak een gedeelte voor de subscripttekst
IPortion subPortion = new Portion();
subPortion.getPortionFormat().setEscapement(-25); // Stel echappement in voor subscript
subPortion.setText("i");
subscriptParagraph.getPortions().add(subPortion);
// Voeg de subscript-alinea toe aan het tekstvak
textFrame.getParagraphs().add(subscriptParagraph);
```
## Stap 6: Sla de presentatie op
```java
// Sla de presentatie op
presentation.save(dataDir + "TestOut.pptx", SaveFormat.Pptx);
```

## Conclusie
In deze tutorial hebben we onderzocht hoe je je Java PowerPoint-presentaties kunt verbeteren met superscript- en subscripttekst met Aspose.Slides voor Java. Door deze stappen te volgen, kun je visueel aantrekkelijkere en informatievere dia's maken die je content effectief overbrengen.

## Veelgestelde vragen
### Wat is Aspose.Slides voor Java?
Aspose.Slides voor Java is een robuuste bibliotheek waarmee ontwikkelaars programmatisch PowerPoint-presentaties kunnen maken, bewerken en converteren.
### Waar kan ik meer documentatie vinden over Aspose.Slides voor Java?
Gedetailleerde documentatie is te vinden [hier](https://reference.aspose.com/slides/java/).
### Hoe kan ik een tijdelijke licentie voor Aspose.Slides voor Java verkrijgen?
U kunt een tijdelijke licentie krijgen [hier](https://purchase.aspose.com/temporary-license/).
### Kan ik Aspose.Slides voor Java gratis uitproberen?
Ja, u kunt een gratis proefversie downloaden van [hier](https://releases.aspose.com/).
### Waar kan ik ondersteuning krijgen voor Aspose.Slides voor Java?
Voor ondersteuning en discussies kunt u terecht op de [Aspose.Slides forum](https://forum.aspose.com/c/slides/11).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}