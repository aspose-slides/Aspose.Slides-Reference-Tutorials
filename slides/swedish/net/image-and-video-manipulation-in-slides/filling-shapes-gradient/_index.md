---
title: Skapa fantastiska gradienter i PowerPoint med Aspose.Slides
linktitle: Fylla former med gradient i presentationsbilder med Aspose.Slides
second_title: Aspose.Slides .NET PowerPoint Processing API
description: Förbättra dina presentationer med Aspose.Slides för .NET! Lär dig steg-för-steg-processen för att fylla former med gradienter. Ladda ner din kostnadsfria testversion nu!
type: docs
weight: 21
url: /sv/net/image-and-video-manipulation-in-slides/filling-shapes-gradient/
---
## Introduktion
Att skapa visuellt fängslande presentationsbilder är viktigt för att fånga och behålla din publiks uppmärksamhet. I den här handledningen går vi igenom processen att förbättra dina bilder genom att fylla en ellipsform med en gradient med Aspose.Slides för .NET.
## Förutsättningar
Innan vi börjar, se till att du har följande:
- Grundläggande kunskaper i programmeringsspråket C#.
- Visual Studio installerat på din dator.
-  Aspose.Slides för .NET-bibliotek. Ladda ner det[här](https://releases.aspose.com/slides/net/).
- En projektkatalog för att organisera dina filer.
## Importera namnområden
I ditt C#-projekt, inkludera de nödvändiga namnrymden för Aspose.Slides:
```csharp
using System.IO;
using Aspose.Slides;
using Aspose.Slides.Export;
```
## Steg 1: Skapa en presentation
Börja med att skapa en ny presentation med Aspose.Slides-biblioteket:
```csharp
string dataDir = "Your Documents Directory";
bool IsExists = System.IO.Directory.Exists(dataDir);
if (!IsExists)
    System.IO.Directory.CreateDirectory(dataDir);
using (Presentation pres = new Presentation())
{
    // Din kod kommer hit...
}
```
## Steg 2: Lägg till en Ellipsform
Infoga en ellipsform i den första bilden av din presentation:
```csharp
ISlide sld = pres.Slides[0];
IShape shp = sld.Shapes.AddAutoShape(ShapeType.Ellipse, 50, 150, 75, 150);
```
## Steg 3: Använd gradientformatering
Ange att formen ska fyllas med en gradient och definiera gradientegenskaperna:
```csharp
shp.FillFormat.FillType = FillType.Gradient;
shp.FillFormat.GradientFormat.GradientShape = GradientShape.Linear;
shp.FillFormat.GradientFormat.GradientDirection = GradientDirection.FromCorner2;
```
## Steg 4: Lägg till gradientstopp
Definiera färgerna och positionerna för gradientstoppen:
```csharp
shp.FillFormat.GradientFormat.GradientStops.Add((float)1.0, PresetColor.Purple);
shp.FillFormat.GradientFormat.GradientStops.Add((float)0, PresetColor.Red);
```
## Steg 5: Spara presentationen
Spara din presentation med den nyligen tillagda gradientfyllda formen:
```csharp
pres.Save(dataDir + "EllipseShpGrad_out.pptx", SaveFormat.Pptx);
```
Upprepa dessa steg i din C#-kod, och säkerställ korrekt sekvens och parametervärden. Detta kommer att resultera i en presentationsfil med en visuellt tilltalande ellipsform fylld med en gradient.
## Slutsats
With Aspose.Slides for .NET, you can effortlessly elevate the visual aesthetics of your presentations. By following this guide, you've learned how to fill shapes with gradients, giving your slides a professional and engaging look.
---
## Vanliga frågor
### F: Kan jag tillämpa gradienter på andra former än ellipser?
A: Visst! Aspose.Slides för .NET stöder gradientfyllning för olika former som rektanglar, polygoner och mer.
### F: Var kan jag hitta ytterligare exempel och detaljerad dokumentation?
 S: Utforska[Aspose.Slides för .NET-dokumentation](https://reference.aspose.com/slides/net/) för omfattande guider och exempel.
### F: Finns det en gratis testversion tillgänglig för Aspose.Slides för .NET?
 S: Ja, du kan få tillgång till en gratis provperiod[här](https://releases.aspose.com/).
### F: Hur kan jag få support för Aspose.Slides för .NET?
 S: Sök hjälp och engagera dig i samhället[Aspose.Slides forum](https://forum.aspose.com/c/slides/11).
### F: Kan jag köpa en tillfällig licens för Aspose.Slides för .NET?
 S: Visst kan du få en tillfällig licens[här](https://purchase.aspose.com/temporary-license/).