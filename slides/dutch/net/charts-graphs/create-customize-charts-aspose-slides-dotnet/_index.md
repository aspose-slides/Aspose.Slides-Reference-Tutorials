---
"date": "2025-04-15"
"description": "Leer hoe u grafieken kunt maken en aanpassen met Aspose.Slides voor .NET, inclusief het weergeven van percentages als gegevenslabels. Volg deze stapsgewijze handleiding."
"title": "Hoe u grafieken kunt maken en aanpassen met Aspose.Slides .NET&#58; percentages weergeven als labels"
"url": "/nl/net/charts-graphs/create-customize-charts-aspose-slides-dotnet/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Grafieken maken en aanpassen met Aspose.Slides .NET: percentages weergeven als labels

## Invoering

Het effectief presenteren van gegevens is cruciaal in veel vakgebieden, en grafieken spelen een essentiële rol door complexe informatie om te zetten in duidelijke beelden. Het creëren van de perfecte grafiek vereist aanpassingstaken zoals het weergeven van percentages op labels – een taak die eenvoudiger wordt met Aspose.Slides voor .NET. Deze bibliotheek vereenvoudigt het proces van het maken en aanpassen van grafieken in PowerPoint-presentaties.

In deze tutorial leer je hoe je met Aspose.Slides voor .NET een gestapeld kolomdiagram helemaal zelf kunt maken en aanpassen door percentagewaarden als gegevenslabels weer te geven. Door deze stappen te volgen, verbeter je je dia's met nauwkeurige en visueel aantrekkelijke gegevensrepresentaties.

**Wat je leert:**
- Aspose.Slides initialiseren voor .NET
- Een gestapelde kolomgrafiek maken
- Percentages berekenen en weergeven op gegevenslabels
- Best practices voor het optimaliseren van grafiekprestaties

Voordat we met de implementatie beginnen, willen we ervoor zorgen dat alles klaar is om te beginnen.

## Vereisten

Om deze tutorial effectief te kunnen volgen, moet u het volgende hebben:
- **.NET Core SDK** op uw computer geïnstalleerd.
- Basiskennis van C#- en .NET-applicatieontwikkeling.
- Visual Studio of een vergelijkbare IDE voor het schrijven en uitvoeren van C#-code.

U hebt Aspose.Slides voor .NET nodig om grafieken te maken. Zorg ervoor dat dit is ingesteld zoals hieronder beschreven.

## Aspose.Slides instellen voor .NET

Aspose.Slides voor .NET is een krachtige bibliotheek waarmee je programmatisch met PowerPoint-presentaties kunt werken. Zo voeg je het toe aan je project:

### Installatie

**.NET CLI:**
```bash
dotnet add package Aspose.Slides
```

**Pakketbeheerconsole:**
```powershell
Install-Package Aspose.Slides
```

**Gebruikersinterface van NuGet Package Manager:** 
- Open NuGet Package Manager en zoek naar "Aspose.Slides". Installeer de nieuwste versie.

### Licentieverwerving

Om Aspose.Slides volledig te benutten, begin je met een gratis proefperiode. Voor langdurig gebruik kun je een tijdelijke licentie aanschaffen of er een kopen bij [Aspose](https://purchase.aspose.com/buy)Volg hun richtlijnen om uw licentie in uw projectomgeving in te stellen.

### Basisinitialisatie

Zodra het is geïnstalleerd, initialiseert u de `Presentation` klas om te beginnen met het maken van dia's:
```csharp
using Aspose.Slides;

// Initialiseer een presentatieklasse-instantie
tPresentation presentation = new Presentation();
```

Laten we nu verder gaan met het implementeren van onze functie voor het maken en aanpassen van grafieken met behulp van Aspose.Slides voor .NET.

## Implementatiegids

### Een gestapelde kolomgrafiek maken

Ons doel is om een gestapelde kolomgrafiek te maken en deze aan te passen door percentages als gegevenslabels weer te geven. Zo werkt het:

#### Initialiseer de presentatie

Begin met het maken van een exemplaar van `Presentation`:
```csharp
using Aspose.Slides;

// Initialiseer een presentatieklasse-instantie
tPresentation presentation = new Presentation();
ISlide slide = presentation.Slides[0];
```

#### Een grafiek toevoegen aan de dia

Voeg een gestapeld kolomdiagram toe aan uw eerste dia met de opgegeven coördinaten en afmetingen:
```csharp
IChart chart = slide.Shapes.AddChart(ChartType.StackedColumn, 20, 20, 400, 400);
```
Deze lijn creëert een `StackedColumn` grafiek op positie (20, 20) met breedte en hoogte van 400.

#### Bereken totale waarden voor percentageberekening

Om percentages weer te geven, berekent u de totale waarde voor elke categorie over alle reeksen:
```csharp
IChartSeries series;
double[] total_for_Cat = new double[chart.ChartData.Categories.Count];

for (int k = 0; k < chart.ChartData.Categories.Count; k++)
{
    IChartCategory cat = chart.ChartData.Categories[k];
    // Tel de waarden van alle reeksen voor elke categorie op
    for (int i = 0; i < chart.ChartData.Series.Count; i++)
    {
        total_for_Cat[k] += Convert.ToDouble(chart.ChartData.Series[i].DataPoints[k].Value.Data);
    }
}
```

#### Pas gegevenslabels aan om percentagewaarden weer te geven

Loop vervolgens door elke reeks en pas de gegevenslabels aan:
```csharp
for (int x = 0; x < chart.ChartData.Series.Count; x++)
{
    series = chart.ChartData.Series[x];
    series.Labels.DefaultDataLabelFormat.ShowLegendKey = false;

    for (int j = 0; j < series.DataPoints.Count; j++)
    {
        IDataLabel lbl = series.DataPoints[j].Label;
        
        // Percentage berekenen
        double dataPontPercent = (Convert.ToDouble(series.DataPoints[j].Value.Data) / total_for_Cat[j]) * 100;
        IPortion port = new Portion();
        port.Text = String.Format("{0:F2} %", dataPontPercent);
        port.PortionFormat.FontHeight = 8f;

        lbl.TextFrameForOverriding.Text = ""; // Duidelijke tekst om overlapping te voorkomen
        IParagraph para = lbl.TextFrameForOverriding.Paragraphs[0];
        para.Portions.Add(port);

        // Labelformaat configureren om standaardgegevenslabels te verbergen
        lbl.DataLabelFormat.ShowSeriesName = false;
        lbl.DataLabelFormat.ShowPercentage = false; 
        lbl.DataLabelFormat.ShowLegendKey = false;
        lbl.DataLabelFormat.ShowCategoryName = false;
        lbl.DataLabelFormat.ShowBubbleSize = false;
    }
}
```

In deze sectie wordt het percentage voor elk gegevenspunt berekend en wordt dit ingesteld als een aangepast label, zodat er geen overlapping is met standaardlabels.

#### Sla de presentatie op

Sla ten slotte uw presentatie op om het resultaat te bekijken:
```csharp
string outputDir = "YOUR_OUTPUT_DIRECTORY";
presentation.Save(outputDir + "/DisplayPercentageAsLabels_out.pptx", SaveFormat.Pptx);
```

## Praktische toepassingen

Het weergeven van percentages in grafieken kan vooral nuttig zijn in scenario's zoals:
1. **Financiële verslaggeving:** Geef portefeuilleverdelingen of beleggingsrendementen weer als percentages.
2. **Verkoopanalyse:** Geef marktaandeelgegevens weer in percentages om de prestaties per regio te benadrukken.
3. **Enquêteresultaten:** Geef enquêtereacties weer als percentages voor een betere visuele vergelijking.
4. **Projectmanagement:** Gebruik cirkeldiagrammen met percentages om de toewijzing van middelen te illustreren.
5. **Onderwijs:** Leg statistische concepten uit met behulp van duidelijke visuele weergaven op basis van percentages.

Door deze aangepaste grafieken te integreren in systemen als CRM of ERP, kunt u dashboards en rapporten verbeteren en zo besluitvormingsprocessen ondersteunen.

## Prestatieoverwegingen

Bij het werken met Aspose.Slides voor .NET, vooral bij grote datasets:
- **Geheugenbeheer:** Gooi presentatieobjecten op de juiste manier weg om geheugen vrij te maken. Gebruik `using` verklaringen waar van toepassing.
- **Efficiënte gegevensverwerking:** Voer indien mogelijk berekeningen buiten lussen uit om de rekenkosten te beperken.
- **Load Balancing:** Zorg ervoor dat de serverbronnen voor webtoepassingen voldoende zijn ingericht voor gelijktijdige aanvragen voor het genereren van grafieken.

## Conclusie

Deze tutorial behandelde het maken en aanpassen van grafieken met Aspose.Slides voor .NET door percentagewaarden als labels weer te geven. Door deze technieken onder de knie te krijgen, kunt u uw presentaties verbeteren met gedetailleerde en visueel aantrekkelijke gegevensrepresentaties.

Verken vervolgens de andere diagramtypen en aanpassingsopties die beschikbaar zijn in Aspose.Slides. Experimenteer met verschillende datasets om ze om te zetten in krachtige beelden die inzichten duidelijk overbrengen.

## FAQ-sectie

**V1: Hoe ga ik om met grote datasets bij het maken van grafieken met Aspose.Slides voor .NET?**
A1: Optimaliseer voor grote datasets de berekeningen en gebruik efficiënte geheugenbeheertechnieken. Verdeel verwerkingstaken om geheugenoverbelasting te voorkomen.

**V2: Kan ik Aspose.Slides voor .NET gebruiken in een webapplicatie?**
A2: Ja, het kan worden geïntegreerd in ASP.NET-applicaties. Zorg voor een correcte toewijzing van serverbronnen voor optimale prestaties.

**V3: Is het mogelijk om grafieken die met Aspose.Slides zijn gemaakt, te exporteren naar andere formaten?**
A3: Absoluut! Je kunt presentaties met je aangepaste grafieken exporteren naar verschillende formaten, zoals PDF en afbeeldingsbestanden, met behulp van de mogelijkheden van de bibliotheek.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}