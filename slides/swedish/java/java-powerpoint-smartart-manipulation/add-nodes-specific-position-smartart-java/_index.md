---
"description": "Upptäck hur du lägger till noder på specifika positioner i SmartArt med hjälp av Java och Aspose.Slides. Skapa dynamiska presentationer utan ansträngning."
"linktitle": "Lägga till noder på en specifik position i SmartArt med hjälp av Java"
"second_title": "Aspose.Slides Java PowerPoint-bearbetnings-API"
"title": "Lägga till noder på en specifik position i SmartArt med hjälp av Java"
"url": "/sv/java/java-powerpoint-smartart-manipulation/add-nodes-specific-position-smartart-java/"
"weight": 16
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Lägga till noder på en specifik position i SmartArt med hjälp av Java

## Introduktion
I den här handledningen guidar vi dig genom processen att lägga till noder på specifika positioner i SmartArt med hjälp av Java och Aspose.Slides. SmartArt är en funktion i PowerPoint som låter dig skapa visuellt tilltalande diagram och tabeller.
## Förkunskapskrav
Innan du börjar, se till att du har följande:
1. Java Development Kit (JDK) installerat på ditt system.
2. Aspose.Slides för Java-biblioteket har laddats ner. Du kan ladda ner det från [här](https://releases.aspose.com/slides/java/).
3. Grundläggande kunskaper i programmeringsspråket Java.

## Importera paket
Låt oss först importera de nödvändiga paketen i vår Java-kod:
```java
import com.aspose.slides.*;
import java.io.File;
```
## Steg 1: Skapa en presentationsinstans
Börja med att skapa en instans av Presentation-klassen:
```java
Presentation pres = new Presentation();
```
## Steg 2: Öppna presentationsbilden
Gå till bilden där du vill lägga till SmartArt-bilden:
```java
ISlide slide = pres.getSlides().get_Item(0);
```
## Steg 3: Lägg till SmartArt-form
Lägg till en SmartArt-form på bilden:
```java
ISmartArt smart = slide.getShapes().addSmartArt(0, 0, 400, 400, SmartArtLayoutType.StackedList);
```
## Steg 4: Åtkomst till SmartArt-noden
Åtkomst till SmartArt-noden vid önskat index:
```java
ISmartArtNode node = smart.getAllNodes().get_Item(0);
```
## Steg 5: Lägg till underordnad nod på specifik position
Lägg till en ny underordnad nod på en specifik position i den överordnade noden:
```java
SmartArtNode chNode = (SmartArtNode) ((SmartArtNodeCollection) node.getChildNodes()).addNodeByPosition(2);
```
## Steg 6: Lägg till text i noden
Ange texten för den nyligen tillagda noden:
```java
chNode.getTextFrame().setText("Sample Text Added");
```
## Steg 7: Spara presentationen
Spara den ändrade presentationen:
```java
pres.save(dataDir + "AddSmartArtNodeByPosition_out.pptx", SaveFormat.Pptx);
```

## Slutsats
I den här handledningen lärde du dig hur du lägger till noder på specifika positioner i SmartArt med hjälp av Java och Aspose.Slides. Genom att följa dessa steg kan du manipulera SmartArt-former programmatiskt för att skapa dynamiska presentationer.
## Vanliga frågor
### Kan jag lägga till flera noder samtidigt?
Ja, du kan lägga till flera noder programmatiskt genom att iterera över de önskade positionerna.
### Är Aspose.Slides kompatibelt med alla versioner av PowerPoint?
Aspose.Slides stöder olika PowerPoint-format, vilket säkerställer kompatibilitet med de flesta versioner.
### Kan jag anpassa utseendet på SmartArt-noder?
Ja, du kan anpassa utseendet på noder, inklusive deras storlek, färg och stil.
### Har Aspose.Slides stöd för andra programmeringsspråk?
Ja, Aspose.Slides tillhandahåller bibliotek för flera programmeringsspråk, inklusive .NET och Python.
### Finns det en testversion tillgänglig för Aspose.Slides?
Ja, du kan ladda ner en gratis testversion från [här](https://releases.aspose.com/).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}