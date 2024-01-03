---
title: Skapa fantastiska skissade former med Aspose.Slides
linktitle: Skapa skissade former i presentationsbilder med Aspose.Slides
second_title: Aspose.Slides .NET PowerPoint Processing API
description: Lär dig hur du lägger till kreativa skissade former till dina presentationsbilder med Aspose.Slides för .NET. Förbättra visuellt tilltal utan ansträngning!
type: docs
weight: 13
url: /sv/net/shape-alignment-and-formatting-in-slides/creating-sketched-shapes/
---
## Introduktion
Välkommen till vår steg-för-steg-guide för att skapa skissade former i presentationsbilder med Aspose.Slides för .NET. Om du vill lägga till en touch av kreativitet till dina presentationer, ger skissade former en unik och handritad estetik. I den här handledningen går vi igenom processen och delar upp den i enkla steg för att säkerställa en smidig upplevelse.
## Förutsättningar
Innan vi dyker in i handledningen, se till att du har följande förutsättningar på plats:
-  Aspose.Slides för .NET: Se till att du har Aspose.Slides-biblioteket för .NET installerat. Du kan ladda ner den[här](https://releases.aspose.com/slides/net/).
- Utvecklingsmiljö: Konfigurera en .NET-utvecklingsmiljö med din föredragna IDE.
## Importera namnområden
Börja med att importera de nödvändiga namnområdena i ditt .NET-projekt. Detta steg säkerställer att du har tillgång till de klasser och funktioner som krävs för att arbeta med Aspose.Slides.
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
Initiera Aspose.Slides genom att lägga till följande kodavsnitt. Detta ställer in presentationen och anger utdatasökvägarna för presentationsfilen och miniatyrbilden.
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
Låt oss nu lägga till en skissad form på bilden. I det här exemplet lägger vi till en rektangel med en frihandsskisseffekt.
```csharp
IAutoShape shape = pres.Slides[0].Shapes.AddAutoShape(ShapeType.Rectangle, 20, 20, 300, 150);
shape.FillFormat.FillType = FillType.NoFill;
// Förvandla form till skiss av en frihandsstil
shape.LineFormat.SketchFormat.SketchType = LineSketchType.Scribble;
```
## Steg 4: Skapa miniatyrbild
Skapa en miniatyrbild av bilden för att visualisera den skissade formen. Spara miniatyren som en PNG-fil.
```csharp
pres.Slides[0].GetThumbnail(4/3f, 4/3f).Save(outPngFile, ImageFormat.Png);
```
## Steg 5: Spara presentationen
Spara presentationsfilen med den skissade formen.
```csharp
pres.Save(outPptxFile, SaveFormat.Pptx);
```
Det är allt! Du har framgångsrikt skapat en presentation med skissade former med Aspose.Slides för .NET.
## Slutsats
Genom att lägga till skissade former till dina presentationsbilder kan du förbättra den visuella överklagandet och engagera din publik. Med Aspose.Slides för .NET blir processen enkel, så att du kan släppa loss din kreativitet utan ansträngning.
## Vanliga frågor
### 1. Kan jag anpassa den skissade effekten?
Ja, Aspose.Slides för .NET tillhandahåller olika anpassningsalternativ för skissade effekter. Referera till[dokumentation](https://reference.aspose.com/slides/net/) för detaljerad information.
### 2. Finns det en gratis provperiod?
 Säkert! Du kan utforska en gratis testversion av Aspose.Slides för .NET[här](https://releases.aspose.com/).
### 3. Var kan jag få stöd?
 För all hjälp eller frågor, besök[Aspose.Slides forum](https://forum.aspose.com/c/slides/11).
### 4. Hur kan jag köpa Aspose.Slides för .NET?
 För att köpa Aspose.Slides för .NET, besök[köpsidan](https://purchase.aspose.com/buy).
### 5. Erbjuder ni tillfälliga licenser?
 Ja, tillfälliga licenser är tillgängliga[här](https://purchase.aspose.com/temporary-license/).