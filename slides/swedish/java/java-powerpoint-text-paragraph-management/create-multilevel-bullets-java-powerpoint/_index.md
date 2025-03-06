---
title: Skapa flernivåpunkter i Java PowerPoint
linktitle: Skapa flernivåpunkter i Java PowerPoint
second_title: Aspose.Slides Java PowerPoint Processing API
description: Lär dig hur du skapar kulor på flera nivåer i PowerPoint med Aspose.Slides för Java. Steg-för-steg guide med kodexempel och vanliga frågor.
weight: 14
url: /sv/java/java-powerpoint-text-paragraph-management/create-multilevel-bullets-java-powerpoint/
---

{< blocks/products/pf/main-wrap-class >}
{< blocks/products/pf/main-container >}
{< blocks/products/pf/tutorial-page-section >}

## Introduktion
I den här handledningen kommer vi att utforska hur man skapar kulor på flera nivåer i PowerPoint-presentationer med Aspose.Slides för Java. Att lägga till punktpunkter är ett vanligt krav för att skapa organiserat och visuellt tilltalande innehåll i presentationer. Vi går igenom processen steg-för-steg och säkerställer att du i slutet av den här guiden är utrustad för att förbättra dina presentationer med strukturerade punktpunkter på flera nivåer.
## Förutsättningar
Innan vi börjar, se till att du har följande inställning:
- Java Development Environment: Se till att Java Development Kit (JDK) är installerat på ditt system.
-  Aspose.Slides for Java Library: Ladda ner och installera Aspose.Slides for Java från[här](https://releases.aspose.com/slides/java/).
- IDE: Använd din föredragna Java Integrated Development Environment (IDE) som IntelliJ IDEA, Eclipse eller andra.
- Grundläggande kunskaper: Förtrogenhet med Java-programmering och grundläggande PowerPoint-koncept kommer att vara till hjälp.

## Importera paket
Innan vi dyker in i handledningen, låt oss importera de nödvändiga paketen från Aspose.Slides för Java som vi kommer att använda genom hela handledningen.
```java
import com.aspose.slides.*;
import java.awt.*;
import java.io.File;
```
## Steg 1: Konfigurera ditt projekt
Skapa först ett nytt Java-projekt i din IDE och lägg till Aspose.Slides för Java till ditt projekts beroenden. Se till att den nödvändiga Aspose.Slides JAR-filen ingår i ditt projekts byggsökväg.
```java
// Sökvägen till dokumentkatalogen.
String dataDir = "Your Document Directory";
```
## Steg 2: Initiera presentationsobjekt
Börja med att skapa en ny presentationsinstans. Detta kommer att fungera som ditt PowerPoint-dokument där du lägger till bilder och innehåll.
```java
Presentation pres = new Presentation();
```
## Steg 3: Öppna bilden
Öppna sedan bilden där du vill lägga till flernivåpunkterna. För det här exemplet kommer vi att arbeta med den första bilden (`Slide(0)`).
```java
ISlide slide = pres.getSlides().get_Item(0);
```
## Steg 4: Lägg till AutoShape med textram
Lägg till en AutoShape på bilden där du placerar din text med flernivåpunkter.
```java
IAutoShape aShp = slide.getShapes().addAutoShape(ShapeType.Rectangle, 200, 200, 400, 200);
```
## Steg 5: Åtkomst till textram
Gå till textramen i AutoShape där du lägger till stycken med punktpunkter.
```java
ITextFrame text = aShp.addTextFrame("");
text.getParagraphs().clear(); //Rensa standardstycken
```
## Steg 6: Lägg till stycken med punkter
Lägg till stycken med olika nivåer av punkter. Så här kan du lägga till flernivåpunkter:
```java
// Första nivån
IParagraph para1 = new Paragraph();
para1.setText("Content");
para1.getParagraphFormat().getBullet().setType(BulletType.Symbol);
para1.getParagraphFormat().getBullet().setChar((char) 8226);
para1.getParagraphFormat().getDefaultPortionFormat().getFillFormat().setFillType(FillType.Solid);
para1.getParagraphFormat().getDefaultPortionFormat().getFillFormat().getSolidFillColor().setColor(Color.BLACK);
para1.getParagraphFormat().setDepth((short) 0);
text.getParagraphs().add(para1);
// Andra nivån
IParagraph para2 = new Paragraph();
para2.setText("Second Level");
para2.getParagraphFormat().getBullet().setType(BulletType.Symbol);
para2.getParagraphFormat().getBullet().setChar('-');
para2.getParagraphFormat().getDefaultPortionFormat().getFillFormat().setFillType(FillType.Solid);
para2.getParagraphFormat().getDefaultPortionFormat().getFillFormat().getSolidFillColor().setColor(Color.BLACK);
para2.getParagraphFormat().setDepth((short) 1);
text.getParagraphs().add(para2);
// Tredje nivån
IParagraph para3 = new Paragraph();
para3.setText("Third Level");
para3.getParagraphFormat().getBullet().setType(BulletType.Symbol);
para3.getParagraphFormat().getBullet().setChar((char) 8226);
para3.getParagraphFormat().getDefaultPortionFormat().getFillFormat().setFillType(FillType.Solid);
para3.getParagraphFormat().getDefaultPortionFormat().getFillFormat().getSolidFillColor().setColor(Color.BLACK);
para3.getParagraphFormat().setDepth((short) 2);
text.getParagraphs().add(para3);
// Fjärde nivån
IParagraph para4 = new Paragraph();
para4.setText("Fourth Level");
para4.getParagraphFormat().getBullet().setType(BulletType.Symbol);
para4.getParagraphFormat().getBullet().setChar('-');
para4.getParagraphFormat().getDefaultPortionFormat().getFillFormat().setFillType(FillType.Solid);
para4.getParagraphFormat().getDefaultPortionFormat().getFillFormat().getSolidFillColor().setColor(Color.BLACK);
para4.getParagraphFormat().setDepth((short) 3);
text.getParagraphs().add(para4);
```
## Steg 7: Spara presentationen
Slutligen, spara presentationen som en PPTX-fil i önskad katalog.
```java
pres.save(dataDir + "MultilevelBullet.pptx", SaveFormat.Pptx);
```

## Slutsats
I den här handledningen har vi täckt hur du skapar flernivåpunkter i PowerPoint-presentationer med Aspose.Slides för Java. Genom att följa dessa steg kan du effektivt strukturera ditt innehåll med organiserade punktpunkter på olika nivåer, vilket förbättrar klarheten och det visuella tilltalande i dina presentationer.
## FAQ's
### Kan jag anpassa kulsymbolerna ytterligare?
Ja, du kan anpassa kulsymbolerna genom att justera Unicode-tecken eller använda olika former.
### Stöder Aspose.Slides andra kultyper?
Ja, Aspose.Slides stöder en mängd olika kultyper inklusive symboler, siffror och anpassade bilder.
### Är Aspose.Slides kompatibel med alla versioner av PowerPoint?
Aspose.Slides genererar presentationer som är kompatibla med Microsoft PowerPoint 2007 och högre versioner.
### Kan jag automatisera genereringen av bilder med Aspose.Slides?
Ja, Aspose.Slides tillhandahåller API:er för att automatisera skapandet, modifieringen och manipuleringen av PowerPoint-presentationer.
### Var kan jag få support för Aspose.Slides för Java?
 Du kan få stöd från Aspose.Slides-communityt och experter på[Aspose.Slides Forum](https://forum.aspose.com/c/slides/11).
{< /blocks/products/pf/tutorial-page-section >}

{< /blocks/products/pf/main-container >}
{< /blocks/products/pf/main-wrap-class >}

{< blocks/products/products-backtop-button >}
