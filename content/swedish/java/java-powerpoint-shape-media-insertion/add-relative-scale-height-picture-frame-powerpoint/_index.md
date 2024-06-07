---
title: Lägg till bildram med relativ skalhöjd i PowerPoint
linktitle: Lägg till bildram med relativ skalhöjd i PowerPoint
second_title: Aspose.Slides Java PowerPoint Processing API
description: Lär dig hur du lägger till bildramar med relativ skalhöjd i PowerPoint-presentationer med Aspose.Slides för Java, vilket förbättrar ditt visuella innehåll.
type: docs
weight: 15
url: /sv/java/java-powerpoint-shape-media-insertion/add-relative-scale-height-picture-frame-powerpoint/
---
## Introduktion
I den här handledningen får du lära dig hur du lägger till en bildram med relativ skalhöjd i PowerPoint-presentationer med Aspose.Slides för Java.
## Förutsättningar
Innan du börjar, se till att du har följande:
1. Java Development Kit (JDK) installerat på ditt system.
2. Aspose.Slides för Java-biblioteket har laddats ner och lagts till i ditt Java-projekt.

## Importera paket
För att börja, importera de nödvändiga paketen i ditt Java-projekt:
```java
import com.aspose.slides.*;
import com.aspose.slides.examples.RunExamples;
import javax.imageio.ImageIO;
import java.awt.image.BufferedImage;
import java.io.File;
import java.io.IOException;
```
## Steg 1: Konfigurera ditt projekt
Se först till att du har en katalog inställd för ditt projekt och att din Java-miljö är korrekt konfigurerad.
## Steg 2: Instantera presentationsobjekt
Skapa ett nytt presentationsobjekt med Aspose.Slides:
```java
Presentation presentation = new Presentation();
```
## Steg 3: Ladda bild som ska läggas till
Ladda bilden du vill lägga till i presentationen:
```java
BufferedImage img = ImageIO.read(new File(dataDir + "aspose-logo.jpg"));
IPPImage image = presentation.getImages().addImage(img);
```
## Steg 4: Lägg till bildram till bild
Lägg till en bildram till en bild i presentationen:
```java
IPictureFrame pf = presentation.getSlides().get_Item(0).getShapes().addPictureFrame(ShapeType.Rectangle, 50, 50, 100, 100, image);
```
## Steg 5: Ställ in relativ skalbredd och höjd
Ställ in den relativa skalbredden och höjden för bildramen:
```java
pf.setRelativeScaleHeight(0.8f);
pf.setRelativeScaleWidth(1.35f);
```
## Steg 6: Spara presentationen
Spara presentationen med den tillagda bildramen:
```java
presentation.save(dataDir + "Adding Picture Frame with Relative Scale_out.pptx", SaveFormat.Pptx);
```

## Slutsats
Genom att följa dessa steg kan du enkelt lägga till en bildram med relativ skalhöjd i PowerPoint-presentationer med Aspose.Slides för Java. Experimentera med olika skalvärden för att uppnå önskat utseende för dina bilder.

## FAQ's
### Kan jag lägga till flera bildramar till en enda bild med den här metoden?
Ja, du kan lägga till flera bildramar till en bild genom att upprepa processen för varje bild.
### Är Aspose.Slides för Java kompatibel med alla versioner av PowerPoint?
Aspose.Slides för Java är kompatibel med olika versioner av PowerPoint, vilket säkerställer flexibilitet när du skapar presentationer.
### Kan jag anpassa bildramens placering och storlek?
 Absolut, du kan justera parametrarna för position och storlek i`addPictureFrame` metod för att passa dina krav.
### Stöder Aspose.Slides för Java andra bildformat än JPEG?
Ja, Aspose.Slides för Java stöder olika bildformat, inklusive PNG, GIF, BMP och mer.
### Finns det ett communityforum eller supportkanal tillgängligt för Aspose.Slides-användare?
Ja, du kan besöka Aspose.Slides-forumet för frågor, diskussioner eller hjälp om biblioteket.