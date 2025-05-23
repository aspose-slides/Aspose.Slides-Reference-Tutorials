---
"date": "2025-04-15"
"description": "Erfahren Sie, wie Sie mit Aspose.Slides die Erstellung von Kreisdiagrammen in .NET-Präsentationen automatisieren und so die Datenvisualisierung mühelos verbessern."
"title": "So erstellen und passen Sie Kreisdiagramme in .NET-Präsentationen mit Aspose.Slides an"
"url": "/de/net/charts-graphs/create-style-pie-charts-net-asposeslides/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# So erstellen und passen Sie Kreisdiagramme in .NET-Präsentationen mit Aspose.Slides an

## Einführung
Die Erstellung ansprechender und informativer Präsentationen ist entscheidend für eine effektive Kommunikation, egal ob Sie Daten im Büro präsentieren oder Ihre neuesten Projektergebnisse vorstellen. Kreisdiagramme sind eine wirkungsvolle Möglichkeit zur Datenvisualisierung, da sie Teile eines Ganzen prägnant darstellen. Die manuelle Erstellung dieser Diagramme in Präsentationssoftware wie PowerPoint kann jedoch zeitaufwändig sein und bietet möglicherweise nicht die nötige Flexibilität für dynamische Aktualisierungen.

Hier kommt Aspose.Slides für .NET ins Spiel. Diese umfassende Bibliothek ermöglicht Ihnen das programmgesteuerte Erstellen, Ändern und Gestalten von Präsentationen. Sie ist ein unschätzbares Werkzeug für Entwickler, die ihren Workflow automatisieren und die Konsistenz aller Präsentationen sicherstellen möchten.

In diesem Tutorial erfahren Sie, wie Sie mit Aspose.Slides für .NET Kreisdiagramme in Ihren Präsentationen erstellen und anpassen. Sie lernen Folgendes:
- **Erstellen Sie eine Präsentation und greifen Sie auf Folien zu**
- **Kreisdiagramme hinzufügen und konfigurieren**
- **Anpassen von Diagrammdaten und -reihen**
- **Kreisdiagrammsektoren gestalten**
- **Benutzerdefinierte Beschriftungen hinzufügen**
- **Anzeigeeigenschaften konfigurieren und Präsentation speichern**

Sind Sie bereit, mit Leichtigkeit beeindruckende Kreisdiagramme zu erstellen? Dann legen wir los!

## Voraussetzungen
Bevor wir beginnen, stellen Sie sicher, dass Sie über die folgende Konfiguration verfügen:

### Erforderliche Bibliotheken
- Aspose.Slides für .NET (Version 21.11 oder höher empfohlen)

### Umgebungs-Setup
- Eine Entwicklungsumgebung mit .NET Framework oder .NET Core/5+/6+
- Ein Code-Editor wie Visual Studio

### Voraussetzungen
- Grundlegende Kenntnisse der C#-Programmierung
- Vertrautheit mit objektorientierten Konzepten

## Einrichten von Aspose.Slides für .NET
Um zu beginnen, müssen Sie die Aspose.Slides-Bibliothek installieren. Sie können dies mit einer der folgenden Methoden tun:

**.NET-CLI**
```bash
dotnet add package Aspose.Slides
```

**Paket-Manager-Konsole**
```powershell
Install-Package Aspose.Slides
```

**NuGet-Paket-Manager-Benutzeroberfläche**
- Öffnen Sie Ihr Projekt in Visual Studio.
- Gehen Sie zu „Tools“ > „NuGet-Paket-Manager“ > „NuGet-Pakete für Lösung verwalten“.
- Suchen Sie nach „Aspose.Slides“ und installieren Sie die neueste Version.

### Schritte zum Lizenzerwerb
Um Aspose.Slides zu nutzen, können Sie mit einer kostenlosen Testversion beginnen, indem Sie eine temporäre Lizenz herunterladen. Besuchen Sie [Asposes Website](https://purchase.aspose.com/temporary-license/) um es zu erhalten. Für die dauerhafte Nutzung sollten Sie den Erwerb einer Volllizenz in Erwägung ziehen.

### Grundlegende Initialisierung und Einrichtung
Initialisieren Sie nach der Installation die Präsentationsklasse, die Ihre PPTX-Datei darstellt:

```csharp
using Aspose.Slides;

Presentation presentation = new Presentation();
```

## Implementierungshandbuch
Wir unterteilen den Prozess der Kreisdiagrammerstellung in überschaubare Abschnitte. Jeder Abschnitt konzentriert sich auf eine bestimmte Funktion, sodass Sie Ihr Wissen schrittweise erweitern können.

### Erstellen Sie eine Präsentation und greifen Sie auf Folien zu
**Überblick:** Erstellen Sie zunächst eine neue Präsentation und öffnen Sie die erste Folie. So können Sie Diagramme und andere Elemente hinzufügen.

```csharp
using Aspose.Slides;

public static void CreatePresentationAndAccessSlide()
{
    // Instanziieren Sie die Präsentationsklasse, die eine PPTX-Datei darstellt
    Presentation presentation = new Presentation();
    
    // Zugriff auf die erste Folie
    ISlide slides = presentation.Slides[0];
}
```

### Kreisdiagramm hinzufügen und konfigurieren
**Überblick:** Erfahren Sie, wie Sie Ihrer Folie ein Kreisdiagramm hinzufügen und seinen Titel für den Kontext festlegen.

```csharp
using Aspose.Slides;
using Aspose.Slides.Charts;

public static void AddAndConfigurePieChart()
{
    // Instanziieren Sie die Präsentationsklasse, die eine PPTX-Datei darstellt
    Presentation presentation = new Presentation();
    
    // Zugriff auf die erste Folie
    ISlide slides = presentation.Slides[0];
    
    // Fügen Sie der Folie ein Diagramm mit Standarddaten hinzu
    IChart chart = slides.Shapes.AddChart(ChartType.Pie, 100, 100, 400, 400);
    
    // Einstellungsdiagrammtitel
    chart.ChartTitle.AddTextFrameForOverriding("Sample Title");
    chart.ChartTitle.TextFrameForOverriding.TextFrameFormat.CenterText = NullableBool.True;
    chart.ChartTitle.Height = 20;
    chart.HasTitle = true;
}
```

### Anpassen von Diagrammdaten und -reihen
**Überblick:** Passen Sie die Datenkategorien und -reihen an Ihre spezifischen Anforderungen an.

```csharp
using Aspose.Slides.Charts;

public static void CustomizeChartDataAndSeries()
{
    // Instanziieren Sie die Präsentationsklasse, die eine PPTX-Datei darstellt
    Presentation presentation = new Presentation();
    
    // Zugriff auf die erste Folie
    ISlide slides = presentation.Slides[0];
    
    // Fügen Sie der Folie ein Diagramm mit Standarddaten hinzu
    IChart chart = slides.Shapes.AddChart(ChartType.Pie, 100, 100, 400, 400);
    
    // Stellen Sie die erste Serie auf „Werte anzeigen“ ein
    chart.ChartData.Series[0].Labels.DefaultDataLabelFormat.ShowValue = true;
    
    // Festlegen des Index des Diagrammdatenblatts
    int defaultWorksheetIndex = 0;
    
    // Abrufen des Arbeitsblatts mit den Diagrammdaten
    IChartDataWorkbook fact = chart.ChartData.ChartDataWorkbook;
    
    // Standardmäßig generierte Serien und Kategorien löschen
    chart.ChartData.Series.Clear();
    chart.ChartData.Categories.Clear();
    
    // Neue Kategorien hinzufügen
    chart.ChartData.Categories.Add(fact.GetCell(0, 1, 0, "First Qtr"));
    chart.ChartData.Categories.Add(fact.GetCell(0, 2, 0, "2nd Qtr"));
    chart.ChartData.Categories.Add(fact.GetCell(0, 3, 0, "3rd Qtr"));
    
    // Neue Serien hinzufügen
    IChartSeries series = chart.ChartData.Series.Add(fact.GetCell(0, 0, 1, "Series 1"), chart.Type);
    
    // Jetzt werden Seriendaten gefüllt
    series.DataPoints.AddDataPointForPieSeries(fact.GetCell(defaultWorksheetIndex, 1, 1, 20));
    series.DataPoints.AddDataPointForPieSeries(fact.GetCell(defaultWorksheetIndex, 2, 1, 50));
    series.DataPoints.AddDataPointForPieSeries(fact.GetCell(defaultWorksheetIndex, 3, 1, 30));
}
```

### Kreisdiagramm-Sektor-Stile anpassen
**Überblick:** Gestalten Sie einzelne Sektoren Ihres Kreisdiagramms, um die visuelle Attraktivität zu steigern und wichtige Datenpunkte hervorzuheben.

```csharp
using Aspose.Slides.Charts;
using System.Drawing;

public static void CustomizePieChartSectorStyles()
{
    // Instanziieren Sie die Präsentationsklasse, die eine PPTX-Datei darstellt
    Presentation presentation = new Presentation();
    
    // Zugriff auf die erste Folie
    ISlide slides = presentation.Slides[0];
    
    // Fügen Sie der Folie ein Diagramm mit Standarddaten hinzu
    IChart chart = slides.Shapes.AddChart(ChartType.Pie, 100, 100, 400, 400);
    
    // Serien aus Diagramm abrufen
    IChartSeries series = chart.ChartData.Series[0];
    
    // Anpassen von Sektorstilen für jeden Datenpunkt in der Reihe
    IChartDataPoint point = series.DataPoints[0];
    point.Format.Fill.FillType = FillType.Solid;
    point.Format.Fill.SolidFillColor.Color = Color.Cyan;
    
    // Sektorgrenze festlegen
    point.Format.Line.FillFormat.FillType = FillType.Solid;
    point.Format.Line.FillFormat.SolidFillColor.Color = Color.Gray;
    point.Format.Line.Width = 3.0;
    point.Format.Line.Style = LineStyle.ThinThick;
    point.Format.Line.DashStyle = LineDashStyle.DashDot;

    IChartDataPoint point1 = series.DataPoints[1];
    point1.Format.Fill.FillType = FillType.Solid;
    point1.Format.Fill.SolidFillColor.Color = Color.Green;
    
    // Sektorgrenze festlegen
    point1.Format.Line.FillFormat.FillType = FillType.Solid;
    point1.Format.Line.FillFormat.SolidFillColor.Color = Color.Black;
    point1.Format.Line.Width = 2.0;
    point1.Format.Line.Style = LineStyle.Solid;

    IChartDataPoint point2 = series.DataPoints[2];
    point2.Format.Fill.FillType = FillType.Solid;
    point2.Format.Fill.SolidFillColor.Color = Color.Yellow;
    
    // Sektorgrenze festlegen
    point2.Format.Line.FillFormat.FillType = FillType.Solid;
    point2.Format.Line.FillFormat.SolidFillColor.Color = Color.Red;
    point2.Format.Line.Width = 2.0;
    point2.Format.Line.Style = LineStyle.Dot;
}
```

### Hinzufügen benutzerdefinierter Beschriftungen zum Kreisdiagramm
**Überblick:** Verbessern Sie Ihr Kreisdiagramm, indem Sie benutzerdefinierte Beschriftungen für eine klarere Datendarstellung hinzufügen.

```csharp
public static void AddCustomLabelsToPieChart(IChart chart)
{
    IChartDataWorkbook fact = chart.ChartData.ChartDataWorkbook;
    IChartSeries series = chart.ChartData.Series[0];

    foreach (IChartDataPoint point in series.DataPoints)
    {
        IDataLabel lbl = point.Label;
        lbl.TextFrameForOverriding.Text = $"{point.Value}";
        lbl.Position = LegendPositionType.Center; // Passen Sie die Etikettenposition nach Bedarf an
    }
}
```

### Abschluss
Sie haben nun gelernt, wie Sie mit Aspose.Slides Kreisdiagramme in .NET-Präsentationen erstellen und anpassen. Diese Automatisierung kann Ihre Datenvisualisierung erheblich verbessern, Zeit sparen und die Konsistenz zwischen Präsentationen gewährleisten.

Um die Möglichkeiten von Aspose.Slides für .NET weiter zu erkunden, sollten Sie sich mit zusätzlichen Funktionen befassen, z. B. mit der Erstellung anderer Diagrammtypen oder der Integration komplexerer Designelemente in Ihre Folien.

Viel Spaß beim Programmieren!

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}