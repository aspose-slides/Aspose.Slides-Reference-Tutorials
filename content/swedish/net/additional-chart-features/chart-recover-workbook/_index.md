---
title: Återställ arbetsbok från diagram
linktitle: Återställ arbetsbok från diagram
second_title: Aspose.Slides .NET PowerPoint Processing API
description: Lär dig hur du återställer en arbetsbok från ett diagram med Aspose.Slides för .NET. Extrahera diagramdata och skapa Excel-arbetsböcker programmatiskt.
type: docs
weight: 12
url: /sv/net/additional-chart-features/chart-recover-workbook/
---

## Introduktion

Olyckor kan hända och du kanske behöver återställa en arbetsbok från ett diagram. Aspose.Slides för .NET kommer till undsättning i sådana situationer. Detta kraftfulla bibliotek låter dig extrahera data från diagram i presentationer och konvertera den till en ny arbetsbok. I den här steg-för-steg-guiden går vi igenom processen att återställa en arbetsbok från ett diagram med Aspose.Slides för .NET.

## Förutsättningar

Innan du börjar, se till att du har följande på plats:

- Visual Studio: Ladda ner och installera Visual Studio, vilket är viktigt för .NET-utveckling.
-  Aspose.Slides för .NET: Du kan ladda ner biblioteket från[här](https://downloads.aspose.com/slides/net).

## Steg 1: Installera Aspose.Slides för .NET

Om du inte redan har gjort det, ladda ner och installera Aspose.Slides för .NET. Det här biblioteket tillhandahåller omfattande funktioner för att arbeta med PowerPoint-presentationer programmatiskt.

## Steg 2: Ladda presentationen

För att komma igång, skapa ett nytt C#-projekt i Visual Studio. Lägg till referenser till de nödvändiga Aspose.Slides-enheterna. Ladda PowerPoint-presentationen som innehåller diagrammet du vill återställa data från.

```csharp
// Ladda presentationen
Presentation presentation = new Presentation("your-presentation.pptx");
```

## Steg 3: Identifiera diagrammet

 Identifiera bilden och diagrammet som du vill återställa data från. Du kan komma åt bilder med hjälp av`presentation.Slides` samling och diagram med hjälp av`slide.Shapes` samling.

```csharp
// Skaffa bilden som innehåller diagrammet
ISlide slide = presentation.Slides[0];

// Skaffa diagrammet
IChart chart = null;
foreach (IShape shape in slide.Shapes)
{
    if (shape is IChart)
    {
        chart = (IChart)shape;
        break;
    }
}
```

## Steg 4: Extrahera data från diagram

Extrahera data från diagrammet med Aspose.Slides API. Du kan hämta värden från diagramserier och kategorier.

```csharp
// Extrahera diagramdata
IChartData chartData = chart.ChartData;
```

## Steg 5: Skapa en ny arbetsbok

Skapa en ny Excel-arbetsbok med hjälp av ett bibliotek som EPPlus eller ClosedXML.

```csharp
// Skapa en ny Excel-arbetsbok
using (var excelPackage = new ExcelPackage())
{
    var worksheet = excelPackage.Workbook.Worksheets.Add("Chart Data");
    // Lägg till kod här för att fylla i kalkylbladets rubriker
}
```

## Steg 6: Fyll i arbetsboken med diagramdata

Fyll i Excel-kalkylbladet med data som extraherats från diagrammet.

```csharp
//Fyll Excel-kalkylblad med diagramdata
int rowIndex = 2;
foreach (var series in chartData.Series)
{
    worksheet.Cells[rowIndex, 1].Value = series.Name;
    // Lägg till kod här för att fylla kalkylbladet med seriedata
    rowIndex++;
}
```

## Steg 7: Spara arbetsboken

Spara Excel-arbetsboken med återställda diagramdata.

```csharp
// Spara Excel-arbetsboken
excelPackage.SaveAs(new FileInfo("recovered-workbook.xlsx"));
```

## Slutsats

Det är enkelt att återställa en arbetsbok från ett diagram med Aspose.Slides för .NET. Genom att följa dessa steg kan du programmatiskt extrahera data från ett diagram i en PowerPoint-presentation och skapa en ny Excel-arbetsbok med återställd data. Denna process kan vara en livräddare när olyckor inträffar och data behöver räddas.

## FAQ's

### Hur installerar jag Aspose.Slides för .NET?

 Du kan ladda ner Aspose.Slides för .NET från[här](https://downloads.aspose.com/slides/net).

### Kan jag återställa data från olika typer av diagram?

Ja, Aspose.Slides för .NET stöder olika diagramtyper, inklusive stapeldiagram, linjediagram, cirkeldiagram och mer.

### Är Aspose.Slides för .NET lämplig för professionell användning?

Absolut! Aspose.Slides för .NET är ett robust bibliotek som används av utvecklare för att effektivt arbeta med PowerPoint-presentationer.

### Finns det några licenskrav för att använda Aspose.Slides för .NET?

 Ja, Aspose.Slides för .NET kräver en giltig licens för kommersiellt bruk. Du kan hitta licensinformation på[Aspose hemsida](https://purchase.aspose.com).

### Kan jag anpassa utseendet på den återställda Excel-arbetsboken?

Ja, du kan anpassa utseendet och formateringen av Excel-arbetsboken med hjälp av bibliotek som EPPlus eller ClosedXML.