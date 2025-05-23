---
"date": "2025-04-15"
"description": "Leer hoe u automatisch cirkeldiagrammen kunt maken in .NET-presentaties met Aspose.Slides, waarmee u moeiteloos uw gegevensvisualisatie kunt verbeteren."
"title": "Cirkeldiagrammen maken en aanpassen in .NET-presentaties met Aspose.Slides"
"url": "/nl/net/charts-graphs/create-style-pie-charts-net-asposeslides/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Cirkeldiagrammen maken en aanpassen in .NET-presentaties met Aspose.Slides

## Invoering
Het maken van boeiende en informatieve presentaties is cruciaal voor effectieve communicatie, of u nu gegevens op uw werk presenteert of uw nieuwste projectresultaten presenteert. Een krachtige manier om gegevens te visualiseren is met cirkeldiagrammen, die delen van een geheel beknopt kunnen weergeven. Het handmatig maken van dergelijke diagrammen in presentatiesoftware zoals PowerPoint kan echter tijdrovend zijn en mist mogelijk de flexibiliteit die nodig is voor dynamische updates.

Daar komt Aspose.Slides voor .NET om de hoek kijken. Met deze uitgebreide bibliotheek kun je presentaties programmatisch maken, aanpassen en stylen, wat het een onmisbare tool maakt voor ontwikkelaars die hun workflow willen automatiseren en consistentie in presentaties willen garanderen.

In deze tutorial laten we zien hoe je Aspose.Slides voor .NET kunt gebruiken om cirkeldiagrammen in je presentaties te maken en aan te passen. Je leert het volgende:
- **Een presentatie maken en toegang krijgen tot dia's**
- **Cirkeldiagrammen toevoegen en configureren**
- **Pas grafiekgegevens en reeksen aan**
- **Stijl cirkeldiagram sectoren**
- **Aangepaste labels toevoegen**
- **Weergave-eigenschappen configureren en de presentatie opslaan**

Klaar om eenvoudig verbluffende cirkeldiagrammen te maken? Laten we beginnen!

## Vereisten
Voordat we beginnen, zorg ervoor dat u de volgende instellingen hebt:

### Vereiste bibliotheken
- Aspose.Slides voor .NET (versie 21.11 of later aanbevolen)

### Omgevingsinstelling
- Een ontwikkelomgeving met .NET Framework of .NET Core/5+/6+
- Een code-editor zoals Visual Studio

### Kennisvereisten
- Basiskennis van C#-programmering
- Kennis van objectgeoriënteerde concepten

## Aspose.Slides instellen voor .NET
Om te beginnen moet je de Aspose.Slides-bibliotheek installeren. Je kunt dit op een van de volgende manieren doen:

**.NET CLI**
```bash
dotnet add package Aspose.Slides
```

**Pakketbeheerconsole**
```powershell
Install-Package Aspose.Slides
```

**NuGet Package Manager-gebruikersinterface**
- Open uw project in Visual Studio.
- Ga naar 'Extra' > 'NuGet-pakketbeheer' > 'NuGet-pakketten beheren voor oplossing'.
- Zoek naar "Aspose.Slides" en installeer de nieuwste versie.

### Stappen voor het verkrijgen van een licentie
Om Aspose.Slides te gebruiken, kunt u beginnen met een gratis proefperiode door een tijdelijke licentie te downloaden. Bezoek [De website van Aspose](https://purchase.aspose.com/temporary-license/) Om het te verkrijgen. Overweeg voor doorlopend gebruik een volledige licentie aan te schaffen.

### Basisinitialisatie en -installatie
Nadat u deze hebt geïnstalleerd, initialiseert u de Presentation-klasse, die uw PPTX-bestand vertegenwoordigt:

```csharp
using Aspose.Slides;

Presentation presentation = new Presentation();
```

## Implementatiegids
We zullen het proces van het maken van een cirkeldiagram opsplitsen in hanteerbare secties. Elke sectie is ontworpen om zich te richten op een specifieke functie, zodat je je kennis stapsgewijs kunt uitbreiden.

### Een presentatie maken en toegang krijgen tot dia's
**Overzicht:** Begin met het maken van een nieuwe presentatie en open de eerste dia. Dit is de basis voor het toevoegen van grafieken en andere elementen.

```csharp
using Aspose.Slides;

public static void CreatePresentationAndAccessSlide()
{
    // Instantieer presentatieklasse die een PPTX-bestand vertegenwoordigt
    Presentation presentation = new Presentation();
    
    // Toegang tot eerste dia
    ISlide slides = presentation.Slides[0];
}
```

### Cirkeldiagram toevoegen en configureren
**Overzicht:** Leer hoe u een cirkeldiagram aan uw dia toevoegt en de titel ervan instelt voor context.

```csharp
using Aspose.Slides;
using Aspose.Slides.Charts;

public static void AddAndConfigurePieChart()
{
    // Instantieer presentatieklasse die een PPTX-bestand vertegenwoordigt
    Presentation presentation = new Presentation();
    
    // Toegang tot eerste dia
    ISlide slides = presentation.Slides[0];
    
    // Grafiek met standaardgegevens aan de dia toevoegen
    IChart chart = slides.Shapes.AddChart(ChartType.Pie, 100, 100, 400, 400);
    
    // Titel van de instellingsgrafiek
    chart.ChartTitle.AddTextFrameForOverriding("Sample Title");
    chart.ChartTitle.TextFrameForOverriding.TextFrameFormat.CenterText = NullableBool.True;
    chart.ChartTitle.Height = 20;
    chart.HasTitle = true;
}
```

### Pas grafiekgegevens en reeksen aan
**Overzicht:** Pas de gegevenscategorieën en reeksen aan uw specifieke vereisten aan.

```csharp
using Aspose.Slides.Charts;

public static void CustomizeChartDataAndSeries()
{
    // Instantieer presentatieklasse die een PPTX-bestand vertegenwoordigt
    Presentation presentation = new Presentation();
    
    // Toegang tot eerste dia
    ISlide slides = presentation.Slides[0];
    
    // Grafiek met standaardgegevens aan de dia toevoegen
    IChart chart = slides.Shapes.AddChart(ChartType.Pie, 100, 100, 400, 400);
    
    // Stel de eerste reeks in op Waarden weergeven
    chart.ChartData.Series[0].Labels.DefaultDataLabelFormat.ShowValue = true;
    
    // De index van het grafiekgegevensblad instellen
    int defaultWorksheetIndex = 0;
    
    // Het werkblad met grafiekgegevens ophalen
    IChartDataWorkbook fact = chart.ChartData.ChartDataWorkbook;
    
    // Standaard gegenereerde series en categorieën verwijderen
    chart.ChartData.Series.Clear();
    chart.ChartData.Categories.Clear();
    
    // Nieuwe categorieën toevoegen
    chart.ChartData.Categories.Add(fact.GetCell(0, 1, 0, "First Qtr"));
    chart.ChartData.Categories.Add(fact.GetCell(0, 2, 0, "2nd Qtr"));
    chart.ChartData.Categories.Add(fact.GetCell(0, 3, 0, "3rd Qtr"));
    
    // Nieuwe series toevoegen
    IChartSeries series = chart.ChartData.Series.Add(fact.GetCell(0, 0, 1, "Series 1"), chart.Type);
    
    // Nu worden reeksgegevens ingevuld
    series.DataPoints.AddDataPointForPieSeries(fact.GetCell(defaultWorksheetIndex, 1, 1, 20));
    series.DataPoints.AddDataPointForPieSeries(fact.GetCell(defaultWorksheetIndex, 2, 1, 50));
    series.DataPoints.AddDataPointForPieSeries(fact.GetCell(defaultWorksheetIndex, 3, 1, 30));
}
```

### Sectorstijlen van cirkeldiagrammen aanpassen
**Overzicht:** Geef de afzonderlijke sectoren van uw cirkeldiagram meer stijl om de visuele aantrekkingskracht te vergroten en de nadruk te leggen op belangrijke gegevenspunten.

```csharp
using Aspose.Slides.Charts;
using System.Drawing;

public static void CustomizePieChartSectorStyles()
{
    // Instantieer presentatieklasse die een PPTX-bestand vertegenwoordigt
    Presentation presentation = new Presentation();
    
    // Toegang tot eerste dia
    ISlide slides = presentation.Slides[0];
    
    // Grafiek met standaardgegevens aan de dia toevoegen
    IChart chart = slides.Shapes.AddChart(ChartType.Pie, 100, 100, 400, 400);
    
    // Serie uit grafiek halen
    IChartSeries series = chart.ChartData.Series[0];
    
    // Sectorstijlen aanpassen voor elk gegevenspunt in de reeks
    IChartDataPoint point = series.DataPoints[0];
    point.Format.Fill.FillType = FillType.Solid;
    point.Format.Fill.SolidFillColor.Color = Color.Cyan;
    
    // Sectorgrens instellen
    point.Format.Line.FillFormat.FillType = FillType.Solid;
    point.Format.Line.FillFormat.SolidFillColor.Color = Color.Gray;
    point.Format.Line.Width = 3.0;
    point.Format.Line.Style = LineStyle.ThinThick;
    point.Format.Line.DashStyle = LineDashStyle.DashDot;

    IChartDataPoint point1 = series.DataPoints[1];
    point1.Format.Fill.FillType = FillType.Solid;
    point1.Format.Fill.SolidFillColor.Color = Color.Green;
    
    // Sectorgrens instellen
    point1.Format.Line.FillFormat.FillType = FillType.Solid;
    point1.Format.Line.FillFormat.SolidFillColor.Color = Color.Black;
    point1.Format.Line.Width = 2.0;
    point1.Format.Line.Style = LineStyle.Solid;

    IChartDataPoint point2 = series.DataPoints[2];
    point2.Format.Fill.FillType = FillType.Solid;
    point2.Format.Fill.SolidFillColor.Color = Color.Yellow;
    
    // Sectorgrens instellen
    point2.Format.Line.FillFormat.FillType = FillType.Solid;
    point2.Format.Line.FillFormat.SolidFillColor.Color = Color.Red;
    point2.Format.Line.Width = 2.0;
    point2.Format.Line.Style = LineStyle.Dot;
}
```

### Aangepaste labels toevoegen aan cirkeldiagram
**Overzicht:** Verbeter uw cirkeldiagram door aangepaste labels toe te voegen voor een duidelijker beeld van uw gegevens.

```csharp
public static void AddCustomLabelsToPieChart(IChart chart)
{
    IChartDataWorkbook fact = chart.ChartData.ChartDataWorkbook;
    IChartSeries series = chart.ChartData.Series[0];

    foreach (IChartDataPoint point in series.DataPoints)
    {
        IDataLabel lbl = point.Label;
        lbl.TextFrameForOverriding.Text = $"{point.Value}";
        lbl.Position = LegendPositionType.Center; // Pas de labelpositie indien nodig aan
    }
}
```

### Conclusie
U hebt nu geleerd hoe u cirkeldiagrammen in .NET-presentaties kunt maken en aanpassen met Aspose.Slides. Deze automatisering kan uw datavisualisatie aanzienlijk verbeteren, tijd besparen en consistentie in presentaties garanderen.

Als u de mogelijkheden van Aspose.Slides voor .NET verder wilt verkennen, kunt u zich verdiepen in aanvullende functies zoals het maken van andere grafiektypen of het integreren van complexere ontwerpelementen in uw dia's.

Veel plezier met coderen!

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}