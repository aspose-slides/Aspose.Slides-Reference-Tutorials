---
title: Voeg een afbeeldingsframe met relatieve schaalhoogte toe in PowerPoint
linktitle: Voeg een afbeeldingsframe met relatieve schaalhoogte toe in PowerPoint
second_title: Aspose.Slides Java PowerPoint-verwerkings-API
description: Leer hoe u afbeeldingsframes op relatieve schaalhoogte kunt toevoegen aan PowerPoint-presentaties met behulp van Aspose.Slides voor Java, waardoor uw visuele inhoud wordt verbeterd.
type: docs
weight: 15
url: /nl/java/java-powerpoint-shape-media-insertion/add-relative-scale-height-picture-frame-powerpoint/
---
## Invoering
In deze zelfstudie leert u hoe u een afbeeldingsframe met relatieve schaalhoogte kunt toevoegen aan PowerPoint-presentaties met behulp van Aspose.Slides voor Java.
## Vereisten
Zorg ervoor dat u over het volgende beschikt voordat u begint:
1. Java Development Kit (JDK) op uw systeem geïnstalleerd.
2. Aspose.Slides voor Java-bibliotheek gedownload en toegevoegd aan uw Java-project.

## Pakketten importeren
Importeer om te beginnen de benodigde pakketten in uw Java-project:
```java
import com.aspose.slides.*;
import com.aspose.slides.examples.RunExamples;
import javax.imageio.ImageIO;
import java.awt.image.BufferedImage;
import java.io.File;
import java.io.IOException;
```
## Stap 1: Stel uw project in
Zorg er eerst voor dat u een directory hebt ingesteld voor uw project en dat uw Java-omgeving correct is geconfigureerd.
## Stap 2: Presentatieobject instantiëren
Maak een nieuw presentatieobject met Aspose.Slides:
```java
Presentation presentation = new Presentation();
```
## Stap 3: Laad de afbeelding die moet worden toegevoegd
Laad de afbeelding die u aan de presentatie wilt toevoegen:
```java
BufferedImage img = ImageIO.read(new File(dataDir + "aspose-logo.jpg"));
IPPImage image = presentation.getImages().addImage(img);
```
## Stap 4: Voeg een fotolijst toe aan de dia
Een fotolijst toevoegen aan een dia in de presentatie:
```java
IPictureFrame pf = presentation.getSlides().get_Item(0).getShapes().addPictureFrame(ShapeType.Rectangle, 50, 50, 100, 100, image);
```
## Stap 5: Stel de relatieve schaalbreedte en -hoogte in
Stel de relatieve schaalbreedte en -hoogte voor de fotolijst in:
```java
pf.setRelativeScaleHeight(0.8f);
pf.setRelativeScaleWidth(1.35f);
```
## Stap 6: Presentatie opslaan
Sla de presentatie op met het toegevoegde fotolijstje:
```java
presentation.save(dataDir + "Adding Picture Frame with Relative Scale_out.pptx", SaveFormat.Pptx);
```

## Conclusie
Door deze stappen te volgen, kunt u eenvoudig een afbeeldingsframe met relatieve schaalhoogte toevoegen aan PowerPoint-presentaties met behulp van Aspose.Slides voor Java. Experimenteer met verschillende schaalwaarden om het gewenste uiterlijk van uw afbeeldingen te bereiken.

## Veelgestelde vragen
### Kan ik met deze methode meerdere fotolijsten aan één dia toevoegen?
Ja, u kunt meerdere fotolijsten aan een dia toevoegen door het proces voor elke afbeelding te herhalen.
### Is Aspose.Slides voor Java compatibel met alle versies van PowerPoint?
Aspose.Slides voor Java is compatibel met verschillende versies van PowerPoint, waardoor flexibiliteit bij het maken van presentaties wordt gegarandeerd.
### Kan ik de positie en het formaat van de fotolijst aanpassen?
 Absoluut, u kunt de positie- en maatparameters aanpassen in de`addPictureFrame` methode die aansluit bij uw wensen.
### Ondersteunt Aspose.Slides voor Java naast JPEG ook andere afbeeldingsformaten?
Ja, Aspose.Slides voor Java ondersteunt verschillende afbeeldingsformaten, waaronder PNG, GIF, BMP en meer.
### Is er een communityforum of ondersteuningskanaal beschikbaar voor Aspose.Slides-gebruikers?
Ja, u kunt het Aspose.Slides-forum bezoeken voor vragen, discussies of hulp met betrekking tot de bibliotheek.