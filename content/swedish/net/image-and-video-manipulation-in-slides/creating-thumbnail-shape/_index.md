---
title: Skapa miniatyrbild för Shape i Aspose.Slides
linktitle: Skapa miniatyrbild för Shape i Aspose.Slides
second_title: Aspose.Slides .NET PowerPoint Processing API
description: Lär dig hur du skapar miniatyrer för former i PowerPoint-presentationer med Aspose.Slides för .NET. Den här steg-för-steg-guiden ger praktiska kodexempel, från att ladda presentationer till att generera och spara miniatyrer.
type: docs
weight: 14
url: /sv/net/image-and-video-manipulation-in-slides/creating-thumbnail-shape/
---

## Introduktion

Aspose.Slides för .NET är ett funktionsrikt bibliotek som ger utvecklare möjlighet att arbeta med PowerPoint-presentationer sömlöst. Ett vanligt krav är att generera miniatyrer för specifika former i bilder. Detta kan vara särskilt användbart när du vill ge en snabb förhandsvisning eller representation av en form i din applikation.

## Förutsättningar

Innan vi dyker in i koden, se till att du har följande förutsättningar på plats:

- Visual Studio eller någon annan lämplig .NET-utvecklingsmiljö.
-  Aspose.Slides för .NET-bibliotek. Du kan ladda ner den från[här](https://releases.aspose.com/slides/net/).

## Installation

1. Ladda ner Aspose.Slides för .NET-biblioteket från den medföljande länken.
2. Installera biblioteket i ditt .NET-projekt genom att lägga till en referens till den nedladdade DLL-filen.

## Laddar en presentation

Låt oss börja med att ladda en PowerPoint-presentation med Aspose.Slides. Följande kod visar hur man laddar en presentation från en fil:

```csharp
using Aspose.Slides;

// Ladda presentationen
using var presentation = new Presentation("sample.pptx");
```

 Byta ut`"sample.pptx"` med den faktiska sökvägen till din PowerPoint-presentation.

## Tillgång till former

När presentationen har laddats kan du komma åt formerna i varje bild. I det här exemplet fokuserar vi på att skapa en miniatyrbild för en specifik form på en viss bild. Så här kommer du åt en form:

```csharp
// Få åtkomst till en bild efter index (0-baserad)
var slide = presentation.Slides[0];

// Få åtkomst till en form efter index (0-baserad)
var shape = slide.Shapes[0];
```

Ändra bild- och formindexen enligt din presentations struktur.

## Skapa miniatyrer

 Nu kommer den spännande delen – att skapa en miniatyrbild för den valda formen. Aspose.Slides låter dig uppnå detta genom att utnyttja`GetThumbnail` metod. Så här skapar du en miniatyrbild för en form:

```csharp
// Definiera miniatyrdimensioner
int thumbnailWidth = 200;
int thumbnailHeight = 150;

// Skapa en miniatyrbild för formen
var thumbnail = shape.GetThumbnail(thumbnailWidth, thumbnailHeight);
```

 Justera`thumbnailWidth` och`thumbnailHeight` variabler för att ställa in önskade dimensioner för din miniatyrbild.

## Sparar miniatyrer

När du har genererat miniatyrbilden kanske du vill spara den som en bildfil. Så här kan du spara miniatyren som en PNG-bild:

```csharp
// Spara miniatyren som en bild
thumbnail.Save("shape_thumbnail.png", ImageFormat.Png);
```

Anpassa filnamnet och formatet enligt dina krav.

## Slutsats

I den här guiden har vi utforskat hur man skapar miniatyrer för former i PowerPoint-presentationer med Aspose.Slides för .NET. Du har lärt dig hur du laddar en presentation, kommer åt former, genererar miniatyrer och sparar dem som bildfiler. Denna funktion kan avsevärt förbättra användarupplevelsen i applikationer som involverar PowerPoint-presentationer.

## FAQ's

### Hur kan jag ange olika miniatyrdimensioner?

 Du kan justera`thumbnailWidth` och`thumbnailHeight` variabler i koden för att ange de dimensioner du behöver för den genererade miniatyrbilden.

### Kan jag skapa miniatyrer för flera former samtidigt?

Ja, du kan iterera genom alla former på en bild och generera miniatyrer för varje form med hjälp av en slinga.

### Är Aspose.Slides kompatibel med olika PowerPoint-format?

Ja, Aspose.Slides stöder olika PowerPoint-format, inklusive PPTX, PPT och mer.

### Kan jag anpassa utseendet på den genererade miniatyrbilden?

 Medan`GetThumbnail` metod ger ett snabbt sätt att generera miniatyrer, du kan manipulera miniatyrbilden ytterligare med hjälp av standardbildbehandlingsbibliotek i .NET.

### Är Aspose.Slides lämplig för andra PowerPoint-relaterade uppgifter?

Absolut, Aspose.Slides erbjuder ett brett utbud av funktioner för att arbeta med PowerPoint-presentationer, inklusive att skapa, redigera, konvertera och rendera bilder.