---
title: Beheer opsommingstekens voor alineaafbeeldingen in Java PowerPoint
linktitle: Beheer opsommingstekens voor alineaafbeeldingen in Java PowerPoint
second_title: Aspose.Slides Java PowerPoint-verwerkings-API
description: Leer hoe u aangepaste afbeeldingsopsommingstekens aan PowerPoint-dia's kunt toevoegen met Aspose.Slides voor Java. Volg deze gedetailleerde, stap-voor-stap handleiding voor een naadloze integratie.
weight: 11
url: /nl/java/java-powerpoint-advanced-paragraph-font-properties/manage-paragraph-picture-bullets-java-powerpoint/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Beheer opsommingstekens voor alineaafbeeldingen in Java PowerPoint

## Invoering
Het creëren van boeiende en visueel aantrekkelijke presentaties is een cruciale vaardigheid in de moderne zakenwereld. Java-ontwikkelaars kunnen Aspose.Slides gebruiken om hun presentaties te verbeteren met aangepaste afbeeldingsopsommingstekens in PowerPoint-dia's. Deze tutorial begeleidt u stap voor stap door het proces, zodat u vol vertrouwen afbeeldingsopsommingstekens aan uw presentaties kunt toevoegen.
## Vereisten
Voordat u in de zelfstudie duikt, moet u ervoor zorgen dat u aan de volgende vereisten voldoet:
- Java Development Kit (JDK) geïnstalleerd
- Integrated Development Environment (IDE) zoals Eclipse of IntelliJ IDEA
- Aspose.Slides voor Java-bibliotheek
- Basiskennis van Java-programmeren
- Afbeeldingsbestand voor de kogelafbeelding
 Om de Aspose.Slides voor Java-bibliotheek te downloaden, gaat u naar de[downloadpagina](https://releases.aspose.com/slides/java/) . Voor documentatie, controleer de[documentatie](https://reference.aspose.com/slides/java/).
## Pakketten importeren
Zorg er eerst voor dat u de benodigde pakketten voor uw project hebt geïmporteerd. Voeg de volgende imports toe aan het begin van uw Java-bestand:
```java
import com.aspose.slides.*;
import javax.imageio.ImageIO;
import java.awt.image.BufferedImage;
import java.io.File;
import java.io.IOException;
```
Laten we het proces opsplitsen in beheersbare stappen.
## Stap 1: Stel uw projectdirectory in
Maak een nieuwe map voor uw project. Deze map bevat uw Java-bestand, de Aspose.Slides-bibliotheek en het afbeeldingsbestand voor het opsommingsteken.
```java
String dataDir = "Your Document Directory";
```
## Stap 2: Initialiseer de presentatie
 Initialiseer een nieuw exemplaar van het`Presentation` klas. Dit object vertegenwoordigt uw PowerPoint-presentatie.
```java
Presentation presentation = new Presentation();
```
## Stap 3: Toegang tot de eerste dia
Ga naar de eerste dia van de presentatie. Dia's zijn op nul geïndexeerd, dus de eerste dia bevindt zich op index 0.
```java
ISlide slide = presentation.getSlides().get_Item(0);
```
## Stap 4: Laad de kogelafbeelding
Laad de afbeelding die u voor de opsommingstekens wilt gebruiken. Deze afbeelding moet in uw projectmap worden geplaatst.
```java
BufferedImage image = ImageIO.read(new File(dataDir + "bullets.png"));
IPPImage ippxImage = presentation.getImages().addImage(image);
```
## Stap 5: Voeg een AutoShape toe aan de dia
Voeg een AutoVorm toe aan de dia. De vorm bevat de tekst met de aangepaste opsommingstekens.
```java
IAutoShape autoShape = slide.getShapes().addAutoShape(ShapeType.Rectangle, 200, 200, 400, 200);
```
## Stap 6: Open het tekstkader
Open het tekstkader van de AutoVorm om de alinea's ervan te manipuleren.
```java
ITextFrame textFrame = autoShape.getTextFrame();
```
## Stap 7: Verwijder de standaardparagraaf
Verwijder de standaardparagraaf die automatisch aan het tekstkader wordt toegevoegd.
```java
textFrame.getParagraphs().removeAt(0);
```
## Stap 8: Maak een nieuwe paragraaf
Maak een nieuwe paragraaf en stel de tekst in. Deze paragraaf bevat de aangepaste afbeeldingsopsommingstekens.
```java
Paragraph paragraph = new Paragraph();
paragraph.setText("Welcome to Aspose.Slides");
```
## Stap 9: Stel de opsommingstekenstijl en afbeelding in
Stel de opsommingstekenstijl in om de eerder geladen aangepaste afbeelding te gebruiken.
```java
paragraph.getParagraphFormat().getBullet().setType(BulletType.Picture);
paragraph.getParagraphFormat().getBullet().getPicture().setImage(ippxImage);
```
## Stap 10: Pas de kogelhoogte aan
Stel de hoogte van de kogel in om ervoor te zorgen dat deze er goed uitziet in de presentatie.
```java
paragraph.getParagraphFormat().getBullet().setHeight(100);
```
## Stap 11: Voeg de alinea toe aan het tekstkader
Voeg de nieuw gemaakte alinea toe aan het tekstkader van de AutoVorm.
```java
textFrame.getParagraphs().add(paragraph);
```
## Stap 12: Sla de presentatie op
Sla ten slotte de presentatie op als zowel een PPTX- als een PPT-bestand.
```java
presentation.save(dataDir + "ParagraphPictureBulletsPPTX_out.pptx", SaveFormat.Pptx);
presentation.save(dataDir + "ParagraphPictureBulletsPPT_out.ppt", SaveFormat.Ppt);
```
## Conclusie
 En daar heb je het! Door deze stappen te volgen, kunt u eenvoudig aangepaste afbeeldingsopsommingstekens toevoegen aan uw PowerPoint-presentaties met behulp van Aspose.Slides voor Java. Deze krachtige bibliotheek biedt een breed scala aan functies waarmee u professionele en visueel aantrekkelijke presentaties kunt maken. Vergeet niet om de[documentatie](https://reference.aspose.com/slides/java/)voor meer geavanceerde functies en aanpassingsmogelijkheden.
## Veelgestelde vragen
### Wat is Aspose.Slides voor Java?
Aspose.Slides voor Java is een krachtige bibliotheek waarmee Java-ontwikkelaars PowerPoint-presentaties programmatisch kunnen maken, wijzigen en manipuleren.
### Kan ik elke afbeelding gebruiken voor de afbeeldingskogels?
Ja, u kunt elke afbeelding gebruiken voor de afbeeldingsopsommingen, zolang deze toegankelijk is vanuit uw projectmap.
### Heb ik een licentie nodig om Aspose.Slides voor Java te gebruiken?
 Aspose.Slides voor Java vereist een licentie voor volledige functionaliteit. Een tijdelijke licentie kunt u verkrijgen bij[hier](https://purchase.aspose.com/temporary-license/) of koop een volledige licentie[hier](https://purchase.aspose.com/buy).
### Kan ik meerdere alinea's met verschillende opsommingstekens in één AutoVorm toevoegen?
Ja, u kunt meerdere alinea's met verschillende stijlen voor opsommingstekens toevoegen aan één AutoVorm door elke alinea afzonderlijk te maken en te configureren.
### Waar kan ik meer voorbeelden en ondersteuning vinden?
 Meer voorbeelden vindt u in de[documentatie](https://reference.aspose.com/slides/java/) en krijg steun van de Aspose-gemeenschap op de[forums](https://forum.aspose.com/c/slides/11).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
