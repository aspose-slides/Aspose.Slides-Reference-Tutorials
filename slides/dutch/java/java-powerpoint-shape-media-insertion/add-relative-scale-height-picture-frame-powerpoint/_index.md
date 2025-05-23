---
"description": "Leer hoe u fotokaders met relatieve schaalhoogte kunt toevoegen aan PowerPoint-presentaties met behulp van Aspose.Slides voor Java, waarmee u uw visuele inhoud kunt verbeteren."
"linktitle": "Voeg een fotolijst met relatieve schaalhoogte toe in PowerPoint"
"second_title": "Aspose.Slides Java PowerPoint-verwerkings-API"
"title": "Voeg een fotolijst met relatieve schaalhoogte toe in PowerPoint"
"url": "/nl/java/java-powerpoint-shape-media-insertion/add-relative-scale-height-picture-frame-powerpoint/"
"weight": 15
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Voeg een fotolijst met relatieve schaalhoogte toe in PowerPoint

## Invoering
In deze zelfstudie leert u hoe u een fotokader met relatieve schaalhoogte toevoegt aan PowerPoint-presentaties met behulp van Aspose.Slides voor Java.
## Vereisten
Voordat u begint, moet u ervoor zorgen dat u het volgende heeft:
1. Java Development Kit (JDK) op uw systeem geïnstalleerd.
2. Aspose.Slides voor Java-bibliotheek gedownload en toegevoegd aan uw Java-project.

## Pakketten importeren
Om te beginnen importeert u de benodigde pakketten in uw Java-project:
```java
import com.aspose.slides.*;

import javax.imageio.ImageIO;
import java.awt.image.BufferedImage;
import java.io.File;
import java.io.IOException;
```
## Stap 1: Stel uw project in
Zorg er eerst voor dat u een directory voor uw project hebt ingesteld en dat uw Java-omgeving correct is geconfigureerd.
## Stap 2: Instantieer presentatieobject
Maak een nieuw presentatieobject met Aspose.Slides:
```java
Presentation presentation = new Presentation();
```
## Stap 3: Laad de toe te voegen afbeelding
Laad de afbeelding die u aan de presentatie wilt toevoegen:
```java
BufferedImage img = ImageIO.read(new File(dataDir + "aspose-logo.jpg"));
IPPImage image = presentation.getImages().addImage(img);
```
## Stap 4: Voeg een fotolijst toe aan de dia
Een fotokader toevoegen aan een dia in de presentatie:
```java
IPictureFrame pf = presentation.getSlides().get_Item(0).getShapes().addPictureFrame(ShapeType.Rectangle, 50, 50, 100, 100, image);
```
## Stap 5: Stel de relatieve schaalbreedte en -hoogte in
Stel de relatieve schaalbreedte en -hoogte voor het fotolijstje in:
```java
pf.setRelativeScaleHeight(0.8f);
pf.setRelativeScaleWidth(1.35f);
```
## Stap 6: Presentatie opslaan
Sla de presentatie op met het toegevoegde fotokader:
```java
presentation.save(dataDir + "Adding Picture Frame with Relative Scale_out.pptx", SaveFormat.Pptx);
```

## Conclusie
Door deze stappen te volgen, kunt u eenvoudig een fotolijst met relatieve schaalhoogte toevoegen aan PowerPoint-presentaties met Aspose.Slides voor Java. Experimenteer met verschillende schaalwaarden om het gewenste uiterlijk voor uw afbeeldingen te bereiken.

## Veelgestelde vragen
### Kan ik met deze methode meerdere fotolijsten aan één dia toevoegen?
Ja, u kunt meerdere fotolijsten aan een dia toevoegen door dit proces voor elke afbeelding te herhalen.
### Is Aspose.Slides voor Java compatibel met alle versies van PowerPoint?
Aspose.Slides voor Java is compatibel met verschillende versies van PowerPoint, wat zorgt voor flexibiliteit bij het maken van presentaties.
### Kan ik de positie en de grootte van de fotolijst aanpassen?
Absoluut, u kunt de positie- en grootteparameters in de `addPictureFrame` een methode die bij uw behoeften past.
### Ondersteunt Aspose.Slides voor Java andere afbeeldingformaten dan JPEG?
Ja, Aspose.Slides voor Java ondersteunt verschillende afbeeldingsformaten, waaronder PNG, GIF, BMP en meer.
### Is er een communityforum of ondersteuningskanaal beschikbaar voor Aspose.Slides-gebruikers?
Ja, u kunt het Aspose.Slides-forum bezoeken voor vragen, discussies of hulp met betrekking tot de bibliotheek.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}