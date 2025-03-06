---
title: Lägga till Stretch Offset för bildfyllning i PowerPoint-presentationer
linktitle: Lägga till Stretch Offset för bildfyllning i diabilder
second_title: Aspose.Slides .NET PowerPoint Processing API
description: Lär dig hur du förbättrar PowerPoint-presentationer med Aspose.Slides för .NET. Följ en steg-för-steg-guide för att lägga till en sträckförskjutning för bildfyllning.
weight: 18
url: /sv/net/shape-effects-and-manipulation-in-slides/adding-stretch-offset-image-fill/
---

{< blocks/products/pf/main-wrap-class >}
{< blocks/products/pf/main-container >}
{< blocks/products/pf/tutorial-page-section >}

## Introduktion
I presentationens dynamiska värld spelar visuella bilder en avgörande roll för att fånga publikens uppmärksamhet. Aspose.Slides för .NET ger utvecklare möjlighet att förbättra sina PowerPoint-presentationer genom att tillhandahålla en robust uppsättning funktioner. En sådan funktion är möjligheten att lägga till en stretchoffset för bildfyllning, vilket möjliggör kreativa och visuellt tilltalande bilder.
## Förutsättningar
Innan du dyker in i handledningen, se till att du har följande förutsättningar på plats:
1.  Aspose.Slides för .NET Library: Ladda ner och installera biblioteket från[Aspose.Slides för .NET-dokumentation](https://reference.aspose.com/slides/net/).
2. Utvecklingsmiljö: Se till att du har en fungerande .NET-utvecklingsmiljö inrättad.
Låt oss nu komma igång med steg-för-steg-guiden.
## Importera namnområden
Importera först de nödvändiga namnområdena för att utnyttja Aspose.Slides-funktionaliteten i din .NET-applikation.
```csharp
using System.IO;
using Aspose.Slides;
using System.Drawing;
using Aspose.Slides.Export;
```
## Steg 1: Konfigurera ditt projekt
Skapa ett nytt .NET-projekt i din föredragna utvecklingsmiljö. Se till att Aspose.Slides för .NET är korrekt refererad.
## Steg 2: Initiera presentationsklass
 Instantiera`Presentation` klass för att representera PowerPoint-filen.
```csharp
string dataDir = "Your Document Directory";
bool isExists = System.IO.Directory.Exists(dataDir);
if (!isExists)
    System.IO.Directory.CreateDirectory(dataDir);
using (Presentation pres = new Presentation())
{
    // Din kod kommer hit
}
```
## Steg 3: Skaffa den första bilden
Hämta den första bilden från presentationen att arbeta med.
```csharp
ISlide sld = pres.Slides[0];
```
## Steg 4: Instantiera ImageEx Class
 Skapa en instans av`ImageEx`klass för att hantera bilden du vill lägga till på bilden.
```csharp
System.Drawing.Image img = (System.Drawing.Image)new Bitmap(dataDir + "aspose-logo.jpg");
IPPImage imgx = pres.Images.AddImage(img);
```
## Steg 5: Lägg till bildram
 Använd`AddPictureFrame` metod för att lägga till en bildram till bilden. Ange mått och placering av ramen.
```csharp
sld.Shapes.AddPictureFrame(ShapeType.Rectangle, 50, 150, imgx.Width, imgx.Height, imgx);
```
## Steg 6: Spara presentationen
Spara den ändrade presentationen på disk.
```csharp
pres.Save(dataDir + "AddStretchOffsetForImageFill_out.pptx", SaveFormat.Pptx);
```
Det är allt! Du har framgångsrikt lagt till en sträckförskjutning för bildfyll i bilder med Aspose.Slides för .NET.
## Slutsats
Att förbättra dina PowerPoint-presentationer är nu enklare än någonsin med Aspose.Slides för .NET. Genom att följa den här handledningen har du lärt dig hur du kan införliva stretch offset för bildfyllning, vilket ger en ny nivå av kreativitet till dina bilder.
## Vanliga frågor
### Kan jag använda Aspose.Slides för .NET i mina webbapplikationer?
Ja, Aspose.Slides för .NET är lämplig för både skrivbords- och webbapplikationer.
### Finns det en gratis testversion tillgänglig för Aspose.Slides för .NET?
 Ja, du kan ladda ner en gratis testversion från[här](https://releases.aspose.com/).
### Hur kan jag få support för Aspose.Slides för .NET?
 Besök[Aspose.Slides forum](https://forum.aspose.com/c/slides/11) för samhällsstöd.
### Var kan jag hitta den fullständiga dokumentationen för Aspose.Slides för .NET?
 Referera till[dokumentation](https://reference.aspose.com/slides/net/) för detaljerad information.
### Kan jag köpa Aspose.Slides för .NET?
 Ja, du kan köpa produkten[här](https://purchase.aspose.com/buy).
{< /blocks/products/pf/tutorial-page-section >}

{< /blocks/products/pf/main-container >}
{< /blocks/products/pf/main-wrap-class >}

{< blocks/products/products-backtop-button >}
