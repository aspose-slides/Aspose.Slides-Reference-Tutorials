---
title: Ersätter bildtitel för OLE-objektram i presentationsbilder
linktitle: Ersätter bildtitel för OLE-objektram i presentationsbilder
second_title: Aspose.Slides .NET PowerPoint Processing API
description: Lär dig hur du ersätter bildtitlar för OLE-objektramar i presentationsbilder med Aspose.Slides för .NET. Steg-för-steg guide med komplett källkod.
type: docs
weight: 15
url: /sv/net/shape-alignment-and-formatting-in-slides/substituting-picture-title-ole-object-frame/
---

## Introduktion till Aspose.Slides för .NET

Aspose.Slides för .NET är ett kraftfullt API som gör att utvecklare kan skapa, ändra och manipulera PowerPoint-presentationer utan att Microsoft Office eller PowerPoint behöver installeras. Den tillhandahåller ett brett utbud av funktioner för att arbeta med olika element i presentationer, inklusive bilder, former, text, bilder och OLE-objektramar.

## Förutsättningar

Innan vi börjar, se till att du har följande:

- Visual Studio eller någon kompatibel .NET-utvecklingsmiljö installerad.
-  Aspose.Slides för .NET-bibliotek. Du kan ladda ner den från[här](https://releases.aspose.com/slides/net/).

## Laddar en presentation

Låt oss börja med att ladda en befintlig PowerPoint-presentation med Aspose.Slides för .NET. Om du inte har en presentation för testning kan du skapa en ny eller ladda ner en exempelpresentation.

```csharp
using Aspose.Slides;

// Ladda presentationen
using var presentation = new Presentation("sample.pptx");
```

## Åtkomst till OLE Object Frames

 OLE (Object Linking and Embedding)-objektramar låter dig bädda in objekt som bilder, dokument eller andra filer i en PowerPoint-bild. För att komma åt OLE-objektramar i en bild, kan du iterera genom formerna och kontrollera om det finns förekomster av`OleObjectFrameEx`.

```csharp
// Iterera genom diabilder
foreach (var slide in presentation.Slides)
{
    // Iterera genom former i bilden
    foreach (var shape in slide.Shapes)
    {
        if (shape is OleObjectFrameEx oleObject)
        {
            //Åtkomst till OLE-objektegenskaper
            var title = oleObject.Title;
            var data = oleObject.ObjectData;
            
            // Utför ytterligare åtgärder
        }
    }
}
```

## Ersätter bildtitel

 För att ersätta bildtiteln på en OLE-objektram kan du helt enkelt uppdatera`Title` egendom av`OleObjectFrameEx` exempel.

```csharp
foreach (var slide in presentation.Slides)
{
    foreach (var shape in slide.Shapes)
    {
        if (shape is OleObjectFrameEx oleObject)
        {
            // Uppdatera titeln
            oleObject.Title = "New Picture Title";
        }
    }
}
```

## Sparar den ändrade presentationen

När du har gjort de nödvändiga ändringarna måste du spara den ändrade presentationen. Du kan spara den i olika format som PPTX, PDF eller bilder.

```csharp
// Spara presentationen
presentation.Save("modified.pptx", SaveFormat.Pptx);
```

## Slutsats

Aspose.Slides för .NET förenklar processen att arbeta med PowerPoint-presentationer programmatiskt. I den här guiden behandlade vi stegen för att ersätta bildtiteln för en OLE-objektram i presentationsbilder. Genom att följa dessa steg kan du effektivt manipulera presentationer enligt dina krav.

## FAQ's

### Hur skaffar jag Aspose.Slides för .NET-biblioteket?

 Du kan ladda ner Aspose.Slides för .NET-biblioteket från[den här länken](https://releases.aspose.com/slides/net/).

### Kan jag använda Aspose.Slides för .NET utan Microsoft Office installerat?

Ja, Aspose.Slides för .NET låter dig arbeta med PowerPoint-presentationer utan att Microsoft Office behöver installeras.

### Finns det andra operationer jag kan utföra på OLE-objektramar?

Absolut! Du kan utföra olika åtgärder på OLE-objektramar, som att ersätta objektdata, ändra storlek eller flytta dem i bilder.

### Är Aspose.Slides för .NET kompatibelt med olika PowerPoint-format?

Ja, Aspose.Slides för .NET stöder ett brett utbud av PowerPoint-format, inklusive PPT, PPTX, PPS och mer.

### Kan jag automatisera skapandet av PowerPoint-presentationer med Aspose.Slides?

Säkert! Aspose.Slides för .NET gör att du dynamiskt kan generera PowerPoint-presentationer från grunden, med olika element som text, bilder, diagram och mer.