---
title: Skapa SmartArt-miniatyr för underordnad anteckning
linktitle: Skapa SmartArt-miniatyr för underordnad anteckning
second_title: Aspose.Slides Java PowerPoint Processing API
description: Lär dig hur du skapar SmartArt-miniatyrer för anteckningar i Java med Aspose.Slides, vilket förbättrar dina PowerPoint-presentationer utan ansträngning.
weight: 15
url: /sv/java/java-powerpoint-shape-thumbnail-creation/create-smartart-child-note-thumbnail/
---

{< blocks/products/pf/main-wrap-class >}
{< blocks/products/pf/main-container >}
{< blocks/products/pf/tutorial-page-section >}

## Introduktion
I den här självstudien kommer vi att undersöka hur du skapar SmartArt-miniatyrer för barnanteckningar i Java med Aspose.Slides. Aspose.Slides är ett kraftfullt Java API som låter utvecklare arbeta med PowerPoint-presentationer programmatiskt, vilket gör det möjligt för dem att skapa, ändra och manipulera bilder med lätthet.
## Förutsättningar
Innan vi börjar, se till att du har följande:
1. Java Development Kit (JDK) installerat på ditt system.
2.  Aspose.Slides för Java-bibliotek nedladdade och konfigurerade i ditt projekt. Du kan ladda ner biblioteket från[här](https://releases.aspose.com/slides/java/).

## Importera paket
Se till att importera de nödvändiga paketen i din Java-klass:
```java
import com.aspose.slides.ISmartArt;
import com.aspose.slides.ISmartArtNode;
import com.aspose.slides.Presentation;
import com.aspose.slides.SmartArtLayoutType;

import javax.imageio.ImageIO;
import java.awt.image.BufferedImage;
import java.io.File;
import java.io.IOException;
```
## Steg 1: Konfigurera ditt projekt
Se till att du har ett Java-projekt inställt och konfigurerat med Aspose.Slides-biblioteket.
## Steg 2: Skapa en presentation
 Instantiera`Presentation` klass för att representera PPTX-filen:
```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
```
## Steg 3: Lägg till SmartArt
Lägg till SmartArt till din presentationsbild:
```java
ISmartArt smart = pres.getSlides().get_Item(0).getShapes().addSmartArt(10, 10, 400, 300, SmartArtLayoutType.BasicCycle);
```
## Steg 4: Skaffa en nodreferens
Få referensen till en nod genom att använda dess index:
```java
ISmartArtNode node = smart.getNodes().get_Item(1);
```
## Steg 5: Skaffa miniatyrbild
Hämta miniatyrbilden av SmartArt-noden:
```java
BufferedImage bmp = node.getShapes().get_Item(0).getThumbnail();
```
## Steg 6: Spara miniatyrbild
Spara miniatyrbilden till en fil:
```java
ImageIO.write(bmp, "jpeg", new File(dataDir + "SmartArt_ChildNote_Thumbnail_out.jpeg"));
```
Upprepa dessa steg för varje SmartArt-nod efter behov i din presentation.

## Slutsats
I den här självstudien har vi lärt oss hur man skapar SmartArt-miniatyrer för barnanteckningar i Java med Aspose.Slides. Med denna kunskap kan du förbättra dina PowerPoint-presentationer programmatiskt, lägga till visuellt tilltalande element med lätthet.
## FAQ's
### Kan jag använda Aspose.Slides för att manipulera befintliga PowerPoint-filer?
Ja, Aspose.Slides låter dig ändra befintliga PowerPoint-filer, inklusive lägga till, ta bort eller redigera bilder och deras innehåll.
### Stöder Aspose.Slides export av bilder till olika filformat?
Absolut! Aspose.Slides stöder export av bilder till olika format, inklusive PDF, bilder och HTML, bland annat.
### Är Aspose.Slides lämpliga för PowerPoint-automatisering på företagsnivå?
Ja, Aspose.Slides är utformad för att hantera PowerPoint-automationsuppgifter på företagsnivå effektivt och tillförlitligt.
### Kan jag skapa komplexa SmartArt-diagram programmatiskt med Aspose.Slides?
Säkert! Aspose.Slides ger omfattande stöd för att skapa och manipulera SmartArt-diagram av olika komplexitet.
### Erbjuder Aspose.Slides teknisk support för utvecklare?
 Ja, Aspose.Slides tillhandahåller dedikerad teknisk support för utvecklare genom deras[forum](https://forum.aspose.com/c/slides/11) och andra kanaler.
{< /blocks/products/pf/tutorial-page-section >}

{< /blocks/products/pf/main-container >}
{< /blocks/products/pf/main-wrap-class >}

{< blocks/products/products-backtop-button >}
