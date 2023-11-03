---
title: Skapa sammanfattning Zooma in presentationsbilder med Aspose.Slides
linktitle: Skapa sammanfattning Zooma in presentationsbilder med Aspose.Slides
second_title: Aspose.Slides .NET PowerPoint Processing API
description: Lär dig hur du skapar fängslande presentationsbilder med sammanfattningszoom med Aspose.Slides för .NET. Vår steg-för-steg-guide ger källkod och anpassningstips för att förbättra interaktivitet.
type: docs
weight: 16
url: /sv/net/image-and-video-manipulation-in-slides/creating-summary-zoom/
---

## Introduktion till Aspose.Slides för .NET

Aspose.Slides för .NET är ett omfattande bibliotek som gör det möjligt för utvecklare att arbeta med PowerPoint-presentationer i sina .NET-applikationer. Det ger ett brett utbud av funktioner, inklusive att skapa, redigera och manipulera bilder, former, text, bilder och mer. I den här guiden kommer vi att fokusera på att använda Aspose.Slides för .NET för att skapa sammanfattande zoombilder i presentationsdäck.

## Förutsättningar

Innan vi börjar, se till att du har följande:

- Visual Studio installerat.
- .NET Framework eller .NET Core installerat.
-  Aspose.Slides för .NET-bibliotek. Du kan ladda ner den från[här](https://releases.aspose.com/slides/net/).

## Att sätta upp utvecklingsmiljön

1. Skapa ett nytt .NET-projekt i Visual Studio.
2. Lägg till en referens till Aspose.Slides-biblioteket i ditt projekt.

## Laddar en presentation

För att komma igång, låt oss ladda en befintlig PowerPoint-presentation:

```csharp
using Aspose.Slides;

// Ladda presentationen
using var presentation = new Presentation("path_to_your_presentation.pptx");
```

## Lägga till bilder till sammanfattningszoom

Sammanfattningszoombilder låter dig ge en översikt över flera bilder i en enda bild. Låt oss lägga till bilder som vi vill sammanfatta:

```csharp
// Lägg till bilder för att sammanfattas
var slideIndexes = new[] { 2, 3, 4 };
var summaryZoomSlide = presentation.Slides.AddSummaryZoomSlide(slideIndexes);
```

## Skapa sammanfattningszoombilder

Låt oss nu skapa den faktiska sammanfattningszoombilden som visar översikten över bilderna vi lade till tidigare:

```csharp
// Skapa en sammanfattande zoombild
var summaryZoom = presentation.Slides.AddSummaryZoomSlide(new[] { summaryZoomSlide });
```

## Anpassa sammanfattningszoombeteende

Du kan anpassa beteendet för sammanfattningszoomningen, till exempel layout och utseende:

```csharp
// Anpassa sammanfattningszoominställningar
var zoomFrame = summaryZoom.Shapes.OfType<ISmartArt>().FirstOrDefault();
if (zoomFrame != null)
{
    zoomFrame.Nodes[0].TextFrame.Text = "Summary Zoom";
    zoomFrame.Nodes[0].IsHidden = true; // Dölj titeln
    zoomFrame.Nodes[1].IsHidden = true; // Dölj innehållet
}
```

## Lägger till källkod för referens

För din bekvämlighet, här är den fullständiga källkoden för att skapa sammanfattande zoombilder:

```csharp
using Aspose.Slides;

class Program
{
    static void Main(string[] args)
    {
        using var presentation = new Presentation("path_to_your_presentation.pptx");

        var slideIndexes = new[] { 2, 3, 4 };
        var summaryZoomSlide = presentation.Slides.AddSummaryZoomSlide(slideIndexes);

        var summaryZoom = presentation.Slides.AddSummaryZoomSlide(new[] { summaryZoomSlide });

        var zoomFrame = summaryZoom.Shapes.OfType<ISmartArt>().FirstOrDefault();
        if (zoomFrame != null)
        {
            zoomFrame.Nodes[0].TextFrame.Text = "Summary Zoom";
            zoomFrame.Nodes[0].IsHidden = true;
            zoomFrame.Nodes[1].IsHidden = true;
        }

        presentation.Save("output.pptx", SaveFormat.Pptx);
    }
}
```

## Slutsats

I den här guiden har vi utforskat hur man använder Aspose.Slides för .NET för att skapa sammanfattande zoombilder i presentationsdäck. Denna kraftfulla funktion kan förbättra interaktiviteten och engagemanget i dina presentationer och ge ditt innehåll en professionell touch.

## FAQ's

### Hur kan jag ladda ner Aspose.Slides för .NET?

 Du kan ladda ner Aspose.Slides för .NET från[Aspose.Slides webbplats](https://releases.aspose.com/slides/net/).

### Kan jag anpassa utseendet på sammanfattningszoombilderna?

Ja, du kan anpassa utseendet på sammanfattningszoombilderna med hjälp av olika egenskaper som tillhandahålls av Aspose.Slides-biblioteket.

### Är Aspose.Slides kompatibel med både .NET Framework och .NET Core?

Ja, Aspose.Slides stöder både .NET Framework och .NET Core, vilket ger dig flexibilitet när du väljer din utvecklingsplattform.

### Kan jag skapa sammanfattande zoombilder för specifika bildintervall?

Absolut! Du kan välja de bilder du vill inkludera i sammanfattningszoomningen med hjälp av deras bildindex.

### Hur kan jag dölja titeln och innehållet på sammanfattningszoombilden?

 Du kan använda`IsHidden` egenskapen för SmartArt-noderna för att dölja titeln och innehållet på sammanfattningszoombilden.