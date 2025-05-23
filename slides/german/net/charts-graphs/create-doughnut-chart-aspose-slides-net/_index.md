---
"date": "2025-04-15"
"description": "Erfahren Sie, wie Sie mit Aspose.Slides für .NET dynamische Ringdiagramme erstellen. Folgen Sie dieser Anleitung für Schritt-für-Schritt-Anleitungen, einschließlich Einrichtung und erweiterten Funktionen."
"title": "Schritt-für-Schritt-Anleitung&#58; Erstellen Sie ein Ringdiagramm mit Aspose.Slides .NET | Diagramme und Grafiken"
"url": "/de/net/charts-graphs/create-doughnut-chart-aspose-slides-net/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Schritt-für-Schritt-Anleitung: Erstellen Sie ein Donut-Diagramm mit Aspose.Slides .NET

## Einführung

Stellen Sie sich vor, Sie müssen Ihrem Team oder Ihren Kunden Datenanalyseergebnisse präsentieren und benötigen eine ansprechende Visualisierung der Informationen. Hier kommt das Ringdiagramm ins Spiel – ein vielseitiges Tool, das Rohzahlen in leicht verständliche Erkenntnisse verwandelt. Mit Aspose.Slides für .NET erstellen Sie ganz einfach und effizient ein individuelles Ringdiagramm in Ihren Präsentationsfolien. Diese Anleitung führt Sie durch die Verwendung von Aspose.Slides zur Erstellung eines optisch ansprechenden Ringdiagramms mit maßgeschneiderten Serienkonfigurationen.

**Was Sie lernen werden:**
- Einrichten Ihrer Entwicklungsumgebung mit Aspose.Slides für .NET
- Erstellen und Anpassen von Ringdiagrammen in Präsentationen
- Implementierung erweiterter Funktionen wie Kategorienamen und Führungslinien
- Optimieren der Leistung für große Datensätze

Lassen Sie uns einen Blick auf die Voraussetzungen werfen, die Sie für den Einstieg benötigen.

## Voraussetzungen

Stellen Sie vor der Implementierung dieser Funktion sicher, dass Ihre Entwicklungsumgebung ordnungsgemäß eingerichtet ist. Dieses Tutorial setzt Grundkenntnisse in der .NET-Programmierung und Kenntnisse in Visual Studio oder einer ähnlichen IDE voraus.

### Erforderliche Bibliotheken und Versionen
- **Aspose.Slides für .NET**: Stellen Sie die Kompatibilität mit der neuesten Version sicher, indem Sie deren [offizielle Dokumentation](https://reference.aspose.com/slides/net/).

### Anforderungen für die Umgebungseinrichtung
- Eine funktionierende .NET-Umgebung.
- Zugriff auf einen Code-Editor, beispielsweise Visual Studio.

### Voraussetzungen
- Grundlegende Kenntnisse von C# und .NET Framework.
- Vertrautheit mit den Konzepten von Präsentationssoftware (optional, aber hilfreich).

## Einrichten von Aspose.Slides für .NET

Um Aspose.Slides in Ihrem Projekt verwenden zu können, müssen Sie es über NuGet installieren. Folgende Methoden stehen zur Verfügung:

**Verwenden der .NET-CLI:**
```bash
dotnet add package Aspose.Slides
```

**Verwenden des Paketmanagers:**
```powershell
Install-Package Aspose.Slides
```

**NuGet-Paket-Manager-Benutzeroberfläche:**
Suchen Sie nach „Aspose.Slides“ und installieren Sie die neueste Version.

### Schritte zum Lizenzerwerb

1. **Kostenlose Testversion**: Beginnen Sie mit einem [kostenlose Testversion](https://releases.aspose.com/slides/net/) um grundlegende Funktionen zu erkunden.
2. **Temporäre Lizenz**: Wenn Sie zu Testzwecken Zugriff auf alle Funktionen benötigen, erhalten Sie eine temporäre Lizenz. Besuchen Sie dazu [Hier](https://purchase.aspose.com/temporary-license/).
3. **Kaufen**: Für die kommerzielle Nutzung erwerben Sie eine Lizenz von der [Aspose-Website](https://purchase.aspose.com/buy).

Initialisieren Sie Aspose.Slides nach der Installation und Lizenzierung in Ihrem Projekt:
```csharp
using Aspose.Slides;

// Initialisieren Sie Aspose.Slides für .NET
var presentation = new Presentation();
```

## Implementierungshandbuch

### Erstellen einer neuen Präsentation und Hinzufügen eines Ringdiagramms

#### Überblick
Wir beginnen mit der Erstellung einer neuen Präsentation und fügen der ersten Folie ein Ringdiagramm hinzu. Dieser Abschnitt behandelt das Laden einer vorhandenen Präsentation, den Zugriff auf Folien und das Einfügen von Diagrammen.

**Schritt 1: Laden oder Erstellen einer Präsentation**
Geben Sie zunächst Ihr Dokumentverzeichnis an und laden Sie eine vorhandene Präsentation:
```csharp
string dataDir = \@"YOUR_DOCUMENT_DIRECTORY";
Presentation pres = new Presentation(dataDir + "testc.pptx");
```
Wenn Sie keine vorhandene Datei haben, erstellen Sie eine neue mit `new Presentation()`.

**Schritt 2: Zugriff auf die erste Folie**
Erhalten Sie Zugriff auf die erste Folie, auf der wir unser Diagramm hinzufügen:
```csharp
ISlide slide = pres.Slides[0];
```

**Schritt 3: Fügen Sie ein Ringdiagramm hinzu**
Fügen Sie an den angegebenen Koordinaten und mit den angegebenen Abmessungen ein Ringdiagramm hinzu:
```csharp
IChart chart = slide.Shapes.AddChart(ChartType.Doughnut, 10, 10, 500, 500, false);
```

### Konfigurieren der Datenarbeitsmappe

#### Überblick
In diesem Abschnitt wird erläutert, wie Sie die mit Ihrem Ringdiagramm verknüpfte Datenarbeitsmappe konfigurieren.

**Schritt 4: Zugriff auf vorhandene Daten und Löschen**
Greifen Sie auf die Datenarbeitsmappe des Diagramms zu. Löschen Sie dann alle vorhandenen Reihen oder Kategorien:
```csharp
IChartDataWorkbook workBook = chart.ChartData.ChartDataWorkbook;
chart.ChartData.Series.Clear();
chart.ChartData.Categories.Clear();
```

**Schritt 5: Legende deaktivieren und Serie hinzufügen**
Deaktivieren Sie die Legende, um das Diagramm übersichtlich zu halten, und fügen Sie dann bis zu 15 Serien mit benutzerdefinierten Konfigurationen hinzu:
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

### Hinzufügen von Kategorien und Datenpunkten

#### Überblick
Füllen wir nun das Diagramm mit Kategorien und Datenpunkten für jede Reihe.

**Schritt 6: Kategorien hinzufügen**
Führen Sie eine Schleife durch, um 15 Kategorien hinzuzufügen:
```csharp
int categoryIndex = 0;
while (categoryIndex < 15)
{
    chart.ChartData.Categories.Add(workBook.GetCell(0, categoryIndex + 1, 0, "CATEGORY " + categoryIndex));
```

**Schritt 7: Datenpunkte füllen**
Fügen Sie Datenpunkte für jede Reihe innerhalb der aktuellen Kategorie hinzu:
```csharp
int i = 0;
while (i < chart.ChartData.Series.Count)
{
    IChartSeries iCS = chart.ChartData.Series[i];
    IChartDataPoint dataPoint = iCS.DataPoints.AddDataPointForDoughnutSeries(workBook.GetCell(0, categoryIndex + 1, i + 1, 1));

    // Anpassen des Erscheinungsbilds
    dataPoint.Format.Fill.FillType = FillType.Solid;
    dataPoint.Format.Line.FillFormat.FillType = FillType.Solid;
    dataPoint.Format.Line.FillFormat.SolidFillColor.Color = System.Drawing.Color.White;
    dataPoint.Format.Line.Width = 1;
    dataPoint.Format.Line.Style = LineStyle.Single;
    dataPoint.Format.Line.DashStyle = LineDashStyle.Solid;

    // Etikettenformat für die letzte Serie konfigurieren
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

        // Beschriftungsanzeige konfigurieren
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

### Speichern der Präsentation

**Schritt 8: Speichern Sie die Datei**
Speichern Sie Ihre Präsentation abschließend in einem angegebenen Verzeichnis:
```csharp
pres.Save(dataDir + "chart.pptx\

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}