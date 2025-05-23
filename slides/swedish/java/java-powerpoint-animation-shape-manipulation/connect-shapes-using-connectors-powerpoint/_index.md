---
"description": "Lär dig hur du kopplar ihop former med hjälp av kopplingar i PowerPoint-presentationer med Aspose.Slides för Java. Steg-för-steg-handledning för nybörjare."
"linktitle": "Koppla ihop former med hjälp av kopplingar i PowerPoint"
"second_title": "Aspose.Slides Java PowerPoint-bearbetnings-API"
"title": "Koppla ihop former med hjälp av kopplingar i PowerPoint"
"url": "/sv/java/java-powerpoint-animation-shape-manipulation/connect-shapes-using-connectors-powerpoint/"
"weight": 18
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Koppla ihop former med hjälp av kopplingar i PowerPoint

## Introduktion
I den här handledningen ska vi utforska hur man kopplar ihop former med hjälp av kopplingar i PowerPoint-presentationer med hjälp av Aspose.Slides för Java. Följ dessa steg-för-steg-instruktioner för att effektivt koppla ihop former och skapa visuellt tilltalande bilder.
## Förkunskapskrav
Innan vi börjar, se till att du har följande förutsättningar:
- Grundläggande kunskaper i programmeringsspråket Java.
- Installerade Java Development Kit (JDK) på ditt system.
- Laddade ner och installerade Aspose.Slides för Java. Om du inte har installerat det än kan du ladda ner det från [här](https://releases.aspose.com/slides/java/).
- En kodredigerare som Eclipse eller IntelliJ IDEA.

## Importera paket
Importera först de paket som behövs för att arbeta med Aspose.Slides i ditt Java-projekt.
```java
import com.aspose.slides.*;

```
## Steg 1: Instansiera presentationsklassen
Instansiera `Presentation` klass, som representerar PPTX-filen du arbetar med.
```java
// Sökvägen till dokumentkatalogen.                    
String dataDir = "Your Document Directory";
Presentation input = new Presentation();
```
## Steg 2: Åtkomst till formsamlingen
Få åtkomst till formsamlingen för den valda bilden där du vill lägga till former och kopplingar.
```java
IShapeCollection shapes = input.getSlides().get_Item(0).getShapes();
```
## Steg 3: Lägg till former
Lägg till de önskade formerna på bilden. I det här exemplet lägger vi till en ellips och en rektangel.
```java
// Lägg till autoform-ellips
IAutoShape ellipse = shapes.addAutoShape(ShapeType.Ellipse, 0, 100, 100, 100);
// Lägg till autoformad rektangel
IAutoShape rectangle = shapes.addAutoShape(ShapeType.Rectangle, 100, 300, 100, 100);
```
## Steg 4: Lägg till koppling
Lägg till en kopplingsform i bildformsamlingen.
```java
IConnector connector = shapes.addConnector(ShapeType.BentConnector2, 0, 0, 10, 10);
```
## Steg 5: Koppla ihop former med kopplingar
Anslut formerna till kopplingen.
```java
connector.setStartShapeConnectedTo(ellipse);
connector.setEndShapeConnectedTo(rectangle);
```
## Steg 6: Omdirigera kontakten
Anropa omdirigering för att ställa in den automatiska kortaste vägen mellan former.
```java
connector.reroute();
```
## Steg 7: Spara presentationen
Spara presentationen efter att du har kopplat ihop former med hjälp av kopplingar.
```java
input.save(dataDir + "Connecting shapes using connectors_out.pptx", SaveFormat.Pptx);
```
Slutligen, glöm inte att göra dig av med Presentation-objektet.
```java
if (input != null) input.dispose();
```
Nu har du framgångsrikt kopplat ihop former med hjälp av kopplingar i PowerPoint med Aspose.Slides för Java.

## Slutsats
I den här handledningen har vi lärt oss hur man kopplar ihop former med hjälp av kopplingar i PowerPoint-presentationer med Aspose.Slides för Java. Genom att följa dessa enkla steg kan du förbättra dina presentationer med visuellt tilltalande diagram och flödesscheman.
## Vanliga frågor
### Kan jag anpassa utseendet på kopplingar i Aspose.Slides för Java?
Ja, du kan anpassa olika egenskaper för kopplingar, till exempel färg, linjestil och tjocklek, så att de passar dina presentationsbehov.
### Är Aspose.Slides för Java kompatibelt med alla versioner av PowerPoint?
Aspose.Slides för Java stöder olika PowerPoint-format, inklusive PPTX, PPT och ODP.
### Kan jag koppla ihop fler än två former med en enda koppling?
Ja, du kan koppla samman flera former med hjälp av komplexa kopplingar som tillhandahålls av Aspose.Slides för Java.
### Har Aspose.Slides för Java stöd för att lägga till text i former?
Absolut, du kan enkelt lägga till text i former och kopplingar programmatiskt med hjälp av Aspose.Slides för Java.
### Finns det ett communityforum eller en supportkanal tillgänglig för Aspose.Slides för Java-användare?
Ja, du kan hitta användbara resurser, ställa frågor och interagera med andra användare på Aspose.Slides-forumet. [här](https://forum.aspose.com/c/slides/11).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}