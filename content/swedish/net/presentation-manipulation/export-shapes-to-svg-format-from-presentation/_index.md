---
title: Exportera former till SVG-format från presentation
linktitle: Exportera former till SVG-format från presentation
second_title: Aspose.Slides .NET PowerPoint Processing API
description: Lär dig hur du exporterar former från en PowerPoint-presentation till SVG-format med Aspose.Slides för .NET. Steg-för-steg guide med källkod ingår. Extrahera effektivt former för olika applikationer.
type: docs
weight: 16
url: /sv/net/presentation-manipulation/export-shapes-to-svg-format-from-presentation/
---
Den här guiden leder dig genom processen att exportera former från en presentation till SVG-format med hjälp av Aspose.Slides för .NET-biblioteket. Aspose.Slides är ett kraftfullt API som låter dig arbeta med Microsoft PowerPoint-filer programmatiskt. I den här handledningen kommer du att lära dig hur du extraherar former från en presentation och sparar dem i SVG-format med C#.

## Förutsättningar

Innan du börjar, se till att du har följande förutsättningar på plats:

- Visual Studio installerat
- Grundläggande förståelse för C#-programmering
-  Aspose.Slides för .NET-bibliotek. Du kan ladda ner den från[här](https://releases.aspose.com/slides/net/).

## Steg-för-steg-guide

Följ dessa steg för att exportera former till SVG-format från en presentation:

### 1. Skapa ett nytt projekt

Öppna Visual Studio och skapa ett nytt C#-projekt.

### 2. Lägg till referens till Aspose.Slides

ditt projekt högerklickar du på "Referenser" i Solution Explorer och klickar sedan på "Lägg till referens". Bläddra och välj Aspose.Slides DLL du laddade ner.

### 3. Ladda presentationen

```csharp
using Aspose.Slides;

// Ladda presentationen
Presentation presentation = new Presentation("presentation.pptx");
```

### 4. Iterera genom former

```csharp
foreach (IShape shape in presentation.Slides[0].Shapes)
{
    // Kontrollera om formen är en gruppform
    if (shape is IGroupShape groupShape)
    {
        foreach (IShape groupChildShape in groupShape.Shapes)
        {
            // Exportera formen till SVG
            string svgFileName = $"shape_{groupChildShape.Id}.svg";
            groupChildShape.WriteAsSvg(svgFileName);
        }
    }
    else
    {
        // Exportera formen till SVG
        string svgFileName = $"shape_{shape.Id}.svg";
        shape.WriteAsSvg(svgFileName);
    }
}
```

### 5. Spara SVG-filer

```csharp
presentation.Save("output.pptx", SaveFormat.Pptx); // Spara ändringar i presentationen
```

## Vanliga frågor

### Hur kan jag installera Aspose.Slides för .NET?

 Du kan ladda ner Aspose.Slides för .NET-biblioteket från[här](https://releases.aspose.com/slides/net/). Följ installationsinstruktionerna i dokumentationen.

### Hur laddar jag en PowerPoint-presentation med Aspose.Slides?

 Du kan ladda en presentation med hjälp av`Presentation` klass konstruktör. Ange sökvägen till PowerPoint-filen som en parameter.

### Hur exporterar jag en form till SVG-format?

 Du kan använda`WriteAsSvg` metod på en`IShape` objekt för att exportera det till SVG-format. Du måste ange filnamnet för SVG-utdata.

## Slutsats

den här handledningen lärde du dig hur du exporterar former från en PowerPoint-presentation till SVG-format med Aspose.Slides för .NET-biblioteket. Detta kan vara användbart när du behöver extrahera individuella former för användning i andra applikationer eller plattformar som stöder SVG-grafik. Aspose.Slides ger ett enkelt och effektivt sätt att uppnå detta programmatiskt.

 För mer information och avancerade funktioner, se[Aspose.Slides för .NET API Referens](https://reference.aspose.com/slides/net/).