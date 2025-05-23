---
"description": "Lär dig hur du kopplar ihop former i PowerPoint med Aspose.Slides för Java. Automatisera dina presentationer utan ansträngning."
"linktitle": "Koppla samman former med hjälp av kopplingsplatser i PowerPoint"
"second_title": "Aspose.Slides Java PowerPoint-bearbetnings-API"
"title": "Koppla samman former med hjälp av kopplingsplatser i PowerPoint"
"url": "/sv/java/java-powerpoint-animation-shape-manipulation/connect-shapes-using-connection-sites-powerpoint/"
"weight": 19
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Koppla samman former med hjälp av kopplingsplatser i PowerPoint

## Introduktion
I den här handledningen ska vi utforska hur man kopplar ihop former med hjälp av kopplingssidor i PowerPoint med hjälp av Aspose.Slides för Java. Detta kraftfulla bibliotek låter oss programmatiskt manipulera PowerPoint-presentationer, vilket gör uppgifter som att koppla ihop former sömlösa och effektiva.
## Förkunskapskrav
Innan vi börjar, se till att du har följande:
1. Java Development Kit (JDK): Se till att du har Java installerat på ditt system. Du kan ladda ner och installera det från [webbplats](https://www.oracle.com/java/technologies/javase-jdk15-downloads.html).
2. Aspose.Slides för Java: Ladda ner och installera Aspose.Slides för Java från [nedladdningssida](https://releases.aspose.com/slides/java/).
3. Integrerad utvecklingsmiljö (IDE): Välj en IDE för Java-utveckling, till exempel IntelliJ IDEA, Eclipse eller NetBeans.

## Importera paket
För att komma igång, importera de nödvändiga paketen till ditt Java-projekt:
```java
import com.aspose.slides.*;

```
## Steg 1: Åtkomst till formsamlingen
Få åtkomst till formsamlingen för den valda bilden:
```java
// Sökvägen till dokumentkatalogen.                    
String dataDir = "Your Document Directory";
// Instansiera Presentation-klassen som representerar PPTX-filen
Presentation presentation = new Presentation();
IShapeCollection shapes = presentation.getSlides().get_Item(0).getShapes();
```
## Steg 2: Lägga till kontaktform
Lägg till en kopplingsform i bildformsamlingen:
```java
IConnector connector = shapes.addConnector(ShapeType.BentConnector3, 0, 0, 10, 10);
```
## Steg 3: Lägga till autoformer
Lägg till automatiska former som ellips och rektangel:
```java
IAutoShape ellipse = shapes.addAutoShape(ShapeType.Ellipse, 0, 100, 100, 100);
IAutoShape rectangle = shapes.addAutoShape(ShapeType.Rectangle, 100, 200, 100, 100);
```
## Steg 4: Koppla ihop former med kopplingar
Koppla ihop formerna med kopplingen:
```java
connector.setStartShapeConnectedTo(ellipse);
connector.setEndShapeConnectedTo(rectangle);
```
## Steg 5: Ställa in anslutningsplatsindex
Ange önskat kopplingsplatsindex för formerna:
```java
long wantedIndex = 6;
if (ellipse.getConnectionSiteCount() > (wantedIndex & 0xFFFFFFFFL))
{
    connector.setStartShapeConnectionSiteIndex(wantedIndex);
}
```

## Slutsats
I den här handledningen har vi lärt oss hur man kopplar ihop former med hjälp av kopplingssidor i PowerPoint med hjälp av Aspose.Slides för Java. Med den här kunskapen kan du nu enkelt automatisera och anpassa dina PowerPoint-presentationer.
## Vanliga frågor
### Kan Aspose.Slides för Java användas för andra PowerPoint-manipulationsuppgifter?
Ja, Aspose.Slides för Java erbjuder ett brett utbud av funktioner för att skapa, redigera och konvertera PowerPoint-presentationer.
### Är Aspose.Slides för Java gratis att använda?
Aspose.Slides för Java är ett kommersiellt bibliotek, men du kan utforska dess funktioner med en gratis provperiod. Besök [här](https://releases.aspose.com/) att komma igång.
### Kan jag få support om jag stöter på problem när jag använder Aspose.Slides för Java?
Ja, du kan få support från Aspose communityforum [här](https://forum.aspose.com/c/slides/11).
### Finns tillfälliga licenser tillgängliga för Aspose.Slides för Java?
Ja, tillfälliga licenser finns tillgängliga för test- och utvärderingsändamål. Du kan skaffa en. [här](https://purchase.aspose.com/temporary-license/).
### Var kan jag köpa en licens för Aspose.Slides för Java?
Du kan köpa en licens från Asposes webbplats [här](https://purchase.aspose.com/buy).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}