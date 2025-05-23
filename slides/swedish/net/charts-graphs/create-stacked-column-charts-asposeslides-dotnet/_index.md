---
"date": "2025-04-15"
"description": "Lär dig hur du skapar visuellt tilltalande procentbaserade staplade kolumndiagram med Aspose.Slides för .NET. Följ den här steg-för-steg-guiden för tydlig datavisualisering."
"title": "Hur man skapar procentbaserade staplade kolumndiagram i .NET med hjälp av Aspose.Slides"
"url": "/sv/net/charts-graphs/create-stacked-column-charts-asposeslides-dotnet/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Hur man skapar ett procentbaserat staplat kolumndiagram med Aspose.Slides för .NET

## Introduktion

Inom datavisualisering är det avgörande för att få fram effektiva beslut att presentera information på ett tydligt och effektivt sätt. För att intuitivt visa komplexa datamängder är procentbaserade staplade kolumndiagram idealiska. Den här guiden guidar dig genom hur du skapar dessa diagram med Aspose.Slides för .NET, ett robust bibliotek utformat för att manipulera presentationsfiler.

Genom att följa den här handledningen kommer du att lära dig:
- Konfigurera diagramdata och talformat.
- Lägga till serier och anpassa deras utseende.
- Formatera etiketter för att förbättra läsbarheten.

Redo att dyka in? Låt oss börja med de förkunskaper du behöver!

## Förkunskapskrav

Innan du skapar dina procentbaserade staplade kolumndiagram, se till att din miljö är korrekt konfigurerad. Du behöver:

### Obligatoriska bibliotek, versioner och beroenden
- **Aspose.Slides för .NET**Se till att det här biblioteket är installerat.

### Krav för miljöinstallation
- En utvecklingsmiljö med .NET SDK installerat.
- Visual Studio eller någon kompatibel IDE för att köra C#-kod.

### Kunskapsförkunskaper
- Grundläggande förståelse för C#-programmering.
- Bekantskap med .NET-projektinstallation och pakethantering.

## Konfigurera Aspose.Slides för .NET

För att börja skapa diagram med Aspose.Slides, installera först biblioteket med någon av dessa metoder:

**.NET CLI**
```bash
dotnet add package Aspose.Slides
```

**Pakethanterare**
```powershell
Install-Package Aspose.Slides
```

**NuGet Package Manager-gränssnitt**
- Sök efter "Aspose.Slides" och installera den senaste versionen.

### Steg för att förvärva licens

Börja med en gratis provperiod genom att ladda ner en tillfällig licens från [Asposes webbplats](https://purchase.aspose.com/temporary-license/)För fortsatt användning, överväg att köpa en fullständig licens. 

När du har konfigurerat, starta Aspose.Slides i ditt projekt:
```csharp
using Aspose.Slides;
```

## Implementeringsguide

När miljön är redo, låt oss dela upp skapandet av ett procentbaserat staplat kolumndiagram i steg.

### Skapa och konfigurera diagrammet

#### Översikt
Skapa en instans av `Presentation` klassen, vilket är viktigt för att arbeta med bilder. Lägg sedan till och konfigurera ett staplat kolumndiagram på din bild.

#### Lägga till ett staplat kolumndiagram
```csharp
// Skapa en instans av Presentation-klassen
document = new Presentation();

// Hämta referens till den första bilden
slide = document.Slides[0];

// Lägg till PercentsStackedColumn-diagrammet vid position (20, 20) med storleken (500x400)
chart = slide.Shapes.AddChart(ChartType.PercentsStackedColumn, 20, 20, 500, 400);
```

#### Konfigurera talformat
Se till att dina data visas som procentandelar:
```csharp
// Konfigurera talformat för den vertikala axeln
columnChart.Axes.VerticalAxis.IsNumberFormatLinkedToSource = false;
columnChart.Axes.VerticalAxis.NumberFormat = "0.00%"; // Ställ in talformatet till procent
```

#### Lägga till dataserier och punkter
Rensa befintliga seriedata och lägg till nya:
```csharp
// Rensa alla befintliga seriedata
columnChart.ChartData.Series.Clear();

int defaultWorksheetIndex = 0;

// Åtkomst till diagramdata-arbetsbok
dataWorkbook = columnChart.ChartData.ChartDataWorkbook;

// Lägg till en ny dataserie "Reds"
series = columnChart.ChartData.Series.Add(dataWorkbook.GetCell(defaultWorksheetIndex, 0, 1, "Reds"), columnChart.Type);
series.DataPoints.AddDataPointForBarSeries(dataWorkbook.GetCell(defaultWorksheetIndex, 1, 1, 0.30));
series.DataPoints.AddDataPointForBarSeries(dataWorkbook.GetCell(defaultWorksheetIndex, 2, 1, 0.50));
series.DataPoints.AddDataPointForBarSeries(dataWorkbook.GetCell(defaultWorksheetIndex, 3, 1, 0.80));
series.DataPoints.AddDataPointForBarSeries(dataWorkbook.GetCell(defaultWorksheetIndex, 4, 1, 0.65));

// Ställ in fyllningsfärgen för serien till röd
series.Format.Fill.FillType = FillType.Solid;
series.Format.Fill.SolidFillColor.Color = System.Drawing.Color.Red;

// Konfigurera etikettformategenskaper för "Reds"-serien
series.Labels.DefaultDataLabelFormat.ShowValue = true;
series.Labels.DefaultDataLabelFormat.IsNumberFormatLinkedToSource = false;
series.Labels.DefaultDataLabelFormat.NumberFormat = "0.0%"; // Ställ in procentformat
columnChart.Series[0].Labels.DefaultDataLabelFormat.TextFormat.PortionFormat.FontHeight = 10;
columnChart.Series[0].Labels.DefaultDataLabelFormat.TextFormat.PortionFormat.FillFormat.FillType = FillType.Solid;
columnChart.Series[0].Labels.DefaultDataLabelFormat.TextFormat.PortionFormat.FillFormat.SolidFillColor.Color = System.Drawing.Color.White;

// Lägg till ytterligare en serie "Blues"
series2 = columnChart.ChartData.Series.Add(dataWorkbook.GetCell(defaultWorksheetIndex, 0, 2, "Blues"), chart.Type);
series2.DataPoints.AddDataPointForBarSeries(dataWorkbook.GetCell(defaultWorksheetIndex, 1, 2, 0.70));
series2.DataPoints.AddDataPointForBarSeries(dataWorkbook.GetCell(defaultWorksheetIndex, 2, 2, 0.50));
series2.DataPoints.AddDataPointForBarSeries(dataWorkbook.GetCell(defaultWorksheetIndex, 3, 2, 0.20));
series2.DataPoints.AddDataPointForBarSeries(dataWorkbook.GetCell(defaultWorksheetIndex, 4, 2, 0.35));

// Ställ in fyllningsfärgen för serien till Blå
series2.Format.Fill.FillType = FillType.Solid;
series2.Format.Fill.SolidFillColor.Color = System.Drawing.Color.Blue;
series2.Labels.DefaultDataLabelFormat.ShowValue = true;
columnChart.Series[1].Labels.DefaultDataLabelFormat.IsNumberFormatLinkedToSource = false;
series2.Labels.DefaultDataLabelFormat.NumberFormat = "0.0%"; // Ställ in procentformat
columnChart.Series[1].Labels.DefaultDataLabelFormat.TextFormat.PortionFormat.FontHeight = 10;
columnChart.Series[1].Labels.DefaultDataLabelFormat.TextFormat.PortionFormat.FillFormat.FillType = FillType.Solid;
columnChart.Series[1].Labels.DefaultDataLabelFormat.TextFormat.PortionFormat.FillFormat.SolidFillColor.Color = System.Drawing.Color.White;
```

#### Spara presentationen
Spara din presentation till en fil:
```csharp
// Spara presentationen i PPTX-format
document.Save("YOUR_OUTPUT_DIRECTORY/SetDataLabelsPercentageSign_out.pptx");
```

### Felsökningstips
- Se till att alla namnrymder importeras korrekt.
- Kontrollera om det finns stavfel i egenskapsnamn och metodanrop.
- Kontrollera att dina sökvägar för att spara filer finns och att de har rätt behörigheter.

## Praktiska tillämpningar

Här är några scenarier där procentbaserade staplade kolumndiagram kan vara värdefulla:
1. **Försäljningsanalys**Visualisera produktprestanda i olika regioner som en andel av den totala försäljningen.
2. **Budgetfördelning**Visa hur avdelningar fördelar sin budget i förhållande till företagets totala utgifter.
3. **Marknadsundersökning**Jämför konsumentpreferenser för olika produktkategorier över tid.
4. **Utbildningsdata**Visa fördelningen av elevernas betyg i olika ämnen.
5. **Hälsovårdsstatistik**Representerar patientdemografi över flera hälsotillstånd.

## Prestandaöverväganden

För optimal prestanda, överväg:
- Begränsa antalet datapunkter till vad som är nödvändigt.
- Förinläsning av data för att minimera körtidsbearbetning.
- Använda effektiva minneshanteringsmetoder med Aspose.Slides för .NET.

## Slutsats

Grattis! Du har nu lärt dig hur man skapar ett procentbaserat staplat kolumndiagram med Aspose.Slides för .NET. Det här verktyget förbättrar presentationer genom att göra komplex data mer begriplig och visuellt tilltalande.

Nästa steg? Utforska andra diagramtyper som finns i Aspose.Slides eller integrera den här funktionen i större applikationer. Lycka till med kodningen!

## FAQ-sektion

**F1: Kan jag använda Aspose.Slides gratis?**
A1: Ja, du kan börja med en gratis provperiod för att testa funktionerna i Aspose.Slides.

**F2: Vilka diagramtyper stöds av Aspose.Slides för .NET?**
A2: Den stöder olika diagram som cirkeldiagram, stapeldiagram, kolumndiagram, linjediagram med mera.

**F3: Hur kommer jag igång med Aspose.Slides för .NET?**
A3: Installera biblioteket med NuGet eller .NET CLI enligt beskrivningen ovan. Följ vår dokumentation för att skapa ditt första diagram.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}