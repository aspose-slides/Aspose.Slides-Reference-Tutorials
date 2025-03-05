---
title: Ställ in Bullet Fill Format i SmartArt med Java
linktitle: Ställ in Bullet Fill Format i SmartArt med Java
second_title: Aspose.Slides Java PowerPoint Processing API
description: Lär dig hur du ställer in punktfyllningsformat i SmartArt med Java med Aspose.Slides. Steg-för-steg-guide för effektiv presentationsmanipulation.
type: docs
weight: 18
url: /sv/java/java-powerpoint-smartart-manipulation/set-bullet-fill-format-smartart-java/
---
## Introduktion
Inom Java-programmering är effektiv manipulering av presentationer ett vanligt krav, särskilt när man hanterar SmartArt-element. Aspose.Slides för Java framstår som ett kraftfullt verktyg för sådana uppgifter, och erbjuder en rad funktioner för att hantera presentationer programmatiskt. I den här handledningen kommer vi att fördjupa oss i processen att ställa in punktfyllningsformat i SmartArt med Java med Aspose.Slides, steg för steg.
## Förutsättningar
Innan vi börjar med den här handledningen, se till att du har följande förutsättningar på plats:
### Java Development Kit (JDK)
 Du måste ha JDK installerat på ditt system. Du kan ladda ner den från[hemsida](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html) och följ installationsanvisningarna.
### Aspose.Slides för Java
 Ladda ner och installera Aspose.Slides för Java från[nedladdningslänk](https://releases.aspose.com/slides/java/). Följ installationsinstruktionerna i dokumentationen för ditt specifika operativsystem.

## Importera paket
För att börja, importera de nödvändiga paketen till ditt Java-projekt:
```java
import com.aspose.slides.*;
import javax.imageio.ImageIO;
import java.awt.image.BufferedImage;
import java.io.File;
import java.io.IOException;
```
#Låt oss dela upp exemplet i flera steg för en tydlig förståelse av hur man ställer in punktfyllningsformat i SmartArt med Java med Aspose.Slides.
## Steg 1: Skapa presentationsobjekt
```java
Presentation presentation = new Presentation();
```
Skapa först en ny instans av klassen Presentation, som representerar en PowerPoint-presentation.
## Steg 2: Lägg till SmartArt
```java
ISmartArt smart = presentation.getSlides().get_Item(0).getShapes().addSmartArt(10, 10, 500, 400, SmartArtLayoutType.VerticalPictureList);
```
Lägg sedan till en SmartArt-form på bilden. Denna kodrad initierar en ny SmartArt-form med specificerade mått och layout.
## Steg 3: Öppna SmartArt Node
```java
ISmartArtNode node = smart.getAllNodes().get_Item(0);
```
Gå nu till den första noden (eller valfri nod) i SmartArt-formen för att ändra dess egenskaper.
## Steg 4: Ställ in punktfyllningsformat
```java
if (node.getBulletFillFormat() != null) {
    BufferedImage img = ImageIO.read(new File(dataDir + "aspose-logo.jpg"));
    IPPImage image = presentation.getImages().addImage(img);
    node.getBulletFillFormat().setFillType(FillType.Picture);
    node.getBulletFillFormat().getPictureFillFormat().getPicture().setImage(image);
    node.getBulletFillFormat().getPictureFillFormat().setPictureFillMode(PictureFillMode.Stretch);
}
```
Här kontrollerar vi om punktfyllningsformatet stöds. Om det är det, laddar vi en bildfil och ställer in den som punktfyllning för SmartArt-noden.
## Steg 5: Spara presentationen
```java
presentation.save(dataDir + "out.pptx", SaveFormat.Pptx);
```
Slutligen, spara den ändrade presentationen på en angiven plats.

## Slutsats
Grattis! Du har framgångsrikt lärt dig hur du ställer in punktfyllningsformat i SmartArt med Java med Aspose.Slides. Denna förmåga öppnar en värld av möjligheter för dynamiska och visuellt tilltalande presentationer i Java-applikationer.
## FAQ's
### Kan jag använda Aspose.Slides för Java för att skapa presentationer från grunden?
Absolut! Aspose.Slides tillhandahåller omfattande API:er för att skapa, ändra och manipulera presentationer helt genom kod.
### Är Aspose.Slides kompatibel med olika versioner av PowerPoint?
Ja, Aspose.Slides säkerställer kompatibilitet med olika versioner av Microsoft PowerPoint, vilket möjliggör sömlös integrering i ditt arbetsflöde.
### Kan jag anpassa SmartArt-element utöver punktfyllningsformat?
Faktum är att Aspose.Slides ger dig möjlighet att anpassa alla aspekter av SmartArt-former, inklusive layout, stil, innehåll och mer.
### Finns det en testversion tillgänglig för Aspose.Slides för Java?
 Ja, du kan utforska funktionerna i Aspose.Slides med en gratis provperiod. Ladda bara ner det från[hemsida](https://releases.aspose.com/slides/java/) och börja utforska.
### Var kan jag hitta support för Aspose.Slides för Java?
 För eventuella frågor eller hjälp kan du besöka Aspose.Slides-forumet på[den här länken](https://forum.aspose.com/c/slides/11).