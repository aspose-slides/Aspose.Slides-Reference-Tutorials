---
title: Skapa formminiatyr i PowerPoint
linktitle: Skapa formminiatyr i PowerPoint
second_title: Aspose.Slides Java PowerPoint Processing API
description: Lär dig hur du skapar miniatyrer av form i PowerPoint-presentationer med Aspose.Slides för Java. Steg-för-steg guide tillhandahålls.
weight: 14
url: /sv/java/java-powerpoint-shape-thumbnail-creation/create-shape-thumbnail-powerpoint/
---

{< blocks/products/pf/main-wrap-class >}
{< blocks/products/pf/main-container >}
{< blocks/products/pf/tutorial-page-section >}

## Introduktion
den här självstudien kommer vi att fördjupa oss i att skapa miniatyrbilder i PowerPoint-presentationer med Aspose.Slides för Java. Aspose.Slides är ett kraftfullt bibliotek som gör det möjligt för utvecklare att arbeta med PowerPoint-filer programmatiskt, vilket möjliggör automatisering av olika uppgifter, inklusive generering av formminiatyrer.
## Förutsättningar
Innan vi börjar, se till att du har följande förutsättningar:
- Grundläggande kunskaper i Java-programmering.
- Java Development Kit (JDK) installerat på ditt system.
-  Aspose.Slides för Java-biblioteket laddas ner och ställs in i ditt projekt. Du kan ladda ner den från[här](https://releases.aspose.com/slides/java/).

## Importera paket
Först måste du importera de nödvändiga paketen i din Java-kod för att använda funktionerna i Aspose.Slides. Inkludera följande importsatser i början av din Java-fil:
```java
import com.aspose.slides.Presentation;

import javax.imageio.ImageIO;
import java.awt.image.BufferedImage;
import java.io.File;
import java.io.IOException;
```
## Steg 1: Definiera dokumentkatalog
```java
String dataDir = "Your Document Directory";
```
 Byta ut`"Your Document Directory"` med sökvägen till katalogen som innehåller din PowerPoint-fil.
## Steg 2: Instantera presentationsobjekt
```java
Presentation presentation = new Presentation(dataDir + "HelloWorld.pptx");
```
 Skapa en ny instans av`Presentation` klass och skickar sökvägen till din PowerPoint-fil som en parameter.
## Steg 3: Skapa Shape-miniatyrbild
```java
BufferedImage bitmap = presentation.getSlides().get_Item(0).getShapes().get_Item(0).getThumbnail();
```
Hämta miniatyren av den önskade formen från den första bilden i presentationen.
## Steg 4: Spara miniatyrbild
```java
ImageIO.write(bitmap, ".png", new File(dataDir + "Shape_thumbnail_out.png"));
```
Spara den genererade miniatyrbilden på disken i PNG-format med det angivna filnamnet.

## Slutsats
Sammanfattningsvis visade den här handledningen hur man skapar miniatyrbilder i PowerPoint-presentationer med Aspose.Slides för Java. Genom att följa den steg-för-steg-guiden och använda de medföljande kodavsnitten kan du effektivt generera formminiatyrer programmatiskt.

## FAQ's
### Kan jag skapa miniatyrer för former på valfri bild i presentationen?
Ja, du kan modifiera koden för att målformera på vilken bild som helst genom att justera bildindexet därefter.
### Stöder Aspose.Slides andra bildformat för att spara miniatyrer?
Ja, förutom PNG stöder Aspose.Slides att spara miniatyrer i olika bildformat som JPEG, GIF och BMP.
### Är Aspose.Slides lämpliga för kommersiellt bruk?
 Ja, Aspose.Slides erbjuder kommersiella licenser för företag och organisationer. Du kan köpa en licens från[här](https://purchase.aspose.com/buy).
### Kan jag prova Aspose.Slides innan jag köper?
 Absolut! Du kan ladda ner en gratis testversion av Aspose.Slides från[här](https://releases.aspose.com/) för att utvärdera dess egenskaper och möjligheter.
### Var kan jag hitta support för Aspose.Slides?
 Om du har några frågor eller behöver hjälp med Aspose.Slides kan du besöka[Aspose.Slides forum](https://forum.aspose.com/c/slides/11) för support.
{< /blocks/products/pf/tutorial-page-section >}

{< /blocks/products/pf/main-container >}
{< /blocks/products/pf/main-wrap-class >}

{< blocks/products/products-backtop-button >}
