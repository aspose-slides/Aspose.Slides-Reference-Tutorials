---
"date": "2025-04-15"
"description": "Erfahren Sie, wie Sie mit der leistungsstarken Bibliothek Aspose.Slides für .NET dynamische und optisch ansprechende Ringdiagramme in PowerPoint-Präsentationen erstellen."
"title": "So erstellen Sie ein Ringdiagramm in PowerPoint mit Aspose.Slides für .NET"
"url": "/de/net/charts-graphs/create-doughnut-chart-powerpoint-aspose-slides/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# So erstellen Sie ein Ringdiagramm in PowerPoint mit Aspose.Slides für .NET
Visuell ansprechende Diagramme sind für eine effektive Datenpräsentation unerlässlich. Ringdiagramme eignen sich perfekt zur Darstellung von Teilen eines Ganzen und sind daher ideal für die prozentuale Datenvisualisierung. Dieses Tutorial führt Sie durch die Erstellung eines dynamischen Ringdiagramms in PowerPoint mit der leistungsstarken Aspose.Slides für .NET-Bibliothek.

## Einführung
Präsentationen erfordern oft die visuelle Darstellung komplexer Datensätze, für die herkömmliche Balken- oder Liniendiagramme nicht ausreichen. Das Ringdiagramm erweist sich als vielseitiges Werkzeug zur effektiven, stilvollen und klaren Darstellung prozentualer Daten. In diesem Tutorial erfahren Sie, wie Aspose.Slides für .NET die Erstellung dieser Diagramme direkt in PowerPoint vereinfacht.

**Was Sie lernen werden:**
- Einrichten von Aspose.Slides für .NET
- Schritt-für-Schritt-Anleitung zum Erstellen eines Ringdiagramms
- Hinzufügen von Reihen und Kategorien zu Ihrem Diagramm
- Konfigurieren von Datenbeschriftungen für mehr Übersichtlichkeit
- Speichern der endgültigen Präsentation

Lassen Sie uns einen Blick darauf werfen, wie Sie Aspose.Slides für .NET nutzen können, um Ihre Präsentationen mit benutzerdefinierten Ringdiagrammen zu verbessern.

## Voraussetzungen
Bevor wir beginnen, stellen Sie sicher, dass Sie Folgendes eingerichtet haben:
- **Aspose.Slides für die .NET-Bibliothek**: Verfügbar über NuGet oder als direkter Download.
- **Entwicklungsumgebung**Für .NET-Projekte wird Visual Studio empfohlen.
- Grundkenntnisse in C# und Vertrautheit mit der Struktur von PowerPoint.

## Einrichten von Aspose.Slides für .NET
Um Diagramme zu erstellen, müssen Sie zunächst die Aspose.Slides-Bibliothek in Ihrem Projekt einrichten. Hier sind mehrere Möglichkeiten zur Installation:

**Verwenden der .NET-CLI:**

```bash
dotnet add package Aspose.Slides
```

**Verwenden der Paketmanager-Konsole:**

```powershell
Install-Package Aspose.Slides
```

**Über die NuGet-Paket-Manager-Benutzeroberfläche:**
Suchen Sie nach „Aspose.Slides“ und installieren Sie die neueste Version.

Nach der Installation können Sie mit der Einrichtung Ihres Projekts beginnen. Wenn Sie Aspose.Slides noch nicht kennen, sollten Sie eine temporäre Lizenz oder eine kostenlose Testversion erwerben, um alle Funktionen ohne Einschränkungen zu nutzen.

### Initialisieren Sie Ihr Projekt
So können Sie Aspose.Slides in Ihrer Anwendung initialisieren:

```csharp
using Aspose.Slides;

class Program
{
    static void Main()
    {
        // Erstellen Sie eine Instanz der Präsentationsklasse
        Presentation presentation = new Presentation();
        
        // Ihr Code zur Manipulation der Präsentation kommt hier hin
        
        // Speichern der Präsentation
        presentation.Save("output.pptx", SaveFormat.Pptx);
    }
}
```

## Implementierungshandbuch
### Erstellen eines Ringdiagramms
#### Überblick
Zunächst erstellen wir ein leeres Ringdiagramm in einer PowerPoint-Folie. Dieses dient als Grundlage für das Hinzufügen von Daten und die Anpassung des Erscheinungsbilds.

**Schritt 1: Fügen Sie ein Ringdiagramm hinzu**

```csharp
using Aspose.Slides;

class CreateDoughnutChart
{
    public static void Main(String[] args)
    {
        string dataDir = "YOUR_DOCUMENT_DIRECTORY";
        Presentation pres = new Presentation(dataDir + "/testc.pptx");
        ISlide slide = pres.getSlides().get_Item(0);
        
        // Fügen Sie der ersten Folie an Position (10, 10) mit der Größe (500, 500) ein Ringdiagramm hinzu.
        IChart chart = slide.getShapes().addChart(
            ChartType.Doughnut, 10, 10, 500, 500, false
        );

        // Vorhandene Serien und Kategorien löschen
        IChartDataWorkbook workBook = chart.getChartData().getChartDataWorkbook();
        chart.getChartData().getSeries().clear();
        chart.getChartData().getCategories().clear();

        // Deaktivieren Sie die Legende für ein übersichtlicheres Erscheinungsbild
        chart.setHasLegend(false);

        pres.Save("YOUR_OUTPUT_DIRECTORY/chart.pptx", SaveFormat.Pptx);
    }
}
```

**Erläuterung:**
- **Diagramm hinzufügen**: Fügt ein neues Ringdiagramm auf der Folie ein.
- **getChartDataWorkbook**: Bietet Zugriff auf Datenzellen im Diagramm zur Bearbeitung.

### Hinzufügen von Serien und Kategorien
#### Überblick
Als Nächstes füllen wir Ihr Diagramm mit aussagekräftigen Daten, indem wir Reihen und Kategorien hinzufügen.

**Schritt 2: Datenreihen hinzufügen**

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

        // Serie hinzufügen
        for (int seriesIndex = 0; seriesIndex < 15; seriesIndex++)
        {
            IChartSeries series = chart.getChartData()
                .getSeries()
                .add(
                    workBook.getCell(0, 0, seriesIndex + 1, "SERIES " + seriesIndex),
                    chart.getType()
                );

            // Anpassen des Donut-Lochs und des Startwinkels
            series.setExplosion(0);
            series.getParentSeriesGroup().setDoughnutHoleSize((byte)20);
            series.getParentSeriesGroup().setFirstSliceAngle(351);
        }

        // Kategorien hinzufügen
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

                // Formatieren der Füllung und Linie des Datenpunkts
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

**Erläuterung:**
- **hinzufügen**: Fügt neue Reihen und Kategorien in das Diagramm ein.
- **Donutlochgröße festlegen**Konfiguriert die Größe des Donut-Lochs und verbessert so seine optische Attraktivität.

### Konfigurieren von Datenbeschriftungen
#### Überblick
Datenbeschriftungen verleihen Ihren Diagrammdaten Kontext. Verbessern Sie die Lesbarkeit, indem Sie sie anpassen.

**Schritt 3: Datenbeschriftungen anpassen**

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

                // Anpassen von Datenbeschriftungen
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

**Erläuterung:**
- **IDataLabel**: Passt die Datenbeschriftungen zur besseren Übersichtlichkeit und Präsentation an.
- **setCenterText**, **Prozentsatz anzeigen**: Verbessern Sie die Lesbarkeit der Beschriftung, indem Sie den Text zentrieren und Prozentwerte anzeigen.

## Abschluss
In dieser Anleitung erfahren Sie, wie Sie mit Aspose.Slides für .NET ein dynamisches Ringdiagramm in PowerPoint erstellen. Diese leistungsstarke Bibliothek ermöglicht umfassende Anpassungen, sodass Sie Ihre Diagramme genau auf Ihre Präsentationsanforderungen zuschneiden können.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}