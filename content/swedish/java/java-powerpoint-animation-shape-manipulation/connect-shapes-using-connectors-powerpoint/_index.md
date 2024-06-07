---
title: Anslut former med Connectors i PowerPoint
linktitle: Anslut former med Connectors i PowerPoint
second_title: Aspose.Slides Java PowerPoint Processing API
description: Lär dig hur du kopplar samman former med hjälp av kopplingar i PowerPoint-presentationer med Aspose.Slides för Java. Steg-för-steg handledning för nybörjare.
type: docs
weight: 18
url: /sv/java/java-powerpoint-animation-shape-manipulation/connect-shapes-using-connectors-powerpoint/
---
## Introduktion
I den här självstudien kommer vi att utforska hur man kopplar samman former med hjälp av kopplingar i PowerPoint-presentationer med hjälp av Aspose.Slides för Java. Följ dessa steg-för-steg-instruktioner för att effektivt ansluta former och skapa visuellt tilltalande bilder.
## Förutsättningar
Innan vi börjar, se till att du har följande förutsättningar:
- Grundläggande kunskaper i programmeringsspråket Java.
- Installerat Java Development Kit (JDK) på ditt system.
-  Laddat ner och ställt in Aspose.Slides för Java. Om du inte har installerat det ännu kan du ladda ner det från[här](https://releases.aspose.com/slides/java/).
- En kodredigerare som Eclipse eller IntelliJ IDEA.

## Importera paket
Importera först de nödvändiga paketen för att arbeta med Aspose.Slides i ditt Java-projekt.
```java
import com.aspose.slides.*;
import com.aspose.slides.examples.RunExamples;
```
## Steg 1: Instantera presentationsklass
 Instantiera`Presentation`class, som representerar PPTX-filen du arbetar med.
```java
// Sökvägen till dokumentkatalogen.
String dataDir = "Your Document Directory";
Presentation input = new Presentation();
```
## Steg 2: Få tillgång till Shapes Collection
Öppna formsamlingen för den valda bilden där du vill lägga till former och kopplingar.
```java
IShapeCollection shapes = input.getSlides().get_Item(0).getShapes();
```
## Steg 3: Lägg till former
Lägg till de önskade formerna på bilden. I det här exemplet lägger vi till en ellips och en rektangel.
```java
// Lägg till autoshape Ellipse
IAutoShape ellipse = shapes.addAutoShape(ShapeType.Ellipse, 0, 100, 100, 100);
// Lägg till autoform rektangel
IAutoShape rectangle = shapes.addAutoShape(ShapeType.Rectangle, 100, 300, 100, 100);
```
## Steg 4: Lägg till anslutning
Lägg till en kopplingsform till samlingen av diabildsform.
```java
IConnector connector = shapes.addConnector(ShapeType.BentConnector2, 0, 0, 10, 10);
```
## Steg 5: Anslut former till kopplingar
Anslut formerna till kontakten.
```java
connector.setStartShapeConnectedTo(ellipse);
connector.setEndShapeConnectedTo(rectangle);
```
## Steg 6: Omdirigera Connector
Ring omdirigering för att ställa in den automatiska kortaste vägen mellan former.
```java
connector.reroute();
```
## Steg 7: Spara presentationen
Spara presentationen efter att ha kopplat samman former med kopplingar.
```java
input.save(dataDir + "Connecting shapes using connectors_out.pptx", SaveFormat.Pptx);
```
Slutligen, glöm inte att kassera Presentationsobjektet.
```java
if (input != null) input.dispose();
```
Nu har du framgångsrikt kopplat former med hjälp av kopplingar i PowerPoint med Aspose.Slides för Java.

## Slutsats
den här handledningen har vi lärt oss hur man kopplar samman former med hjälp av kopplingar i PowerPoint-presentationer med Aspose.Slides för Java. Genom att följa dessa enkla steg kan du förbättra dina presentationer med visuellt tilltalande diagram och flödesscheman.
## FAQ's
### Kan jag anpassa utseendet på kontakter i Aspose.Slides för Java?
Ja, du kan anpassa olika egenskaper för kopplingar som färg, linjestil och tjocklek för att passa dina presentationsbehov.
### Är Aspose.Slides för Java kompatibel med alla versioner av PowerPoint?
Aspose.Slides för Java stöder olika PowerPoint-format, inklusive PPTX, PPT och ODP.
### Kan jag ansluta fler än två former med en enda kontakt?
Ja, du kan ansluta flera former med hjälp av komplexa kontakter från Aspose.Slides för Java.
### Har Aspose.Slides för Java stöd för att lägga till text i former?
Absolut, du kan enkelt lägga till text till former och kopplingar programmatiskt med Aspose.Slides för Java.
### Finns det ett communityforum eller supportkanal tillgängligt för Aspose.Slides för Java-användare?
 Ja, du kan hitta användbara resurser, ställa frågor och interagera med andra användare på Aspose.Slides-forumet[här](https://forum.aspose.com/c/slides/11).