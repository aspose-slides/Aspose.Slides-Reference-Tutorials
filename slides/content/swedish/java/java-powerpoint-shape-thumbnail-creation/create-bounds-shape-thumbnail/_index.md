---
title: Skapa miniatyrbild av gränser
linktitle: Skapa miniatyrbild av gränser
second_title: Aspose.Slides Java PowerPoint Processing API
description: Lär dig hur du skapar miniatyrbilder med gränser med Aspose.Slides för Java. Denna steg-för-steg handledning guidar dig genom processen.
type: docs
weight: 10
url: /sv/java/java-powerpoint-shape-thumbnail-creation/create-bounds-shape-thumbnail/
---
## Introduktion
Aspose.Slides för Java är ett kraftfullt bibliotek som låter Java-utvecklare skapa, manipulera och konvertera PowerPoint-presentationer programmatiskt. I den här handledningen kommer vi att lära oss hur man skapar en miniatyrbild av en form med gränser med Aspose.Slides för Java.
## Förutsättningar
Innan du börjar, se till att du har följande:
1. Java Development Kit (JDK) installerat på ditt system.
2.  Aspose.Slides för Java-biblioteket har laddats ner och lagts till i ditt projekt. Du kan ladda ner den från[här](https://releases.aspose.com/slides/java/).

## Importera paket
Se till att du importerar de nödvändiga paketen i din Java-kod:
```java
import com.aspose.slides.Presentation;
import com.aspose.slides.ShapeThumbnailBounds;

import javax.imageio.ImageIO;
import java.awt.image.BufferedImage;
import java.io.File;
import java.io.IOException;
```
## Steg 1: Konfigurera ditt projekt
Skapa ett nytt Java-projekt i din föredragna IDE och lägg till Aspose.Slides for Java-biblioteket till ditt projekts beroenden.
## Steg 2: Instantiera ett presentationsobjekt
 Instantiera en`Presentation` objekt genom att ange sökvägen till din PowerPoint-presentationsfil.
```java
String dataDir = "Your Document Directory";
Presentation presentation = new Presentation(dataDir + "HelloWorld.pptx");
```
## Steg 3: Skapa miniatyrbild av gränser
Låt oss nu skapa en miniatyrbild av en form med gränser från presentationen.
```java
try {
    BufferedImage bitmap = presentation.getSlides().get_Item(0).getShapes().get_Item(0).getThumbnail(ShapeThumbnailBounds.Appearance, 1, 1);
    ImageIO.write(bitmap, ".png", new File(dataDir + "Shape_thumbnail_Bound_Shape_out.png"));
} finally {
    if (presentation != null) presentation.dispose();
}
```

## Slutsats
I den här handledningen har vi lärt oss hur man skapar en miniatyrbild av en form med gränser med Aspose.Slides för Java. Genom att följa dessa steg kan du enkelt generera miniatyrbilder av former i dina PowerPoint-presentationer programmatiskt.
## FAQ's
### Kan jag skapa miniatyrer för specifika former i en bild?
Ja, du kan komma åt enskilda former i en bild och skapa miniatyrer för dem med Aspose.Slides för Java.
### Är Aspose.Slides för Java kompatibel med alla versioner av PowerPoint-filer?
Aspose.Slides för Java stöder olika PowerPoint-filformat, inklusive PPT, PPTX, PPS, PPSX och mer.
### Kan jag anpassa utseendet på de genererade miniatyrbilderna?
Ja, du kan justera egenskaperna för miniatyrbilderna, såsom storlek och kvalitet, enligt dina krav.
### Stöder Aspose.Slides för Java andra funktioner förutom generering av miniatyrbilder?
Ja, Aspose.Slides för Java tillhandahåller omfattande funktioner för att arbeta med PowerPoint-presentationer, inklusive bildmanipulering, textextraktion och diagramgenerering.
### Finns det en testversion tillgänglig för Aspose.Slides för Java?
 Ja, du kan ladda ner en gratis testversion från[här](https://releases.aspose.com/).