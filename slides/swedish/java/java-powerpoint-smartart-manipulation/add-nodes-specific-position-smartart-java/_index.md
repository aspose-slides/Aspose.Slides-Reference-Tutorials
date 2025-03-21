---
title: Lägg till noder vid specifik position i SmartArt med Java
linktitle: Lägg till noder vid specifik position i SmartArt med Java
second_title: Aspose.Slides Java PowerPoint Processing API
description: Upptäck hur du lägger till noder på specifika positioner i SmartArt med Java med Aspose.Slides. Skapa dynamiska presentationer utan ansträngning.
weight: 16
url: /sv/java/java-powerpoint-smartart-manipulation/add-nodes-specific-position-smartart-java/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Lägg till noder vid specifik position i SmartArt med Java

## Introduktion
I den här handledningen guidar vi dig genom processen att lägga till noder på specifika positioner i SmartArt med hjälp av Java med Aspose.Slides. SmartArt är en funktion i PowerPoint som låter dig skapa visuellt tilltalande diagram och diagram.
## Förutsättningar
Innan du börjar, se till att du har följande:
1. Java Development Kit (JDK) installerat på ditt system.
2.  Aspose.Slides för Java-bibliotek nedladdade. Du kan ladda ner den från[här](https://releases.aspose.com/slides/java/).
3. Grundläggande kunskaper i programmeringsspråket Java.

## Importera paket
Låt oss först importera de nödvändiga paketen i vår Java-kod:
```java
import com.aspose.slides.*;
import java.io.File;
```
## Steg 1: Skapa en presentationsinstans
Börja med att skapa en instans av klassen Presentation:
```java
Presentation pres = new Presentation();
```
## Steg 2: Öppna presentationsbilden
Gå till bilden där du vill lägga till SmartArt:
```java
ISlide slide = pres.getSlides().get_Item(0);
```
## Steg 3: Lägg till SmartArt Shape
Lägg till en SmartArt-form på bilden:
```java
ISmartArt smart = slide.getShapes().addSmartArt(0, 0, 400, 400, SmartArtLayoutType.StackedList);
```
## Steg 4: Öppna SmartArt Node
Gå till SmartArt-noden vid önskat index:
```java
ISmartArtNode node = smart.getAllNodes().get_Item(0);
```
## Steg 5: Lägg till barnnod vid specifik position
Lägg till en ny underordnad nod på en specifik position i den överordnade noden:
```java
SmartArtNode chNode = (SmartArtNode) ((SmartArtNodeCollection) node.getChildNodes()).addNodeByPosition(2);
```
## Steg 6: Lägg till text till noden
Ställ in texten för den nyligen tillagda noden:
```java
chNode.getTextFrame().setText("Sample Text Added");
```
## Steg 7: Spara presentationen
Spara den ändrade presentationen:
```java
pres.save(dataDir + "AddSmartArtNodeByPosition_out.pptx", SaveFormat.Pptx);
```

## Slutsats
I den här handledningen lärde du dig hur du lägger till noder på specifika positioner i SmartArt med hjälp av Java med Aspose.Slides. Genom att följa dessa steg kan du manipulera SmartArt-former programmatiskt för att skapa dynamiska presentationer.
## FAQ's
### Kan jag lägga till flera noder samtidigt?
Ja, du kan lägga till flera noder programmatiskt genom att iterera över de önskade positionerna.
### Är Aspose.Slides kompatibel med alla versioner av PowerPoint?
Aspose.Slides stöder olika PowerPoint-format, vilket säkerställer kompatibilitet med de flesta versioner.
### Kan jag anpassa utseendet på SmartArt-noder?
Ja, du kan anpassa utseendet på noder, inklusive deras storlek, färg och stil.
### Erbjuder Aspose.Slides stöd för andra programmeringsspråk?
Ja, Aspose.Slides tillhandahåller bibliotek för flera programmeringsspråk, inklusive .NET och Python.
### Finns det en testversion tillgänglig för Aspose.Slides?
 Ja, du kan ladda ner en gratis testversion från[här](https://releases.aspose.com/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
