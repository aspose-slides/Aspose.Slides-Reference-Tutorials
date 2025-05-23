---
"description": "Lär dig hur du ändrar OLE-objektdata i PowerPoint med Aspose.Slides för Java. En steg-för-steg-guide för effektiva och enkla uppdateringar."
"linktitle": "Ändra OLE-objektdata i PowerPoint"
"second_title": "Aspose.Slides Java PowerPoint-bearbetnings-API"
"title": "Ändra OLE-objektdata i PowerPoint"
"url": "/sv/java/java-powerpoint-animation-shape-manipulation/change-ole-object-data-powerpoint/"
"weight": 14
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Ändra OLE-objektdata i PowerPoint

## Introduktion
Att ändra OLE-objektdata i PowerPoint-presentationer kan vara en avgörande uppgift när du behöver uppdatera inbäddat innehåll utan att manuellt redigera varje bild. Den här omfattande guiden guidar dig genom processen med Aspose.Slides för Java, ett kraftfullt bibliotek utformat för att hantera PowerPoint-presentationer. Oavsett om du är en erfaren utvecklare eller precis har börjat, kommer du att tycka att den här handledningen är hjälpsam och lätt att följa.
## Förkunskapskrav
Innan vi går in i koden, låt oss se till att du har allt du behöver för att komma igång.
1. Java Development Kit (JDK): Se till att du har JDK installerat på ditt system. Du kan ladda ner det från [Oracles webbplats](https://www.oracle.com/java/technologies/javase-downloads.html).
2. Aspose.Slides för Java: Ladda ner den senaste versionen från [Nedladdningssida för Aspose.Slides](https://releases.aspose.com/slides/java/).
3. Integrerad utvecklingsmiljö (IDE): Du kan använda vilken Java IDE som helst, till exempel IntelliJ IDEA, Eclipse eller NetBeans.
4. Aspose.Cells för Java: Detta krävs för att ändra den inbäddade datan i OLE-objektet. Ladda ner det från [Aspose.Cells nedladdningssida](https://releases.aspose.com/cells/java/).
5. Presentationsfil: Ha en PowerPoint-fil redo med ett inbäddat OLE-objekt. För den här handledningen ska vi namnge den `ChangeOLEObjectData.pptx`.
## Importera paket
Låt oss först importera de nödvändiga paketen i ditt Java-projekt.
```java
import com.aspose.cells.OoxmlSaveOptions;
import com.aspose.cells.Workbook;
import com.aspose.slides.*;

import java.io.ByteArrayInputStream;
import java.io.ByteArrayOutputStream;
```

Nu ska vi dela upp processen i enkla, hanterbara steg.
## Steg 1: Ladda PowerPoint-presentationen
För att börja måste du ladda PowerPoint-presentationen som innehåller OLE-objektet.
```java
// Sökvägen till dokumentkatalogen.
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "ChangeOLEObjectData.pptx");
```
## Steg 2: Öppna bilden som innehåller OLE-objektet
Hämta sedan bilden där OLE-objektet är inbäddat.
```java
ISlide slide = pres.getSlides().get_Item(0);
```
## Steg 3: Hitta OLE-objektet i bilden
Iterera genom formerna i bilden för att hitta OLE-objektet.
```java
OleObjectFrame ole = null;
// Korsar alla former för Ole-ramen
for (IShape shape : slide.getShapes()) {
    if (shape instanceof OleObjectFrame) {
        ole = (OleObjectFrame) shape;
        break;
    }
}
```
## Steg 4: Extrahera inbäddad data från OLE-objektet
Om OLE-objektet hittas, extrahera dess inbäddade data.
```java
if (ole != null) {
    ByteArrayInputStream msln = new ByteArrayInputStream(ole.getEmbeddedData().getEmbeddedFileData());
```
## Steg 5: Ändra den inbäddade datan med hjälp av Aspose.Cells
Använd nu Aspose.Cells för att läsa och ändra den inbäddade informationen, vilket i det här fallet troligen är en Excel-arbetsbok.
```java
    Workbook wb = new Workbook(msln);
    // Ändra arbetsboksdata
    wb.getWorksheets().get(0).getCells().get(0, 4).putValue("E");
    wb.getWorksheets().get(0).getCells().get(1, 4).putValue(12);
    wb.getWorksheets().get(0).getCells().get(2, 4).putValue(14);
    wb.getWorksheets().get(0).getCells().get(3, 4).putValue(15);
```
## Steg 6: Spara de modifierade data tillbaka till OLE-objektet
När du har gjort de nödvändiga ändringarna sparar du den ändrade arbetsboken tillbaka till OLE-objektet.
```java
    ByteArrayOutputStream msout = new ByteArrayOutputStream();
    OoxmlSaveOptions so1 = new OoxmlSaveOptions(SaveFormat.XLSX);
    wb.save(msout, so1);
    IOleEmbeddedDataInfo newData = new OleEmbeddedDataInfo(msout.toByteArray(), ole.getEmbeddedData().getEmbeddedFileExtension());
    ole.setEmbeddedData(newData);
```
## Steg 7: Spara den uppdaterade presentationen
Spara slutligen den uppdaterade PowerPoint-presentationen.
```java
    pres.save(dataDir + "OleEdit_out.pptx", SaveFormat.Pptx);
} catch (IOException e) {
    e.printStackTrace();
} finally {
    if (pres != null) pres.dispose();
}
```
## Slutsats
Att uppdatera OLE-objektdata i PowerPoint-presentationer med Aspose.Slides för Java är en enkel process när du väl har uppdelat den i enkla steg. Den här guiden guidade dig genom hur du laddar en presentation, öppnar och ändrar inbäddade OLE-data och sparar den uppdaterade presentationen. Med dessa steg kan du effektivt hantera och uppdatera inbäddat innehåll i dina PowerPoint-bilder programmatiskt.
## Vanliga frågor
### Vad är ett OLE-objekt i PowerPoint?
Ett OLE-objekt (Object Linking and Embedding) gör det möjligt att bädda in innehåll från andra program, som Excel-kalkylblad, i PowerPoint-bilder.
### Kan jag använda Aspose.Slides med andra programmeringsspråk?
Ja, Aspose.Slides stöder flera språk, inklusive .NET, Python och C++.
### Behöver jag Aspose.Cells för att modifiera OLE-objekt i PowerPoint?
Ja, om OLE-objektet är ett Excel-kalkylblad behöver du Aspose.Cells för att ändra det.
### Finns det en testversion av Aspose.Slides?
Ja, du kan få en [gratis provperiod](https://releases.aspose.com/) för att testa funktionerna i Aspose.Slides.
### Var kan jag hitta dokumentationen för Aspose.Slides?
Du kan hitta detaljerad dokumentation på [Dokumentationssida för Aspose.Slides](https://reference.aspose.com/slides/java/).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}