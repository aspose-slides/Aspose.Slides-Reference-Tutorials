---
"description": "Lär dig hur du lägger till styckepunkter i PowerPoint-bilder med Aspose.Slides för Java. Den här handledningen guidar dig steg för steg med kodexempel."
"linktitle": "Lägg till styckepunkter i PowerPoint med Java"
"second_title": "Aspose.Slides Java PowerPoint-bearbetnings-API"
"title": "Lägg till styckepunkter i PowerPoint med Java"
"url": "/sv/java/java-powerpoint-text-paragraph-management/add-paragraph-bullets-powerpoint-java/"
"weight": 15
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Lägg till styckepunkter i PowerPoint med Java

## Introduktion
Att lägga till styckepunkter förbättrar läsbarheten och strukturen i PowerPoint-presentationer. Aspose.Slides för Java tillhandahåller robusta verktyg för att manipulera presentationer programmatiskt, inklusive möjligheten att formatera text med olika punktformat. I den här handledningen lär du dig hur du integrerar punktlistor i PowerPoint-bilder med hjälp av Java-kod och Aspose.Slides.
## Förkunskapskrav
Innan du börjar, se till att du har följande:
- Grundläggande kunskaper i Java-programmering.
- JDK (Java Development Kit) installerat på ditt system.
- Aspose.Slides för Java-biblioteket. Du kan ladda ner det från [här](https://releases.aspose.com/slides/java/).

## Importera paket
För att komma igång, importera nödvändiga Aspose.Slides-paket till ditt Java-projekt:
```java
import com.aspose.slides.*;
import java.awt.*;
import java.io.File;
```
## Steg 1: Konfigurera ditt projekt
Skapa först ett nytt Java-projekt och lägg till Aspose.Slides för Java-biblioteket i projektets byggsökväg.
## Steg 2: Initiera en presentation
Initiera ett presentationsobjekt (`Presentation`) för att börja arbeta med bilder.
```java
// Sökvägen till dokumentkatalogen.
String dataDir = "Your Document Directory";
// Skapa en presentationsinstans
Presentation pres = new Presentation();
```
## Steg 3: Åtkomst till bild- och textramen
Åtkomst till bilden (`ISlide`) och dess textram (`ITextFrame`) där du vill lägga till punkter.
```java
// Åtkomst till den första bilden
ISlide slide = pres.getSlides().get_Item(0);
// Lägga till och komma åt autoform
IAutoShape aShp = slide.getShapes().addAutoShape(ShapeType.Rectangle, 200, 200, 400, 200);
// Åtkomst till textramen för den skapade autoformen
ITextFrame txtFrm = aShp.getTextFrame();
```
## Steg 4: Skapa och formatera stycken med punktlistor
Skapa stycken (`Paragraph`) och ange deras punktformat, indentering och text.
```java
// Skapa ett stycke
Paragraph para = new Paragraph();
para.getParagraphFormat().getBullet().setType(BulletType.Symbol);
para.getParagraphFormat().getBullet().setChar((char) 8226);
para.setText("Welcome to Aspose.Slides");
para.getParagraphFormat().setIndent(25);
txtFrm.getParagraphs().add(para);
// Skapa ytterligare ett stycke
Paragraph para2 = new Paragraph();
para2.getParagraphFormat().getBullet().setType(BulletType.Numbered);
para2.getParagraphFormat().getBullet().setNumberedBulletStyle(NumberedBulletStyle.BulletCircleNumWDBlackPlain);
para2.setText("This is numbered bullet");
para2.getParagraphFormat().setIndent(25);
txtFrm.getParagraphs().add(para2);
```
## Steg 5: Spara presentationen
Spara den ändrade presentationen till en PowerPoint-fil (`PPTX`).
```java
// Att skriva presentationen som en PPTX-fil
pres.save(dataDir + "Bullet_out.pptx", SaveFormat.Pptx);
```
## Steg 6: Rensa upp resurser
Kassera presentationsobjektet för att frigöra resurser.
```java
// Kassera presentationsobjektet
if (pres != null) {
    pres.dispose();
}
```

## Slutsats
Att lägga till styckepunkter i PowerPoint med Aspose.Slides för Java är enkelt med de medföljande kodexemplen. Anpassa punktstilar och formatering så att de passar dina presentationsbehov sömlöst.

## Vanliga frågor
### Kan jag anpassa punktfärgerna?
Ja, du kan ange anpassade färger för punkter med hjälp av Aspose.Slides API.
### Hur lägger jag till kapslade punkter?
Kapsling av punkter innebär att lägga till stycken inom stycken och justera indraget därefter.
### Kan jag skapa olika punktformat för olika bilder?
Ja, du kan programmatiskt tillämpa unika punktformat på olika bilder.
### Är Aspose.Slides kompatibelt med Java 11?
Ja, Aspose.Slides stöder Java 11 och senare versioner.
### Var kan jag hitta fler exempel och dokumentation?
Besök [Aspose.Slides för Java-dokumentation](https://reference.aspose.com/slides/java/) för omfattande guider och exempel.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}