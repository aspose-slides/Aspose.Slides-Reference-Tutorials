---
"description": "Lär dig hur du lägger till kreativa skissade former i dina presentationsbilder med Aspose.Slides för .NET. Förbättra det visuella utseendet utan ansträngning!"
"linktitle": "Skapa skissade former i presentationsbilder med Aspose.Slides"
"second_title": "Aspose.Slides .NET PowerPoint-bearbetnings-API"
"title": "Skapa fantastiska skissade former med Aspose.Slides"
"url": "/sv/net/shape-alignment-and-formatting-in-slides/creating-sketched-shapes/"
"weight": 13
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Skapa fantastiska skissade former med Aspose.Slides

## Introduktion
Välkommen till vår steg-för-steg-guide om hur du skapar skissade former i presentationsbilder med Aspose.Slides för .NET. Om du vill lägga till en touch av kreativitet i dina presentationer ger skissade former en unik och handritad estetik. I den här handledningen kommer vi att guida dig genom processen och dela upp den i enkla steg för att säkerställa en smidig upplevelse.
## Förkunskapskrav
Innan vi dyker in i handledningen, se till att du har följande förutsättningar på plats:
- Aspose.Slides för .NET: Se till att du har Aspose.Slides-biblioteket för .NET installerat. Du kan ladda ner det [här](https://releases.aspose.com/slides/net/).
- Utvecklingsmiljö: Konfigurera en .NET-utvecklingsmiljö med din föredragna IDE.
## Importera namnrymder
Börja med att importera de nödvändiga namnrymderna i ditt .NET-projekt. Detta steg säkerställer att du har tillgång till de klasser och funktioner som krävs för att arbeta med Aspose.Slides.
```csharp
using System;
using System.Collections.Generic;
using System.Drawing.Imaging;
using System.IO;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
using Aspose.Slides;
using Aspose.Slides.Examples.CSharp;
using Aspose.Slides.Util;
using Aspose.Slides.Export;
using Aspose.Slides.MathText;
```
## Steg 1: Konfigurera projektet
Börja med att skapa ett nytt .NET-projekt eller öppna ett befintligt. Se till att inkludera Aspose.Slides i dina projektreferenser.
## Steg 2: Initiera Aspose.Slides
Initiera Aspose.Slides genom att lägga till följande kodavsnitt. Detta konfigurerar presentationen och anger sökvägarna för presentationsfilen och miniatyrbilden.
```csharp
string dataDir = "Your Document Directory";
string outPptxFile = Path.Combine(dataDir, "SketchedShapes_out.pptx");
string outPngFile = Path.Combine(dataDir, "SketchedShapes_out.png");
using (Presentation pres = new Presentation())
{
    // Fortsätt till nästa steg...
}
```
## Steg 3: Lägg till skissad form
Nu ska vi lägga till en skissad form på bilden. I det här exemplet lägger vi till en rektangel med en frihandsskisseffekt.
```csharp
IAutoShape shape = pres.Slides[0].Shapes.AddAutoShape(ShapeType.Rectangle, 20, 20, 300, 150);
shape.FillFormat.FillType = FillType.NoFill;
// Omvandla form till skiss av en frihandsstil
shape.LineFormat.SketchFormat.SketchType = LineSketchType.Scribble;
```
## Steg 4: Generera miniatyrbild
Generera en miniatyrbild av bilden för att visualisera den skissade formen. Spara miniatyrbilden som en PNG-fil.
```csharp
pres.Slides[0].GetThumbnail(4/3f, 4/3f).Save(outPngFile, ImageFormat.Png);
```
## Steg 5: Spara presentationen
Spara presentationsfilen med den skissade formen.
```csharp
pres.Save(outPptxFile, SaveFormat.Pptx);
```
Det var allt! Du har skapat en presentation med skissade former med Aspose.Slides för .NET.
## Slutsats
Att lägga till skissade former i dina presentationsbilder kan förbättra det visuella intrycket och engagera din publik. Med Aspose.Slides för .NET blir processen enkel, vilket gör att du kan släppa lös din kreativitet utan ansträngning.
## Vanliga frågor
### 1. Kan jag anpassa den skissade effekten?
Ja, Aspose.Slides för .NET erbjuder olika anpassningsalternativ för skissade effekter. Se [dokumentation](https://reference.aspose.com/slides/net/) för detaljerad information.
### 2. Finns det en gratis provperiod tillgänglig?
Absolut! Du kan utforska en gratis provperiod av Aspose.Slides för .NET [här](https://releases.aspose.com/).
### 3. Var kan jag få stöd?
För hjälp eller frågor, besök [Aspose.Slides-forum](https://forum.aspose.com/c/slides/11).
### 4. Hur kan jag köpa Aspose.Slides för .NET?
För att köpa Aspose.Slides för .NET, besök [köpsida](https://purchase.aspose.com/buy).
### 5. Erbjuder ni tillfälliga licenser?
Ja, tillfälliga licenser finns tillgängliga [här](https://purchase.aspose.com/temporary-license/).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}