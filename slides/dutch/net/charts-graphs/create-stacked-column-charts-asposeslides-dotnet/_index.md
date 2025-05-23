---
"date": "2025-04-15"
"description": "Leer hoe u visueel aantrekkelijke, op percentages gebaseerde, gestapelde kolomdiagrammen maakt met Aspose.Slides voor .NET. Volg deze stapsgewijze handleiding voor duidelijke datavisualisatie."
"title": "Hoe u op percentages gebaseerde gestapelde kolomdiagrammen in .NET kunt maken met behulp van Aspose.Slides"
"url": "/nl/net/charts-graphs/create-stacked-column-charts-asposeslides-dotnet/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Een op percentages gebaseerd gestapeld kolomdiagram maken met Aspose.Slides voor .NET

## Invoering

Op het gebied van datavisualisatie is het duidelijk en effectief presenteren van informatie cruciaal voor effectieve besluitvorming. Om complexe datasets intuïtief weer te geven, zijn op percentages gebaseerde gestapelde kolomdiagrammen ideaal. Deze handleiding begeleidt u bij het maken van deze diagrammen met Aspose.Slides voor .NET, een robuuste bibliotheek voor het bewerken van presentatiebestanden.

Door deze tutorial te volgen, leert u:
- Grafiekgegevens instellen en getalnotaties configureren.
- Serieën toevoegen en hun uiterlijk aanpassen.
- Labels opmaken voor een betere leesbaarheid.

Klaar om te beginnen? Laten we beginnen met de vereisten die je nodig hebt!

## Vereisten

Voordat u uw op percentages gebaseerde gestapelde kolomdiagrammen maakt, moet u ervoor zorgen dat uw omgeving correct is ingesteld. U hebt het volgende nodig:

### Vereiste bibliotheken, versies en afhankelijkheden
- **Aspose.Slides voor .NET**: Zorg ervoor dat deze bibliotheek is geïnstalleerd.

### Vereisten voor omgevingsinstellingen
- Een ontwikkelomgeving met de .NET SDK geïnstalleerd.
- Visual Studio of een andere compatibele IDE voor het uitvoeren van C#-code.

### Kennisvereisten
- Basiskennis van C#-programmering.
- Kennis van .NET-projectconfiguratie en pakketbeheer.

## Aspose.Slides instellen voor .NET

Om met Aspose.Slides grafieken te kunnen maken, moet u eerst de bibliotheek installeren met een van de volgende methoden:

**.NET CLI**
```bash
dotnet add package Aspose.Slides
```

**Pakketbeheerder**
```powershell
Install-Package Aspose.Slides
```

**NuGet Package Manager-gebruikersinterface**
- Zoek naar "Aspose.Slides" en installeer de nieuwste versie.

### Stappen voor het verkrijgen van een licentie

Begin met een gratis proefperiode door een tijdelijke licentie te downloaden van [De website van Aspose](https://purchase.aspose.com/temporary-license/)Voor voortgezet gebruik kunt u overwegen een volledige licentie aan te schaffen. 

Zodra u Aspose.Slides hebt ingesteld, start u het in uw project:
```csharp
using Aspose.Slides;
```

## Implementatiegids

Nu de omgeving gereed is, kunnen we het maken van een op percentages gebaseerd gestapeld kolomdiagram opsplitsen in stappen.

### Het diagram maken en configureren

#### Overzicht
Maak een exemplaar van de `Presentation` klasse, die essentieel is voor het werken met dia's. Voeg vervolgens een gestapeld kolomdiagram toe aan uw dia en configureer het.

#### Een gestapelde kolomgrafiek toevoegen
```csharp
// Een exemplaar van de presentatieklasse maken
document = new Presentation();

// Verwijs naar de eerste dia
slide = document.Slides[0];

// PercentsStackedColumn-diagram toevoegen op positie (20, 20) met grootte (500x400)
chart = slide.Shapes.AddChart(ChartType.PercentsStackedColumn, 20, 20, 500, 400);
```

#### Getallennotatie configureren
Zorg ervoor dat uw gegevens als percentages worden weergegeven:
```csharp
// Configureer getalnotatie voor de verticale as
columnChart.Axes.VerticalAxis.IsNumberFormatLinkedToSource = false;
columnChart.Axes.VerticalAxis.NumberFormat = "0.00%"; // Stel getalnotatie in op percentage
```

#### Gegevensreeksen en punten toevoegen
Bestaande reeksgegevens wissen en nieuwe toevoegen:
```csharp
// Wis alle bestaande reeksgegevens
columnChart.ChartData.Series.Clear();

int defaultWorksheetIndex = 0;

// Werkmap met toegang tot grafiekgegevens
dataWorkbook = columnChart.ChartData.ChartDataWorkbook;

// Voeg een nieuwe gegevensreeks toe "Rood"
series = columnChart.ChartData.Series.Add(dataWorkbook.GetCell(defaultWorksheetIndex, 0, 1, "Reds"), columnChart.Type);
series.DataPoints.AddDataPointForBarSeries(dataWorkbook.GetCell(defaultWorksheetIndex, 1, 1, 0.30));
series.DataPoints.AddDataPointForBarSeries(dataWorkbook.GetCell(defaultWorksheetIndex, 2, 1, 0.50));
series.DataPoints.AddDataPointForBarSeries(dataWorkbook.GetCell(defaultWorksheetIndex, 3, 1, 0.80));
series.DataPoints.AddDataPointForBarSeries(dataWorkbook.GetCell(defaultWorksheetIndex, 4, 1, 0.65));

// Stel de vulkleur voor de serie in op Rood
series.Format.Fill.FillType = FillType.Solid;
series.Format.Fill.SolidFillColor.Color = System.Drawing.Color.Red;

// Configureer labelopmaakeigenschappen voor de serie "Reds"
series.Labels.DefaultDataLabelFormat.ShowValue = true;
series.Labels.DefaultDataLabelFormat.IsNumberFormatLinkedToSource = false;
series.Labels.DefaultDataLabelFormat.NumberFormat = "0.0%"; // Percentage-indeling instellen
columnChart.Series[0].Labels.DefaultDataLabelFormat.TextFormat.PortionFormat.FontHeight = 10;
columnChart.Series[0].Labels.DefaultDataLabelFormat.TextFormat.PortionFormat.FillFormat.FillType = FillType.Solid;
columnChart.Series[0].Labels.DefaultDataLabelFormat.TextFormat.PortionFormat.FillFormat.SolidFillColor.Color = System.Drawing.Color.White;

// Voeg nog een serie toe "Blues"
series2 = columnChart.ChartData.Series.Add(dataWorkbook.GetCell(defaultWorksheetIndex, 0, 2, "Blues"), chart.Type);
series2.DataPoints.AddDataPointForBarSeries(dataWorkbook.GetCell(defaultWorksheetIndex, 1, 2, 0.70));
series2.DataPoints.AddDataPointForBarSeries(dataWorkbook.GetCell(defaultWorksheetIndex, 2, 2, 0.50));
series2.DataPoints.AddDataPointForBarSeries(dataWorkbook.GetCell(defaultWorksheetIndex, 3, 2, 0.20));
series2.DataPoints.AddDataPointForBarSeries(dataWorkbook.GetCell(defaultWorksheetIndex, 4, 2, 0.35));

// Stel de vulkleur voor de serie in op Blauw
series2.Format.Fill.FillType = FillType.Solid;
series2.Format.Fill.SolidFillColor.Color = System.Drawing.Color.Blue;
series2.Labels.DefaultDataLabelFormat.ShowValue = true;
columnChart.Series[1].Labels.DefaultDataLabelFormat.IsNumberFormatLinkedToSource = false;
series2.Labels.DefaultDataLabelFormat.NumberFormat = "0.0%"; // Percentage-indeling instellen
columnChart.Series[1].Labels.DefaultDataLabelFormat.TextFormat.PortionFormat.FontHeight = 10;
columnChart.Series[1].Labels.DefaultDataLabelFormat.TextFormat.PortionFormat.FillFormat.FillType = FillType.Solid;
columnChart.Series[1].Labels.DefaultDataLabelFormat.TextFormat.PortionFormat.FillFormat.SolidFillColor.Color = System.Drawing.Color.White;
```

#### De presentatie opslaan
Sla uw presentatie op in een bestand:
```csharp
// Sla de presentatie op in PPTX-formaat
document.Save("YOUR_OUTPUT_DIRECTORY/SetDataLabelsPercentageSign_out.pptx");
```

### Tips voor probleemoplossing
- Zorg ervoor dat alle naamruimten correct zijn geïmporteerd.
- Controleer op typefouten in eigenschapsnamen en methodeaanroepen.
- Controleer of de paden voor het opslaan van bestanden bestaan en of u de juiste machtigingen hebt.

## Praktische toepassingen

Hier zijn enkele scenario's waarin op percentages gebaseerde gestapelde kolomdiagrammen waardevol kunnen zijn:
1. **Verkoopanalyse**:Visualiseer de productprestaties in verschillende regio's als een percentage van de totale omzet.
2. **Budgettoewijzing**: Laat zien hoe afdelingen hun budget verdelen in verhouding tot de totale uitgaven van het bedrijf.
3. **Marktonderzoek**: Vergelijk consumentenvoorkeuren voor verschillende productcategorieën in de loop van de tijd.
4. **Onderwijsgegevens**: Geef de verdeling van de cijfers van studenten in verschillende vakken weer.
5. **Gezondheidszorgstatistieken**: Geef patiëntgegevens weer met betrekking tot verschillende gezondheidsproblemen.

## Prestatieoverwegingen

Voor optimale prestaties kunt u het volgende overwegen:
- Beperk het aantal datapunten tot het noodzakelijke.
- Gegevens vooraf laden om de runtime-verwerking te minimaliseren.
- Efficiënt geheugenbeheer toepassen met Aspose.Slides voor .NET.

## Conclusie

Gefeliciteerd! Je hebt succesvol geleerd hoe je een op percentages gebaseerd gestapeld kolomdiagram maakt met Aspose.Slides voor .NET. Deze tool verbetert presentaties door complexe gegevens begrijpelijker en visueel aantrekkelijker te maken.

Volgende stappen? Ontdek andere grafiektypen die beschikbaar zijn in Aspose.Slides of integreer deze functionaliteit in grotere applicaties. Veel plezier met coderen!

## FAQ-sectie

**V1: Kan ik Aspose.Slides gratis gebruiken?**
A1: Ja, u kunt beginnen met een gratis proefperiode om de functies van Aspose.Slides te testen.

**Vraag 2: Welke grafiektypen worden ondersteund door Aspose.Slides voor .NET?**
A2: Het ondersteunt verschillende diagrammen, zoals cirkel-, staaf-, kolom-, lijndiagrammen en meer.

**V3: Hoe ga ik aan de slag met Aspose.Slides voor .NET?**
A3: Installeer de bibliotheek met NuGet of .NET CLI zoals hierboven beschreven. Volg onze documentatie om uw eerste grafiek te maken.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}