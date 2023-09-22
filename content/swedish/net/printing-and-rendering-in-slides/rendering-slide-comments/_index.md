---
title: Återge bildkommentarer i Aspose.Slides
linktitle: Återge bildkommentarer i Aspose.Slides
second_title: Aspose.Slides .NET PowerPoint Processing API
description: Lär dig hur du återger bildkommentarer i PowerPoint-presentationer med Aspose.Slides för .NET. Den här steg-för-steg-guiden ger källkodsexempel för åtkomst, anpassning och visning av kommentarer programmatiskt.
type: docs
weight: 12
url: /sv/net/printing-and-rendering-in-slides/rendering-slide-comments/
---

## Introduktion

Bildkommentarer ger värdefulla insikter, förklaringar och diskussioner relaterade till specifika bilder i en presentation. Genom att rendera dessa kommentarer programmatiskt kan granskningen och samarbetsprocessen effektiviseras. Aspose.Slides för .NET förenklar denna uppgift genom att tillhandahålla en omfattande uppsättning API:er för hantering och återgivning av bildkommentarer.

## Förutsättningar

Innan vi dyker in i implementeringen, se till att du har följande förutsättningar på plats:

- Visual Studio installerat på din dator.
- Grundläggande förståelse för C# och .NET utveckling.
-  Aspose.Slides för .NET-bibliotek. Du kan ladda ner den från[här](https://releases.aspose.com/slides/net/).

## Konfigurera projektet

1. Skapa ett nytt C#-projekt i Visual Studio.

2. Lägg till en referens till Aspose.Slides för .NET-biblioteket i ditt projekt.

## Laddar en presentation

För att komma igång, låt oss ladda en PowerPoint-presentation som innehåller bildkommentarer:

```csharp
using Aspose.Slides;

// Ladda presentationen
using var presentation = new Presentation("presentation.pptx");
```

## Få åtkomst till bildkommentarer

Låt oss sedan gå igenom bilderna i presentationen och komma åt kommentarerna som är kopplade till varje bild:

```csharp
// Iterera genom diabilder
foreach (var slide in presentation.Slides)
{
    // Få åtkomst till bildkommentarer
    var comments = slide.Comments;
    foreach (var comment in comments)
    {
        // Få åtkomst till kommentarsegenskaper
        var author = comment.Author;
        var text = comment.Text;
        
        // Bearbeta kommentaren efter behov
    }
}
```

## Återge kommentarer på bilder

Låt oss nu återge kommentarerna på bilderna. Vi lägger till kommentarerna som textrutor under varje bild:

```csharp
foreach (var slide in presentation.Slides)
{
    // Få åtkomst till bildkommentarer
    var comments = slide.Comments;
    foreach (var comment in comments)
    {
        // Skapa en textruta för kommentaren
        var textBox = slide.Shapes.AddTextFrame("");
        var textFrame = textBox.TextFrame;
        
        // Ställ in kommentaregenskaper som text
        textFrame.Text = $"{comment.Author}: {comment.Text}";
        
        // Placera textrutan under bilden
        textBox.Left = slide.SlideSize.Size.Width / 2;
        textBox.Top = slide.SlideSize.Size.Height + 20;
        
        // Anpassa textrutans utseende om det behövs
        
        // Bearbeta kommentaren efter behov
    }
}
```

## Anpassa kommentarsrendering

Du kan ytterligare anpassa utseendet på de renderade kommentarerna, såsom teckenstorlek, färg och position. Detta gör att du kan matcha kommentarerna med din presentations stil:

```csharp
// Anpassa textrutans utseende
var fontHeight = 12;
var fontColor = Color.Black;
var margin = 20;

foreach (var slide in presentation.Slides)
{
    // ...
    foreach (var comment in comments)
    {
        // ...
        
        // Anpassa textrutans utseende
        textFrame.Paragraphs[0].Portions[0].PortionFormat.FontHeight = fontHeight;
        textFrame.Paragraphs[0].Portions[0].PortionFormat.FillFormat.SolidFillColor.Color = fontColor;
        
        //Justera textrutans position
        textBox.Top = slide.SlideSize.Size.Height - margin;
        margin += 30; // Öka marginalen för nästa kommentar
    }
}
```

## Sparar den renderade presentationen

När du har återgett kommentarerna på bilderna kan du spara den ändrade presentationen:

```csharp
// Spara den ändrade presentationen
presentation.Save("rendered_presentation.pptx", SaveFormat.Pptx);
```

## Slutsats

I den här guiden har vi utforskat hur man renderar bildkommentarer i PowerPoint-presentationer med Aspose.Slides för .NET. Genom att följa stegen som beskrivs ovan kan du programmässigt komma åt och visa kommentarer, vilket förbättrar samarbete och kommunikation inom dina bildspel.

## FAQ's

### Hur kan jag installera Aspose.Slides för .NET?

 Du kan ladda ner Aspose.Slides för .NET-biblioteket från[den här länken](https://releases.aspose.com/slides/net/). När du har laddat ner den kan du lägga till den som referens i ditt Visual Studio-projekt.

### Kan jag anpassa utseendet på de renderade kommentarerna?

Ja, du kan anpassa utseendet på de renderade kommentarerna, inklusive teckenstorlek, färg och position. Detta gör att du kan matcha kommentarerna med din presentations stil.

### Hur kommer jag åt enskilda kommentarsegenskaper?

 Du kan komma åt kommentarsegenskaper som författare och text med hjälp av`Author` och`Text` egenskaper för kommentarobjektet.

### Kan jag återge kommentarer som länktexter istället för textrutor?

Ja, du kan återge kommentarer som bildtexter genom att skapa anpassade former och lägga till text till dem. Du måste justera bildtexternas position och utseende.

### Är Aspose.Slides för .NET lämplig för andra PowerPoint-relaterade uppgifter?

Absolut! Aspose.Slides för .NET tillhandahåller ett brett utbud av API:er för att arbeta med PowerPoint-presentationer. Du kan skapa, ändra, konvertera och manipulera olika aspekter av presentationer programmatiskt.