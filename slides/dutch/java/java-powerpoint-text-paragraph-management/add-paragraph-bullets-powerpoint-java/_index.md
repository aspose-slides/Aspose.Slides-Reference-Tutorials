---
title: Voeg alinea-opsommingstekens toe in PowerPoint met behulp van Java
linktitle: Voeg alinea-opsommingstekens toe in PowerPoint met behulp van Java
second_title: Aspose.Slides Java PowerPoint-verwerkings-API
description: Leer hoe u alinea-opsommingstekens kunt toevoegen aan PowerPoint-dia's met behulp van Aspose.Slides voor Java. Deze tutorial begeleidt u stap voor stap met codevoorbeelden.
weight: 15
url: /nl/java/java-powerpoint-text-paragraph-management/add-paragraph-bullets-powerpoint-java/
---

{< blocks/products/pf/main-wrap-class >}
{< blocks/products/pf/main-container >}
{< blocks/products/pf/tutorial-page-section >}

## Invoering
Het toevoegen van alineaopsommingstekens verbetert de leesbaarheid en structuur van PowerPoint-presentaties. Aspose.Slides voor Java biedt robuuste tools om presentaties programmatisch te manipuleren, inclusief de mogelijkheid om tekst op te maken met verschillende opsommingstekens. In deze zelfstudie leert u hoe u opsommingstekens in PowerPoint-dia's kunt integreren met behulp van Java-code, waarbij gebruik wordt gemaakt van Aspose.Slides.
## Vereisten
Zorg ervoor dat u over het volgende beschikt voordat u begint:
- Basiskennis van Java-programmeren.
- JDK (Java Development Kit) op uw systeem geïnstalleerd.
-  Aspose.Slides voor Java-bibliotheek. Je kunt het downloaden van[hier](https://releases.aspose.com/slides/java/).

## Pakketten importeren
Om te beginnen importeert u de benodigde Aspose.Slides-pakketten in uw Java-project:
```java
import com.aspose.slides.*;
import java.awt.*;
import java.io.File;
```
## Stap 1: Stel uw project in
Maak eerst een nieuw Java-project en voeg de Aspose.Slides voor Java-bibliotheek toe aan het buildpad van uw project.
## Stap 2: Initialiseer een presentatie
Initialiseer een presentatieobject (`Presentation`) om met dia's te gaan werken.
```java
// Het pad naar de documentenmap.
String dataDir = "Your Document Directory";
// Een presentatie-exemplaar maken
Presentation pres = new Presentation();
```
## Stap 3: Open het dia- en tekstframe
Toegang tot de dia (`ISlide`en het tekstkader (`ITextFrame`) waar u opsommingstekens wilt toevoegen.
```java
// Toegang tot de eerste dia
ISlide slide = pres.getSlides().get_Item(0);
// Autoshape toevoegen en openen
IAutoShape aShp = slide.getShapes().addAutoShape(ShapeType.Rectangle, 200, 200, 400, 200);
// Toegang tot het tekstframe van de gemaakte autoshape
ITextFrame txtFrm = aShp.getTextFrame();
```
## Stap 4: Alinea's maken en opmaken met opsommingstekens
Maak alinea's (`Paragraph`) en stel de opsommingstekens, inspringing en tekst in.
```java
// Een alinea maken
Paragraph para = new Paragraph();
para.getParagraphFormat().getBullet().setType(BulletType.Symbol);
para.getParagraphFormat().getBullet().setChar((char) 8226);
para.setText("Welcome to Aspose.Slides");
para.getParagraphFormat().setIndent(25);
txtFrm.getParagraphs().add(para);
// Nog een paragraaf maken
Paragraph para2 = new Paragraph();
para2.getParagraphFormat().getBullet().setType(BulletType.Numbered);
para2.getParagraphFormat().getBullet().setNumberedBulletStyle(NumberedBulletStyle.BulletCircleNumWDBlackPlain);
para2.setText("This is numbered bullet");
para2.getParagraphFormat().setIndent(25);
txtFrm.getParagraphs().add(para2);
```
## Stap 5: Sla de presentatie op
Sla de gewijzigde presentatie op in een PowerPoint-bestand (`PPTX`).
```java
// De presentatie schrijven als een PPTX-bestand
pres.save(dataDir + "Bullet_out.pptx", SaveFormat.Pptx);
```
## Stap 6: Bronnen opruimen
Gooi het presentatieobject weg om bronnen vrij te maken.
```java
// Gooi het presentatieobject weg
if (pres != null) {
    pres.dispose();
}
```

## Conclusie
Het toevoegen van alinea-opsommingstekens in PowerPoint met Aspose.Slides voor Java is eenvoudig met de meegeleverde codevoorbeelden. Pas de stijlen en opmaak van opsommingstekens naadloos aan uw presentatiebehoeften aan.

## Veelgestelde vragen
### Kan ik de kleuren van opsommingstekens aanpassen?
Ja, u kunt aangepaste kleuren voor opsommingstekens instellen met behulp van de Aspose.Slides API.
### Hoe voeg ik geneste opsommingstekens toe?
Bij het nesten van opsommingstekens worden alinea's binnen alinea's toegevoegd, waarbij de inspringing dienovereenkomstig wordt aangepast.
### Kan ik verschillende opsommingstekens maken voor verschillende dia's?
Ja, u kunt programmatisch unieke opsommingstekenstijlen op verschillende dia's toepassen.
### Is Aspose.Slides compatibel met Java 11?
Ja, Aspose.Slides ondersteunt Java 11 en hogere versies.
### Waar kan ik meer voorbeelden en documentatie vinden?
 Bezoek[Aspose.Slides voor Java-documentatie](https://reference.aspose.com/slides/java/) voor uitgebreide handleidingen en voorbeelden.
{< /blocks/products/pf/tutorial-page-section >}

{< /blocks/products/pf/main-container >}
{< /blocks/products/pf/main-wrap-class >}

{< blocks/products/products-backtop-button >}
