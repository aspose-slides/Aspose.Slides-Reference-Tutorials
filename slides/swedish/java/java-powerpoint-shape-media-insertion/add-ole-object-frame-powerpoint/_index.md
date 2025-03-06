---
title: Lägg till OLE Object Frame i PowerPoint
linktitle: Lägg till OLE Object Frame i PowerPoint
second_title: Aspose.Slides Java PowerPoint Processing API
description: Lär dig hur du sömlöst integrerar OLE Object Frames i PowerPoint-presentationer med Aspose.Slides för Java.
weight: 13
url: /sv/java/java-powerpoint-shape-media-insertion/add-ole-object-frame-powerpoint/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Lägg till OLE Object Frame i PowerPoint

## Introduktion
Att lägga till en OLE (Object Linking and Embedding)-objektram i PowerPoint-presentationer kan avsevärt förbättra dina bilders visuella tilltalande och funktionalitet. Med Aspose.Slides för Java blir denna process strömlinjeformad och effektiv. I den här självstudien guidar vi dig genom stegen som krävs för att sömlöst integrera OLE Object Frames i dina PowerPoint-presentationer.
### Förutsättningar
Innan vi börjar, se till att du har följande förutsättningar på plats:
1. Java Development Environment: Se till att du har Java Development Kit (JDK) installerat på ditt system.
2.  Aspose.Slides för Java: Ladda ner och installera Aspose.Slides för Java från webbplatsen[här](https://releases.aspose.com/slides/java/).
3. Grundläggande förståelse för Java-programmering: Bekanta dig med Java-programmeringskoncept och -syntax.
## Importera paket
För det första måste du importera de nödvändiga paketen för att utnyttja funktionerna i Aspose.Slides för Java. Så här kan du göra det:
```java
import com.aspose.slides.*;

import java.io.ByteArrayOutputStream;
import java.io.File;
import java.io.FileInputStream;
import java.io.IOException;
```
## Steg 1: Ställ in din miljö
Se till att ditt projekt är korrekt konfigurerat och att Aspose.Slides-biblioteket ingår i din klassväg.
## Steg 2: Initiera presentationsobjekt
Skapa ett presentationsobjekt för att representera PowerPoint-filen du arbetar med:
```java
String dataDir = "Your Document Directory";
String outPath = "Your Output Directory";
// Instantiate Presentation-klass som representerar PPTX
Presentation pres = new Presentation();
```
## Steg 3: Gå till bild och ladda objekt
Gå till bilden där du vill lägga till OLE Object Frame och ladda objektfilen:
```java
ISlide sld = pres.getSlides().get_Item(0);
// Ladda en fil för att streama
FileInputStream fs = new FileInputStream(dataDir + "book1.xlsx");
ByteArrayOutputStream mstream = new ByteArrayOutputStream();
byte[] buf = new byte[4096];
while (true) {
    int bytesRead = fs.read(buf, 0, buf.length);
    if (bytesRead <= 0)
        break;
    mstream.write(buf, 0, bytesRead);
}
```
## Steg 4: Skapa inbäddat dataobjekt
Skapa ett dataobjekt för att bädda in filen:
```java
IOleEmbeddedDataInfo dataInfo = new OleEmbeddedDataInfo(mstream.toByteArray(), "xlsx");
```
## Steg 5: Lägg till OLE Object Frame
Lägg till en OLE Object Frame-form till bilden:
```java
IOleObjectFrame oleObjectFrame = sld.getShapes().addOleObjectFrame(0, 0, (float)pres.getSlideSize().getSize().getWidth(),
        (float)pres.getSlideSize().getSize().getHeight(), dataInfo);
```
## Steg 6: Spara presentationen
Spara den ändrade presentationen på disken:
```java
pres.save(outPath + "OleEmbed_out.pptx", SaveFormat.Pptx);
```

## Slutsats
Grattis! Du har framgångsrikt lärt dig hur du lägger till en OLE-objektram i PowerPoint-presentationer med Aspose.Slides för Java. Denna kraftfulla funktion låter dig bädda in olika typer av objekt, vilket förbättrar dina bilders interaktivitet och visuella tilltalande.

## FAQ's
### Kan jag bädda in andra objekt än Excel-filer med Aspose.Slides för Java?
Ja, du kan bädda in olika typer av objekt inklusive Word-dokument, PDF-filer och mer.
### Är Aspose.Slides kompatibel med olika versioner av PowerPoint?
Aspose.Slides ger kompatibilitet med ett brett utbud av PowerPoint-versioner, vilket säkerställer sömlös integration.
### Kan jag anpassa utseendet på OLE-objektramen?
Absolut! Aspose.Slides erbjuder omfattande alternativ för att anpassa utseendet och beteendet hos OLE Object Frames.
### Finns det en testversion tillgänglig för Aspose.Slides för Java?
 Ja, du kan ladda ner en gratis testversion från[här](https://releases.aspose.com/).
### Var kan jag hitta support för Aspose.Slides för Java?
 Du kan söka stöd och hjälp från Aspose.Slides-forumet[här](https://forum.aspose.com/c/slides/11).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
