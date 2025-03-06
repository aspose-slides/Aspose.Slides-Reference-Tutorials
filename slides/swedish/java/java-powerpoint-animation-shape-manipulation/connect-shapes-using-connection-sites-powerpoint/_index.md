---
title: Anslut former med Connection Sites i PowerPoint
linktitle: Anslut former med Connection Sites i PowerPoint
second_title: Aspose.Slides Java PowerPoint Processing API
description: Lär dig hur du kopplar samman former i PowerPoint med Aspose.Slides för Java. Automatisera dina presentationer utan ansträngning.
weight: 19
url: /sv/java/java-powerpoint-animation-shape-manipulation/connect-shapes-using-connection-sites-powerpoint/
---

{< blocks/products/pf/main-wrap-class >}
{< blocks/products/pf/main-container >}
{< blocks/products/pf/tutorial-page-section >}

## Introduktion
I den här självstudien kommer vi att utforska hur man kopplar samman former med anslutningsplatser i PowerPoint med Aspose.Slides för Java. Detta kraftfulla bibliotek låter oss manipulera PowerPoint-presentationer programmatiskt, vilket gör uppgifter som att ansluta former sömlösa och effektiva.
## Förutsättningar
Innan vi börjar, se till att du har följande:
1.  Java Development Kit (JDK): Se till att du har Java installerat på ditt system. Du kan ladda ner och installera den från[hemsida](https://www.oracle.com/java/technologies/javase-jdk15-downloads.html).
2.  Aspose.Slides för Java: Ladda ner och installera Aspose.Slides för Java från[nedladdningssida](https://releases.aspose.com/slides/java/).
3. Integrated Development Environment (IDE): Välj en IDE för Java-utveckling, till exempel IntelliJ IDEA, Eclipse eller NetBeans.

## Importera paket
För att komma igång, importera nödvändiga paket till ditt Java-projekt:
```java
import com.aspose.slides.*;

```
## Steg 1: Få åtkomst till Shapes Collection
Öppna formsamlingen för den valda bilden:
```java
// Sökvägen till dokumentkatalogen.
String dataDir = "Your Document Directory";
// Instantiate Presentation-klass som representerar PPTX-filen
Presentation presentation = new Presentation();
IShapeCollection shapes = presentation.getSlides().get_Item(0).getShapes();
```
## Steg 2: Lägga till kontaktform
Lägg till en kopplingsform till samlingen av diabilder:
```java
IConnector connector = shapes.addConnector(ShapeType.BentConnector3, 0, 0, 10, 10);
```
## Steg 3: Lägga till AutoShapes
Lägg till automatiska former som ellips och rektangel:
```java
IAutoShape ellipse = shapes.addAutoShape(ShapeType.Ellipse, 0, 100, 100, 100);
IAutoShape rectangle = shapes.addAutoShape(ShapeType.Rectangle, 100, 200, 100, 100);
```
## Steg 4: Sammanfoga former till kopplingar
Fäst formerna till kontakten:
```java
connector.setStartShapeConnectedTo(ellipse);
connector.setEndShapeConnectedTo(rectangle);
```
## Steg 5: Ställa in anslutningsplatsindex
Ställ in önskat anslutningsplatsindex för formerna:
```java
long wantedIndex = 6;
if (ellipse.getConnectionSiteCount() > (wantedIndex & 0xFFFFFFFFL))
{
    connector.setStartShapeConnectionSiteIndex(wantedIndex);
}
```

## Slutsats
den här handledningen har vi lärt oss hur man kopplar samman former med anslutningsplatser i PowerPoint med Aspose.Slides för Java. Med denna kunskap kan du nu automatisera och anpassa dina PowerPoint-presentationer med lätthet.
## FAQ's
### Kan Aspose.Slides för Java användas för andra PowerPoint-manipulationsuppgifter?
Ja, Aspose.Slides för Java tillhandahåller ett brett utbud av funktioner för att skapa, redigera och konvertera PowerPoint-presentationer.
### Är Aspose.Slides för Java gratis att använda?
 Aspose.Slides för Java är ett kommersiellt bibliotek, men du kan utforska dess funktioner med en gratis provperiod. Besök[här](https://releases.aspose.com/) för att starta.
### Kan jag få support om jag stöter på några problem när jag använder Aspose.Slides för Java?
 Ja, du kan få stöd från Asposes communityforum[här](https://forum.aspose.com/c/slides/11).
### Finns tillfälliga licenser tillgängliga för Aspose.Slides för Java?
 Ja, tillfälliga licenser är tillgängliga för test- och utvärderingssyften. Du kan få en[här](https://purchase.aspose.com/temporary-license/).
### Var kan jag köpa en licens för Aspose.Slides för Java?
Du kan köpa en licens från Asposes webbplats[här](https://purchase.aspose.com/buy).
{< /blocks/products/pf/tutorial-page-section >}

{< /blocks/products/pf/main-container >}
{< /blocks/products/pf/main-wrap-class >}

{< blocks/products/products-backtop-button >}
