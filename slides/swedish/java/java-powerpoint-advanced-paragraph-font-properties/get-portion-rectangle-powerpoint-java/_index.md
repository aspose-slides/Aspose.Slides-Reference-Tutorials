---
"description": "Lär dig hur du får delrektangeln i PowerPoint med Aspose.Slides för Java med den här detaljerade steg-för-steg-handledningen. Perfekt för Java-utvecklare."
"linktitle": "Hämta portionsrektangel i PowerPoint med Java"
"second_title": "Aspose.Slides Java PowerPoint-bearbetnings-API"
"title": "Hämta portionsrektangel i PowerPoint med Java"
"url": "/sv/java/java-powerpoint-advanced-paragraph-font-properties/get-portion-rectangle-powerpoint-java/"
"weight": 12
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Hämta portionsrektangel i PowerPoint med Java

## Introduktion
Att skapa dynamiska presentationer i Java är en barnlek med Aspose.Slides för Java. I den här handledningen går vi in på detaljerna kring att få portionsrektangeln i PowerPoint med hjälp av Aspose.Slides. Vi går igenom allt från att konfigurera din miljö till att bryta ner koden steg för steg. Så, låt oss sätta igång!
## Förkunskapskrav
Innan vi går in i koden, låt oss se till att du har allt du behöver för att följa med smidigt:
1. Java Development Kit (JDK): Se till att du har JDK 8 eller senare installerat på din dator.
2. Aspose.Slides för Java: Ladda ner den senaste versionen från [här](https://releases.aspose.com/slides/java/).
3. Integrerad utvecklingsmiljö (IDE): Eclipse, IntelliJ IDEA eller någon annan Java IDE som du väljer.
4. Grundläggande kunskaper i Java: Förståelse för Java-programmering är viktigt.
## Importera paket
Först och främst, låt oss importera de nödvändiga paketen. Detta inkluderar Aspose.Slides och några andra för att hantera vår uppgift effektivt.
```java
import com.aspose.slides.*;
import com.aspose.slides.examples.RunExamples;
import java.awt.*;
import java.awt.geom.Rectangle2D;
```
## Steg 1: Konfigurera presentationen
Det första steget är att skapa en ny presentation. Detta kommer att vara vår arbetsyta att arbeta med.
```java
Presentation pres = new Presentation();
```
## Steg 2: Skapa en tabell
Nu ska vi lägga till en tabell på den första bilden i vår presentation. Den här tabellen kommer att innehålla cellerna där vi ska lägga till vår text.
```java
ITable tbl = pres.getSlides().get_Item(0).getShapes().addTable(50, 50, new double[]{50, 70}, new double[]{50, 50, 50});
```
## Steg 3: Lägga till stycken i celler
Nästa steg är att skapa stycken och lägga till dem i en specifik cell i tabellen. Detta innebär att vi tar bort all befintlig text och sedan lägger till nya stycken.
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
## Steg 4: Lägga till en textram till en autoform
För att göra vår presentation mer dynamisk lägger vi till en textram i en autofigur och anger dess justering.
```java
IAutoShape autoShape = pres.getSlides().get_Item(0).getShapes().addAutoShape(ShapeType.Rectangle, 400, 100, 60, 120);
autoShape.getTextFrame().setText("Text in shape");
autoShape.getTextFrame().getParagraphs().get_Item(0).getParagraphFormat().setAlignment(TextAlignment.Left);
```
## Steg 5: Beräkning av koordinater
Vi behöver få koordinaterna för det övre vänstra hörnet av tabellcellen. Detta hjälper oss att placera formerna korrekt.
```java
double x = tbl.getX() + cell.getOffsetX();
double y = tbl.getY() + cell.getOffsetY();
```
## Steg 6: Lägga till ramar i stycken och delar
Använda `IParagraph.getRect()` och `IPortion.getRect()` metoder kan vi lägga till ramar i våra stycken och delar. Detta innebär att vi itererar igenom stycken och delar, skapar former runt dem och anpassar deras utseende.
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
## Steg 7: Lägga till ramar i autoformade stycken
På samma sätt lägger vi till ramar i styckena i vår autoform, vilket förbättrar presentationens visuella attraktionskraft.
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
Slutligen sparar vi vår presentation till en angiven sökväg.
```java
String outPath = "path_to_output_directory";
pres.save(outPath + "GetRect_Out.pptx", SaveFormat.Pptx);
```
## Steg 9: Städning
Det är bra att göra sig av med presentationsobjektet för att frigöra resurser.
```java
if (pres != null) pres.dispose();
```
## Slutsats
Grattis! Du har framgångsrikt lärt dig hur man får fram portionsrektangeln i PowerPoint med hjälp av Aspose.Slides för Java. Detta kraftfulla bibliotek öppnar upp en värld av möjligheter för att skapa dynamiska och visuellt tilltalande presentationer programmatiskt. Fördjupa dig i Aspose.Slides och utforska fler funktioner för att ytterligare förbättra dina presentationer.
## Vanliga frågor
### Vad är Aspose.Slides för Java?
Aspose.Slides för Java är ett kraftfullt bibliotek som låter utvecklare skapa, modifiera och manipulera PowerPoint-presentationer programmatiskt.
### Kan jag använda Aspose.Slides för Java i kommersiella projekt?
Ja, Aspose.Slides för Java kan användas i kommersiella projekt. Du kan köpa en licens från [här](https://purchase.aspose.com/buy).
### Finns det en gratis testversion av Aspose.Slides för Java?
Ja, du kan ladda ner en gratis provversion från [här](https://releases.aspose.com/).
### Var kan jag hitta dokumentationen för Aspose.Slides för Java?
Dokumentationen finns tillgänglig [här](https://reference.aspose.com/slides/java/).
### Hur kan jag få support för Aspose.Slides för Java?
Du kan få stöd från Aspose-forumet [här](https://forum.aspose.com/c/slides/11).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}