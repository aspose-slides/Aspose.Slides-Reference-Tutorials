---
"description": "Lär dig hur du lägger till anpassade underordnade noder till SmartArt i PowerPoint-presentationer med Java och Aspose.Slides. Förbättra dina bilder utan ansträngning med professionell grafik."
"linktitle": "Lägga till anpassade underordnade noder i SmartArt med hjälp av Java"
"second_title": "Aspose.Slides Java PowerPoint-bearbetnings-API"
"title": "Lägga till anpassade underordnade noder i SmartArt med hjälp av Java"
"url": "/sv/java/java-powerpoint-smartart-manipulation/add-custom-child-nodes-smartart-java/"
"weight": 11
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Lägga till anpassade underordnade noder i SmartArt med hjälp av Java

## Introduktion
SmartArt är en kraftfull funktion i PowerPoint som låter användare skapa professionellt utseende grafik snabbt och enkelt. I den här handledningen lär vi oss hur man lägger till anpassade underordnade noder till SmartArt med hjälp av Java och Aspose.Slides.
## Förkunskapskrav
Innan vi börjar, se till att du har följande:
1. Java Development Kit (JDK): Se till att du har Java installerat på ditt system.
2. Aspose.Slides för Java: Ladda ner och installera Aspose.Slides för Java från [här](https://releases.aspose.com/slides/java/).

## Importera paket
För att börja, importera de nödvändiga paketen i ditt Java-projekt:
```java
import com.aspose.slides.*;
```
## Steg 1: Ladda presentationen
Ladda PowerPoint-presentationen där du vill lägga till anpassade underordnade noder till SmartArt-objektet:
```java
String dataDir = "Your Document Directory";
// Ladda önskad presentation
Presentation pres = new Presentation(dataDir + "YourPresentation.pptx");
```
## Steg 2: Lägg till SmartArt till bilden
Nu lägger vi till SmartArt i bilden:
```java
ISmartArt smart = pres.getSlides().get_Item(0).getShapes().addSmartArt(20, 20, 600, 500, SmartArtLayoutType.OrganizationChart);
```
## Steg 3: Flytta SmartArt-formen
Flytta SmartArt-formen till en ny position:
```java
ISmartArtNode node = smart.getAllNodes().get_Item(1);
ISmartArtShape shape = node.getShapes().get_Item(1);
shape.setX(shape.getX() + (shape.getWidth() * 2));
shape.setY(shape.getY() - (shape.getHeight() / 2));
```
## Steg 4: Ändra formens bredd
Ändra bredden på SmartArt-formen:
```java
node = smart.getAllNodes().get_Item(2);
shape = node.getShapes().get_Item(1);
shape.setWidth(shape.getWidth() + (shape.getWidth() / 2));
```
## Steg 5: Ändra formens höjd
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
Spara slutligen den ändrade presentationen:
```java
pres.save(dataDir + "ModifiedPresentation.pptx", SaveFormat.Pptx);
```

## Slutsats
den här handledningen lärde vi oss hur man lägger till anpassade underordnade noder till SmartArt med hjälp av Java och Aspose.Slides. Genom att följa dessa steg kan du förbättra dina presentationer med anpassad grafik, vilket gör dem mer engagerande och professionella.
## Vanliga frågor
### Kan jag lägga till olika typer av SmartArt-layouter med Aspose.Slides för Java?
Ja, Aspose.Slides för Java stöder olika SmartArt-layouter, så att du kan välja den som bäst passar dina presentationsbehov.
### Är Aspose.Slides för Java kompatibelt med olika versioner av PowerPoint?
Aspose.Slides för Java är utformat för att fungera sömlöst med olika versioner av PowerPoint, vilket säkerställer kompatibilitet och konsekvens över olika plattformar.
### Kan jag anpassa utseendet på SmartArt-former programmatiskt?
Absolut! Med Aspose.Slides för Java kan du programmatiskt anpassa utseende, storlek, färg och layout för SmartArt-former så att de passar dina designpreferenser.
### Tillhandahåller Aspose.Slides för Java dokumentation och support?
Ja, du hittar omfattande dokumentation och tillgång till supportforum på Asposes webbplats.
### Finns det en testversion tillgänglig för Aspose.Slides för Java?
Ja, du kan ladda ner en gratis testversion av Aspose.Slides för Java från webbplatsen för att utforska dess funktioner och möjligheter innan du gör ett köp. [här](https://releases.aspose.com/slides/java/).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}