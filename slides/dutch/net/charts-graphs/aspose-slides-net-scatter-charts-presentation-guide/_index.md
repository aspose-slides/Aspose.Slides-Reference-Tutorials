---
"date": "2025-04-15"
"description": "Leer hoe u uw presentaties kunt verbeteren met spreidingsdiagrammen in Aspose.Slides voor .NET. Volg deze uitgebreide handleiding om effectief diagrammen te maken en aan te passen."
"title": "Spreidingsdiagrammen toevoegen aan presentaties met Aspose.Slides .NET&#58; een stapsgewijze handleiding"
"url": "/nl/net/charts-graphs/aspose-slides-net-scatter-charts-presentation-guide/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Spreidingsdiagrammen toevoegen aan presentaties met Aspose.Slides .NET: een stapsgewijze handleiding

## Invoering
Wilt u uw presentaties verbeteren door moeiteloos spreidingsdiagrammen te integreren? Met de kracht van Aspose.Slides voor .NET wordt het maken en aanpassen van diagrammen een fluitje van een cent. Deze tutorial begeleidt u bij het toevoegen van spreidingsdiagrammen aan uw dia's met Aspose.Slides voor .NET. Door deze technieken onder de knie te krijgen, presenteert u gegevens effectiever en maakt u visueel aantrekkelijke presentaties.

**Wat je leert:**
- Aspose.Slides voor .NET in uw project installeren
- Een nieuwe presentatie maken en toegang krijgen tot de eerste dia
- Spreidingsdiagrammen met vloeiende lijnen toevoegen aan dia's
- Bestaande series wissen en nieuwe toevoegen aan grafieken
- Gegevenspunten en markerstijlen aanpassen voor verbeterde visualisatie
- De presentatie opslaan in een opgegeven map

Laten we beginnen met het doornemen van de vereisten.

## Vereisten
Voordat u Aspose.Slides voor .NET implementeert, moet u ervoor zorgen dat u over het volgende beschikt:
- **Aspose.Slides voor .NET-bibliotheek**: Versie 23.7 of later.
- **Ontwikkelomgeving**: Visual Studio 2019 of nieuwer met .NET Framework 4.6.1+ of .NET Core/5+.
- **Basiskennis C#**: Kennis van objectgeoriënteerd programmeren in C#.

## Aspose.Slides instellen voor .NET
Om Aspose.Slides te kunnen gebruiken, moet je de bibliotheek in je project installeren. Zo doe je dat:

**Met behulp van .NET CLI:**
```bash
dotnet add package Aspose.Slides
```

**Pakketbeheerconsole gebruiken:**
```powershell
Install-Package Aspose.Slides
```

**Gebruikersinterface van NuGet Package Manager:**
- Zoek naar "Aspose.Slides" en installeer de nieuwste versie.

### Licentieverwerving
U kunt beginnen met een gratis proefperiode of een tijdelijke licentie aanvragen om alle functies te ontdekken. Volg deze stappen om te kopen:
1. Bezoek [Aankoop Aspose.Slides](https://purchase.aspose.com/buy) om een volledige licentie te kopen.
2. Voor een tijdelijke licentie, bezoek [Tijdelijke licentiepagina](https://purchase.aspose.com/temporary-license/).

Zodra u uw licentiebestand hebt ontvangen, voegt u dit als volgt toe aan uw project:
```csharp
Aspose.Slides.License license = new Aspose.Slides.License();
license.SetLicense("Aspose.Slides.lic");
```

## Implementatiegids
We verdelen de implementatie in logische secties op basis van functies.

### Presentatie maken en dia toevoegen
In dit gedeelte laten we zien hoe u een presentatie maakt en hoe u de eerste dia opent.

#### Overzicht
Begin met het maken van een exemplaar van de `Presentation` klasse, die uw PowerPoint-bestand vertegenwoordigt. Toegang tot dia's is eenvoudig met dit objectmodel.

#### Implementatiestappen
**Stap 1: Presentatie initialiseren**
```csharp
using Aspose.Slides;

// Een nieuwe presentatie maken
t Presentation pres = new Presentation();
```
Deze code initialiseert een nieuw presentatiedocument.

**Stap 2: Toegang tot de eerste dia**
```csharp
// Toegang tot de eerste dia in de presentatie
ISlide slide = pres.Slides[0];
```
Hier, `pres.Slides[0]` geeft toegang tot de allereerste dia. 

### Spreidingsdiagram toevoegen aan dia
Laten we nu een spreidingsdiagram aan uw presentatie toevoegen.

#### Overzicht
Door grafieken toe te voegen, kunt u gegevens visueel weergeven in presentaties. Aspose.Slides maakt het eenvoudig om verschillende soorten grafieken te integreren, waaronder spreidingsdiagrammen.

#### Implementatiestappen
**Stap 1: Spreidingsdiagram maken en toevoegen**
```csharp
using Aspose.Slides.Charts;

// Maak en voeg een standaardspreidingsdiagram met vloeiende lijnen toe
IChart chart = slide.Shapes.AddChart(ChartType.ScatterWithSmoothLines, 0, 0, 400, 400);
```
Met dit fragment wordt een spreidingsdiagram toegevoegd op de opgegeven positie en grootte.

### Wissen en reeksen toevoegen aan grafiekgegevens
#### Overzicht
Mogelijk moet u uw grafiek aanpassen door bestaande reeksen te wissen en nieuwe toe te voegen. Deze sectie behandelt die functionaliteit.

#### Implementatiestappen
**Stap 1: Toegang tot grafiekgegevenswerkmap**
```csharp
int defaultWorksheetIndex = 0;
IChartDataWorkbook fact = chart.ChartData.ChartDataWorkbook;

// Alle bestaande series wissen
chart.ChartData.Series.Clear();
```
Deze code wist bestaande gegevens, zodat er met een nieuwe reeks kan worden begonnen.

**Stap 2: Nieuwe serie toevoegen**
```csharp
// Voeg een nieuwe serie toe met de naam "Serie 1"
chart.ChartData.Series.Add(fact.GetCell(defaultWorksheetIndex, 1, 1, "Series 1"), chart.Type);

// Voeg een andere serie toe met de naam "Serie 2"
chart.ChartData.Series.Add(fact.GetCell(defaultWorksheetIndex, 1, 3, "Series 2"), chart.Type);
```
Met deze stappen worden twee nieuwe reeksen aan de grafiek toegevoegd.

### Wijzig de eerste reeks gegevenspunten en de markeringstijl
#### Overzicht
Pas datapunten en markeringsstijlen aan voor een betere visualisatie van uw spreidingsdiagrammen.

#### Implementatiestappen
**Stap 1: Toegang krijgen tot en toevoegen van datapunten**
```csharp
IChartSeries series = chart.ChartData.Series[0];

// Voeg datapunten (1, 3) en (2, 10) toe
series.DataPoints.AddDataPointForScatterSeries(fact.GetCell(defaultWorksheetIndex, 2, 1, 1), fact.GetCell(defaultWorksheetIndex, 2, 2, 3));
series.DataPoints.AddDataPointForScatterSeries(fact.GetCell(defaultWorksheetIndex, 3, 1, 2), fact.GetCell(defaultWorksheetIndex, 3, 2, 10));
```
**Stap 2: Wijzig de markerstijl**
```csharp
// Wijzig het serietype en wijzig de markeringstijl
series.Type = ChartType.ScatterWithStraightLinesAndMarkers;
series.Marker.Size = 10;
series.Marker.Symbol = MarkerStyleType.Star;
```
### Wijzig de tweede reeks gegevenspunten en de markeringstijl
#### Overzicht
U kunt de tweede serie op vergelijkbare wijze aanpassen aan uw presentatiebehoeften.

#### Implementatiestappen
**Stap 1: Toegang krijgen tot en toevoegen van meerdere datapunten**
```csharp
// Toegang tot de tweede grafiekserie
series = chart.ChartData.Series[1];

// Meerdere datapunten toevoegen
series.DataPoints.AddDataPointForScatterSeries(fact.GetCell(defaultWorksheetIndex, 2, 3, 5), fact.GetCell(defaultWorksheetIndex, 2, 4, 2));
series.DataPoints.AddDataPointForScatterSeries(fact.GetCell(defaultWorksheetIndex, 3, 3, 3), fact.GetCell(defaultWorksheetIndex, 3, 4, 1));
series.DataPoints.AddDataPointForScatterSeries(fact.GetCell(defaultWorksheetIndex, 4, 3, 2), fact.GetCell(defaultWorksheetIndex, 4, 4, 2));
series.DataPoints.AddDataPointForScatterSeries(fact.GetCell(defaultWorksheetIndex, 5, 3, 5), fact.GetCell(defaultWorksheetIndex, 5, 4, 1));
```
**Stap 2: Wijzig de markerstijl**
```csharp
// Wijzig de markeringsgrootte en het symbool voor de tweede reeks
series.Marker.Size = 10;
series.Marker.Symbol = MarkerStyleType.Circle;
```
### Presentatie opslaan
Sla ten slotte uw presentatie op in de opgegeven map.

#### Implementatiestappen
**Stap 1: Directory definiëren**
Zorg ervoor dat de uitvoermap bestaat. Zo niet, maak deze dan aan:
```csharp
using Aspose.Slides.Export;
using System.IO;

string YOUR_DOCUMENT_DIRECTORY = "YOUR_DOCUMENT_DIRECTORY";
bool isExists = Directory.Exists(YOUR_DOCUMENT_DIRECTORY);
if (!isExists) 
    Directory.CreateDirectory(YOUR_DOCUMENT_DIRECTORY);

// Sla de presentatie op
pres.Save(YOUR_DOCUMENT_DIRECTORY + "\AsposeChart_out.pptx", SaveFormat.Pptx);
```
Met deze code wordt uw presentatiebestand op een opgegeven locatie opgeslagen.

## Conclusie
hebt nu succesvol spreidingsdiagrammen aan uw presentaties toegevoegd met Aspose.Slides voor .NET. Ontdek de extra functies en aanpassingen in de bibliotheek om uw vaardigheden in datavisualisatie te verbeteren.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}