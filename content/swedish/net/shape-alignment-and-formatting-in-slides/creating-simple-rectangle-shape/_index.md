---
title: Skapa enkel rektangelform i presentationsbilder med Aspose.Slides
linktitle: Skapa enkel rektangelform i presentationsbilder med Aspose.Slides
second_title: Aspose.Slides .NET PowerPoint Processing API
description: Lär dig hur du skapar en enkel rektangel i PowerPoint-bilder med Aspose.Slides för .NET. Denna steg-för-steg-guide ger källkod och instruktioner för att lägga till, anpassa och förbättra dina presentationer programmatiskt.
type: docs
weight: 12
url: /sv/net/shape-alignment-and-formatting-in-slides/creating-simple-rectangle-shape/
---

## Introduktion till Aspose.Slides för .NET

Aspose.Slides för .NET är ett kraftfullt bibliotek som gör det möjligt för utvecklare att arbeta med PowerPoint-presentationer programmatiskt. Den tillhandahåller ett brett utbud av funktioner för att skapa, manipulera och hantera presentationselement, inklusive bilder, former, text, bilder och mer. I den här guiden kommer vi att fokusera på att skapa en enkel rektangelform i en presentationsbild med hjälp av funktionerna i Aspose.Slides för .NET.

## Ställa in utvecklingsmiljön

Innan vi dyker in i koden, låt oss ställa in vår utvecklingsmiljö. Följ dessa steg:

1.  Ladda ner Aspose.Slides för .NET: Besök[nedladdningssida](https://releases.aspose.com/slides/net/) och välj den version som är kompatibel med ditt projekt.

2. Installera Aspose.Slides: Efter nedladdning, installera Aspose.Slides genom att lägga till DLL-referensen till ditt projekt.

3. Skapa ett nytt projekt: Skapa ett nytt .NET-projekt med din föredragna utvecklingsmiljö (till exempel Visual Studio).

## Skapa en ny presentation

Låt oss börja med att skapa en ny PowerPoint-presentation med Aspose.Slides för .NET.

```csharp
using Aspose.Slides;

class Program
{
    static void Main(string[] args)
    {
        // Skapa en ny presentation
        Presentation presentation = new Presentation();

        // Lägg till en tom bild i presentationen
        Slide slide = presentation.Slides.AddEmptySlide();

        // Din kod för att lägga till rektangelformen kommer hit

        // Spara presentationen
        presentation.Save("RectangleShapePresentation.pptx", SaveFormat.Pptx);
    }
}
```

## Lägga till en rektangelform till bilden

Nu när vi har vår presentationsbild redo, låt oss fortsätta att lägga till en rektangelform till den.

```csharp
// Lägg till en rektangelform på bilden
double x = 100; // X-koordinat för formen
double y = 100; // Y-koordinat för formen
double width = 200; // Formens bredd
double height = 100; // Formens höjd

slide.Shapes.AddRectangle(x, y, width, height);
```

## Anpassa rektangelformen

Du kan anpassa olika aspekter av rektangelformen, som dess fyllningsfärg, kantstil med mera.

```csharp
// Få den tillagda formen (rektangel)
IShape rectangle = slide.Shapes[0];

// Anpassa fyllningsfärg
rectangle.FillFormat.SolidFillColor.Color = Color.Blue;

// Anpassa gränsen
rectangle.LineFormat.Width = 2; // Gränsbredd
rectangle.LineFormat.DashStyle = LineDashStyle.DashDot; // Border stil
rectangle.LineFormat.FillFormat.SolidFillColor.Color = Color.Red; // Gräns färg
```

## Sparar presentationen

När du har lagt till och anpassat rektangelformen är det dags att spara presentationen.

```csharp
// Spara presentationen
presentation.Save("RectangleShapePresentation.pptx", SaveFormat.Pptx);
```

## Slutsats

I den här guiden utforskade vi hur man skapar en enkel rektangelform i en presentationsbild med Aspose.Slides för .NET. Vi täckte de grundläggande stegen för att ställa in utvecklingsmiljön, skapa en ny presentation, lägga till en rektangelform, anpassa dess utseende och spara den slutliga presentationen. Med Aspose.Slides för .NET kan du enkelt automatisera och förbättra dina PowerPoint-presentationer och lägga till ett lager av dynamik och interaktivitet.

## FAQ's

### Hur installerar jag Aspose.Slides för .NET?

För att installera Aspose.Slides för .NET, följ dessa steg:

1.  Besök[nedladdningssida](https://releases.aspose.com/slides/net/).
2. Välj den version som är kompatibel med ditt projekt.
3. Lägg till Aspose.Slides DLL-referensen till ditt .NET-projekt.

### Kan jag anpassa fyllningsfärgen för rektangelformen?

 Ja, du kan anpassa fyllningsfärgen för rektangelformen med hjälp av`FillFormat` fast egendom. Kom bara åt formens`FillFormat` och ställ in önskad`SolidFillColor`.

### Hur sparar jag presentationen efter att ha lagt till rektangelformen?

Du kan spara presentationen med hjälp av`Save` metod för`Presentation` klass. Ange önskat filnamn och önskat sparaformat (t.ex`SaveFormat.Pptx`).

### Är Aspose.Slides för .NET endast lämplig för rektangelformer?

Nej, Aspose.Slides för .NET stöder ett brett utbud av former och presentationselement. Du kan skapa och manipulera former som rektanglar, cirklar, pilar och mer.

### Var kan jag hitta mer dokumentation om Aspose.Slides för .NET?

 Du kan hitta detaljerad dokumentation och API-referenser för Aspose.Slides för .NET på[dokumentationssida](https://reference.aspose.com/slides/net/).