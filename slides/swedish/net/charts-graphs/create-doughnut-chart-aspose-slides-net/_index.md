---
"date": "2025-04-15"
"description": "Lär dig hur du skapar dynamiska ringdiagram med Aspose.Slides för .NET. Följ den här guiden för steg-för-steg-instruktioner, inklusive installation och avancerade funktioner."
"title": "Steg-för-steg-guide Skapa ett ringdiagram med Aspose.Slides .NET | Diagram och grafer"
"url": "/sv/net/charts-graphs/create-doughnut-chart-aspose-slides-net/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Steg-för-steg-guide: Skapa ett ringdiagram med Aspose.Slides .NET

## Introduktion

Tänk dig att du har i uppgift att presentera dataanalysresultat för ditt team eller dina kunder, och du behöver ett engagerande sätt att visualisera informationen. Använd ringdiagrammet – ett mångsidigt verktyg som kan omvandla råa siffror till lättförståeliga insikter. Med Aspose.Slides för .NET är det enkelt och effektivt att skapa ett anpassat ringdiagram i dina presentationsbilder. Den här guiden guidar dig genom att använda Aspose.Slides för att skapa ett visuellt tilltalande ringdiagram, komplett med skräddarsydda seriekonfigurationer.

**Vad du kommer att lära dig:**
- Konfigurera din utvecklingsmiljö med Aspose.Slides för .NET
- Skapa och anpassa ringdiagram i presentationer
- Implementera avancerade funktioner som kategorinamn och riktlinjer
- Optimera prestanda för stora datamängder

Låt oss dyka in i de förutsättningar du behöver för att komma igång.

## Förkunskapskrav

Innan du implementerar den här funktionen, se till att din utvecklingsmiljö är korrekt konfigurerad. Den här handledningen förutsätter grundläggande kunskaper om .NET-programmering och förtrogenhet med Visual Studio eller en liknande IDE.

### Nödvändiga bibliotek och versioner
- **Aspose.Slides för .NET**Säkerställ kompatibilitet med den senaste versionen genom att kontrollera deras [officiell dokumentation](https://reference.aspose.com/slides/net/).

### Krav för miljöinstallation
- En fungerande .NET-miljö.
- Tillgång till en kodredigerare, till exempel Visual Studio.

### Kunskapsförkunskaper
- Grundläggande förståelse för C# och .NET framework.
- Bekantskap med koncept inom presentationsprogramvara (valfritt men fördelaktigt).

## Konfigurera Aspose.Slides för .NET

För att börja använda Aspose.Slides i ditt projekt måste du installera det via NuGet. Här är de tillgängliga metoderna:

**Använda .NET CLI:**
```bash
dotnet add package Aspose.Slides
```

**Använda pakethanteraren:**
```powershell
Install-Package Aspose.Slides
```

**NuGet-pakethanterarens användargränssnitt:**
Sök efter "Aspose.Slides" och installera den senaste versionen.

### Steg för att förvärva licens

1. **Gratis provperiod**Börja med en [gratis provperiod](https://releases.aspose.com/slides/net/) att utforska grundläggande funktioner.
2. **Tillfällig licens**Skaffa en tillfällig licens om du behöver tillgång till alla funktioner för utvärderingsändamål genom att besöka [här](https://purchase.aspose.com/temporary-license/).
3. **Köpa**För kommersiellt bruk, köp en licens från [Asposes webbplats](https://purchase.aspose.com/buy).

När Aspose.Slides är installerat och licensierat, initiera dem i ditt projekt:
```csharp
using Aspose.Slides;

// Initiera Aspose.Slides för .NET
var presentation = new Presentation();
```

## Implementeringsguide

### Skapa en ny presentation och lägga till ett ringdiagram

#### Översikt
Vi börjar med att skapa en ny presentation och lägga till ett ringdiagram på den första bilden. Det här avsnittet behandlar hur man laddar en befintlig presentation, öppnar bilder och infogar diagram.

**Steg 1: Ladda eller skapa en presentation**
Ange först din dokumentkatalog och ladda en befintlig presentation:
```csharp
string dataDir = \@"YOUR_DOCUMENT_DIRECTORY";
Presentation pres = new Presentation(dataDir + "testc.pptx");
```
Om du inte har en befintlig fil, skapa en ny med `new Presentation()`.

**Steg 2: Öppna den första bilden**
Få tillgång till den första bilden där vi lägger till vårt diagram:
```csharp
ISlide slide = pres.Slides[0];
```

**Steg 3: Lägg till ett ringdiagram**
Lägg till ett ringdiagram vid angivna koordinater och dimensioner:
```csharp
IChart chart = slide.Shapes.AddChart(ChartType.Doughnut, 10, 10, 500, 500, false);
```

### Konfigurera dataarbetsboken

#### Översikt
Det här avsnittet förklarar hur du konfigurerar dataarbetsboken som är associerad med ditt ringdiagram.

**Steg 4: Åtkomst till och rensa befintliga data**
Gå till diagrammets dataarbetsbok. Rensa sedan alla befintliga serier eller kategorier:
```csharp
IChartDataWorkbook workBook = chart.ChartData.ChartDataWorkbook;
chart.ChartData.Series.Clear();
chart.ChartData.Categories.Clear();
```

**Steg 5: Inaktivera förklaring och lägg till serier**
Inaktivera förklaringen för att hålla diagrammet rent och lägg sedan till upp till 15 serier med anpassade konfigurationer:
```csharp
chart.HasLegend = false;

int seriesIndex = 0;
while (seriesIndex < 15)
{
    IChartSeries series = chart.ChartData.Series.Add(workBook.GetCell(0, 0, seriesIndex + 1, "SERIES " + seriesIndex), chart.Type);
    series.Explosion = 0;
    series.ParentSeriesGroup.DoughnutHoleSize = (byte)20;
    series.ParentSeriesGroup.FirstSliceAngle = 351;
    seriesIndex++;
}
```

### Lägga till kategorier och datapunkter

#### Översikt
Nu ska vi fylla i diagrammet med kategorier och datapunkter för varje serie.

**Steg 6: Lägg till kategorier**
Gå igenom för att lägga till 15 kategorier:
```csharp
int categoryIndex = 0;
while (categoryIndex < 15)
{
    chart.ChartData.Categories.Add(workBook.GetCell(0, categoryIndex + 1, 0, "CATEGORY " + categoryIndex));
```

**Steg 7: Fyll i datapunkter**
Lägg till datapunkter för varje serie inom den aktuella kategorin:
```csharp
int i = 0;
while (i < chart.ChartData.Series.Count)
{
    IChartSeries iCS = chart.ChartData.Series[i];
    IChartDataPoint dataPoint = iCS.DataPoints.AddDataPointForDoughnutSeries(workBook.GetCell(0, categoryIndex + 1, i + 1, 1));

    // Anpassa utseendet
    dataPoint.Format.Fill.FillType = FillType.Solid;
    dataPoint.Format.Line.FillFormat.FillType = FillType.Solid;
    dataPoint.Format.Line.FillFormat.SolidFillColor.Color = System.Drawing.Color.White;
    dataPoint.Format.Line.Width = 1;
    dataPoint.Format.Line.Style = LineStyle.Single;
    dataPoint.Format.Line.DashStyle = LineDashStyle.Solid;

    // Konfigurera etikettformat för den senaste serien
    if (i == chart.ChartData.Series.Count - 1)
    {
        IDataLabel lbl = dataPoint.Label;
        lbl.TextFormat.TextBlockFormat.AutofitType = TextAutofitType.Shape;
        lbl.DataLabelFormat.TextFormat.PortionFormat.FontBold = NullableBool.True;
        lbl.DataLabelFormat.TextFormat.PortionFormat.LatinFont = new FontData("DINPro-Bold");
        lbl.DataLabelFormat.TextFormat.PortionFormat.FontHeight = 12;
        lbl.DataLabelFormat.TextFormat.PortionFormat.FillFormat.FillType = FillType.Solid;
        lbl.DataLabelFormat.TextFormat.PortionFormat.FillFormat.SolidFillColor.Color = System.Drawing.Color.LightGray;
        lbl.DataLabelFormat.Format.Line.FillFormat.SolidFillColor.Color = System.Drawing.Color.White;

        // Konfigurera etikettvisning
        lbl.DataLabelFormat.ShowValue = false;
        lbl.DataLabelFormat.ShowCategoryName = true;
        lbl.DataLabelFormat.ShowSeriesName = false;
        lbl.DataLabelFormat.ShowLeaderLines = true;

        chart.ValidateChartLayout();
        lbl.AsILayoutable.X += 0.5f;
        lbl.AsILayoutable.Y += 0.5f;
    }
    i++;
}
categoryIndex++;
```

### Spara presentationen

**Steg 8: Spara filen**
Slutligen, spara din presentation till en angiven katalog:
```csharp
pres.Save(dataDir + "chart.pptx\

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}