---
title: Lägg till Assistant Node till SmartArt i Java PowerPoint
linktitle: Lägg till Assistant Node till SmartArt i Java PowerPoint
second_title: Aspose.Slides Java PowerPoint Processing API
description: Lär dig hur du lägger till en assistentnod till SmartArt i Java PowerPoint-presentationer med Aspose.Slides. Förbättra dina färdigheter i PowerPoint-redigering.
weight: 17
url: /sv/java/java-powerpoint-smartart-manipulation/add-assistant-node-smartart-java-powerpoint/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Lägg till Assistant Node till SmartArt i Java PowerPoint

## Introduktion
I den här självstudien guidar vi dig genom processen att lägga till en assistentnod till SmartArt i Java PowerPoint-presentationer med Aspose.Slides.
## Förutsättningar
Innan vi börjar, se till att du har följande förutsättningar på plats:
1.  Java Development Kit (JDK): Se till att du har Java installerat på ditt system. Du kan ladda ner och installera den senaste JDK från[här](https://www.oracle.com/java/technologies/javase-jdk15-downloads.html).
2.  Aspose.Slides for Java: Ladda ner och installera Aspose.Slides for Java-biblioteket från[den här länken](https://releases.aspose.com/slides/java/).

## Importera paket
Till att börja med, importera de nödvändiga paketen i din Java-kod:
```java
import com.aspose.slides.*;
```
## Steg 1: Konfigurera presentationen
Börja med att skapa en presentationsinstans med hjälp av sökvägen till din PowerPoint-fil:
```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "AssistantNode.pptx");
```
## Steg 2: Gå igenom former
Gå igenom varje form inuti den första bilden av presentationen:
```java
for (IShape shape : pres.getSlides().get_Item(0).getShapes())
```
## Steg 3: Sök efter SmartArt-former
Kontrollera om formen är av typen SmartArt:
```java
if (shape instanceof ISmartArt)
```
## Steg 4: Gå igenom SmartArt-noder
Gå igenom alla noder i SmartArt-formen:
```java
for (ISmartArtNode node : smart.getAllNodes())
```
## Steg 5: Sök efter Assistant Node
Kontrollera om noden är en assistentnod:
```java
if (node.isAssistant())
```
## Steg 6: Ställ in Assistant Node på Normal
Om noden är en assistentnod, ställ in den på en normal nod:
```java
node.setAssistant(false);
```
## Steg 7: Spara presentationen
Spara den ändrade presentationen:
```java
pres.save(dataDir + "ChangeAssistantNode_out.pptx", SaveFormat.Pptx);
```

## Slutsats
Grattis! Du har framgångsrikt lagt till en assistentnod till SmartArt i din Java PowerPoint-presentation med Aspose.Slides.

## FAQ's
### Kan jag lägga till flera assistentnoder till en SmartArt i presentationen?
Ja, du kan lägga till flera assistentnoder genom att upprepa processen för varje nod.
### Fungerar den här handledningen för både PowerPoint- och PowerPoint-mallar?
Ja, du kan tillämpa den här handledningen på både PowerPoint-presentationer och mallar.
### Är Aspose.Slides kompatibel med alla versioner av PowerPoint?
Aspose.Slides stöder PowerPoint-versioner från 97-2003 till den senaste versionen.
### Kan jag anpassa utseendet på assistentnoden?
Ja, du kan anpassa utseendet med hjälp av olika egenskaper och metoder som tillhandahålls av Aspose.Slides.
### Finns det någon gräns för antalet noder i en SmartArt?
SmartArt i PowerPoint stöder ett stort antal noder, men det rekommenderas att hålla det rimligt för bättre läsbarhet.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
