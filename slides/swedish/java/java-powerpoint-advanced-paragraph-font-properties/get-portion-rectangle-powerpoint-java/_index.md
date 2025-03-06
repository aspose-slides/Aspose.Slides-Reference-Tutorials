---
title: Skaffa Portion Rectangle i PowerPoint med Java
linktitle: Skaffa Portion Rectangle i PowerPoint med Java
second_title: Aspose.Slides Java PowerPoint Processing API
description: Lär dig hur du får delrektangeln i PowerPoint med Aspose.Slides för Java med denna detaljerade, steg-för-steg handledning. Perfekt för Java-utvecklare.
weight: 12
url: /sv/java/java-powerpoint-advanced-paragraph-font-properties/get-portion-rectangle-powerpoint-java/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

## Introduktion
Att skapa dynamiska presentationer i Java är en bris med Aspose.Slides för Java. I den här självstudien kommer vi att dyka in i det nitty-gritty att få delrektangeln i PowerPoint med Aspose.Slides. Vi kommer att täcka allt från att ställa in din miljö till att bryta ner koden steg för steg. Så, låt oss komma igång!
## Förutsättningar
Innan vi går in i koden, låt oss se till att du har allt du behöver för att följa smidigt:
1. Java Development Kit (JDK): Se till att du har JDK 8 eller högre installerat på din maskin.
2.  Aspose.Slides för Java: Ladda ner den senaste versionen från[här](https://releases.aspose.com/slides/java/).
3. Integrated Development Environment (IDE): Eclipse, IntelliJ IDEA, eller vilken annan Java IDE som du väljer.
4. Grundläggande kunskaper om Java: Förståelse av Java-programmering är viktigt.
## Importera paket
Först till kvarn, låt oss importera de nödvändiga paketen. Detta kommer att inkludera Aspose.Slides och några andra för att hantera vår uppgift effektivt.
```java
import com.aspose.slides.*;
import com.aspose.slides.examples.RunExamples;
import java.awt.*;
import java.awt.geom.Rectangle2D;
```
## Steg 1: Konfigurera presentationen
Det första steget är att skapa en ny presentation. Det här blir vår duk att arbeta på.
```java
Presentation pres = new Presentation();
```
## Steg 2: Skapa en tabell
Låt oss nu lägga till en tabell till den första bilden i vår presentation. Den här tabellen kommer att innehålla cellerna där vi lägger till vår text.
```java
ITable tbl = pres.getSlides().get_Item(0).getShapes().addTable(50, 50, new double[]{50, 70}, new double[]{50, 50, 50});
```
## Steg 3: Lägga till stycken i celler
Därefter skapar vi stycken och lägger till dem i en specifik cell i tabellen. Detta innebär att all befintlig text raderas och sedan läggas till nya stycken.
```java
// Skapa stycken
IParagraph paragraph0 = new Paragraph();
paragraph0.getPortions().add(new Portion("Text "));
paragraph0.getPortions().add(new Portion("in0"));
paragraph0.getPortions().add(new Portion(" Cell"));
IParagraph paragraph1 = new Paragraph();
paragraph1.setText("On0");
IParagraph paragraph2 = new Paragraph();
paragraph2.getPortions().add(new Portion("Hi there "));
paragraph2.getPortions().add(new Portion("col0"));
// Lägg till text i tabellcellen
ICell cell = tbl.get_Item(1, 1);
cell.getTextFrame().getParagraphs().clear();
cell.getTextFrame().getParagraphs().add(paragraph0);
cell.getTextFrame().getParagraphs().add(paragraph1);
cell.getTextFrame().getParagraphs().add(paragraph2);
```
## Steg 4: Lägga till en textram till en AutoShape
För att göra vår presentation mer dynamisk lägger vi till en textram i en AutoShape och ställer in dess justering.
```java
IAutoShape autoShape = pres.getSlides().get_Item(0).getShapes().addAutoShape(ShapeType.Rectangle, 400, 100, 60, 120);
autoShape.getTextFrame().setText("Text in shape");
autoShape.getTextFrame().getParagraphs().get_Item(0).getParagraphFormat().setAlignment(TextAlignment.Left);
```
## Steg 5: Beräkna koordinater
Vi måste få koordinaterna för det övre vänstra hörnet av tabellcellen. Detta kommer att hjälpa oss att placera formerna korrekt.
```java
double x = tbl.getX() + cell.getOffsetX();
double y = tbl.getY() + cell.getOffsetY();
```
## Steg 6: Lägga till ramar till stycken och delar
 Använda`IParagraph.getRect()` och`IPortion.getRect()`metoder kan vi lägga till ramar i våra stycken och delar. Detta innebär att iterera genom styckena och delarna, skapa former runt dem och anpassa deras utseende.
```java
for (IParagraph para : cell.getTextFrame().getParagraphs()) {
    if ("".equals(para.getText())) continue;
    Rectangle2D.Float rect = (Rectangle2D.Float) para.getRect().clone();
    IAutoShape shape = pres.getSlides().get_Item(0).getShapes().addAutoShape(
        ShapeType.Rectangle,
        (float) rect.getX() + (float) x,
        (float) rect.getY() + (float) y,
        (float) rect.getWidth(),
        (float) rect.getHeight()
    );
    shape.getFillFormat().setFillType(FillType.NoFill);
    shape.getLineFormat().getFillFormat().getSolidFillColor().setColor(Color.YELLOW);
    shape.getLineFormat().getFillFormat().setFillType(FillType.Solid);
    for (IPortion portion : para.getPortions()) {
        if (portion.getText().contains("0")) {
            rect = portion.getRect();
            shape = pres.getSlides().get_Item(0).getShapes().addAutoShape(
                ShapeType.Rectangle,
                (float) rect.getX() + (float) x,
                (float) rect.getY() + (float) y,
                (float) rect.getWidth(),
                (float) rect.getHeight()
            );
            shape.getFillFormat().setFillType(FillType.NoFill);
        }
    }
}
```
## Steg 7: Lägga till ramar till AutoShape-stycken
På samma sätt kommer vi att lägga till ramar till styckena i vår AutoShape, vilket förstärker presentationens visuella tilltalande.
```java
for (IParagraph para : autoShape.getTextFrame().getParagraphs()) {
    Rectangle2D.Float rect = (Rectangle2D.Float) para.getRect().clone();
    IAutoShape shape = pres.getSlides().get_Item(0).getShapes().addAutoShape(
        ShapeType.Rectangle,
        (float) rect.getX() + autoShape.getX(),
        (float) rect.getY() + autoShape.getY(),
        (float) rect.getWidth(),
        (float) rect.getHeight()
    );
    shape.getFillFormat().setFillType(FillType.NoFill);
    shape.getLineFormat().getFillFormat().getSolidFillColor().setColor(Color.YELLOW);
    shape.getLineFormat().getFillFormat().setFillType(FillType.Solid);
}
```
## Steg 8: Spara presentationen
Slutligen kommer vi att spara vår presentation på en angiven väg.
```java
String outPath = "path_to_output_directory";
pres.save(outPath + "GetRect_Out.pptx", SaveFormat.Pptx);
```
## Steg 9: Rensa
Det är bra att göra sig av med presentationsobjektet för att frigöra resurser.
```java
if (pres != null) pres.dispose();
```
## Slutsats
Grattis! Du har framgångsrikt lärt dig hur du får delrektangeln i PowerPoint med Aspose.Slides för Java. Detta kraftfulla bibliotek öppnar upp en värld av möjligheter för att skapa dynamiska och visuellt tilltalande presentationer programmatiskt. Dyk djupare in i Aspose.Slides och utforska fler funktioner för att förbättra dina presentationer ytterligare.
## FAQ's
### Vad är Aspose.Slides för Java?
Aspose.Slides för Java är ett kraftfullt bibliotek som låter utvecklare skapa, modifiera och manipulera PowerPoint-presentationer programmatiskt.
### Kan jag använda Aspose.Slides för Java i kommersiella projekt?
 Ja, Aspose.Slides för Java kan användas i kommersiella projekt. Du kan köpa en licens från[här](https://purchase.aspose.com/buy).
### Finns det en gratis testversion tillgänglig för Aspose.Slides för Java?
 Ja, du kan ladda ner en gratis testversion från[här](https://releases.aspose.com/).
### Var kan jag hitta dokumentationen för Aspose.Slides för Java?
 Dokumentationen finns tillgänglig[här](https://reference.aspose.com/slides/java/).
### Hur kan jag få support för Aspose.Slides för Java?
 Du kan få stöd från Aspose-forumet[här](https://forum.aspose.com/c/slides/11).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
