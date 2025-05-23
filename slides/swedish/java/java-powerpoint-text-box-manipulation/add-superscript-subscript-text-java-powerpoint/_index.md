---
"description": "Lär dig hur du lägger till upphöjd och nedsänkt text i PowerPoint-presentationer i Java med Aspose.Slides för Java. Perfekt för att förbättra dina bilder."
"linktitle": "Lägg till upphöjd och nedsänkt text i Java PowerPoint"
"second_title": "Aspose.Slides Java PowerPoint-bearbetnings-API"
"title": "Lägg till upphöjd och nedsänkt text i Java PowerPoint"
"url": "/sv/java/java-powerpoint-text-box-manipulation/add-superscript-subscript-text-java-powerpoint/"
"weight": 13
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Lägg till upphöjd och nedsänkt text i Java PowerPoint

## Introduktion
Att skapa engagerande och informativa PowerPoint-presentationer kräver ofta användning av formateringsfunktioner som upphöjd och nedsänkt text. Den här handledningen guidar dig genom processen att integrera upphöjd och nedsänkt text i dina Java PowerPoint-presentationer med Aspose.Slides för Java.
## Förkunskapskrav
Innan du börjar, se till att du har följande:
- Java Development Kit (JDK) installerat på ditt system.
- Aspose.Slides för Java-biblioteket. Du kan ladda ner det från [här](https://releases.aspose.com/slides/java/).
- En integrerad utvecklingsmiljö (IDE) som IntelliJ IDEA eller Eclipse konfigurerad för Java-utveckling.
- Grundläggande kunskaper i Java-programmering och PowerPoint-presentationer.

## Importera paket
Importera först de nödvändiga paketen från Aspose.Slides för Java:
```java
import com.aspose.slides.*;
```
## Steg 1: Ställ in presentationen
```java
// Sökvägen till dokumentkatalogen.
String dataDir = "Your Document Directory";
Presentation presentation = new Presentation();
```
## Steg 2: Öppna bilden
```java
// Hämta den första bilden
ISlide slide = presentation.getSlides().get_Item(0);
```
## Steg 3: Skapa en textruta
```java
// Skapa en autoform som ska fungera som en textruta
IAutoShape shape = slide.getShapes().addAutoShape(ShapeType.Rectangle, 100, 100, 200, 100);
ITextFrame textFrame = shape.getTextFrame();
textFrame.getParagraphs().clear();
```
## Steg 4: Lägg till upphöjd text
```java
// Skapa ett stycke för huvudtexten
IParagraph mainParagraph = new Paragraph();
IPortion mainPortion = new Portion();
mainPortion.setText("SlideTitle");
mainParagraph.getPortions().add(mainPortion);
// Skapa en del för den upphöjda texten
IPortion superPortion = new Portion();
superPortion.getPortionFormat().setEscapement(30); // Ställ in escapement för upphöjd skrift
superPortion.setText("TM");
mainParagraph.getPortions().add(superPortion);
// Lägg till huvudstycket med upphöjd skrift i textrutan
textFrame.getParagraphs().add(mainParagraph);
```
## Steg 5: Lägg till prenumerationstext
```java
// Skapa ett annat stycke för nedsänkt text
IParagraph subscriptParagraph = new Paragraph();
IPortion subscriptPortion = new Portion();
subscriptPortion.setText("a");
subscriptParagraph.getPortions().add(subscriptPortion);
// Skapa en del för den nedsänkta texten
IPortion subPortion = new Portion();
subPortion.getPortionFormat().setEscapement(-25); // Ställ in escapement för subscript
subPortion.setText("i");
subscriptParagraph.getPortions().add(subPortion);
// Lägg till nedsänkt stycke i textrutan
textFrame.getParagraphs().add(subscriptParagraph);
```
## Steg 6: Spara presentationen
```java
// Spara presentationen
presentation.save(dataDir + "TestOut.pptx", SaveFormat.Pptx);
```

## Slutsats
I den här handledningen utforskade vi hur du kan förbättra dina PowerPoint-presentationer i Java med upphöjd och nedsänkt text med hjälp av Aspose.Slides för Java. Genom att följa dessa steg kan du skapa mer visuellt tilltalande och informativa bilder som effektivt kommunicerar ditt innehåll.

## Vanliga frågor
### Vad är Aspose.Slides för Java?
Aspose.Slides för Java är ett robust bibliotek som låter utvecklare skapa, manipulera och konvertera PowerPoint-presentationer programmatiskt.
### Var kan jag hitta mer dokumentation om Aspose.Slides för Java?
Detaljerad dokumentation finns [här](https://reference.aspose.com/slides/java/).
### Hur kan jag få en tillfällig licens för Aspose.Slides för Java?
Du kan få en tillfällig licens [här](https://purchase.aspose.com/temporary-license/).
### Kan jag prova Aspose.Slides för Java gratis?
Ja, du kan ladda ner en gratis testversion från [här](https://releases.aspose.com/).
### Var kan jag få support för Aspose.Slides för Java?
För stöd och diskussioner, besök [Aspose.Slides-forum](https://forum.aspose.com/c/slides/11).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}