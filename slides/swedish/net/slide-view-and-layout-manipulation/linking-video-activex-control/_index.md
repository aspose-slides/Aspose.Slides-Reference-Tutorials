---
title: Länka video via ActiveX-kontroll i PowerPoint
linktitle: Länka video via ActiveX-kontroll
second_title: Aspose.Slides .NET PowerPoint Processing API
description: Lär dig hur du länkar videor till PowerPoint-bilder med Aspose.Slides för .NET. Den här steg-för-steg-guiden innehåller källkod och tips för att skapa interaktiva och engagerande presentationer med länkade videor.
weight: 12
url: /sv/net/slide-view-and-layout-manipulation/linking-video-activex-control/
---

{< blocks/products/pf/main-wrap-class >}
{< blocks/products/pf/main-container >}
{< blocks/products/pf/tutorial-page-section >}

Länka en video via ActiveX-kontroll i en presentation med Aspose.Slides för .NET

I Aspose.Slides för .NET kan du programmässigt länka en video till en presentationsbild med ActiveX-kontrollen. Detta gör att du kan skapa interaktiva presentationer där videoinnehållet kan spelas upp direkt i bilden. I den här steg-för-steg-guiden går vi igenom processen att länka en video till en presentationsbild med Aspose.Slides för .NET.

## Förutsättningar:
- Visual Studio (eller någon annan .NET-utvecklingsmiljö)
-  Aspose.Slides för .NET-bibliotek. Du kan ladda ner den från[här](https://releases.aspose.com/slides/net/).

## Steg 1: Skapa ett nytt projekt
Skapa ett nytt projekt i din föredragna .NET-utvecklingsmiljö (t.ex. Visual Studio) och lägg till referenser till Aspose.Slides för .NET-biblioteket.

## Steg 2: Importera nödvändiga namnutrymmen
ditt projekt, importera de nödvändiga namnrymden för att arbeta med Aspose.Slides:

```csharp
using Aspose.Slides;
using Aspose.Slides.ActiveXControls;
```

## Steg 3: Ladda presentationen
Ladda PowerPoint-presentationen där du vill lägga till den länkade videon:

```csharp
string presentationPath = "path_to_your_presentation.pptx";
using (Presentation presentation = new Presentation(presentationPath))
{
    // Din kod för att lägga till den länkade videon kommer hit
}
```

## Steg 4: Lägg till ActiveX-kontroll
 Skapa en instans av`IOleObjectFrame` gränssnitt för att lägga till ActiveX-kontrollen till bilden:

```csharp
ISlide slide = presentation.Slides[0]; // Välj bilden där du vill lägga till videon
IOleObjectFrame oleObjectFrame = slide.Shapes.AddOleObjectFrame(0, 0, 640, 480, "Video", "ShockwaveFlash.ShockwaveFlash.10");
```

I koden ovan lägger vi till en ActiveX-kontrollram med dimensionerna 640x480 till bilden. Vi anger ProgID för ShockwaveFlash ActiveX-kontrollen, som vanligtvis används för att bädda in videor.

## Steg 5: Ställ in egenskaper för ActiveX-kontrollen
Ställ in egenskaperna för ActiveX-kontrollen för att ange den länkade videokällan:

```csharp
oleObjectFrame.ObjectData = Encoding.UTF8.GetBytes("YourVideoPathHere"); // Ersätt med den faktiska videofilens sökväg
oleObjectFrame.AlternativeText = "Linked Video";
```

 Byta ut`"YourVideoPathHere"` med den faktiska sökvägen till din videofil. De`AlternativeText` egenskapen ger en beskrivning för den länkade videon.

## Steg 6: Spara presentationen
Spara den ändrade presentationen:

```csharp
string outputPresentationPath = "output_presentation.pptx";
presentation.Save(outputPresentationPath, SaveFormat.Pptx);
```

## Vanliga frågor:

### Hur kan jag specificera storleken och positionen för den länkade videon på bilden?
Du kan justera dimensionerna och positionen för ActiveX-kontrollramen med hjälp av parametrarna för`AddOleObjectFrame` metod. De fyra numeriska argumenten representerar X- och Y-koordinaterna för det övre vänstra hörnet och ramens bredd respektive höjd.

### Kan jag länka videor i olika format med detta tillvägagångssätt?
Ja, du kan länka videor i olika format så länge som lämplig ActiveX-kontroll är tillgänglig för det formatet. Till exempel är ShockwaveFlash ActiveX-kontrollen som används i den här guiden lämplig för Flash-videor (SWF). För andra format kan du behöva använda andra ProgID.

### Finns det en gräns för storleken på den länkade videon?
Storleken på den länkade videon kan påverka den övergripande storleken och prestandan för din presentation. Vi rekommenderar att du optimerar dina videor för webbuppspelning innan du länkar dem till presentationen.

### Slutsats:
Genom att följa stegen som beskrivs i den här guiden kan du enkelt länka en video via ActiveX-kontroll i en presentation med Aspose.Slides för .NET. Den här funktionen gör att du kan skapa engagerande och interaktiva presentationer som integrerar multimediainnehåll sömlöst.

 För mer information och avancerade alternativ kan du se[Aspose.Slides för .NET-dokumentation](https://reference.aspose.com/slides/net/).
{< /blocks/products/pf/tutorial-page-section >}

{< /blocks/products/pf/main-container >}
{< /blocks/products/pf/main-wrap-class >}

{< blocks/products/products-backtop-button >}
