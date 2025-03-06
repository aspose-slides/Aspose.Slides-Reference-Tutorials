---
title: Skapa skalningsfaktorminiatyr
linktitle: Skapa skalningsfaktorminiatyr
second_title: Aspose.Slides Java PowerPoint Processing API
description: Lär dig hur du skapar skalningsfaktorminiatyrer i Java med Aspose.Slides för Java. Lätt att följa guide med steg-för-steg instruktioner.
weight: 12
url: /sv/java/java-powerpoint-shape-thumbnail-creation/create-scaling-factor-thumbnail/
---

{< blocks/products/pf/main-wrap-class >}
{< blocks/products/pf/main-container >}
{< blocks/products/pf/tutorial-page-section >}

## Introduktion
I den här handledningen kommer vi att guida dig genom processen att skapa en skalningsfaktorminiatyr med Aspose.Slides för Java. Följ dessa steg-för-steg-instruktioner för att uppnå önskat resultat.
## Förutsättningar
Innan du börjar, se till att du har följande förutsättningar:
- Java Development Kit (JDK) installerat på ditt system.
- Aspose.Slides för Java-biblioteket laddas ner och ställs in i ditt Java-projekt.
- Grundläggande förståelse för programmeringsspråket Java.

## Importera paket
Importera först de nödvändiga paketen som krävs för att arbeta med Aspose.Slides i din Java-kod. 
```java
import com.aspose.slides.Presentation;
import com.aspose.slides.ShapeThumbnailBounds;

import javax.imageio.ImageIO;
import java.awt.image.BufferedImage;
import java.io.File;
import java.io.IOException;
```

Låt oss nu dela upp exemplet i flera steg:
## Steg 1: Ställ in dokumentkatalogen
Definiera sökvägen till din dokumentkatalog där PowerPoint-presentationsfilen finns.
```java
String dataDir = "Your Document Directory";
```
 Byta ut`"Your Document Directory"` med sökvägen till din faktiska dokumentkatalog.
## Steg 2: Instantiera presentationsobjektet
Skapa en instans av klassen Presentation för att representera PowerPoint-presentationsfilen.
```java
Presentation p = new Presentation(dataDir + "HelloWorld.pptx");
```
 Se till att byta ut`"HelloWorld.pptx"` med namnet på din PowerPoint-presentationsfil.
## Steg 3: Skapa fullskalig bild
Skapa en fullskalig bild av den önskade bilden från presentationen.
```java
BufferedImage bitmap = p.getSlides().get_Item(0).getShapes().get_Item(0).getThumbnail(ShapeThumbnailBounds.Shape, 1, 1);
```
Den här koden hämtar miniatyren av den första formen på den första bilden i presentationen.
## Steg 4: Spara bilden
Spara den genererade bilden på disken i PNG-format.
```java
ImageIO.write(bitmap, ".png", new File(dataDir + "Scaling Factor Thumbnail_out.png"));
```
 Se till att byta ut`"Scaling Factor Thumbnail_out.png"` med önskat utdatafilnamn.

## Slutsats
Sammanfattningsvis har du framgångsrikt skapat en skalningsfaktorminiatyr med Aspose.Slides för Java. Genom att följa de medföljande stegen kan du enkelt integrera denna funktion i dina Java-applikationer.
## FAQ's
### Kan jag använda Aspose.Slides för Java med vilken Java IDE som helst?
Ja, Aspose.Slides för Java kan användas med alla Java Integrated Development Environment (IDE) som Eclipse, IntelliJ IDEA eller NetBeans.
### Finns det en gratis testversion tillgänglig för Aspose.Slides för Java?
 Ja, du kan använda en gratis testversion av Aspose.Slides för Java genom att besöka[hemsida](https://releases.aspose.com/).
### Var kan jag hitta support för Aspose.Slides för Java?
 Du kan hitta stöd för Aspose.Slides för Java på[Aspose.Slides forum](https://forum.aspose.com/c/slides/11).
### Hur kan jag köpa Aspose.Slides för Java?
 Du kan köpa Aspose.Slides för Java från[köpsidan](https://purchase.aspose.com/buy).
### Behöver jag en tillfällig licens för att använda Aspose.Slides för Java?
 Ja, du kan få en tillfällig licens från[sida för tillfällig licens](https://purchase.aspose.com/temporary-license/).
{< /blocks/products/pf/tutorial-page-section >}

{< /blocks/products/pf/main-container >}
{< /blocks/products/pf/main-wrap-class >}

{< blocks/products/products-backtop-button >}
