---
title: Hantera Paragraph Picture Bullets i Java PowerPoint
linktitle: Hantera Paragraph Picture Bullets i Java PowerPoint
second_title: Aspose.Slides Java PowerPoint Processing API
description: Lär dig hur du lägger till anpassade bildpunkter till PowerPoint-bilder med Aspose.Slides för Java. Följ denna detaljerade, steg-för-steg-guide för sömlös integration.
weight: 11
url: /sv/java/java-powerpoint-advanced-paragraph-font-properties/manage-paragraph-picture-bullets-java-powerpoint/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hantera Paragraph Picture Bullets i Java PowerPoint

## Introduktion
Att skapa engagerande och visuellt tilltalande presentationer är en avgörande färdighet i den moderna affärsvärlden. Java-utvecklare kan utnyttja Aspose.Slides för att förbättra sina presentationer med anpassade bildpunkter i PowerPoint-bilder. Denna handledning guidar dig genom processen steg för steg, vilket säkerställer att du med säkerhet kan lägga till bildpunkter i dina presentationer.
## Förutsättningar
Innan du dyker in i handledningen, se till att du har följande förutsättningar på plats:
- Java Development Kit (JDK) installerat
- Integrated Development Environment (IDE) som Eclipse eller IntelliJ IDEA
- Aspose.Slides för Java-bibliotek
- Grundläggande kunskaper i Java-programmering
- Bildfil för punktbilden
 För att ladda ner Aspose.Slides for Java-biblioteket, besök[nedladdningssida](https://releases.aspose.com/slides/java/) . För dokumentation, kontrollera[dokumentation](https://reference.aspose.com/slides/java/).
## Importera paket
Se först till att du har importerat de nödvändiga paketen för ditt projekt. Lägg till följande importer i början av din Java-fil:
```java
import com.aspose.slides.*;
import javax.imageio.ImageIO;
import java.awt.image.BufferedImage;
import java.io.File;
import java.io.IOException;
```
Låt oss dela upp processen i hanterbara steg.
## Steg 1: Konfigurera din projektkatalog
Skapa en ny katalog för ditt projekt. Den här katalogen kommer att innehålla din Java-fil, Aspose.Slides-biblioteket och bildfilen för kulan.
```java
String dataDir = "Your Document Directory";
```
## Steg 2: Initiera presentationen
 Initiera en ny instans av`Presentation` klass. Detta objekt representerar din PowerPoint-presentation.
```java
Presentation presentation = new Presentation();
```
## Steg 3: Öppna den första bilden
Öppna den första bilden av presentationen. Bilder är nollindexerade, så den första bilden är på index 0.
```java
ISlide slide = presentation.getSlides().get_Item(0);
```
## Steg 4: Ladda punktbilden
Ladda bilden du vill använda för kulorna. Den här bilden bör placeras i din projektkatalog.
```java
BufferedImage image = ImageIO.read(new File(dataDir + "bullets.png"));
IPPImage ippxImage = presentation.getImages().addImage(image);
```
## Steg 5: Lägg till en AutoShape till bilden
Lägg till en AutoShape på bilden. Formen kommer att innehålla texten med de anpassade punktpunkterna.
```java
IAutoShape autoShape = slide.getShapes().addAutoShape(ShapeType.Rectangle, 200, 200, 400, 200);
```
## Steg 6: Öppna textramen
Gå till textramen i AutoShape för att manipulera dess stycken.
```java
ITextFrame textFrame = autoShape.getTextFrame();
```
## Steg 7: Ta bort standardstycket
Ta bort standardstycket som automatiskt läggs till i textramen.
```java
textFrame.getParagraphs().removeAt(0);
```
## Steg 8: Skapa ett nytt stycke
Skapa ett nytt stycke och ställ in dess text. Detta stycke kommer att innehålla de anpassade bildpunkterna.
```java
Paragraph paragraph = new Paragraph();
paragraph.setText("Welcome to Aspose.Slides");
```
## Steg 9: Ställ in Bullet Style och Image
Ställ in punktstilen för att använda den anpassade bilden som laddades tidigare.
```java
paragraph.getParagraphFormat().getBullet().setType(BulletType.Picture);
paragraph.getParagraphFormat().getBullet().getPicture().setImage(ippxImage);
```
## Steg 10: Justera kulhöjden
Ställ in höjden på kulan för att se till att den ser bra ut i presentationen.
```java
paragraph.getParagraphFormat().getBullet().setHeight(100);
```
## Steg 11: Lägg till stycket i textramen
Lägg till det nyskapade stycket i textramen i AutoShape.
```java
textFrame.getParagraphs().add(paragraph);
```
## Steg 12: Spara presentationen
Slutligen, spara presentationen som både en PPTX- och en PPT-fil.
```java
presentation.save(dataDir + "ParagraphPictureBulletsPPTX_out.pptx", SaveFormat.Pptx);
presentation.save(dataDir + "ParagraphPictureBulletsPPT_out.ppt", SaveFormat.Ppt);
```
## Slutsats
 Och där har du det! Genom att följa dessa steg kan du enkelt lägga till anpassade bildpunkter till dina PowerPoint-presentationer med Aspose.Slides för Java. Detta kraftfulla bibliotek erbjuder ett brett utbud av funktioner som hjälper dig att skapa professionella och visuellt tilltalande presentationer. Glöm inte att utforska[dokumentation](https://reference.aspose.com/slides/java/)för mer avancerade funktioner och anpassningsalternativ.
## FAQ's
### Vad är Aspose.Slides för Java?
Aspose.Slides för Java är ett kraftfullt bibliotek som låter Java-utvecklare skapa, modifiera och manipulera PowerPoint-presentationer programmatiskt.
### Kan jag använda vilken bild som helst för bildkulorna?
Ja, du kan använda vilken bild som helst för bildkulorna så länge den är tillgänglig från din projektkatalog.
### Behöver jag en licens för att använda Aspose.Slides för Java?
 Aspose.Slides för Java kräver en licens för full funktionalitet. Du kan få en tillfällig licens från[här](https://purchase.aspose.com/temporary-license/) eller köp en fullständig licens[här](https://purchase.aspose.com/buy).
### Kan jag lägga till flera stycken med olika punktformat i en AutoShape?
Ja, du kan lägga till flera stycken med olika punktstilar till en enda AutoShape genom att skapa och konfigurera varje stycke individuellt.
### Var kan jag hitta fler exempel och stöd?
 Du kan hitta fler exempel i[dokumentation](https://reference.aspose.com/slides/java/) och få stöd från Aspose-gemenskapen på[forum](https://forum.aspose.com/c/slides/11).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
