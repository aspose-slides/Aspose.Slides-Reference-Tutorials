---
"description": "Lär dig hur du skapar miniatyrer av SmartArt-anteckningar i Java med Aspose.Slides och förbättrar dina PowerPoint-presentationer utan ansträngning."
"linktitle": "Skapa miniatyrbild av SmartArt-underanteckning"
"second_title": "Aspose.Slides Java PowerPoint-bearbetnings-API"
"title": "Skapa miniatyrbild av SmartArt-underanteckning"
"url": "/sv/java/java-powerpoint-shape-thumbnail-creation/create-smartart-child-note-thumbnail/"
"weight": 15
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Skapa miniatyrbild av SmartArt-underanteckning

## Introduktion
den här handledningen ska vi utforska hur man skapar miniatyrer av SmartArt-anteckningar i Java med hjälp av Aspose.Slides. Aspose.Slides är ett kraftfullt Java API som låter utvecklare arbeta med PowerPoint-presentationer programmatiskt, vilket gör att de enkelt kan skapa, modifiera och manipulera bilder.
## Förkunskapskrav
Innan vi börjar, se till att du har följande:
1. Java Development Kit (JDK) installerat på ditt system.
2. Aspose.Slides för Java-biblioteket har laddats ner och konfigurerats i ditt projekt. Du kan ladda ner biblioteket från [här](https://releases.aspose.com/slides/java/).

## Importera paket
Se till att importera nödvändiga paket i din Java-klass:
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
Se till att du har ett Java-projekt konfigurerat och installerat med Aspose.Slides-biblioteket.
## Steg 2: Skapa en presentation
Instansiera `Presentation` klass för att representera PPTX-filen:
```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
```
## Steg 3: Lägg till SmartArt
Lägg till SmartArt i din presentationsbild:
```java
ISmartArt smart = pres.getSlides().get_Item(0).getShapes().addSmartArt(10, 10, 400, 300, SmartArtLayoutType.BasicCycle);
```
## Steg 4: Hämta en nodreferens
Hämta referensen till en nod med hjälp av dess index:
```java
ISmartArtNode node = smart.getNodes().get_Item(1);
```
## Steg 5: Hämta miniatyrbild
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
I den här handledningen har vi lärt oss hur man skapar miniatyrer av SmartArt-anteckningar i Java med hjälp av Aspose.Slides. Med den här kunskapen kan du förbättra dina PowerPoint-presentationer programmatiskt och enkelt lägga till visuellt tilltalande element.
## Vanliga frågor
### Kan jag använda Aspose.Slides för att manipulera befintliga PowerPoint-filer?
Ja, Aspose.Slides låter dig modifiera befintliga PowerPoint-filer, inklusive att lägga till, ta bort eller redigera bilder och deras innehåll.
### Stöder Aspose.Slides export av bilder till olika filformat?
Absolut! Aspose.Slides stöder export av bilder till olika format, inklusive PDF, bilder och HTML, bland annat.
### Är Aspose.Slides lämplig för PowerPoint-automation på företagsnivå?
Ja, Aspose.Slides är utformat för att hantera PowerPoint-automatiseringsuppgifter på företagsnivå effektivt och tillförlitligt.
### Kan jag skapa komplexa SmartArt-diagram programmatiskt med Aspose.Slides?
Absolut! Aspose.Slides erbjuder omfattande stöd för att skapa och manipulera SmartArt-diagram av varierande komplexitet.
### Erbjuder Aspose.Slides teknisk support för utvecklare?
Ja, Aspose.Slides erbjuder dedikerad teknisk support för utvecklare genom deras [forum](https://forum.aspose.com/c/slides/11) och andra kanaler.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}