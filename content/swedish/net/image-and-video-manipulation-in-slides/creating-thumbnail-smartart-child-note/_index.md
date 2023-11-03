---
title: Skapa miniatyrbild för SmartArt Child Note i Aspose.Slides
linktitle: Skapa miniatyrbild för SmartArt Child Note i Aspose.Slides
second_title: Aspose.Slides .NET PowerPoint Processing API
description: Lär dig hur du skapar miniatyrer för SmartArt-underordnade anteckningar med Aspose.Slides för .NET. Steg-för-steg guide med komplett källkod.
type: docs
weight: 15
url: /sv/net/image-and-video-manipulation-in-slides/creating-thumbnail-smartart-child-note/
---

## Introduktion till att skapa miniatyrbilder för SmartArt Child Note

I den här handledningen kommer vi att gå igenom processen att skapa en miniatyrbild för en SmartArt-anteckning med Aspose.Slides-biblioteket i .NET. Aspose.Slides är ett kraftfullt API som låter utvecklare arbeta med PowerPoint-presentationer programmatiskt. Vi kommer att gå steg för steg, demonstrera koden och förklara varje del av processen.

## Förutsättningar

Innan vi börjar, se till att du har följande:

- Visual Studio (eller någon annan .NET-utvecklingsmiljö) installerad.
-  Aspose.Slides för .NET-bibliotek. Du kan ladda ner den från[här](https://releases.aspose.com/slides/net/).

## Konfigurera projektet

1. Skapa ett nytt C#-projekt i Visual Studio.
2. Lägg till en referens till Aspose.Slides för .NET-biblioteket.

## Laddar presentationen

```csharp
using Aspose.Slides;

class Program
{
    static void Main(string[] args)
    {
        // Ladda presentationen
        using (Presentation presentation = new Presentation("presentation.pptx"))
        {
            // Din kod här
        }
    }
}
```

## Åtkomst till SmartArt Shapes

```csharp
// Förutsatt att vi har en SmartArt-form på den första bilden
ISlide slide = presentation.Slides[0];
ISmartArt smartArt = (ISmartArt)slide.Shapes[0];

// Åtkomst till barnnoder
ISmartArtNodeCollection nodes = smartArt.AllNodes;
```

## Skapa en miniatyrbild för en barnanteckning

```csharp
foreach (ISmartArtNode node in nodes)
{
    // Förutsatt att noden har underordnade noder
    ISmartArtNodeCollection childNodes = node.ChildNodes;

    // Skapa en miniatyrbild
    using (Bitmap thumbnail = childNodes.GenerateThumbnail(new Size(200, 150)))
    {
        //Spara miniatyrbilden eller utför andra åtgärder
        thumbnail.Save($"thumbnail_{node.Text}.png");
    }
}
```

## Spara presentationen med miniatyrer

```csharp
// Spara presentationen med miniatyrer
presentation.Save("presentation_with_thumbnails.pptx", SaveFormat.Pptx);
```

## Slutsats

I den här handledningen lärde vi oss hur man skapar miniatyrer för SmartArt-anteckningar för barn med Aspose.Slides för .NET. Vi täckte hela processen från att ladda en presentation till att komma åt SmartArt-former, generera miniatyrer och spara presentationen med miniatyrer.

## FAQ's

### Hur kan jag installera Aspose.Slides för .NET?

 Du kan ladda ner Aspose.Slides för .NET från deras hemsida[här](https://releases.aspose.com/slides/net/).

### Kan jag skapa miniatyrer för andra former också?

Ja, Aspose.Slides tillhandahåller olika metoder för att skapa miniatyrer för olika typer av former, inklusive bilder, diagram och mer.

### Är Aspose.Slides lämplig för både personliga och kommersiella projekt?

Ja, Aspose.Slides kan användas i både personliga och kommersiella projekt. Se dock till att granska deras licensvillkor före implementering.

### Kan jag anpassa utseendet på de genererade miniatyrerna?

Absolut! Aspose.Slides låter dig anpassa storleken, kvaliteten och andra egenskaper för de genererade miniatyrerna för att matcha dina krav.

### Stöder Aspose.Slides andra programmeringsspråk förutom .NET?

Ja, Aspose.Slides är tillgängligt för flera programmeringsspråk, inklusive Java, Python och mer, vilket gör det mångsidigt för olika utvecklingsmiljöer.