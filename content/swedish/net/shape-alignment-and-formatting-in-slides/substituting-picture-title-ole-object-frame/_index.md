---
title: Bädda in OLE-objektguide med Aspose.Slides för .NET
linktitle: Ersätter bildtitel för OLE-objektram i presentationsbilder
second_title: Aspose.Slides .NET PowerPoint Processing API
description: Lär dig hur du förbättrar dina presentationsbilder med dynamiska OLE-objekt med Aspose.Slides för .NET. Följ vår steg-för-steg-guide för sömlös integration.
type: docs
weight: 15
url: /sv/net/shape-alignment-and-formatting-in-slides/substituting-picture-title-ole-object-frame/
---
## Introduktion
Att skapa dynamiska och engagerande presentationsbilder involverar ofta inkorporering av olika multimediaelement. I den här självstudien kommer vi att undersöka hur man ersätter bildrubriken för en OLE (Object Linking and Embedding)-objektram i presentationsbilder med hjälp av det kraftfulla Aspose.Slides for .NET-biblioteket. Aspose.Slides förenklar processen att hantera OLE-objekt, vilket ger utvecklare verktygen för att förbättra sina presentationer med lätthet.
## Förutsättningar
Innan vi dyker in i steg-för-steg-guiden, se till att du har följande förutsättningar på plats:
-  Aspose.Slides for .NET Library: Se till att du har Aspose.Slides for .NET-biblioteket installerat. Du kan ladda ner den från[Aspose.Slides .NET dokumentation](https://reference.aspose.com/slides/net/).
- Exempeldata: Förbered ett exempel på en Excel-fil (t.ex. "ExcelObject.xlsx") som du vill bädda in som ett OLE-objekt i presentationen. Dessutom, ha en bildfil (t.ex. "Image.png") som kommer att fungera som ikonen för OLE-objektet.
- Utvecklingsmiljö: Skapa en utvecklingsmiljö med nödvändiga verktyg, som Visual Studio eller någon annan föredragen IDE för .NET-utveckling.
## Importera namnområden
I ditt .NET-projekt, se till att importera de nödvändiga namnrymden för att arbeta med Aspose.Slides:
```csharp
using Aspose.Slides;
using Aspose.Slides.Examples.CSharp;
using System;
using System.Collections.Generic;
using System.Drawing;
using System.IO;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
using Aspose.Slides.DOM.Ole;
```
## Steg 1: Konfigurera dokumentkatalogen
```csharp
string dataDir = "Your Document Directory";
```
Se till att ersätta "Din dokumentkatalog" med den faktiska sökvägen till din dokumentkatalog.
## Steg 2: Definiera sökvägar för OLE-källfil och ikonfil
```csharp
string oleSourceFile = dataDir + "ExcelObject.xlsx";
string oleIconFile = dataDir + "Image.png";
```
Uppdatera dessa sökvägar med de faktiska sökvägarna till din exempelfil och bildfil i Excel.
## Steg 3: Skapa en presentationsinstans
```csharp
using (Presentation pres = new Presentation())
{
    // Koden för efterföljande steg kommer hit
}
```
 Initiera en ny instans av`Presentation` klass.
## Steg 4: Lägg till OLE Object Frame
```csharp
ISlide slide = pres.Slides[0];
byte[] allbytes = File.ReadAllBytes(oleSourceFile);
IOleEmbeddedDataInfo dataInfo = new OleEmbeddedDataInfo(allbytes, "xlsx");
IOleObjectFrame oof = slide.Shapes.AddOleObjectFrame(20, 20, 50, 50, dataInfo);
oof.IsObjectIcon = true;
```
Lägg till en OLE-objektram till bilden och ange dess position och dimensioner.
## Steg 5: Lägg till bildobjekt
```csharp
byte[] imgBuf = File.ReadAllBytes(oleIconFile);
using (MemoryStream ms = new MemoryStream(imgBuf))
{
    IPPImage image = pres.Images.AddImage(new Bitmap(ms));
}
```
Läs bildfilen och lägg till den i presentationen som ett bildobjekt.
## Steg 6: Ställ in bildtext till OLE-ikon
```csharp
oof.SubstitutePictureTitle = "Caption example";
```
Ställ in önskad bildtext för OLE-ikonen.
## Slutsats
Att införliva OLE-objekt i dina presentationsbilder med Aspose.Slides för .NET är en enkel process. Denna handledning har guidat dig genom de väsentliga stegen, från att ställa in dokumentkatalogen till att lägga till och anpassa OLE-objekt. Experimentera med olika filtyper och bildtexter för att förbättra dina presentationers visuella tilltalande.
## Vanliga frågor
### Kan jag bädda in andra typer av filer som OLE-objekt med Aspose.Slides?
Ja, Aspose.Slides stöder inbäddning av olika typer av filer, som Excel-kalkylblad, Word-dokument och mer.
### Är OLE-objektikonen anpassningsbar?
Absolut. Du kan ersätta standardikonen med valfri bild för att bättre passa din presentations tema.
### Ger Aspose.Slides stöd för animeringar med OLE-objekt?
Från och med den senaste versionen fokuserar Aspose.Slides på inbäddning och visning av OLE-objekt, och hanterar inte direkt animationer i OLE-objekten.
### Kan jag manipulera OLE-objekt programmatiskt efter att ha lagt till dem på en bild?
Säkert. Du har full programmatisk kontroll över OLE-objekt, så att du kan ändra deras egenskaper och utseende efter behov.
### Finns det några begränsningar för storleken på de inbäddade OLE-objekten?
Även om det finns storleksbegränsningar är de generellt generösa. Det rekommenderas att testa med ditt specifika användningsfall för att säkerställa optimal prestanda.