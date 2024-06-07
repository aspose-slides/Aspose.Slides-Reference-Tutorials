---
title: Lägg till vanlig linje till bild
linktitle: Lägg till vanlig linje till bild
second_title: Aspose.Slides Java PowerPoint Processing API
description: Lär dig hur du lägger till en vanlig linje till en PowerPoint-bild med hjälp av Aspose.Slides för Java. Öka din produktivitet med denna steg-för-steg-guide.
type: docs
weight: 14
url: /sv/java/java-powerpoint-shape-media-insertion/add-plain-line-slide/
---
## Introduktion
Aspose.Slides för Java är ett kraftfullt bibliotek som låter Java-utvecklare arbeta med PowerPoint-presentationer programmatiskt. Med Aspose.Slides kan du skapa, ändra och konvertera PowerPoint-filer med lätthet, vilket sparar tid och ansträngning. I den här handledningen går vi igenom processen att lägga till en vanlig linje på en bild i en PowerPoint-presentation med Aspose.Slides för Java.
## Förutsättningar
Innan vi börjar, se till att du har följande förutsättningar:
- Java Development Kit (JDK) installerat på ditt system
- Aspose.Slides för Java-biblioteket har laddats ner och lagts till i ditt Java-projekt
- Grundläggande kunskaper i programmeringsspråket Java

## Importera paket
För att börja måste du importera de nödvändiga paketen i din Java-kod. Så här kan du göra det:
```java
import com.aspose.slides.ISlide;
import com.aspose.slides.Presentation;
import com.aspose.slides.SaveFormat;
import com.aspose.slides.ShapeType;
import com.aspose.slides.examples.RunExamples;
import java.io.File;
```
## Steg 1: Ställ in miljön
 Skapa först ett nytt Java-projekt och lägg till Aspose.Slides for Java-biblioteket till ditt projekts klassväg. Du kan ladda ner biblioteket från[här](https://releases.aspose.com/slides/java/).
## Steg 2: Skapa en ny presentation
 Nästa, instansiera`Presentation` klass för att skapa en ny PowerPoint-presentation.
```java
Presentation pres = new Presentation();
```
## Steg 3: Lägg till en bild
Hämta den första bilden av presentationen och lagra den i en variabel.
```java
ISlide slide = pres.getSlides().get_Item(0);
```
## Steg 4: Lägg till en linjeform
Lägg nu till en autoform av typlinje på bilden.
```java
slide.getShapes().addAutoShape(ShapeType.Line, 50, 150, 300, 0);
```
## Steg 5: Spara presentationen
Slutligen, spara presentationen på disk.
```java
pres.save("Your Document Directory/LineShape1_out.pptx", SaveFormat.Pptx);
```

## Slutsats
Grattis! Du har framgångsrikt lagt till en vanlig linje till en bild i en PowerPoint-presentation med Aspose.Slides för Java. Med Aspose.Slides kan du enkelt manipulera PowerPoint-filer programmatiskt, vilket öppnar upp en värld av möjligheter för dina Java-applikationer.

## FAQ's
### Kan jag anpassa egenskaperna för linjeformen?
Ja, du kan anpassa olika egenskaper som linjefärg, bredd, stil och mer med Aspose.Slides API.
### Är Aspose.Slides kompatibel med olika versioner av PowerPoint?
Ja, Aspose.Slides stöder olika PowerPoint-format, inklusive PPT, PPTX och andra, vilket säkerställer kompatibilitet mellan olika versioner.
### Ger Aspose.Slides stöd för att lägga till andra former än linjer?
Absolut! Aspose.Slides erbjuder ett brett utbud av formtyper, inklusive rektanglar, cirklar, pilar och mer.
### Kan jag lägga till text på bilden tillsammans med linjeformen?
Ja, du kan lägga till text, bilder och annat innehåll till bilden med Aspose.Slides API.
### Finns det en gratis testversion tillgänglig för Aspose.Slides?
Ja, du kan ladda ner en gratis testversion av Aspose.Slides från[här](https://releases.aspose.com/).