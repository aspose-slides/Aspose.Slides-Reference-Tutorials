---
title: Ställ in Custom Bullets Number i Java PowerPoint
linktitle: Ställ in Custom Bullets Number i Java PowerPoint
second_title: Aspose.Slides Java PowerPoint Processing API
description: Lär dig hur du ställer in anpassade punktnummer i Java PowerPoint med Aspose.Slides, vilket förbättrar presentationens tydlighet och struktur programmässigt.
type: docs
weight: 15
url: /sv/java/java-powerpoint-text-font-customization/set-custom-bullets-number-java-powerpoint/
---
## Introduktion
I dagens digitala tidsålder är det avgörande att skapa dynamiska presentationer för att effektivt kommunicera idéer och data. Aspose.Slides för Java tillhandahåller en kraftfull verktygslåda för att manipulera PowerPoint-presentationer programmatiskt, och erbjuder omfattande funktioner för att förbättra din presentationsprocess. Den här artikeln fördjupar sig i att ställa in anpassade punktnummer i Java PowerPoint-presentationer med Aspose.Slides. Oavsett om du är en erfaren utvecklare eller nykomling, kommer den här handledningen att guida dig steg-för-steg genom processen, vilket säkerställer att du kan utnyttja denna förmåga effektivt.
## Förutsättningar
Innan du dyker in i handledningen, se till att du har följande förutsättningar för din utvecklingsmiljö:
- Java Development Kit (JDK) installerat
- Integrated Development Environment (IDE) som IntelliJ IDEA eller Eclipse
-  Aspose.Slides för Java-bibliotek. Du kan ladda ner den från[här](https://releases.aspose.com/slides/java/)
- Grundläggande förståelse för Java programmeringsspråk och objektorienterade begrepp

## Importera paket
Importera först de nödvändiga Aspose.Slides-klasserna och andra Java-standardbibliotek:
```java
import com.aspose.slides.*;
```
## Steg 1: Skapa ett presentationsobjekt
Börja med att skapa en ny PowerPoint-presentation med Aspose.Slides.
```java
String dataDir = "Your Document Directory";
Presentation presentation = new Presentation();
```
## Steg 2: Lägg till en AutoShape med text
Infoga en AutoShape (rektangel) på bilden och få tillgång till dess textram.
```java
IAutoShape shape = presentation.getSlides().get_Item(0).getShapes().addAutoShape(ShapeType.Rectangle, 200, 200, 400, 200);
ITextFrame textFrame = shape.getTextFrame();
```
## Steg 3: Ta bort standardstycke
Ta bort det befintliga standardstycket från textramen.
```java
textFrame.getParagraphs().removeAt(0);
```
## Steg 4: Lägg till numrerade kulor
Lägg till stycken med anpassade numrerade punkter från specifika siffror.
```java
// Exempelstycke med punkt som börjar från 2
Paragraph paragraph1 = new Paragraph();
paragraph1.setText("bullet 2");
paragraph1.getParagraphFormat().setDepth((short) 4);
paragraph1.getParagraphFormat().getBullet().setNumberedBulletStartWith((short) 2);
paragraph1.getParagraphFormat().getBullet().setType(BulletType.Numbered);
textFrame.getParagraphs().add(paragraph1);
// Exempelstycke med punkt som börjar från 3
Paragraph paragraph2 = new Paragraph();
paragraph2.setText("bullet 3");
paragraph2.getParagraphFormat().setDepth((short) 4);
paragraph2.getParagraphFormat().getBullet().setNumberedBulletStartWith((short) 3);
paragraph2.getParagraphFormat().getBullet().setType(BulletType.Numbered);
textFrame.getParagraphs().add(paragraph2);
// Exempelstycke med punkt som börjar från 7
Paragraph paragraph3 = new Paragraph();
paragraph3.setText("bullet 7");
paragraph3.getParagraphFormat().setDepth((short) 4);
paragraph3.getParagraphFormat().getBullet().setNumberedBulletStartWith((short) 7);
paragraph3.getParagraphFormat().getBullet().setType(BulletType.Numbered);
textFrame.getParagraphs().add(paragraph3);
```
## Steg 5: Spara presentationen
Slutligen, spara den ändrade presentationen på önskad plats.
```java
presentation.save(dataDir + "SetCustomBulletsNumber-slides.pptx", SaveFormat.Pptx);
```

## Slutsats
Sammanfattningsvis förenklar Aspose.Slides för Java processen att ställa in anpassade punktnummer i PowerPoint-presentationer programmatiskt. Genom att följa stegen som beskrivs i denna handledning kan du förbättra den visuella klarheten och strukturen i dina presentationer effektivt.
## FAQ's
### Kan jag anpassa utseendet på kulor ytterligare?
Ja, Aspose.Slides erbjuder omfattande alternativ för att anpassa kultyp, storlek, färg och mer.
### Är Aspose.Slides kompatibel med alla versioner av PowerPoint?
Aspose.Slides stöder PowerPoint-format från 97-2003 till de senaste versionerna.
### Hur kan jag få teknisk support för Aspose.Slides?
 Besök[Aspose.Slides Forum](https://forum.aspose.com/c/slides/11) för teknisk assistans.
### Kan jag prova Aspose.Slides innan jag köper?
 Ja, du kan ladda ner en gratis testversion från[här](https://releases.aspose.com/).
### Var kan jag köpa Aspose.Slides?
 Du kan köpa Aspose.Slides från[här](https://purchase.aspose.com/buy).