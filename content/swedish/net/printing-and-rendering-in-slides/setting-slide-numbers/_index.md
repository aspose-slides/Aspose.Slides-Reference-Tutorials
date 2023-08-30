---
title: Ställa in bildnummer för presentationer med Aspose.Slides
linktitle: Ställa in bildnummer för presentationer med Aspose.Slides
second_title: Aspose.Slides .NET PowerPoint Processing API
description: Lär dig hur du lägger till och anpassar bildnummer i PowerPoint-presentationer med Aspose.Slides för .NET. Den här steg-för-steg-guiden ger källkodsexempel för att ställa in projektet, ladda en presentation, lägga till bildnummer, anpassa deras format och justera deras placering.
type: docs
weight: 16
url: /sv/net/printing-and-rendering-in-slides/setting-slide-numbers/
---

## Introduktion till Aspose.Slides för .NET

Aspose.Slides för .NET är ett mångsidigt bibliotek som gör det möjligt för .NET-utvecklare att skapa, modifiera och manipulera PowerPoint-presentationer programmatiskt. Det ger ett brett utbud av funktioner för att interagera med olika delar av presentationer, inklusive bilder, former, text, bilder och mer. I den här guiden kommer vi att fokusera på att lägga till och anpassa bildnummer med Aspose.Slides för .NET.

## Förutsättningar

Innan vi börjar, se till att du har följande förutsättningar på plats:

- Visual Studio (eller någon annan .NET-utvecklingsmiljö)
-  Aspose.Slides för .NET-bibliotek (Ladda ner från[här](https://releases.aspose.com/slides/net/)

## Att sätta upp projektet

1. Skapa ett nytt Visual Studio-projekt (till exempel konsolapplikation).
2. Lägg till en referens till Aspose.Slides för .NET-biblioteket.

## Laddar en presentation

För att komma igång, låt oss ladda en befintlig PowerPoint-presentation:

```csharp
using Aspose.Slides;

// Ladda presentationen
using Presentation presentation = new Presentation("your-presentation.pptx");
```

## Lägga till bildnummer

Låt oss sedan lägga till bildnummer till varje bild i presentationen:

```csharp
// Aktivera bildnummer
foreach (ISlide slide in presentation.Slides)
{
    // Lägg till bildnummerform
    IAutoShape slideNumberShape = slide.Shapes.AddAutoShape(ShapeType.Rectangle, 10, 10, 50, 20);
    slideNumberShape.TextFrame.Text = (slide.SlideNumber).ToString();
}
```

## Anpassa bildnummerformat

Du kan anpassa utseendet på diabildsnumren genom att justera teckensnitt, färg, storlek och mer:

```csharp
foreach (IAutoShape shape in presentation.Slides[0].Shapes.OfType<IAutoShape>())
{
    // Anpassa teckensnitt och färg
    ITextFrame textFrame = shape.TextFrame;
    IParagraph paragraph = textFrame.Paragraphs[0];
    IPortion portion = paragraph.Portions[0];
    
    portion.PortionFormat.FontHeight = 12;
    portion.PortionFormat.FillFormat.SolidFillColor.Color = Color.Black;
}
```

## Uppdaterar placeringen av bildnummer

Du kan också justera positionen för diabildsnumren på varje bild:

```csharp
foreach (ISlide slide in presentation.Slides)
{
    foreach (IAutoShape shape in slide.Shapes.OfType<IAutoShape>())
    {
        shape.Left = slide.SlideSize.Size.Width - shape.Width - 10;
        shape.Top = slide.SlideSize.Size.Height - shape.Height - 10;
    }
}
```

## Sparar den ändrade presentationen

När du har lagt till och anpassat bildnummer, spara den ändrade presentationen:

```csharp
presentation.Save("output-presentation.pptx", SaveFormat.Pptx);
```

## Slutsats

den här guiden utforskade vi hur du förbättrar dina presentationer genom att lägga till och anpassa bildnummer med Aspose.Slides för .NET. Genom att följa de medföljande stegen och kodexemplen kan du automatisera processen att lägga till bildnummer och skapa professionella presentationer.

## FAQ's

### Hur installerar jag Aspose.Slides för .NET?

 Du kan ladda ner Aspose.Slides för .NET-biblioteket från[här](https://releases.aspose.com/slides/net/). Efter nedladdning lägger du till en referens till biblioteket i ditt .NET-projekt.

### Kan jag anpassa utseendet på bildnummer?

Ja, du kan anpassa teckensnitt, färg, storlek och andra attribut för bildnummer med hjälp av de medföljande kodexemplen.

### Hur kan jag justera positionen för bildnummer på varje bild?

Du kan justera positionen för diabildsnummer genom att ändra koordinaterna för diabildsnummerformerna, som visas i kodexemplen.

### Är Aspose.Slides för .NET endast för att lägga till bildnummer?

Nej, Aspose.Slides för .NET erbjuder ett brett utbud av funktioner utöver att lägga till bildnummer. Det låter dig skapa, ändra och manipulera olika delar av PowerPoint-presentationer programmatiskt.

### Är ändringarna reversibla om jag vill ta bort bildnummer senare?

Ja, du kan enkelt ta bort diabildsnumren genom att ta bort motsvarande former från bilderna med Aspose.Slides-biblioteket.