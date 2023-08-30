---
title: Lägg till anteckningsbild med snygg anteckningsformatering
linktitle: Lägg till anteckningsbild med snygg anteckningsformatering
second_title: Aspose.Slides .NET PowerPoint Processing API
description: Lär dig hur du förbättrar dina PowerPoint-presentationer med snygg anteckningsformatering med Aspose.Slides för .NET. Den här steg-för-steg-guiden tar upp hur du lägger till en anteckningsbild, tillämpar attraktiv formatering och mer.
type: docs
weight: 14
url: /sv/net/slide-access-and-manipulation/add-notes-slide-with-notes-style/
---

## Introduktion till Aspose.Slides för .NET:

Aspose.Slides för .NET är ett omfattande bibliotek som låter utvecklare arbeta med PowerPoint-presentationer i sina .NET-applikationer. Det ger ett brett utbud av funktioner, inklusive att skapa, läsa, skriva och manipulera bilder, former, text, bilder och mer. I den här handledningen kommer vi att fokusera på att lägga till en anteckningsbild och tillämpa snygg formatering på anteckningarna.

## Förutsättningar:

Innan vi börjar, se till att du har följande förutsättningar på plats:

- Visual Studio eller någon annan .NET-utvecklingsmiljö.
-  Aspose.Slides för .NET-bibliotek. Du kan ladda ner den från[här](https://releases.aspose.com/slides/net/).

## Konfigurera projektet:

1. Skapa ett nytt .NET-projekt i din föredragna utvecklingsmiljö.
2. Lägg till en referens till Aspose.Slides för .NET-biblioteket i ditt projekt.

## Skapa en presentation:

Låt oss börja med att skapa en ny PowerPoint-presentation med Aspose.Slides för .NET. Vi kommer sedan att lägga till en anteckningsbild till denna presentation.

```csharp
using Aspose.Slides;
using System;

namespace NotesSlideTutorial
{
    class Program
    {
        static void Main(string[] args)
        {
            // Skapa en ny presentation
            Presentation presentation = new Presentation();

            // Spara presentationen
            presentation.Save("MyPresentation.pptx", SaveFormat.Pptx);
        }
    }
}
```

## Lägga till en anteckningsbild:

Därefter lägger vi till en anteckningsbild till presentationen. En anteckningsbild innehåller vanligtvis ytterligare information eller talaranteckningar relaterade till innehållet på huvudbilden.

```csharp
// Lägg till en anteckningsbild efter den första bilden
NotesSlide notesSlide = presentation.Slides[0].NotesSlideManager.AddNotesSlide();

// Lägg till innehåll i anteckningsbilden
notesSlide.NotesTextFrame.Text = "These are the speaker notes for the first slide.";
```

## Snygg formatering för anteckningar:

För att göra anteckningarna mer visuellt tilltalande kan vi använda stilfull formatering med Aspose.Slides för .NET. Detta inkluderar att ändra teckensnitt, färg, storlek och andra formateringsalternativ.

```csharp
// Öppna textramen för anteckningsbilden
ITextFrame notesTextFrame = notesSlide.NotesTextFrame;

// Använd formatering på texten
IParagraph paragraph = notesTextFrame.Paragraphs[0];
IPortion portion = paragraph.Portions[0];

// Ändra teckensnitt, teckenstorlek och färg
portion.PortionFormat.LatinFont = new FontData("Arial");
portion.PortionFormat.FontHeight = 14;
portion.PortionFormat.FillFormat.SolidFillColor.Color = Color.DarkBlue;
```

## Slutsats:

I den här handledningen har vi lärt oss hur man använder Aspose.Slides för .NET för att lägga till en anteckningsbild med snygg formatering till en PowerPoint-presentation. Vi behandlade att skapa en presentation, lägga till en anteckningsbild och tillämpa formatering på anteckningsinnehållet. Aspose.Slides för .NET ger utvecklare en kraftfull verktygslåda för att förbättra sina PowerPoint-presentationer programmatiskt.

## FAQ's

### Hur kan jag ändra placeringen av anteckningarna på anteckningsbilden?

 Du kan justera positionen för anteckningstextramen med hjälp av`notesSlide.NotesTextFrame.X` och`notesSlide.NotesTextFrame.Y` egenskaper.

### Kan jag lägga till bilder på anteckningsbilden?

 Ja, du kan lägga till bilder till anteckningsbilden med hjälp av`notesSlide.Shapes.AddPicture()` metod.

### Är Aspose.Slides för .NET kompatibelt med olika PowerPoint-format?

Ja, Aspose.Slides för .NET stöder olika PowerPoint-format, inklusive PPTX, PPT och mer.

### Hur kan jag tillämpa formatering på specifika delar av anteckningstexten?

 Du kan komma åt delar inom ett stycke och tillämpa formatering med hjälp av`portion.PortionFormat` fast egendom.

### Var kan jag hitta mer information om Aspose.Slides för .NET?

 För detaljerad dokumentation och exempel kan du besöka[Aspose.Slides för .NET-dokumentation](https://reference.aspose.com/slides/net/).