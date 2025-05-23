---
"description": "Lär dig hur du förbättrar PowerPoint-presentationer med Aspose.Slides för .NET. Följ vår steg-för-steg-guide för att lägga till stretchoffset till vänster för bildramar."
"linktitle": "Lägga till sträckningsförskjutning till vänster för bildram i Aspose.Slides"
"second_title": "Aspose.Slides .NET PowerPoint-bearbetnings-API"
"title": "Lägga till stretchoffset till vänster i PowerPoint med Aspose.Slide"
"url": "/sv/net/shape-alignment-and-formatting-in-slides/adding-stretch-offset-left-picture-frame/"
"weight": 14
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Lägga till stretchoffset till vänster i PowerPoint med Aspose.Slide

## Introduktion
Aspose.Slides för .NET är ett kraftfullt bibliotek som gör det möjligt för utvecklare att enkelt manipulera PowerPoint-presentationer. I den här handledningen utforskar vi processen att lägga till en sträckningsförskjutning till vänster för en bildram med hjälp av Aspose.Slides för .NET. Följ den här steg-för-steg-guiden för att förbättra dina färdigheter i att arbeta med bilder och former i PowerPoint-presentationer.
## Förkunskapskrav
Innan du börjar med handledningen, se till att du har följande förutsättningar på plats:
- Aspose.Slides för .NET: Se till att du har biblioteket installerat. Om inte, ladda ner det från [Aspose.Slides för .NET-dokumentation](https://reference.aspose.com/slides/net/).
- Utvecklingsmiljö: Ha en fungerande utvecklingsmiljö med .NET-funktioner.
## Importera namnrymder
Börja med att importera de nödvändiga namnrymderna i ditt .NET-projekt:
```csharp
using System.IO;
using Aspose.Slides;
using System.Drawing;
using Aspose.Slides.Export;
```
## Steg 1: Konfigurera ditt projekt
Skapa ett nytt projekt eller öppna ett befintligt. Se till att du har refererat till Aspose.Slides-biblioteket i ditt projekt.
## Steg 2: Skapa presentationsobjekt
Instansiera `Presentation` klass, som representerar PPTX-filen:
```csharp
using (Presentation pres = new Presentation())
{
    // Din kod för efterföljande steg kommer att placeras här.
}
```
## Steg 3: Hämta den första bilden
Hämta den första bilden från presentationen:
```csharp
ISlide slide = pres.Slides[0];
```
## Steg 4: Instansiera bilden
Ladda bilden du vill använda:
```csharp
System.Drawing.Image img = (System.Drawing.Image)new Bitmap(dataDir + "aspose-logo.jpg");
IPPImage imgEx = pres.Images.AddImage(img);
```
## Steg 5: Lägg till rektangelformad autoform
Skapa en autoform av typen rektangel:
```csharp
IAutoShape aShape = slide.Shapes.AddAutoShape(ShapeType.Rectangle, 100, 100, 300, 300);
```
## Steg 6: Ställ in fyllningstyp och bildfyllningsläge
Konfigurera formens fyllningstyp och bildfyllningsläge:
```csharp
aShape.FillFormat.FillType = FillType.Picture;
aShape.FillFormat.PictureFillFormat.PictureFillMode = PictureFillMode.Stretch;
```
## Steg 7: Ställ in bilden för att fylla formen
Ange bilden som ska fylla formen:
```csharp
aShape.FillFormat.PictureFillFormat.Picture.Image = imgEx;
```
## Steg 8: Ange sträckningsförskjutningar
Definiera bildförskjutningarna från motsvarande kanter i formens avgränsningsram:
```csharp
aShape.FillFormat.PictureFillFormat.StretchOffsetLeft = 25;
aShape.FillFormat.PictureFillFormat.StretchOffsetRight = 25;
aShape.FillFormat.PictureFillFormat.StretchOffsetTop = -20;
aShape.FillFormat.PictureFillFormat.StretchOffsetBottom = -10;
```
## Steg 9: Spara presentationen
Skriv PPTX-filen till disk:
```csharp
pres.Save(dataDir + "StretchOffsetLeftForPictureFrame_out.pptx", SaveFormat.Pptx);
```
Grattis! Du har lagt till en sträckningsförskjutning till vänster för en bildram med hjälp av Aspose.Slides för .NET.
## Slutsats
I den här handledningen utforskade vi processen att manipulera bildramar i PowerPoint-presentationer med hjälp av Aspose.Slides för .NET. Genom att följa steg-för-steg-guiden har du fått insikter i hur du arbetar med bilder, former och offsets.
## Vanliga frågor
### F: Kan jag tillämpa sträckförskjutningar på andra former förutom rektanglar?
A: Även om den här handledningen fokuserar på rektanglar, kan sträckförskjutningar tillämpas på olika former som stöds av Aspose.Slides.
### F: Hur kan jag justera stretchoffsets för olika effekter?
A: Experimentera med olika offsetvärden för att uppnå önskad visuell effekt. Finjustera värdena så att de passar dina specifika behov.
### F: Är Aspose.Slides kompatibel med det senaste .NET-ramverket?
A: Aspose.Slides uppdateras regelbundet för att säkerställa kompatibilitet med de senaste versionerna av .NET Framework.
### F: Var kan jag hitta ytterligare exempel och resurser för Aspose.Slides?
A: Utforska [Aspose.Slides-dokumentation](https://reference.aspose.com/slides/net/) för omfattande exempel och vägledning.
### F: Kan jag tillämpa flera sträckningsförskjutningar på en enda form?
A: Ja, du kan kombinera flera stretchoffsets för att uppnå komplexa och anpassade visuella effekter.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}