---
"date": "2025-04-15"
"description": "Lär dig hur du automatiserar skapandet av cirkeldiagram i .NET-presentationer med Aspose.Slides, vilket enkelt förbättrar datavisualiseringen."
"title": "Hur man skapar och anpassar cirkeldiagram i .NET-presentationer med hjälp av Aspose.Slides"
"url": "/sv/net/charts-graphs/create-style-pie-charts-net-asposeslides/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Hur man skapar och anpassar cirkeldiagram i .NET-presentationer med hjälp av Aspose.Slides

## Introduktion
Att skapa engagerande och informativa presentationer är avgörande för effektiv kommunikation, oavsett om du presenterar data på jobbet eller visar upp dina senaste projektresultat. Ett kraftfullt sätt att visualisera data är genom cirkeldiagram, som kortfattat kan representera delar av en helhet. Att manuellt skapa dessa diagram i presentationsprogram som PowerPoint kan dock vara tidskrävande och kan sakna den flexibilitet som krävs för dynamiska uppdateringar.

Det är där Aspose.Slides för .NET kommer in i bilden. Detta omfattande bibliotek låter dig skapa, modifiera och formatera presentationer programmatiskt, vilket gör det till ett ovärderligt verktyg för utvecklare som vill automatisera sina arbetsflöden och säkerställa enhetlighet i alla presentationer.

I den här handledningen ska vi utforska hur man använder Aspose.Slides för .NET för att skapa och anpassa cirkeldiagram i dina presentationer. Du lär dig hur du:
- **Skapa en presentation och få åtkomst till bilder**
- **Lägg till och konfigurera cirkeldiagram**
- **Anpassa diagramdata och serier**
- **Stilisera cirkeldiagramsektorer**
- **Lägg till anpassade etiketter**
- **Konfigurera visningsegenskaper och spara presentationen**

Redo att enkelt skapa fantastiska cirkeldiagram? Nu sätter vi igång!

## Förkunskapskrav
Innan vi börjar, se till att du har följande inställningar på plats:

### Obligatoriska bibliotek
- Aspose.Slides för .NET (version 21.11 eller senare rekommenderas)

### Miljöinställningar
- En utvecklingsmiljö som kör .NET Framework eller .NET Core/5+/6+
- En kodredigerare som Visual Studio

### Kunskapsförkunskaper
- Grundläggande förståelse för C#-programmering
- Bekantskap med objektorienterade koncept

## Konfigurera Aspose.Slides för .NET
För att komma igång måste du installera Aspose.Slides-biblioteket. Du kan göra detta med någon av följande metoder:

**.NET CLI**
```bash
dotnet add package Aspose.Slides
```

**Pakethanterarkonsol**
```powershell
Install-Package Aspose.Slides
```

**NuGet Package Manager-gränssnitt**
- Öppna ditt projekt i Visual Studio.
- Gå till "Verktyg" > "NuGet-pakethanterare" > "Hantera NuGet-paket för lösningen".
- Sök efter "Aspose.Slides" och installera den senaste versionen.

### Steg för att förvärva licens
För att använda Aspose.Slides kan du börja med en gratis provperiod genom att ladda ner en tillfällig licens. Besök [Asposes webbplats](https://purchase.aspose.com/temporary-license/) för att få tag på den. För kontinuerlig användning, överväg att köpa en fullständig licens.

### Grundläggande initialisering och installation
När den är installerad, initiera Presentation-klassen, som representerar din PPTX-fil:

```csharp
using Aspose.Slides;

Presentation presentation = new Presentation();
```

## Implementeringsguide
Vi kommer att dela upp processen för att skapa cirkeldiagram i hanterbara avsnitt. Varje avsnitt är utformat för att fokusera på en specifik funktion, vilket gör att du kan bygga upp dina kunskaper stegvis.

### Skapa en presentation och få åtkomst till bilder
**Översikt:** Börja med att skapa en ny presentation och öppna dess första bild. Detta förbereder grunden för att lägga till diagram och andra element.

```csharp
using Aspose.Slides;

public static void CreatePresentationAndAccessSlide()
{
    // Instansiera presentationsklassen som representerar en PPTX-fil
    Presentation presentation = new Presentation();
    
    // Åtkomst till första bilden
    ISlide slides = presentation.Slides[0];
}
```

### Lägg till och konfigurera cirkeldiagram
**Översikt:** Lär dig hur du lägger till ett cirkeldiagram i din bild och anger dess titel för sammanhang.

```csharp
using Aspose.Slides;
using Aspose.Slides.Charts;

public static void AddAndConfigurePieChart()
{
    // Instansiera presentationsklassen som representerar en PPTX-fil
    Presentation presentation = new Presentation();
    
    // Åtkomst till första bilden
    ISlide slides = presentation.Slides[0];
    
    // Lägg till diagram med standarddata på bilden
    IChart chart = slides.Shapes.AddChart(ChartType.Pie, 100, 100, 400, 400);
    
    // Titel för sättningstabell
    chart.ChartTitle.AddTextFrameForOverriding("Sample Title");
    chart.ChartTitle.TextFrameForOverriding.TextFrameFormat.CenterText = NullableBool.True;
    chart.ChartTitle.Height = 20;
    chart.HasTitle = true;
}
```

### Anpassa diagramdata och serier
**Översikt:** Anpassa datakategorierna och serierna så att de passar dina specifika behov.

```csharp
using Aspose.Slides.Charts;

public static void CustomizeChartDataAndSeries()
{
    // Instansiera presentationsklassen som representerar en PPTX-fil
    Presentation presentation = new Presentation();
    
    // Åtkomst till första bilden
    ISlide slides = presentation.Slides[0];
    
    // Lägg till diagram med standarddata på bilden
    IChart chart = slides.Shapes.AddChart(ChartType.Pie, 100, 100, 400, 400);
    
    // Ställ in första serien på Visa värden
    chart.ChartData.Series[0].Labels.DefaultDataLabelFormat.ShowValue = true;
    
    // Ställa in index för diagramdatablad
    int defaultWorksheetIndex = 0;
    
    // Hämta diagramdataarbetsbladet
    IChartDataWorkbook fact = chart.ChartData.ChartDataWorkbook;
    
    // Ta bort standardgenererade serier och kategorier
    chart.ChartData.Series.Clear();
    chart.ChartData.Categories.Clear();
    
    // Lägger till nya kategorier
    chart.ChartData.Categories.Add(fact.GetCell(0, 1, 0, "First Qtr"));
    chart.ChartData.Categories.Add(fact.GetCell(0, 2, 0, "2nd Qtr"));
    chart.ChartData.Categories.Add(fact.GetCell(0, 3, 0, "3rd Qtr"));
    
    // Lägger till nya serier
    IChartSeries series = chart.ChartData.Series.Add(fact.GetCell(0, 0, 1, "Series 1"), chart.Type);
    
    // Nu fyller seriedata
    series.DataPoints.AddDataPointForPieSeries(fact.GetCell(defaultWorksheetIndex, 1, 1, 20));
    series.DataPoints.AddDataPointForPieSeries(fact.GetCell(defaultWorksheetIndex, 2, 1, 50));
    series.DataPoints.AddDataPointForPieSeries(fact.GetCell(defaultWorksheetIndex, 3, 1, 30));
}
```

### Anpassa sektorstilar för cirkeldiagram
**Översikt:** Stilisera enskilda sektorer i ditt cirkeldiagram för att förbättra den visuella attraktionskraften och betona viktiga datapunkter.

```csharp
using Aspose.Slides.Charts;
using System.Drawing;

public static void CustomizePieChartSectorStyles()
{
    // Instansiera presentationsklassen som representerar en PPTX-fil
    Presentation presentation = new Presentation();
    
    // Åtkomst till första bilden
    ISlide slides = presentation.Slides[0];
    
    // Lägg till diagram med standarddata på bilden
    IChart chart = slides.Shapes.AddChart(ChartType.Pie, 100, 100, 400, 400);
    
    // Hämta serier från diagrammet
    IChartSeries series = chart.ChartData.Series[0];
    
    // Anpassa sektorstilar för varje datapunkt i serien
    IChartDataPoint point = series.DataPoints[0];
    point.Format.Fill.FillType = FillType.Solid;
    point.Format.Fill.SolidFillColor.Color = Color.Cyan;
    
    // Ställa in sektorgräns
    point.Format.Line.FillFormat.FillType = FillType.Solid;
    point.Format.Line.FillFormat.SolidFillColor.Color = Color.Gray;
    point.Format.Line.Width = 3.0;
    point.Format.Line.Style = LineStyle.ThinThick;
    point.Format.Line.DashStyle = LineDashStyle.DashDot;

    IChartDataPoint point1 = series.DataPoints[1];
    point1.Format.Fill.FillType = FillType.Solid;
    point1.Format.Fill.SolidFillColor.Color = Color.Green;
    
    // Ställa in sektorgräns
    point1.Format.Line.FillFormat.FillType = FillType.Solid;
    point1.Format.Line.FillFormat.SolidFillColor.Color = Color.Black;
    point1.Format.Line.Width = 2.0;
    point1.Format.Line.Style = LineStyle.Solid;

    IChartDataPoint point2 = series.DataPoints[2];
    point2.Format.Fill.FillType = FillType.Solid;
    point2.Format.Fill.SolidFillColor.Color = Color.Yellow;
    
    // Ställa in sektorgräns
    point2.Format.Line.FillFormat.FillType = FillType.Solid;
    point2.Format.Line.FillFormat.SolidFillColor.Color = Color.Red;
    point2.Format.Line.Width = 2.0;
    point2.Format.Line.Style = LineStyle.Dot;
}
```

### Lägg till anpassade etiketter i cirkeldiagrammet
**Översikt:** Förbättra ditt cirkeldiagram genom att lägga till anpassade etiketter för tydligare datarepresentation.

```csharp
public static void AddCustomLabelsToPieChart(IChart chart)
{
    IChartDataWorkbook fact = chart.ChartData.ChartDataWorkbook;
    IChartSeries series = chart.ChartData.Series[0];

    foreach (IChartDataPoint point in series.DataPoints)
    {
        IDataLabel lbl = point.Label;
        lbl.TextFrameForOverriding.Text = $"{point.Value}";
        lbl.Position = LegendPositionType.Center; // Justera etikettpositionen efter behov
    }
}
```

### Slutsats
Du har nu lärt dig hur du skapar och anpassar cirkeldiagram i .NET-presentationer med hjälp av Aspose.Slides. Denna automatisering kan avsevärt förbättra dina datavisualiseringsinsatser, spara tid och säkerställa enhetlighet i alla presentationer.

För att ytterligare utforska funktionerna i Aspose.Slides för .NET, överväg att utforska ytterligare funktioner som att skapa andra diagramtyper eller integrera mer komplexa designelement i dina bilder.

Lycka till med kodningen!

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}