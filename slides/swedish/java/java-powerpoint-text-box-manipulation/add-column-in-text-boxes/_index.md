---
title: Lägg till kolumn i textrutor med Aspose.Slides för Java
linktitle: Lägg till kolumn i textrutor med Aspose.Slides för Java
second_title: Aspose.Slides Java PowerPoint Processing API
description: Lär dig hur du lägger till kolumner i textrutor i PowerPoint med Aspose.Slides för Java. Förbättra dina presentationer med denna steg-för-steg-guide.
type: docs
weight: 10
url: /sv/java/java-powerpoint-text-box-manipulation/add-column-in-text-boxes/
---
## Introduktion
den här handledningen kommer vi att utforska hur man förbättrar textrutor genom att lägga till kolumner med Aspose.Slides för Java. Aspose.Slides är ett kraftfullt Java-bibliotek som låter utvecklare skapa, manipulera och konvertera PowerPoint-presentationer programmatiskt utan att behöva Microsoft Office. Att lägga till kolumner i textrutor kan avsevärt förbättra läsbarheten och organiseringen av innehåll i bilder, vilket gör dina presentationer mer engagerande och professionella.
## Förutsättningar
Innan vi börjar, se till att du har följande förutsättningar:
- Grundläggande kunskaper i Java-programmering.
- JDK (Java Development Kit) installerat på din maskin.
-  Aspose.Slides för Java-bibliotek. Du kan ladda ner den från[här](https://releases.aspose.com/slides/java/).

## Importera paket
För att komma igång måste du importera de nödvändiga Aspose.Slides-klasserna till din Java-fil. Så här kan du göra det:
```java
import com.aspose.slides.*;
```
## Steg 1: Initiera presentation och bild
Skapa först en ny PowerPoint-presentation och initiera den första bilden.
```java
// Sökvägen till dokumentkatalogen.
String dataDir = "Your Document Directory";
Presentation presentation = new Presentation();
try {
    // Hämta den första bilden av presentationen
    ISlide slide = presentation.getSlides().get_Item(0);
```
## Steg 2: Lägg till AutoShape (rektangel)
Lägg sedan till en AutoShape av rektangeltyp på bilden.
```java
    // Lägg till en AutoShape av typen rektangel
    IAutoShape aShape = slide.getShapes().addAutoShape(ShapeType.Rectangle, 100, 100, 300, 300);
```
## Steg 3: Lägg till TextFrame till rektangeln
Lägg nu till en textram till rektangelns autoform och ställ in dess initiala text.
```java
    // Lägg till TextFrame till rektangeln
    aShape.addTextFrame("All these columns are limited to be within a single text container -- " +
            "you can add or delete text and the new or remaining text automatically adjusts " +
            "itself to flow within the container. You cannot have text flow from one container " +
            "to other though -- we told you PowerPoint's column options for text are limited!");
```
## Steg 4: Ställ in antal kolumner
Ange antalet kolumner inom TextFrame.
```java
    // Få textformat för TextFrame
    ITextFrameFormat format = aShape.getTextFrame().getTextFrameFormat();
    // Ange antal kolumner i TextFrame
    format.setColumnCount(3);
```
## Steg 5: Justera kolumnavståndet
Ställ in avståndet mellan kolumner i TextFrame.
```java
    // Ange avstånd mellan kolumner
    format.setColumnSpacing(10);
```
## Steg 6: Spara presentationen
Slutligen, spara den ändrade presentationen i en PowerPoint-fil.
```java
    // Spara skapad presentation
    presentation.save(dataDir + "ColumnCount.pptx", SaveFormat.Pptx);
} finally {
    if (presentation != null) presentation.dispose();
}
```

## Slutsats
Genom att följa dessa steg kan du enkelt lägga till kolumner i textrutor i PowerPoint-presentationer med Aspose.Slides för Java. Den här funktionen låter dig förbättra strukturen och läsbarheten för dina bilder, vilket gör dem mer visuellt tilltalande och professionella.
## FAQ's
### Kan jag lägga till fler än tre kolumner i en textruta?
Ja, du kan ange valfritt antal kolumner programmatiskt med Aspose.Slides.
### Är Aspose.Slides kompatibel med Java 11?
Ja, Aspose.Slides stöder Java 11 och högre versioner.
### Hur kan jag få en tillfällig licens för Aspose.Slides?
 Du kan få en tillfällig licens[här](https://purchase.aspose.com/temporary-license/).
### Kräver Aspose.Slides Microsoft Office installerat?
Nej, Aspose.Slides kräver inte att Microsoft Office är installerat på maskinen.
### Var kan jag hitta mer dokumentation om Aspose.Slides för Java?
 Detaljerad dokumentation finns tillgänglig[här](https://reference.aspose.com/slides/java/).