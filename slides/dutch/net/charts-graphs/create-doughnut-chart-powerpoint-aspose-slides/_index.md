---
"date": "2025-04-15"
"description": "Leer hoe u dynamische en visueel aantrekkelijke ringdiagrammen maakt in PowerPoint-presentaties met behulp van de krachtige Aspose.Slides voor .NET-bibliotheek."
"title": "Een ringdiagram maken in PowerPoint met Aspose.Slides voor .NET"
"url": "/nl/net/charts-graphs/create-doughnut-chart-powerpoint-aspose-slides/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Een ringdiagram maken in PowerPoint met Aspose.Slides voor .NET
Het maken van visueel aantrekkelijke diagrammen is essentieel voor een effectieve datapresentatie. Ringdiagrammen zijn perfect om delen van een geheel te illustreren, waardoor ze ideaal zijn voor percentagegebaseerde datavisualisatie. Deze tutorial begeleidt je bij het maken van een dynamisch ringdiagram in PowerPoint met behulp van de krachtige Aspose.Slides voor .NET-bibliotheek.

## Invoering
Presentaties vereisen vaak visuele weergaven van complexe datasets, waar traditionele staaf- of lijndiagrammen mogelijk tekortschieten. De ringdiagram is een veelzijdige tool om percentagegebaseerde gegevens effectief en helder te communiceren. In deze tutorial onderzoeken we hoe Aspose.Slides voor .NET het proces van het maken van deze diagrammen rechtstreeks in PowerPoint vereenvoudigt.

**Wat je leert:**
- Aspose.Slides instellen voor .NET
- Stapsgewijze instructies voor het maken van een ringdiagram
- Series en categorieën toevoegen aan uw grafiek
- Gegevenslabels configureren voor meer duidelijkheid
- De definitieve presentatie opslaan

Laten we eens kijken hoe u Aspose.Slides voor .NET kunt gebruiken om uw presentaties te verbeteren met aangepaste ringdiagrammen.

## Vereisten
Voordat we beginnen, zorg ervoor dat u het volgende heeft geregeld:
- **Aspose.Slides voor .NET-bibliotheek**: Beschikbaar via NuGet of directe download.
- **Ontwikkelomgeving**Visual Studio wordt aanbevolen voor .NET-projecten.
- Basiskennis van C# en bekendheid met de structuur van PowerPoint.

## Aspose.Slides instellen voor .NET
Om grafieken te kunnen maken, moet u eerst de Aspose.Slides-bibliotheek in uw project installeren. Hier zijn verschillende manieren om deze te installeren:

**Met behulp van .NET CLI:**

```bash
dotnet add package Aspose.Slides
```

**Pakketbeheerconsole gebruiken:**

```powershell
Install-Package Aspose.Slides
```

**Via de NuGet Package Manager-gebruikersinterface:**
Zoek naar "Aspose.Slides" en installeer de nieuwste versie.

Na de installatie kunt u beginnen met het instellen van uw project. Bent u nieuw met Aspose.Slides? Overweeg dan een tijdelijke licentie of gratis proefversie aan te schaffen om alle mogelijkheden zonder beperkingen te ontdekken.

### Initialiseer uw project
Hier leest u hoe u Aspose.Slides in uw toepassing kunt initialiseren:

```csharp
using Aspose.Slides;

class Program
{
    static void Main()
    {
        // Een exemplaar van de presentatieklasse maken
        Presentation presentation = new Presentation();
        
        // Hier komt uw code om de presentatie te manipuleren
        
        // Sla de presentatie op
        presentation.Save("output.pptx", SaveFormat.Pptx);
    }
}
```

## Implementatiegids
### Een donutdiagram maken
#### Overzicht
Eerst maken we een leeg ringdiagram in een PowerPoint-dia. Dit dient als basis voor het toevoegen van gegevens en het aanpassen van de weergave.

**Stap 1: Voeg een donutdiagram toe**

```csharp
using Aspose.Slides;

class CreateDoughnutChart
{
    public static void Main(String[] args)
    {
        string dataDir = "YOUR_DOCUMENT_DIRECTORY";
        Presentation pres = new Presentation(dataDir + "/testc.pptx");
        ISlide slide = pres.getSlides().get_Item(0);
        
        // Voeg een donutdiagram toe aan de eerste dia op positie (10, 10) met grootte (500, 500)
        IChart chart = slide.getShapes().addChart(
            ChartType.Doughnut, 10, 10, 500, 500, false
        );

        // Bestaande series en categorieën wissen
        IChartDataWorkbook workBook = chart.getChartData().getChartDataWorkbook();
        chart.getChartData().getSeries().clear();
        chart.getChartData().getCategories().clear();

        // Schakel de legenda uit voor een overzichtelijker uiterlijk
        chart.setHasLegend(false);

        pres.Save("YOUR_OUTPUT_DIRECTORY/chart.pptx", SaveFormat.Pptx);
    }
}
```

**Uitleg:**
- **addChart**: Voegt een nieuw ringdiagram in de dia in.
- **getChartDataWerkboek**: Biedt toegang tot gegevenscellen in de grafiek voor manipulatie.

### Series en categorieën toevoegen
#### Overzicht
Vervolgens vullen we uw grafiek met zinvolle gegevens door reeksen en categorieën toe te voegen.

**Stap 2: Gegevensreeksen toevoegen**

```csharp
using Aspose.Slides;

class AddSeriesAndCategories
{
    public static void Main(String[] args)
    {
        string dataDir = "YOUR_DOCUMENT_DIRECTORY";
        Presentation pres = new Presentation(dataDir + "/testc.pptx");
        ISlide slide = pres.getSlides().get_Item(0);
        IChart chart = (IChart)slide.getShapes().get_Item(1);

        IChartDataWorkbook workBook = chart.getChartData().getChartDataWorkbook();

        // Serie toevoegen
        for (int seriesIndex = 0; seriesIndex < 15; seriesIndex++)
        {
            IChartSeries series = chart.getChartData()
                .getSeries()
                .add(
                    workBook.getCell(0, 0, seriesIndex + 1, "SERIES " + seriesIndex),
                    chart.getType()
                );

            // Het aanpassen van het donutgat en de starthoek
            series.setExplosion(0);
            series.getParentSeriesGroup().setDoughnutHoleSize((byte)20);
            series.getParentSeriesGroup().setFirstSliceAngle(351);
        }

        // Categorieën toevoegen
        for (int categoryIndex = 0; categoryIndex < 15; categoryIndex++)
        {
            chart.getChartData()
                .getCategories()
                .add(workBook.getCell(0, categoryIndex + 1, 0, "CATEGORY " + categoryIndex));

            for (int i = 0; i < chart.getChartData().getSeries().size(); i++)
            {
                IChartSeries iCS = chart.getChartData().getSeries().get_Item(i);
                IChartDataPoint dataPoint = iCS
                    .getDataPoints()
                    .addDataPointForDoughnutSeries(workBook.getCell(0, categoryIndex + 1, i + 1, 1));

                // De vulling en lijn van het gegevenspunt opmaken
                dataPoint.getFormat().getFill().setFillType(FillType.Solid);
                dataPoint.getFormat().getLine()
                    .getFillFormat()
                    .setFillType(FillType.Solid);
                
                dataPoint.getFormat().getLine()
                    .getFillFormat()
                    .getSolidFillColor()
                    .setColor(Color.WHITE);
                
                dataPoint.getFormat().getLine().setWidth(1.0);
                dataPoint.getFormat().getLine().setStyle(LineStyle.Single);
                dataPoint.getFormat().getLine().setDashStyle(LineDashStyle.Solid);
            }
        }

        pres.Save("YOUR_OUTPUT_DIRECTORY/chart.pptx", SaveFormat.Pptx);
    }
}
```

**Uitleg:**
- **toevoegen**: Voegt nieuwe series en categorieën in het diagram in.
- **setDonutHoleSize**Hiermee bepaalt u de grootte van het donutgat, waardoor het er visueel aantrekkelijker uitziet.

### Gegevenslabels configureren
#### Overzicht
Gegevenslabels bieden context aan uw diagramgegevens. Laten we de leesbaarheid verbeteren door ze aan te passen.

**Stap 3: Gegevenslabels aanpassen**

```csharp
using Aspose.Slides;

class ConfigureDataLabels
{
    public static void Main(String[] args)
    {
        string dataDir = "YOUR_DOCUMENT_DIRECTORY";
        Presentation pres = new Presentation(dataDir + "/testc.pptx");
        ISlide slide = pres.getSlides().get_Item(0);
        IChart chart = (IChart)slide.getShapes().get_Item(1);

        IChartDataWorkbook workBook = chart.getChartData().getChartDataWorkbook();

        for (int categoryIndex = 0; categoryIndex < 15; categoryIndex++)
        {
            for (int i = 0; i < chart.getChartData().getSeries().size(); i++)
            {
                IChartSeries series = chart.getChartData().getSeries().get_Item(i);
                IChartDataPoint dataPoint = series
                    .getDataPoints()
                    .addDataPointForDoughnutSeries(workBook.getCell(0, categoryIndex + 1, i + 1, 1));

                // Gegevenslabels aanpassen
                IDataLabel lbl = dataPoint.getLabel();
                lbl.getDataLabelFormat().setTextFormat()
                    .setCenterText(NullableBool.True)
                    .setShowPercentage(true);
                lbl.setVisible(true);
            }
        }

        pres.Save("YOUR_OUTPUT_DIRECTORY/chart.pptx", SaveFormat.Pptx);
    }
}
```

**Uitleg:**
- **IDataLabel**: Past de gegevenslabels aan voor duidelijkheid en presentatie.
- **setCenterText**, **showPercentage**: Verbeter de leesbaarheid van labels door tekst te centreren en percentages weer te geven.

## Conclusie
Door deze handleiding te volgen, hebt u geleerd hoe u een dynamische ringdiagram in PowerPoint maakt met Aspose.Slides voor .NET. Deze krachtige bibliotheek biedt uitgebreide mogelijkheden voor aanpassing, zodat u uw diagrammen precies kunt afstemmen op uw presentatiebehoeften.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}