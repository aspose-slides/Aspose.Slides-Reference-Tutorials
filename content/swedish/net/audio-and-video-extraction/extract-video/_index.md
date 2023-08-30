---
title: Extrahera video från Slide
linktitle: Extrahera video från Slide
second_title: Aspose.Slides .NET PowerPoint Processing API
description: Bemästra videoextraktion från PowerPoint-bilder med Aspose.Slides för .NET. Följ vår guide med kodexempel.
type: docs
weight: 14
url: /sv/net/audio-and-video-extraction/extract-video/
---

## Introduktion

dagens digitala värld har multimediapresentationer blivit en viktig del av kommunikationen. PowerPoint-presentationer innehåller ofta en blandning av text, bilder och videor för att förmedla information effektivt. Det kan dock finnas tillfällen då du behöver extrahera en video från en bild för olika ändamål, som arkivering, delning eller ytterligare redigering. Det är här Aspose.Slides för .NET kommer in i bilden.

## Förutsättningar

Innan vi dyker in i steg-för-steg-guiden, se till att du har följande förutsättningar på plats:

- Grundläggande kunskaper i C# och .NET framework
- Visual Studio installerat
-  Aspose.Slides för .NET-biblioteket (ladda ner från[här](https://releases.aspose.com/slides/net)

## Steg-för-steg-guide

Låt oss gå igenom processen att extrahera en video från en bild med Aspose.Slides för .NET:

### Steg 1: Installation

1. Öppna Visual Studio och skapa ett nytt C#-projekt.
2. Högerklicka på ditt projekt i Solution Explorer och välj "Hantera NuGet-paket."
3. Sök efter "Aspose.Slides" och installera den senaste versionen.

### Steg 2: Ladda presentationen

```csharp
using Aspose.Slides;

// Ladda presentationen
using var presentation = new Presentation("your-presentation.pptx");
```

 Byta ut`"your-presentation.pptx"` med den faktiska sökvägen till din PowerPoint-presentationsfil.

### Steg 3: Extrahera video

```csharp
// Få den första bilden
var slide = presentation.Slides[0];

// Iterera genom diabilder
foreach (var shape in slide.Shapes)
{
    if (shape is IVideoFrame videoFrame)
    {
        // Extrahera videon från videoramen
        var video = videoFrame.EmbeddedVideo;
        // Ytterligare bearbetning kan göras med videoobjektet
    }
}
```

### Steg 4: Spara video

```csharp
// Spara den extraherade videon
video.WriteToFile("extracted-video.mp4");
```

 Byta ut`"extracted-video.mp4"` med önskat namn och sökväg för den extraherade videofilen.

## Slutsats

Aspose.Slides för .NET förenklar uppgiften att extrahera videor från PowerPoint-presentationer. Med bara några rader kod kan du hämta videor inbäddade i bilder och spara dem som separata videofiler. Oavsett om du vill återanvända innehåll eller skapa sammanställningar, erbjuder det här biblioteket en sömlös lösning.

## FAQ's

### Hur kommer jag åt Aspose.Slides-dokumentationen?

 Du kan hänvisa till dokumentationen för Aspose.Slides för .NET på[här](https://reference.aspose.com/slides/net/).

### Är Aspose.Slides tillgängligt för andra programmeringsspråk?

Ja, Aspose.Slides är tillgängligt för flera programmeringsspråk, inklusive Java. Du kan hitta lämpliga bibliotek på Asposes webbplats.

### Kan jag extrahera ljud på samma sätt?

Nej, exemplet är specifikt för att extrahera videor. För att extrahera ljud måste du ändra koden för att fungera med ljudramar.

### Finns det några licensavgifter för att använda Aspose.Slides?

Ja, Aspose.Slides är en kommersiell produkt. Du kan hitta detaljerad information om licensiering och prissättning på Asposes webbplats.

### Hur kommer jag åt den extraherade videons egenskaper?

 De`EmbeddedVideo` föremål som erhållits från`IVideoFrame` ger åtkomst till olika egenskaper för videon, som längd, upplösning och mer.