---
title: Skapa gruppformer i presentationsbilder med Aspose.Slides
linktitle: Skapa gruppformer i presentationsbilder med Aspose.Slides
second_title: Aspose.Slides .NET PowerPoint Processing API
description: Lär dig hur du skapar fängslande presentationsbilder med gruppformer med Aspose.Slides för .NET. Följ vår steg-för-steg-guide och källkodsexempel för att enkelt lägga till, gruppera och transformera former, vilket förbättrar dina presentationer.
type: docs
weight: 11
url: /sv/net/image-and-video-manipulation-in-slides/creating-group-shapes/
---

## Introduktion till Aspose.Slides för .NET

Aspose.Slides för .NET är ett omfattande och funktionsrikt bibliotek som låter utvecklare manipulera PowerPoint-presentationer programmatiskt. Oavsett om du vill skapa, modifiera eller konvertera presentationsfiler, erbjuder Aspose.Slides ett brett utbud av verktyg och funktioner för att förenkla processen.

## Förutsättningar

Innan du börjar arbeta med Aspose.Slides för .NET, se till att du har följande förutsättningar på plats:

- Visual Studio: Installera Visual Studio på din dator.
-  Aspose.Slides Library: Ladda ner och referera till Aspose.Slides-biblioteket i ditt projekt. Du kan ladda ner den från[här](https://releases.aspose.com/slides/net/).

## Lägga till Aspose.Slides till ditt projekt

1. Ladda ner Aspose.Slides-biblioteket från den medföljande länken.
2. Skapa ett nytt projekt i Visual Studio eller öppna ett befintligt.
3. Högerklicka på ditt projekt i Solution Explorer och välj "Hantera NuGet-paket."
4. Välj fliken "Bläddra" och sök efter "Aspose.Slides".
5. Installera Aspose.Slides-paketet i ditt projekt.

## Skapa en ny presentation

Låt oss börja med att skapa en ny PowerPoint-presentation med Aspose.Slides:

```csharp
using Aspose.Slides;

// Skapa en ny presentation
Presentation presentation = new Presentation();
```

## Lägga till former i bilden

Låt oss sedan lägga till några former till bilden. I det här exemplet lägger vi till två rektanglar:

```csharp
// Gå till den första bilden
ISlide slide = presentation.Slides[0];

// Lägg till rektanglar på bilden
IShape shape1 = slide.Shapes.AddRectangle(100, 100, 200, 100);
IShape shape2 = slide.Shapes.AddRectangle(300, 100, 150, 150);
```

## Gruppera former tillsammans

Låt oss nu gruppera formerna för att hantera dem kollektivt:

```csharp
// Gruppformer
IGroupShape groupShape = slide.Shapes.GroupShapes(new IShape[] { shape1, shape2 });
```

## Tillämpa transformationer på grupperade former

Du kan tillämpa olika transformationer på de grupperade formerna. Låt oss till exempel rotera de grupperade formerna 45 grader:

```csharp
// Vrid gruppen 45 grader
groupShape.Rotation = 45;
```

## Exempel på källkod

Här är det kompletta källkodsexemplet för att skapa gruppformer med Aspose.Slides:

```csharp
using Aspose.Slides;

namespace GroupShapesExample
{
    class Program
    {
        static void Main(string[] args)
        {
            // Skapa en ny presentation
            Presentation presentation = new Presentation();

            // Gå till den första bilden
            ISlide slide = presentation.Slides[0];

            // Lägg till rektanglar på bilden
            IShape shape1 = slide.Shapes.AddRectangle(100, 100, 200, 100);
            IShape shape2 = slide.Shapes.AddRectangle(300, 100, 150, 150);

            // Gruppformer
            IGroupShape groupShape = slide.Shapes.GroupShapes(new IShape[] { shape1, shape2 });

            // Vrid gruppen 45 grader
            groupShape.Rotation = 45;

            // Spara presentationen
            presentation.Save("GroupShapesExample.pptx", SaveFormat.Pptx);
        }
    }
}
```

## Slutsats

I den här handledningen har du lärt dig hur du skapar gruppformer i presentationsbilder med Aspose.Slides för .NET. Biblioteket ger ett enkelt sätt att lägga till former, gruppera dem och tillämpa transformationer för att förbättra dina presentationer dynamiskt.

## FAQ's

### Hur installerar jag Aspose.Slides för .NET?

Du kan ladda ner Aspose.Slides-biblioteket från den medföljande länken:[här](https://releases.aspose.com/slides/net/). När du har laddat ner den kan du lägga till den i ditt projekt med NuGet-paket.

### Kan jag tillämpa olika transformationer på grupperade former?

Ja, du kan använda olika transformationer som rotation, skalning och positionering på de grupperade formerna, så att du kan anpassa det visuella utseendet på dina bilder.

### Är Aspose.Slides lämpligt för både att skapa och modifiera presentationer?

Absolut! Aspose.Slides för .NET är ett mångsidigt bibliotek som stöder skapande, modifiering och konvertering av presentationsfiler. Det ger ett brett utbud av funktioner för att tillgodose olika behov.

### Kan jag gruppera former av olika typer?

 Ja, du kan gruppera former av olika typer, såsom rektanglar, cirklar och textrutor, tillsammans med`GroupShapes` metod. Detta gör att du kan hantera och manipulera dem kollektivt.

### Är Aspose.Slides endast lämplig för .NET-applikationer?

Ja, Aspose.Slides är speciellt utformad för .NET-applikationer. Det finns dock versioner tillgängliga för andra programmeringsspråk också, som Java.