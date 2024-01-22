---
title: Dölj former i PowerPoint med Aspose.Slides .NET Tutorial
linktitle: Döljer former i presentationsbilder med Aspose.Slides
second_title: Aspose.Slides .NET PowerPoint Processing API
description: Lär dig hur du döljer former i PowerPoint-bilder med Aspose.Slides för .NET. Anpassa presentationer programmatiskt med denna steg-för-steg-guide.
type: docs
weight: 21
url: /sv/net/shape-geometry-and-positioning-in-slides/hiding-shapes/
---
## Introduktion
presentationens dynamiska värld är anpassning nyckeln. Aspose.Slides för .NET tillhandahåller en kraftfull lösning för att manipulera PowerPoint-presentationer programmatiskt. Ett vanligt krav är förmågan att dölja specifika former i en bild. Denna handledning guidar dig genom processen att dölja former i presentationsbilder med Aspose.Slides för .NET.
## Förutsättningar
Innan du dyker in i handledningen, se till att du har följande förutsättningar på plats:
-  Aspose.Slides för .NET: Se till att du har Aspose.Slides-biblioteket installerat. Du kan ladda ner den[här](https://releases.aspose.com/slides/net/).
- Utvecklingsmiljö: Konfigurera din föredragna utvecklingsmiljö för .NET.
- Grundläggande kunskaper om C#: Bekanta dig med C# eftersom kodexemplen som tillhandahålls är på detta språk.
## Importera namnområden
För att börja arbeta med Aspose.Slides, importera de nödvändiga namnrymden i ditt C#-projekt. Detta säkerställer att du har tillgång till de klasser och metoder som krävs.
```csharp
using System;
using Aspose.Slides.Export;
using Aspose.Slides;
```
Låt oss nu dela upp exempelkoden i flera steg för en tydlig och koncis förståelse.
## Steg 1: Konfigurera ditt projekt
Skapa ett nytt C#-projekt och se till att inkludera Aspose.Slides-biblioteket.
## Steg 2: Skapa en presentation
 Instantiera`Presentation` klass, som representerar PowerPoint-filen. Lägg till en bild och få en referens till den.
```csharp
string dataDir = "Your Document Directory";
bool IsExists = System.IO.Directory.Exists(dataDir);
if (!IsExists)
    System.IO.Directory.CreateDirectory(dataDir);
Presentation pres = new Presentation();
ISlide sld = pres.Slides[0];
```
## Steg 3: Lägg till former i bilden
Lägg till autoformer till bilden, som rektanglar och månar, med specifika mått.
```csharp
IShape shp1 = sld.Shapes.AddAutoShape(ShapeType.Rectangle, 50, 40, 150, 50);
IShape shp2 = sld.Shapes.AddAutoShape(ShapeType.Moon, 160, 40, 150, 50);
```
## Steg 4: Dölj former baserat på alternativ text
Ange en alternativ text och dölj former som matchar denna text.
```csharp
String alttext = "User Defined";
int iCount = sld.Shapes.Count;
for (int i = 0; i < iCount; i++)
{
    AutoShape ashp = (AutoShape)sld.Shapes[i];
    if (String.Compare(ashp.AlternativeText, alttext, StringComparison.Ordinal) == 0)
    {
        ashp.Hidden = true;
    }
}
```
## Steg 5: Spara presentationen
Spara den modifierade presentationen på disk i PPTX-format.
```csharp
pres.Save(dataDir + "Hiding_Shapes_out.pptx", SaveFormat.Pptx);
```
## Slutsats
Congratulations! You've successfully hidden shapes in your presentation using Aspose.Slides for .NET. This opens up a world of possibilities for creating dynamic and customized slides programmatically.
---
## Vanliga frågor
### Är Aspose.Slides kompatibel med .NET Core?
Ja, Aspose.Slides stöder .NET Core, vilket ger flexibilitet i din utvecklingsmiljö.
### Kan jag dölja former baserat på andra villkor än alternativ text?
Absolut! Du kan anpassa döljningslogiken baserat på olika attribut som formtyp, färg eller position.
### Var kan jag hitta ytterligare Aspose.Slides-dokumentation?
 Utforska dokumentationen[här](https://reference.aspose.com/slides/net/) för fördjupad information och exempel.
### Finns tillfälliga licenser tillgängliga för Aspose.Slides?
 Ja, du kan få en tillfällig licens[här](https://purchase.aspose.com/temporary-license/) för teständamål.
### Hur kan jag få gemenskapsstöd för Aspose.Slides?
 Gå med i Aspose.Slides-communityt på[forum](https://forum.aspose.com/c/slides/11) för diskussioner och hjälp.