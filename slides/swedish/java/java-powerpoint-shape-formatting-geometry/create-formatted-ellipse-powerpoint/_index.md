---
title: Skapa formaterad ellips i PowerPoint
linktitle: Skapa formaterad ellips i PowerPoint
second_title: Aspose.Slides Java PowerPoint Processing API
description: Lär dig hur du skapar en formaterad ellips i PowerPoint med Aspose.Slides för Java med vår detaljerade steg-för-steg-guide.
weight: 17
url: /sv/java/java-powerpoint-shape-formatting-geometry/create-formatted-ellipse-powerpoint/
---

{< blocks/products/pf/main-wrap-class >}
{< blocks/products/pf/main-container >}
{< blocks/products/pf/tutorial-page-section >}

## Introduktion
Välkommen till denna omfattande handledning om att skapa en formaterad ellips i PowerPoint med Aspose.Slides för Java. Aspose.Slides är ett kraftfullt bibliotek som låter utvecklare manipulera PowerPoint-filer programmatiskt. Oavsett om du automatiserar bildgenerering eller förbättrar presentationer med anpassade former, kommer den här guiden att leda dig genom varje steg, vilket säkerställer att du enkelt kan lägga till en perfekt formaterad ellips till dina bilder. Låt oss dyka in och se hur vi kan uppnå detta!
## Förutsättningar
Innan vi börjar, se till att du har följande förutsättningar:
1. Java Development Kit (JDK): Se till att du har JDK 1.6 eller högre installerat.
2.  Aspose.Slides för Java: Ladda ner den senaste versionen från[Aspose.Slides för Java](https://releases.aspose.com/slides/java/).
3. Integrated Development Environment (IDE): Använd en IDE som IntelliJ IDEA eller Eclipse.
4. Grundläggande kunskaper i Java: Kännedom om Java-programmering krävs.
## Importera paket
För att börja använda Aspose.Slides måste du importera de nödvändiga paketen. Så här kan du göra det:
```java
import com.aspose.slides.*;

import java.awt.*;
import java.io.File;
```
## Steg 1: Konfigurera din projektkatalog
Först behöver du en katalog för att lagra dina PowerPoint-filer.
### Skapa katalog
```java
// Sökvägen till dokumentkatalogen.
String dataDir = "Your Document Directory";
// Skapa katalog om den inte redan finns.
boolean IsExists = new File(dataDir).exists();
if (!IsExists)
	new File(dataDir).mkdirs();
```
 Se till att du byter ut`"Your Document Directory"` med den faktiska sökvägen där du vill lagra dina filer.
## Steg 2: Initiera presentationen
Instantiera nu klassen Presentation, som representerar PowerPoint-filen.
```java
// Instantiate Presentation-klass som representerar PPTX
Presentation pres = new Presentation();
```
## Steg 3: Skaffa den första bilden
Hämta sedan den första bilden från presentationen där du lägger till ellipsen.
```java
// Få den första bilden
ISlide sld = pres.getSlides().get_Item(0);
```
## Steg 4: Lägg till en Ellipsform
Lägg till en automatisk form av ellipstyp till bilden.
```java
// Lägg till autoform av ellipstyp
IShape shp = sld.getShapes().addAutoShape(ShapeType.Ellipse, 50, 150, 150, 50);
```
 Här,`50, 150, 150, 50` är ellipsens koordinater och storlek (x-position, y-position, bredd, höjd).
## Steg 5: Använd formatering på Ellipsen
Applicera nu lite formatering på ellipsen. Vi ställer in en enfärgad fyllningsfärg och en linjefärg.
### Ställ in fyllningsfärg
```java
// Använd lite formatering på ellipsform
shp.getFillFormat().setFillType(FillType.Solid);
shp.getFillFormat().getSolidFillColor().setColor(new Color(PresetColor.Chocolate));
```
### Ställ in linjefärg och bredd
```java
// Tillämpa lite formatering på Ellipselinjen
shp.getLineFormat().getFillFormat().setFillType(FillType.Solid);
shp.getLineFormat().getFillFormat().getSolidFillColor().setColor(Color.BLACK);
shp.getLineFormat().setWidth(5);
```
## Steg 6: Spara presentationen
Slutligen sparar du presentationen i din angivna katalog.
```java
// Skriv PPTX-filen till disken
pres.save(dataDir + "EllipseShp2_out.pptx", SaveFormat.Pptx);
```
## Steg 7: Kassera presentationsobjektet
Kassera presentationsobjektet för att frigöra resurser.
```java
finally {
    if (pres != null) pres.dispose();
}
```
## Slutsats
Grattis! Du har framgångsrikt skapat en formaterad ellips i en PowerPoint-presentation med Aspose.Slides för Java. Denna handledning ledde dig genom att ställa in ditt projekt, lägga till en ellips, tillämpa formatering och spara din presentation. Med dessa färdigheter kan du nu förbättra dina PowerPoint-bilder programmatiskt, vilket gör dina presentationer mer dynamiska och visuellt tilltalande.
## FAQ's
### Vad är Aspose.Slides för Java?
Aspose.Slides för Java är ett kraftfullt bibliotek som låter utvecklare skapa, ändra och hantera PowerPoint-presentationer programmatiskt.
### Kan jag använda Aspose.Slides för Java med vilken IDE som helst?
Ja, du kan använda Aspose.Slides för Java med vilken Java IDE som helst som IntelliJ IDEA, Eclipse eller NetBeans.
### Behöver jag en licens för Aspose.Slides?
Ja, Aspose.Slides är en kommersiell produkt och du behöver en licens för full funktionalitet. Du kan få en tillfällig licens[här](https://purchase.aspose.com/temporary-license/).
### Var kan jag hitta mer dokumentation om Aspose.Slides för Java?
 Du kan hitta detaljerad dokumentation på Aspose.Slides för Java[dokumentationssida](https://reference.aspose.com/slides/java/).
### Finns det stöd tillgängligt för Aspose.Slides?
 Ja, Aspose erbjuder support genom deras[forum](https://forum.aspose.com/c/slides/11).
{< /blocks/products/pf/tutorial-page-section >}

{< /blocks/products/pf/main-container >}
{< /blocks/products/pf/main-wrap-class >}

{< blocks/products/products-backtop-button >}
