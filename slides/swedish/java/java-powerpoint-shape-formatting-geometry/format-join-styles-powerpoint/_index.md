---
title: Formatera Sammanfoga stilar i PowerPoint
linktitle: Formatera Sammanfoga stilar i PowerPoint
second_title: Aspose.Slides Java PowerPoint Processing API
description: Lär dig hur du förbättrar dina PowerPoint-presentationer genom att ställa in olika linjekopplingsstilar för former med Aspose.Slides för Java. Följ vår steg-för-steg-guide.
type: docs
weight: 15
url: /sv/java/java-powerpoint-shape-formatting-geometry/format-join-styles-powerpoint/
---
## Introduktion
Att skapa visuellt tilltalande PowerPoint-presentationer kan vara en skrämmande uppgift, särskilt när du vill att varje detalj ska vara perfekt. Det är här Aspose.Slides för Java kommer väl till pass. Det är ett kraftfullt API som låter dig skapa, manipulera och hantera presentationer programmatiskt. En av funktionerna som du kan använda är att ställa in olika linjefogningsstilar för former, vilket avsevärt kan förbättra estetiken hos dina bilder. I den här självstudien kommer vi att dyka in i hur du kan använda Aspose.Slides för Java för att ställa in sammanfogningsstilar för former i PowerPoint-presentationer. 
## Förutsättningar
Innan vi börjar finns det några förutsättningar du måste ha på plats:
1.  Java Development Kit (JDK): Se till att du har JDK installerat på din maskin. Du kan ladda ner den från[Oracles hemsida](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html).
2.  Aspose.Slides for Java Library: Du måste ladda ner och inkludera Aspose.Slides för Java i ditt projekt. Du kan få det från[här](https://releases.aspose.com/slides/java/).
3. Integrated Development Environment (IDE): Använd en IDE som IntelliJ IDEA, Eclipse eller NetBeans för att skriva och köra din Java-kod.
4. Grundläggande kunskaper om Java: En grundläggande förståelse för Java-programmering hjälper dig att följa handledningen.
## Importera paket
Först måste du importera de nödvändiga paketen för Aspose.Slides. Detta är viktigt för att komma åt de klasser och metoder som krävs för våra presentationsmanipulationer.
```java
import com.aspose.slides.*;

import java.awt.*;
import java.io.File;
```
## Steg 1: Konfigurera projektkatalogen
Låt oss börja med att skapa en katalog för att lagra våra presentationsfiler. Detta säkerställer att alla våra filer är organiserade och lättillgängliga.
```java
String dataDir = "Your Document Directory";
// Skapa katalog om den inte redan finns.
boolean IsExists = new File(dataDir).exists();
if (!IsExists)
    new File(dataDir).mkdirs();
```
I det här steget definierar vi en katalogsökväg och kontrollerar om den finns. Om det inte gör det skapar vi katalogen. Detta är ett enkelt men effektivt sätt att hålla dina filer organiserade.
## Steg 2: Initiera presentationen
 Därefter instansierar vi`Presentation` klass, som representerar vår PowerPoint-fil. Detta är grunden på vilken vi kommer att bygga våra diabilder och former.
```java
Presentation pres = new Presentation();
```
Denna kodrad skapar en ny presentation. Se det som att öppna en tom PowerPoint-fil där du lägger till allt ditt innehåll.
## Steg 3: Lägg till former i bilden
### Skaffa den första bilden
Innan vi lägger till former måste vi få en referens till den första bilden i vår presentation. Som standard innehåller en ny presentation en tom bild.
```java
ISlide sld = pres.getSlides().get_Item(0);
```
### Lägg till rektangelformer
Låt oss nu lägga till tre rektangulära former till vår bild. Dessa former kommer att visa de olika linjesammanfogningsstilarna.
```java
IShape shp1 = sld.getShapes().addAutoShape(ShapeType.Rectangle, 50, 100, 150, 75);
IShape shp2 = sld.getShapes().addAutoShape(ShapeType.Rectangle, 300, 100, 150, 75);
IShape shp3 = sld.getShapes().addAutoShape(ShapeType.Rectangle, 50, 250, 150, 75);
```
I det här steget lägger vi till tre rektanglar på angivna positioner på bilden. Varje rektangel kommer senare att utformas annorlunda för att visa upp olika sammanfogningsstilar.
## Steg 4: Style formerna
### Ställ in fyllningsfärg
Vi vill att våra rektanglar ska fyllas med en enfärgad färg. Här väljer vi svart som fyllningsfärg.
```java
shp1.getFillFormat().setFillType(FillType.Solid);
shp1.getFillFormat().getSolidFillColor().setColor(Color.BLACK);
shp2.getFillFormat().setFillType(FillType.Solid);
shp2.getFillFormat().getSolidFillColor().setColor(Color.BLACK);
shp3.getFillFormat().setFillType(FillType.Solid);
shp3.getFillFormat().getSolidFillColor().setColor(Color.BLACK);
```
### Ställ in linjebredd och färg
Därefter definierar vi linjebredden och färgen för varje rektangel. Detta hjälper till att visuellt differentiera sammanfogningsstilarna.
```java
shp1.getLineFormat().setWidth(15);
shp2.getLineFormat().setWidth(15);
shp3.getLineFormat().setWidth(15);
shp1.getLineFormat().getFillFormat().setFillType(FillType.Solid);
shp1.getLineFormat().getFillFormat().getSolidFillColor().setColor(Color.BLUE);
shp2.getLineFormat().getFillFormat().setFillType(FillType.Solid);
shp2.getLineFormat().getFillFormat().getSolidFillColor().setColor(Color.BLUE);
shp3.getLineFormat().getFillFormat().setFillType(FillType.Solid);
shp3.getLineFormat().getFillFormat().getSolidFillColor().setColor(Color.BLUE);
```
## Steg 5: Använd Join Styles
Höjdpunkten i denna handledning är att ställa in stilar för linjekoppling. Vi kommer att använda tre olika stilar: Gering, Bevel och Round.
```java
shp1.getLineFormat().setJoinStyle(LineJoinStyle.Miter);
shp2.getLineFormat().setJoinStyle(LineJoinStyle.Bevel);
shp3.getLineFormat().setJoinStyle(LineJoinStyle.Round);
```
Varje linjefogstil ger formerna en unik look i hörnen där linjerna möts. Detta kan vara särskilt användbart för att skapa visuellt distinkta diagram eller illustrationer.
## Steg 6: Lägg till text i former
För att göra det tydligt vad varje form representerar, lägger vi till text till varje rektangel som beskriver den kopplingsstil som används.
```java
((IAutoShape) shp1).getTextFrame().setText("This is Miter Join Style");
((IAutoShape) shp2).getTextFrame().setText("This is Bevel Join Style");
((IAutoShape) shp3).getTextFrame().setText("This is Round Join Style");
```
Att lägga till text hjälper till att identifiera de olika stilarna när du presenterar eller delar bilden.
## Steg 7: Spara presentationen
Slutligen sparar vi vår presentation i den angivna katalogen.
```java
pres.save(dataDir + "RectShpLnJoin_out.pptx", SaveFormat.Pptx);
```
Detta kommando skriver presentationen till en PPTX-fil, som du kan öppna med Microsoft PowerPoint eller någon annan kompatibel programvara.
## Slutsats
Och där har du det! Du har precis skapat en PowerPoint-bild med tre rektanglar, som var och en visar en annan linjekopplingsstil med Aspose.Slides för Java. Denna handledning hjälper dig inte bara att förstå grunderna i Aspose.Slides utan visar också hur du förbättrar dina presentationer med unika stilar. Glad presentation!
## FAQ's
### Vad är Aspose.Slides för Java?
Aspose.Slides för Java är ett kraftfullt API för att skapa, manipulera och hantera PowerPoint-presentationer programmatiskt.
### Kan jag använda Aspose.Slides för Java i vilken IDE som helst?
Ja, du kan använda Aspose.Slides för Java i alla Java-stödda IDE som IntelliJ IDEA, Eclipse eller NetBeans.
### Finns det en gratis testversion av Aspose.Slides för Java?
 Ja, du kan få en gratis provperiod från[här](https://releases.aspose.com/).
### Vad är linjekopplingsstilar i PowerPoint?
Linjefogstilar hänvisar till formen på hörnen där två linjer möts. Vanliga stilar inkluderar Mitre, Bevel och Round.
### Var kan jag hitta mer dokumentation om Aspose.Slides för Java?
 Du kan hitta detaljerad dokumentation[här](https://reference.aspose.com/slides/java/).