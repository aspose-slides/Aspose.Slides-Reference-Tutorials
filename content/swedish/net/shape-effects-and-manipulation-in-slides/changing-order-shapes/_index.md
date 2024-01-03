---
title: Omforma presentationsbilder med Aspose.Slides för .NET
linktitle: Ändra ordning på former i presentationsbilder med Aspose.Slides
second_title: Aspose.Slides .NET PowerPoint Processing API
description: Lär dig hur du omformar presentationsbilder med Aspose.Slides för .NET. Följ den här steg-för-steg-guiden för att ändra ordning på former och förbättra den visuella dragningskraften.
type: docs
weight: 26
url: /sv/net/shape-effects-and-manipulation-in-slides/changing-order-shapes/
---
## Introduktion
Att skapa visuellt tilltalande presentationsbilder är en avgörande aspekt av effektiv kommunikation. Aspose.Slides för .NET ger utvecklare möjlighet att manipulera bilder programmatiskt och erbjuder ett brett utbud av funktioner. I den här handledningen kommer vi att fördjupa oss i processen att ändra ordningen på former i presentationsbilder med Aspose.Slides för .NET.
## Förutsättningar
Innan vi ger oss ut på denna resa, se till att du har följande förutsättningar på plats:
-  Aspose.Slides för .NET: Se till att du har Aspose.Slides-biblioteket integrerat i ditt .NET-projekt. Om inte kan du ladda ner den från[släpper sida](https://releases.aspose.com/slides/net/).
- Utvecklingsmiljö: Skapa en fungerande utvecklingsmiljö med Visual Studio eller något annat .NET-utvecklingsverktyg.
- Grundläggande förståelse för C#: Bekanta dig med grunderna i programmeringsspråket C#.
## Importera namnområden
I ditt C#-projekt, inkludera de nödvändiga namnrymden för att komma åt Aspose.Slides-funktionen:
```csharp
using Aspose.Slides.Export;
using Aspose.Slides;
```
## Steg 1: Konfigurera ditt projekt
Skapa ett nytt projekt i Visual Studio eller din föredragna .NET-utvecklingsmiljö. Se till att Aspose.Slides för .NET refereras till i ditt projekt.
## Steg 2: Ladda presentationen
```csharp
string dataDir = "Your Document Directory";
Presentation presentation = new Presentation(dataDir + "HelloWorld.pptx");
```
## Steg 3: Få tillgång till bilden och formerna
```csharp
ISlide slide = presentation.Slides[0];
```
## Steg 4: Lägg till en ny form
```csharp
IAutoShape shp3 = slide.Shapes.AddAutoShape(ShapeType.Rectangle, 200, 365, 400, 150);
shp3.FillFormat.FillType = FillType.NoFill;
shp3.AddTextFrame(" ");
```
## Steg 5: Ändra texten i formen
```csharp
ITextFrame txtFrame = shp3.TextFrame;
IParagraph para = txtFrame.Paragraphs[0];
IPortion portion = para.Portions[0];
portion.Text = "Watermark Text Watermark Text Watermark Text";
```
## Steg 6: Lägg till en annan form
```csharp
shp3 = slide.Shapes.AddAutoShape(ShapeType.Triangle, 200, 365, 400, 150);
```
## Steg 7: Ändra ordningen på former
```csharp
slide.Shapes.Reorder(2, shp3);
```
## Steg 8: Spara den ändrade presentationen
```csharp
presentation.Save(dataDir + "Reshape_out.pptx", SaveFormat.Pptx);
```
Detta kompletterar steg-för-steg-guiden för att ändra ordningen på former i presentationsbilder med Aspose.Slides för .NET.
## Slutsats
Aspose.Slides för .NET förenklar uppgiften att manipulera presentationsbilder programmatiskt. Genom att följa den här handledningen har du lärt dig hur du ändrar ordning på former, så att du kan förbättra det visuella tilltalande i dina presentationer.
## Vanliga frågor
### F: Kan jag använda Aspose.Slides för .NET i både Windows- och Linux-miljöer?
S: Ja, Aspose.Slides för .NET är kompatibel med både Windows- och Linux-miljöer.
### F: Finns det några licensöverväganden för att använda Aspose.Slides i ett kommersiellt projekt?
 S: Ja, du kan hitta licensinformation och köpalternativ på[Köpsida Aspose.Slides](https://purchase.aspose.com/buy).
### F: Finns det en gratis testversion tillgänglig för Aspose.Slides för .NET?
 S: Ja, du kan utforska funktionerna med[gratis provperiod](https://releases.aspose.com/) tillgänglig på Aspose.Slides webbplats.
### F: Var kan jag hitta support eller ställa frågor relaterade till Aspose.Slides för .NET?
 A: Besök[Aspose.Slides forum](https://forum.aspose.com/c/slides/11) att få stöd och engagera sig i samhället.
### F: Hur kan jag få en tillfällig licens för Aspose.Slides för .NET?
 A: Du kan förvärva en[tillfällig licens](https://purchase.aspose.com/temporary-license/) i utvärderingssyfte.