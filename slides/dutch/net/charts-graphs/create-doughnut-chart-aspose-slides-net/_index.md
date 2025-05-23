---
"date": "2025-04-15"
"description": "Leer hoe u dynamische ringdiagrammen maakt met Aspose.Slides voor .NET. Volg deze handleiding voor stapsgewijze instructies, inclusief installatie en geavanceerde functies."
"title": "Stapsgewijze handleiding&#58; maak een donutdiagram met Aspose.Slides .NET | Grafieken en diagrammen"
"url": "/nl/net/charts-graphs/create-doughnut-chart-aspose-slides-net/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Stapsgewijze handleiding: een donutdiagram maken met Aspose.Slides .NET

## Invoering

Stel je voor dat je de resultaten van data-analyses moet presenteren aan je team of klanten en je hebt een aantrekkelijke manier nodig om de informatie te visualiseren. Maak kennis met het ringdiagram: een veelzijdige tool die ruwe cijfers kan omzetten in gemakkelijk te begrijpen inzichten. Met Aspose.Slides voor .NET is het maken van een aangepast ringdiagram in je presentatieslides eenvoudig en efficiënt. Deze handleiding begeleidt je bij het gebruik van Aspose.Slides om een visueel aantrekkelijk ringdiagram te maken, compleet met aangepaste reeksconfiguraties.

**Wat je leert:**
- Uw ontwikkelomgeving instellen met Aspose.Slides voor .NET
- Het maken en aanpassen van ringdiagrammen in presentaties
- Geavanceerde functies implementeren, zoals categorienamen en leiderlijnen
- Prestaties optimaliseren voor grote datasets

Laten we eens kijken naar de vereisten die je nodig hebt om te beginnen.

## Vereisten

Voordat u deze functie implementeert, moet u ervoor zorgen dat uw ontwikkelomgeving correct is ingesteld. Deze tutorial veronderstelt basiskennis van .NET-programmering en vertrouwdheid met Visual Studio of een vergelijkbare IDE.

### Vereiste bibliotheken en versies
- **Aspose.Slides voor .NET**: Zorg ervoor dat de compatibiliteit met de nieuwste versie is gewaarborgd door de volgende informatie te controleren: [officiële documentatie](https://reference.aspose.com/slides/net/).

### Vereisten voor omgevingsinstellingen
- Een werkende .NET-omgeving.
- Toegang tot een code-editor, zoals Visual Studio.

### Kennisvereisten
- Basiskennis van C# en .NET Framework.
- Kennis van presentatiesoftwareconcepten (optioneel, maar nuttig).

## Aspose.Slides instellen voor .NET

Om Aspose.Slides in uw project te kunnen gebruiken, moet u het via NuGet installeren. Hieronder staan de beschikbare methoden:

**Met behulp van .NET CLI:**
```bash
dotnet add package Aspose.Slides
```

**Pakketbeheer gebruiken:**
```powershell
Install-Package Aspose.Slides
```

**Gebruikersinterface van NuGet Package Manager:**
Zoek naar "Aspose.Slides" en installeer de nieuwste versie.

### Stappen voor het verkrijgen van een licentie

1. **Gratis proefperiode**: Begin met een [gratis proefperiode](https://releases.aspose.com/slides/net/) om basisfunctionaliteiten te verkennen.
2. **Tijdelijke licentie**: Verkrijg een tijdelijke licentie als u toegang nodig hebt tot alle functies voor evaluatiedoeleinden door naar [hier](https://purchase.aspose.com/temporary-license/).
3. **Aankoop**: Voor commercieel gebruik, koop een licentie van de [Aspose-website](https://purchase.aspose.com/buy).

Nadat u Aspose.Slides hebt geïnstalleerd en gelicentieerd, initialiseert u het in uw project:
```csharp
using Aspose.Slides;

// Initialiseer Aspose.Slides voor .NET
var presentation = new Presentation();
```

## Implementatiegids

### Een nieuwe presentatie maken en een ringdiagram toevoegen

#### Overzicht
We beginnen met het maken van een nieuwe presentatie en voegen een ringdiagram toe aan de eerste dia. Deze sectie behandelt het laden van een bestaande presentatie, het openen van dia's en het invoegen van diagrammen.

**Stap 1: Laad of maak een presentatie**
Geef eerst uw documentmap op en laad een bestaande presentatie:
```csharp
string dataDir = \@"YOUR_DOCUMENT_DIRECTORY";
Presentation pres = new Presentation(dataDir + "testc.pptx");
```
Als u geen bestaand bestand hebt, maak dan een nieuw bestand met `new Presentation()`.

**Stap 2: Toegang tot de eerste dia**
Krijg toegang tot de eerste dia waar we onze grafiek zullen toevoegen:
```csharp
ISlide slide = pres.Slides[0];
```

**Stap 3: Voeg een donutdiagram toe**
Voeg een ringdiagram toe met de opgegeven coördinaten en afmetingen:
```csharp
IChart chart = slide.Shapes.AddChart(ChartType.Doughnut, 10, 10, 500, 500, false);
```

### Het gegevenswerkboek configureren

#### Overzicht
In dit gedeelte wordt uitgelegd hoe u de gegevenswerkmap configureert die aan uw ringdiagram is gekoppeld.

**Stap 4: Toegang krijgen tot en bestaande gegevens wissen**
Open de gegevenswerkmap van de grafiek. Wis vervolgens alle bestaande reeksen of categorieën:
```csharp
IChartDataWorkbook workBook = chart.ChartData.ChartDataWorkbook;
chart.ChartData.Series.Clear();
chart.ChartData.Categories.Clear();
```

**Stap 5: Legenda uitschakelen en reeksen toevoegen**
Schakel de legenda uit om de grafiek overzichtelijk te houden en voeg vervolgens maximaal 15 reeksen toe met aangepaste configuraties:
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

### Categorieën en datapunten toevoegen

#### Overzicht
Laten we nu de grafiek vullen met categorieën en datapunten voor elke reeks.

**Stap 6: Categorieën toevoegen**
Ga door om 15 categorieën toe te voegen:
```csharp
int categoryIndex = 0;
while (categoryIndex < 15)
{
    chart.ChartData.Categories.Add(workBook.GetCell(0, categoryIndex + 1, 0, "CATEGORY " + categoryIndex));
```

**Stap 7: Gegevenspunten vullen**
Voeg datapunten toe voor elke reeks binnen de huidige categorie:
```csharp
int i = 0;
while (i < chart.ChartData.Series.Count)
{
    IChartSeries iCS = chart.ChartData.Series[i];
    IChartDataPoint dataPoint = iCS.DataPoints.AddDataPointForDoughnutSeries(workBook.GetCell(0, categoryIndex + 1, i + 1, 1));

    // Uiterlijk aanpassen
    dataPoint.Format.Fill.FillType = FillType.Solid;
    dataPoint.Format.Line.FillFormat.FillType = FillType.Solid;
    dataPoint.Format.Line.FillFormat.SolidFillColor.Color = System.Drawing.Color.White;
    dataPoint.Format.Line.Width = 1;
    dataPoint.Format.Line.Style = LineStyle.Single;
    dataPoint.Format.Line.DashStyle = LineDashStyle.Solid;

    // Labelformaat configureren voor de laatste serie
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

        // Labelweergave configureren
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

### De presentatie opslaan

**Stap 8: Sla het bestand op**
Sla ten slotte uw presentatie op in de opgegeven map:
```csharp
pres.Save(dataDir + "chart.pptx\

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}