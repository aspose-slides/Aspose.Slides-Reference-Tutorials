---
"description": "Leer hoe je aangepaste afbeeldingen met opsommingstekens toevoegt aan PowerPoint-dia's met Aspose.Slides voor Java. Volg deze gedetailleerde, stapsgewijze handleiding voor naadloze integratie."
"linktitle": "Alinea-afbeeldingen met opsommingstekens beheren in Java PowerPoint"
"second_title": "Aspose.Slides Java PowerPoint-verwerkings-API"
"title": "Alinea-afbeeldingen met opsommingstekens beheren in Java PowerPoint"
"url": "/nl/java/java-powerpoint-advanced-paragraph-font-properties/manage-paragraph-picture-bullets-java-powerpoint/"
"weight": 11
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Alinea-afbeeldingen met opsommingstekens beheren in Java PowerPoint

## Invoering
Het creëren van boeiende en visueel aantrekkelijke presentaties is een cruciale vaardigheid in de moderne zakenwereld. Java-ontwikkelaars kunnen Aspose.Slides gebruiken om hun presentaties te verbeteren met aangepaste opsommingstekens met afbeeldingen in PowerPoint-dia's. Deze tutorial leidt je stap voor stap door het proces, zodat je vol vertrouwen opsommingstekens met afbeeldingen aan je presentaties kunt toevoegen.
## Vereisten
Voordat u met de tutorial begint, moet u ervoor zorgen dat u aan de volgende vereisten voldoet:
- Java Development Kit (JDK) geïnstalleerd
- Geïntegreerde ontwikkelomgeving (IDE) zoals Eclipse of IntelliJ IDEA
- Aspose.Slides voor Java-bibliotheek
- Basiskennis van Java-programmering
- Afbeeldingsbestand voor de kogelfoto
Om de Aspose.Slides voor Java-bibliotheek te downloaden, gaat u naar de [downloadpagina](https://releases.aspose.com/slides/java/)Voor documentatie, zie de [documentatie](https://reference.aspose.com/slides/java/).
## Pakketten importeren
Zorg er eerst voor dat u de benodigde pakketten voor uw project hebt geïmporteerd. Voeg de volgende imports toe aan het begin van uw Java-bestand:
```java
import com.aspose.slides.*;
import javax.imageio.ImageIO;
import java.awt.image.BufferedImage;
import java.io.File;
import java.io.IOException;
```
Laten we het proces opdelen in hanteerbare stappen.
## Stap 1: Stel uw projectmap in
Maak een nieuwe map voor je project. Deze map bevat je Java-bestand, de Aspose.Slides-bibliotheek en het afbeeldingsbestand voor de bullet.
```java
String dataDir = "Your Document Directory";
```
## Stap 2: Initialiseer de presentatie
Initialiseer een nieuw exemplaar van de `Presentation` klasse. Dit object vertegenwoordigt uw PowerPoint-presentatie.
```java
Presentation presentation = new Presentation();
```
## Stap 3: Toegang tot de eerste dia
Ga naar de eerste dia van de presentatie. Dia's hebben een index van nul, dus de eerste dia staat op index 0.
```java
ISlide slide = presentation.getSlides().get_Item(0);
```
## Stap 4: Laad de Bullet-afbeelding
Laad de afbeelding die je voor de bullets wilt gebruiken. Plaats deze afbeelding in je projectmap.
```java
BufferedImage image = ImageIO.read(new File(dataDir + "bullets.png"));
IPPImage ippxImage = presentation.getImages().addImage(image);
```
## Stap 5: Een AutoVorm toevoegen aan de dia
Voeg een AutoVorm toe aan de dia. De vorm bevat de tekst met de aangepaste opsommingstekens.
```java
IAutoShape autoShape = slide.getShapes().addAutoShape(ShapeType.Rectangle, 200, 200, 400, 200);
```
## Stap 6: Toegang tot het tekstkader
Gebruik het tekstkader van de AutoVorm om de alinea's te bewerken.
```java
ITextFrame textFrame = autoShape.getTextFrame();
```
## Stap 7: Verwijder de standaardalinea
Verwijder de standaardalinea die automatisch aan het tekstkader wordt toegevoegd.
```java
textFrame.getParagraphs().removeAt(0);
```
## Stap 8: Een nieuwe alinea maken
Maak een nieuwe alinea en stel de tekst in. Deze alinea zal de aangepaste afbeeldingsopsommingstekens bevatten.
```java
Paragraph paragraph = new Paragraph();
paragraph.setText("Welcome to Aspose.Slides");
```
## Stap 9: Opsommingstekenstijl en afbeelding instellen
Stel de opsommingstekenstijl in om de eerder geladen aangepaste afbeelding te gebruiken.
```java
paragraph.getParagraphFormat().getBullet().setType(BulletType.Picture);
paragraph.getParagraphFormat().getBullet().getPicture().setImage(ippxImage);
```
## Stap 10: Pas de kogelhoogte aan
Stel de hoogte van het opsommingsteken in om ervoor te zorgen dat het er goed uitziet in de presentatie.
```java
paragraph.getParagraphFormat().getBullet().setHeight(100);
```
## Stap 11: Voeg de alinea toe aan het tekstkader
Voeg de nieuw gemaakte alinea toe aan het tekstkader van de AutoVorm.
```java
textFrame.getParagraphs().add(paragraph);
```
## Stap 12: Sla de presentatie op
Sla ten slotte de presentatie op als PPTX- en PPT-bestand.
```java
presentation.save(dataDir + "ParagraphPictureBulletsPPTX_out.pptx", SaveFormat.Pptx);
presentation.save(dataDir + "ParagraphPictureBulletsPPT_out.ppt", SaveFormat.Ppt);
```
## Conclusie
En voilà! Door deze stappen te volgen, kunt u eenvoudig aangepaste opsommingstekens met afbeeldingen toevoegen aan uw PowerPoint-presentaties met Aspose.Slides voor Java. Deze krachtige bibliotheek biedt een breed scala aan functies waarmee u professionele en visueel aantrekkelijke presentaties kunt maken. Vergeet niet om de [documentatie](https://reference.aspose.com/slides/java/) voor meer geavanceerde functies en aanpassingsopties.
## Veelgestelde vragen
### Wat is Aspose.Slides voor Java?
Aspose.Slides voor Java is een krachtige bibliotheek waarmee Java-ontwikkelaars programmatisch PowerPoint-presentaties kunnen maken, wijzigen en manipuleren.
### Kan ik elke afbeelding gebruiken voor de fotobulletins?
Ja, u kunt elke afbeelding gebruiken voor de afbeeldingsopsommingstekens, zolang deze toegankelijk is via uw projectmap.
### Heb ik een licentie nodig om Aspose.Slides voor Java te gebruiken?
Voor volledige functionaliteit is voor Aspose.Slides voor Java een licentie vereist. U kunt een tijdelijke licentie verkrijgen via [hier](https://purchase.aspose.com/temporary-license/) of koop een volledige licentie [hier](https://purchase.aspose.com/buy).
### Kan ik meerdere alinea's met verschillende opsommingstekenstijlen in één AutoVorm toevoegen?
Ja, u kunt meerdere alinea's met verschillende opsommingstekenstijlen toevoegen aan één AutoVorm door elke alinea afzonderlijk te maken en te configureren.
### Waar kan ik meer voorbeelden en ondersteuning vinden?
Meer voorbeelden vindt u in de [documentatie](https://reference.aspose.com/slides/java/) en krijg ondersteuning van de Aspose-community op de [forums](https://forum.aspose.com/c/slides/11).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}