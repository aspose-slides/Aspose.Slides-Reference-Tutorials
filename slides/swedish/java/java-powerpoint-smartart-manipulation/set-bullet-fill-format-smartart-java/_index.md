---
"description": "Lär dig hur du ställer in punktformat i SmartArt med Java och Aspose.Slides. Steg-för-steg-guide för effektiv presentationshantering."
"linktitle": "Ställ in punktfyllningsformat i SmartArt med Java"
"second_title": "Aspose.Slides Java PowerPoint-bearbetnings-API"
"title": "Ställ in punktfyllningsformat i SmartArt med Java"
"url": "/sv/java/java-powerpoint-smartart-manipulation/set-bullet-fill-format-smartart-java/"
"weight": 18
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Ställ in punktfyllningsformat i SmartArt med Java

## Introduktion
Inom Java-programmering är effektiv hantering av presentationer ett vanligt krav, särskilt när man arbetar med SmartArt-element. Aspose.Slides för Java framstår som ett kraftfullt verktyg för sådana uppgifter och erbjuder en rad funktioner för att hantera presentationer programmatiskt. I den här handledningen kommer vi att fördjupa oss i processen att ställa in punktformat i SmartArt med hjälp av Java med Aspose.Slides, steg för steg.
## Förkunskapskrav
Innan vi börjar med den här handledningen, se till att du har följande förutsättningar på plats:
### Java-utvecklingspaket (JDK)
Du måste ha JDK installerat på ditt system. Du kan ladda ner det från [webbplats](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html) och följ installationsanvisningarna.
### Aspose.Slides för Java
Ladda ner och installera Aspose.Slides för Java från [nedladdningslänk](https://releases.aspose.com/slides/java/)Följ installationsanvisningarna i dokumentationen för ditt specifika operativsystem.

## Importera paket
För att börja, importera de nödvändiga paketen till ditt Java-projekt:
```java
import com.aspose.slides.*;
import javax.imageio.ImageIO;
import java.awt.image.BufferedImage;
import java.io.File;
import java.io.IOException;
```
#Låt oss dela upp exemplet i flera steg för att få en tydlig förståelse för hur man ställer in punktformat i SmartArt med hjälp av Java och Aspose.Slides.
## Steg 1: Skapa presentationsobjekt
```java
Presentation presentation = new Presentation();
```
Skapa först en ny instans av Presentation-klassen, som representerar en PowerPoint-presentation.
## Steg 2: Lägg till SmartArt
```java
ISmartArt smart = presentation.getSlides().get_Item(0).getShapes().addSmartArt(10, 10, 500, 400, SmartArtLayoutType.VerticalPictureList);
```
Lägg sedan till en SmartArt-form på bilden. Den här kodraden initierar en ny SmartArt-form med angivna dimensioner och layout.
## Steg 3: Åtkomst till SmartArt-noden
```java
ISmartArtNode node = smart.getAllNodes().get_Item(0);
```
Nu kan du komma åt den första noden (eller valfri nod) i SmartArt-formen för att ändra dess egenskaper.
## Steg 4: Ställ in punktformat
```java
if (node.getBulletFillFormat() != null) {
    BufferedImage img = ImageIO.read(new File(dataDir + "aspose-logo.jpg"));
    IPPImage image = presentation.getImages().addImage(img);
    node.getBulletFillFormat().setFillType(FillType.Picture);
    node.getBulletFillFormat().getPictureFillFormat().getPicture().setImage(image);
    node.getBulletFillFormat().getPictureFillFormat().setPictureFillMode(PictureFillMode.Stretch);
}
```
Här kontrollerar vi om punktformatet stöds. Om det stöds laddar vi en bildfil och ställer in den som punktformat för SmartArt-noden.
## Steg 5: Spara presentationen
```java
presentation.save(dataDir + "out.pptx", SaveFormat.Pptx);
```
Spara slutligen den ändrade presentationen på en angiven plats.

## Slutsats
Grattis! Du har nu lärt dig hur man ställer in punktformat i SmartArt med hjälp av Java och Aspose.Slides. Den här funktionen öppnar upp en värld av möjligheter för dynamiska och visuellt tilltalande presentationer i Java-applikationer.
## Vanliga frågor
### Kan jag använda Aspose.Slides för Java för att skapa presentationer från grunden?
Absolut! Aspose.Slides tillhandahåller omfattande API:er för att skapa, modifiera och manipulera presentationer helt och hållet via kod.
### Är Aspose.Slides kompatibelt med olika versioner av PowerPoint?
Ja, Aspose.Slides säkerställer kompatibilitet med olika versioner av Microsoft PowerPoint, vilket möjliggör sömlös integration i ditt arbetsflöde.
### Kan jag anpassa SmartArt-element utöver punktfyllningsformatet?
Aspose.Slides ger dig verkligen möjlighet att anpassa alla aspekter av SmartArt-former, inklusive layout, stil, innehåll och mer.
### Finns det en testversion tillgänglig för Aspose.Slides för Java?
Ja, du kan utforska funktionerna i Aspose.Slides med en gratis provperiod. Ladda bara ner den från [webbplats](https://releases.aspose.com/slides/java/) och börja utforska.
### Var kan jag hitta support för Aspose.Slides för Java?
För eventuella frågor eller hjälp kan du besöka Aspose.Slides-forumet på [den här länken](https://forum.aspose.com/c/slides/11).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}