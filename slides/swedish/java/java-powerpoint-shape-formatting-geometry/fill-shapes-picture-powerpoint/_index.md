---
"description": "Lär dig hur du fyller former med bilder i PowerPoint-presentationer med Aspose.Slides för Java. Förbättra den visuella attraktionskraften utan ansträngning."
"linktitle": "Fyll former med bild i PowerPoint"
"second_title": "Aspose.Slides Java PowerPoint-bearbetnings-API"
"title": "Fyll former med bild i PowerPoint"
"url": "/sv/java/java-powerpoint-shape-formatting-geometry/fill-shapes-picture-powerpoint/"
"weight": 12
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Fyll former med bild i PowerPoint

## Introduktion
PowerPoint-presentationer kräver ofta visuella element som former fyllda med bilder för att förbättra deras attraktionskraft och förmedla information effektivt. Aspose.Slides för Java tillhandahåller en kraftfull uppsättning verktyg för att utföra denna uppgift sömlöst. I den här handledningen lär vi oss hur man fyller former med bilder med hjälp av Aspose.Slides för Java steg för steg.
## Förkunskapskrav
Innan vi börjar, se till att du har följande:
1. Java Development Kit (JDK) installerat på ditt system.
2. Aspose.Slides för Java-biblioteket har laddats ner. Du kan hämta det från [här](https://releases.aspose.com/slides/java/).
3. Grundläggande kunskaper i Java-programmering.
## Importera paket
Importera nödvändiga paket i ditt Java-projekt:
```java
import com.aspose.slides.*;

import javax.imageio.ImageIO;
import java.awt.image.BufferedImage;
import java.io.File;
import java.io.IOException;
```
## Steg 1: Konfigurera projektkatalogen
```java
String dataDir = "Your Document Directory";
boolean isExists = new File(dataDir).exists();
if (!isExists)
    new File(dataDir).mkdirs();
```
Se till att byta ut `"Your Document Directory"` med sökvägen till din projektkatalog.
## Steg 2: Skapa en presentation
```java
Presentation pres = new Presentation();
```
Instansiera `Presentation` klassen för att skapa en ny PowerPoint-presentation.
## Steg 3: Lägg till en bild och form
```java
ISlide sld = pres.getSlides().get_Item(0);
IShape shp = sld.getShapes().addAutoShape(ShapeType.Rectangle, 50, 150, 75, 150);
```
Lägg till en bild i presentationen och skapa en rektangelform på den.
## Steg 4: Ställ in fyllningstyp till Bild
```java
shp.getFillFormat().setFillType(FillType.Picture);
```
Ställ in fyllningstypen för formen till bild.
## Steg 5: Ställ in bildfyllningsläge
```java
shp.getFillFormat().getPictureFillFormat().setPictureFillMode(PictureFillMode.Tile);
```
Ställ in bildfyllningsläge för formen.
## Steg 6: Ställ in bild
```java
BufferedImage img = ImageIO.read(new File(dataDir + "Tulips.jpg"));
IPPImage imgx = pres.getImages().addImage(img);
shp.getFillFormat().getPictureFillFormat().getPicture().setImage(imgx);
```
Ladda bilden och ange den som fyllning för formen.
## Steg 7: Spara presentationen
```java
pres.save(dataDir + "RectShpPic_out.pptx", SaveFormat.Pptx);
```
Spara den ändrade presentationen till en fil.

## Slutsats
Med Aspose.Slides för Java blir det enkelt att fylla former med bilder i PowerPoint-presentationer. Genom att följa stegen som beskrivs i den här handledningen kan du enkelt förbättra dina presentationer med visuellt tilltalande element.

## Vanliga frågor
### Kan jag fylla olika former med bilder med hjälp av Aspose.Slides för Java?
Ja, Aspose.Slides för Java stöder att fylla olika former med bilder, vilket ger flexibilitet i designen.
### Är Aspose.Slides för Java kompatibelt med alla versioner av PowerPoint?
Aspose.Slides för Java genererar presentationer som är kompatibla med PowerPoint 97 och senare, vilket säkerställer bred kompatibilitet.
### Hur kan jag ändra storleken på bilden inom formen?
Du kan ändra storlek på bilden inom formen genom att justera formens dimensioner eller skala bilden därefter innan du ställer in den som fyllning.
### Finns det några begränsningar för de bildformat som stöds för att fylla former?
Aspose.Slides för Java stöder ett brett utbud av bildformat, inklusive JPEG, PNG, GIF, BMP och TIFF, bland andra.
### Kan jag tillämpa effekter på de fyllda formerna?
Ja, Aspose.Slides för Java tillhandahåller omfattande API:er för att tillämpa olika effekter, såsom skuggor, reflektioner och 3D-rotationer, på fyllda former.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}