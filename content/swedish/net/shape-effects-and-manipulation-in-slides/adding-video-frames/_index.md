---
title: Lägga till videoramar till presentationsbilder med Aspose.Slides
linktitle: Lägga till videoramar till presentationsbilder med Aspose.Slides
second_title: Aspose.Slides .NET PowerPoint Processing API
description: Lär dig hur du förbättrar dina presentationer genom att lägga till videoramar med Aspose.Slides för .NET. Skapa engagerande och interaktivt innehåll sömlöst.
type: docs
weight: 19
url: /sv/net/shape-effects-and-manipulation-in-slides/adding-video-frames/
---

## Introduktion till Aspose.Slides och videointegration

Aspose.Slides är ett omfattande bibliotek som ger utvecklare möjlighet att skapa, manipulera och konvertera PowerPoint-presentationer programmatiskt. Genom att integrera videoramar i dina bilder kan du lyfta dina presentationer och göra dem mer dynamiska och engagerande.

## Förutsättningar för att införliva videor

Innan du börjar, se till att du har följande:

- Visual Studio eller någon föredragen .NET-utvecklingsmiljö
- Aspose.Slides för .NET-biblioteket installerat
- En PowerPoint-presentation (PPTX) där du vill lägga till videoramar

## Konfigurera din utvecklingsmiljö

1. Öppna Visual Studio och skapa ett nytt .NET-projekt.
2.  Installera Aspose.Slides NuGet-paketet:`Install-Package Aspose.Slides`.

## Ladda en presentation och komma åt bilder

För att komma igång, ladda din PowerPoint-presentation med Aspose.Slides:

```csharp
using Aspose.Slides;

// Ladda presentationen
using Presentation presentation = new Presentation("your-presentation.pptx");

// Få åtkomst till bilder
ISlideCollection slides = presentation.Slides;
```

## Lägga till videofiler till presentationen

1. Placera dina videofiler i en mapp i ditt projekt.
2. Lägg till referenser till dessa filer i din kod:

```csharp
// Lägg till videofiler
string videoPath = "path-to-your-videos-folder";
string[] videoFiles = Directory.GetFiles(videoPath, "*.mp4");
```

## Placera videoramar på bilder

Iterera genom bilderna och lägg till videoramar:

```csharp
foreach (ISlide slide in slides)
{
    foreach (string videoFile in videoFiles)
    {
        IVideoFrame videoFrame = slide.Shapes.AddVideoFrame(100, 100, 320, 240, videoFile);
    }
}
```

## Anpassa egenskaper för videoram

Du kan anpassa videoramsegenskaper som position, storlek och stil:

```csharp
foreach (IVideoFrame videoFrame in slide.Shapes.OfType<IVideoFrame>())
{
    videoFrame.X = 200;
    videoFrame.Y = 150;
    videoFrame.Width = 480;
    videoFrame.Height = 360;
}
```

## Hantera uppspelningsalternativ

 Styr videouppspelning med hjälp av`VideoPlayModePreset` uppräkning:

```csharp
foreach (IVideoFrame videoFrame in slide.Shapes.OfType<IVideoFrame>())
{
    videoFrame.PlayMode = VideoPlayModePreset.Auto;
}
```

## Spara och exportera den ändrade presentationen

Spara din presentation efter att ha lagt till videoramar:

```csharp
presentation.Save("modified-presentation.pptx", SaveFormat.Pptx);
```

## Slutsats

Att införliva videoramar i dina presentationsbilder med Aspose.Slides förbättrar den visuella effekten av ditt innehåll. Du har lärt dig hur du sömlöst integrerar videor, anpassar videoramsegenskaper och styr uppspelningsalternativ. Börja skapa dynamiska och engagerande presentationer som fängslar din publik.

## Vanliga frågor

### Hur lägger jag till flera videor till en enda bild?

Gå igenom dina videofiler och lägg till videoramar till önskad bild med den medföljande koden.

### Kan jag styra inställningar för videouppspelning?

 Ja, du kan använda`VideoPlayModePreset` uppräkning för att ställa in uppspelningsalternativ såsom automatisk uppspelning.

### Vilka videoformat stöds?

Aspose.Slides stöder olika videoformat, inklusive MP4, AVI, WMV och mer.

### Är det möjligt att lägga till videor programmatiskt i C#?

Absolut, Aspose.Slides för .NET tillhandahåller ett användarvänligt API för att lägga till videor till bilder programmatiskt med C#.

### Kan jag ändra utseendet på videoramen?

Ja, du kan anpassa videoramens position, storlek och andra visuella egenskaper enligt dina krav.