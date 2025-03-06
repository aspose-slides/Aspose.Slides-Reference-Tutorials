---
title: Lägga till Stretch Offset till vänster i PowerPoint med Aspose.Slide
linktitle: Lägga till Stretch Offset till vänster för bildram i Aspose.Slides
second_title: Aspose.Slides .NET PowerPoint Processing API
description: Lär dig hur du förbättrar PowerPoint-presentationer med Aspose.Slides för .NET. Följ vår steg-för-steg-guide för att lägga till stretch offset till vänster för bildramar.
weight: 14
url: /sv/net/shape-alignment-and-formatting-in-slides/adding-stretch-offset-left-picture-frame/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Lägga till Stretch Offset till vänster i PowerPoint med Aspose.Slide

## Introduktion
Aspose.Slides för .NET är ett kraftfullt bibliotek som ger utvecklare möjlighet att manipulera PowerPoint-presentationer med lätthet. I den här handledningen kommer vi att utforska processen att lägga till en sträckförskjutning till vänster för en bildram med Aspose.Slides för .NET. Följ den här steg-för-steg-guiden för att förbättra dina färdigheter i att arbeta med bilder och former i PowerPoint-presentationer.
## Förutsättningar
Innan du dyker in i handledningen, se till att du har följande förutsättningar på plats:
-  Aspose.Slides för .NET: Se till att du har biblioteket installerat. Om inte, ladda ner den från[Aspose.Slides för .NET-dokumentation](https://reference.aspose.com/slides/net/).
- Utvecklingsmiljö: Ha en fungerande utvecklingsmiljö med .NET-funktioner.
## Importera namnområden
Börja med att importera de nödvändiga namnområdena i ditt .NET-projekt:
```csharp
using System.IO;
using Aspose.Slides;
using System.Drawing;
using Aspose.Slides.Export;
```
## Steg 1: Konfigurera ditt projekt
Skapa ett nytt projekt eller öppna ett befintligt. Se till att du har Aspose.Slides-biblioteket som refereras till i ditt projekt.
## Steg 2: Skapa presentationsobjekt
 Instantiera`Presentation` klass, som representerar PPTX-filen:
```csharp
using (Presentation pres = new Presentation())
{
    // Din kod för efterföljande steg kommer hit.
}
```
## Steg 3: Skaffa den första bilden
Hämta den första bilden från presentationen:
```csharp
ISlide slide = pres.Slides[0];
```
## Steg 4: Instantiera bilden
Ladda bilden du vill använda:
```csharp
System.Drawing.Image img = (System.Drawing.Image)new Bitmap(dataDir + "aspose-logo.jpg");
IPPImage imgEx = pres.Images.AddImage(img);
```
## Steg 5: Lägg till Rectangle AutoShape
Skapa en AutoShape av rektangeltyp:
```csharp
IAutoShape aShape = slide.Shapes.AddAutoShape(ShapeType.Rectangle, 100, 100, 300, 300);
```
## Steg 6: Ställ in fyllningstyp och bildfyllningsläge
Konfigurera formens fyllningstyp och bildfyllningsläge:
```csharp
aShape.FillFormat.FillType = FillType.Picture;
aShape.FillFormat.PictureFillFormat.PictureFillMode = PictureFillMode.Stretch;
```
## Steg 7: Ställ in bild för att fylla formen
Ange bilden för att fylla formen:
```csharp
aShape.FillFormat.PictureFillFormat.Picture.Image = imgEx;
```
## Steg 8: Ange Stretch Offsets
Definiera bildförskjutningarna från motsvarande kanter på formens begränsningsram:
```csharp
aShape.FillFormat.PictureFillFormat.StretchOffsetLeft = 25;
aShape.FillFormat.PictureFillFormat.StretchOffsetRight = 25;
aShape.FillFormat.PictureFillFormat.StretchOffsetTop = -20;
aShape.FillFormat.PictureFillFormat.StretchOffsetBottom = -10;
```
## Steg 9: Spara presentationen
Skriv PPTX-filen till disken:
```csharp
pres.Save(dataDir + "StretchOffsetLeftForPictureFrame_out.pptx", SaveFormat.Pptx);
```
Grattis! Du har framgångsrikt lagt till en sträckförskjutning till vänster för en bildram med Aspose.Slides för .NET.
## Slutsats
I den här handledningen utforskade vi processen att manipulera bildramar i PowerPoint-presentationer med Aspose.Slides för .NET. Genom att följa den steg-för-steg-guiden har du fått insikter i att arbeta med bilder, former och förskjutningar.
## Vanliga frågor
### F: Kan jag använda sträckförskjutningar på andra former förutom rektanglar?
S: Även om den här handledningen fokuserar på rektanglar, kan sträckförskjutningar tillämpas på olika former som stöds av Aspose.Slides.
### F: Hur kan jag justera stretch offseten för olika effekter?
S: Experimentera med olika offsetvärden för att uppnå önskad visuell effekt. Finjustera värdena för att passa dina specifika krav.
### F: Är Aspose.Slides kompatibel med det senaste .NET-ramverket?
S: Aspose.Slides uppdateras regelbundet för att säkerställa kompatibilitet med de senaste .NET framework-versionerna.
### F: Var kan jag hitta ytterligare exempel och resurser för Aspose.Slides?
 S: Utforska[Aspose.Slides dokumentation](https://reference.aspose.com/slides/net/) för omfattande exempel och vägledning.
### F: Kan jag tillämpa flera sträckförskjutningar på en enda form?
S: Ja, du kan kombinera flera sträckförskjutningar för att uppnå komplexa och anpassade visuella effekter.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
