---
title: Lägg till anpassade underordnade noder i SmartArt med Java
linktitle: Lägg till anpassade underordnade noder i SmartArt med Java
second_title: Aspose.Slides Java PowerPoint Processing API
description: Lär dig hur du lägger till anpassade underordnade noder till SmartArt i PowerPoint-presentationer med Java med Aspose.Slides. Förbättra dina bilder med professionell grafik utan ansträngning.
weight: 11
url: /sv/java/java-powerpoint-smartart-manipulation/add-custom-child-nodes-smartart-java/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Lägg till anpassade underordnade noder i SmartArt med Java

## Introduktion
SmartArt är en kraftfull funktion i PowerPoint som låter användare skapa professionell grafik snabbt och enkelt. I den här handledningen kommer vi att lära oss hur du lägger till anpassade underordnade noder till SmartArt med Java med Aspose.Slides.
## Förutsättningar
Innan vi börjar, se till att du har följande:
1. Java Development Kit (JDK): Se till att du har Java installerat på ditt system.
2.  Aspose.Slides för Java: Ladda ner och installera Aspose.Slides för Java från[här](https://releases.aspose.com/slides/java/).

## Importera paket
För att börja, importera nödvändiga paket i ditt Java-projekt:
```java
import com.aspose.slides.*;
```
## Steg 1: Ladda presentationen
Ladda PowerPoint-presentationen där du vill lägga till anpassade underordnade noder till SmartArt:
```java
String dataDir = "Your Document Directory";
// Ladda önskad presentation
Presentation pres = new Presentation(dataDir + "YourPresentation.pptx");
```
## Steg 2: Lägg till SmartArt till Slide
Låt oss nu lägga till SmartArt till bilden:
```java
ISmartArt smart = pres.getSlides().get_Item(0).getShapes().addSmartArt(20, 20, 600, 500, SmartArtLayoutType.OrganizationChart);
```
## Steg 3: Flytta SmartArt Shape
Flytta SmartArt-formen till en ny position:
```java
ISmartArtNode node = smart.getAllNodes().get_Item(1);
ISmartArtShape shape = node.getShapes().get_Item(1);
shape.setX(shape.getX() + (shape.getWidth() * 2));
shape.setY(shape.getY() - (shape.getHeight() / 2));
```
## Steg 4: Ändra formbredd
Ändra bredden på SmartArt-formen:
```java
node = smart.getAllNodes().get_Item(2);
shape = node.getShapes().get_Item(1);
shape.setWidth(shape.getWidth() + (shape.getWidth() / 2));
```
## Steg 5: Ändra formhöjd
Ändra höjden på SmartArt-formen:
```java
node = smart.getAllNodes().get_Item(3);
shape = node.getShapes().get_Item(1);
shape.setHeight(shape.getHeight() + (shape.getHeight() / 2));
```
## Steg 6: Rotera formen
Rotera SmartArt-formen:
```java
node = smart.getAllNodes().get_Item(4);
shape = node.getShapes().get_Item(1);
shape.setRotation(90);
```
## Steg 7: Spara presentationen
Slutligen, spara den ändrade presentationen:
```java
pres.save(dataDir + "ModifiedPresentation.pptx", SaveFormat.Pptx);
```

## Slutsats
I den här handledningen lärde vi oss hur man lägger till anpassade underordnade noder till SmartArt med Java med Aspose.Slides. Genom att följa dessa steg kan du förbättra dina presentationer med anpassad grafik, vilket gör dem mer engagerande och professionella.
## FAQ's
### Kan jag lägga till olika typer av SmartArt-layouter med Aspose.Slides för Java?
Ja, Aspose.Slides för Java stöder olika SmartArt-layouter, så att du kan välja den som bäst passar dina presentationsbehov.
### Är Aspose.Slides för Java kompatibel med olika versioner av PowerPoint?
Aspose.Slides för Java är utformad för att fungera sömlöst med olika versioner av PowerPoint, vilket säkerställer kompatibilitet och konsistens över plattformar.
### Kan jag anpassa utseendet på SmartArt-former programmatiskt?
Absolut! Med Aspose.Slides för Java kan du programmässigt anpassa utseendet, storleken, färgen och layouten för SmartArt-former för att passa dina designpreferenser.
### Tillhandahåller Aspose.Slides för Java dokumentation och support?
Ja, du kan hitta omfattande dokumentation och tillgång till community supportforum på Asposes webbplats.
### Finns det en testversion tillgänglig för Aspose.Slides för Java?
 Ja, du kan ladda ner en gratis testversion av Aspose.Slides för Java från webbplatsen för att utforska dess funktioner och möjligheter innan du gör ett köp[här](https://releases.aspose.com/slides/java/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
