---
"date": "2025-04-15"
"description": "Erfahren Sie, wie Sie mit Aspose.Slides für .NET visuell ansprechende, prozentbasierte Säulendiagramme erstellen. Folgen Sie dieser Schritt-für-Schritt-Anleitung für eine übersichtliche Datenvisualisierung."
"title": "So erstellen Sie prozentbasierte gestapelte Säulendiagramme in .NET mit Aspose.Slides"
"url": "/de/net/charts-graphs/create-stacked-column-charts-asposeslides-dotnet/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# So erstellen Sie ein prozentbasiertes gestapeltes Säulendiagramm mit Aspose.Slides für .NET

## Einführung

Im Bereich der Datenvisualisierung ist die klare und effektive Darstellung von Informationen entscheidend für wirkungsvolle Entscheidungen. Für die intuitive Darstellung komplexer Datensätze eignen sich prozentuale, gestapelte Säulendiagramme ideal. Diese Anleitung führt Sie durch die Erstellung dieser Diagramme mit Aspose.Slides für .NET, einer robusten Bibliothek zur Bearbeitung von Präsentationsdateien.

In diesem Tutorial erfahren Sie:
- Einrichten von Diagrammdaten und Konfigurieren von Zahlenformaten.
- Serien hinzufügen und deren Erscheinungsbild anpassen.
- Formatieren von Beschriftungen zur Verbesserung der Lesbarkeit.

Bereit zum Eintauchen? Beginnen wir mit den Voraussetzungen, die Sie benötigen!

## Voraussetzungen

Bevor Sie Ihre prozentbasierten gestapelten Säulendiagramme erstellen, stellen Sie sicher, dass Ihre Umgebung korrekt eingerichtet ist. Sie benötigen:

### Erforderliche Bibliotheken, Versionen und Abhängigkeiten
- **Aspose.Slides für .NET**: Stellen Sie sicher, dass diese Bibliothek installiert ist.

### Anforderungen für die Umgebungseinrichtung
- Eine Entwicklungsumgebung mit installiertem .NET SDK.
- Visual Studio oder eine andere kompatible IDE zum Ausführen von C#-Code.

### Voraussetzungen
- Grundlegende Kenntnisse der C#-Programmierung.
- Vertrautheit mit der Einrichtung und Paketverwaltung von .NET-Projekten.

## Einrichten von Aspose.Slides für .NET

Um mit der Erstellung von Diagrammen mit Aspose.Slides zu beginnen, installieren Sie zunächst die Bibliothek mit einer der folgenden Methoden:

**.NET-CLI**
```bash
dotnet add package Aspose.Slides
```

**Paketmanager**
```powershell
Install-Package Aspose.Slides
```

**NuGet-Paket-Manager-Benutzeroberfläche**
- Suchen Sie nach „Aspose.Slides“ und installieren Sie die neueste Version.

### Schritte zum Lizenzerwerb

Beginnen Sie mit einer kostenlosen Testversion, indem Sie eine temporäre Lizenz herunterladen von [Asposes Website](https://purchase.aspose.com/temporary-license/). Für die fortgesetzte Nutzung sollten Sie den Erwerb einer Volllizenz in Erwägung ziehen. 

Starten Sie Aspose.Slides nach der Einrichtung in Ihrem Projekt:
```csharp
using Aspose.Slides;
```

## Implementierungshandbuch

Nachdem die Umgebung bereit ist, können wir die Erstellung eines prozentbasierten gestapelten Säulendiagramms in Schritte unterteilen.

### Erstellen und Konfigurieren des Diagramms

#### Überblick
Erstellen Sie eine Instanz des `Presentation` Klasse, die für die Arbeit mit Folien unerlässlich ist. Fügen Sie anschließend ein gestapeltes Säulendiagramm auf Ihrer Folie hinzu und konfigurieren Sie es.

#### Hinzufügen eines gestapelten Säulendiagramms
```csharp
// Erstellen Sie eine Instanz der Präsentationsklasse
document = new Presentation();

// Verweis auf die erste Folie erhalten
slide = document.Slides[0];

// Fügen Sie das PercentsStackedColumn-Diagramm an Position (20, 20) mit der Größe (500 x 400) hinzu.
chart = slide.Shapes.AddChart(ChartType.PercentsStackedColumn, 20, 20, 500, 400);
```

#### Konfigurieren des Zahlenformats
Stellen Sie sicher, dass Ihre Daten als Prozentsätze angezeigt werden:
```csharp
// Konfigurieren des Zahlenformats für die vertikale Achse
columnChart.Axes.VerticalAxis.IsNumberFormatLinkedToSource = false;
columnChart.Axes.VerticalAxis.NumberFormat = "0.00%"; // Zahlenformat auf Prozent einstellen
```

#### Hinzufügen von Datenreihen und Punkten
Vorhandene Seriendaten löschen und neue hinzufügen:
```csharp
// Löschen Sie alle vorhandenen Seriendaten
columnChart.ChartData.Series.Clear();

int defaultWorksheetIndex = 0;

// Access-Diagrammdaten-Arbeitsmappe
dataWorkbook = columnChart.ChartData.ChartDataWorkbook;

// Neue Datenreihe „Rot“ hinzufügen
series = columnChart.ChartData.Series.Add(dataWorkbook.GetCell(defaultWorksheetIndex, 0, 1, "Reds"), columnChart.Type);
series.DataPoints.AddDataPointForBarSeries(dataWorkbook.GetCell(defaultWorksheetIndex, 1, 1, 0.30));
series.DataPoints.AddDataPointForBarSeries(dataWorkbook.GetCell(defaultWorksheetIndex, 2, 1, 0.50));
series.DataPoints.AddDataPointForBarSeries(dataWorkbook.GetCell(defaultWorksheetIndex, 3, 1, 0.80));
series.DataPoints.AddDataPointForBarSeries(dataWorkbook.GetCell(defaultWorksheetIndex, 4, 1, 0.65));

// Stellen Sie die Füllfarbe für die Serie auf Rot ein
series.Format.Fill.FillType = FillType.Solid;
series.Format.Fill.SolidFillColor.Color = System.Drawing.Color.Red;

// Konfigurieren der Etikettenformateigenschaften für die Serie „Rot“
series.Labels.DefaultDataLabelFormat.ShowValue = true;
series.Labels.DefaultDataLabelFormat.IsNumberFormatLinkedToSource = false;
series.Labels.DefaultDataLabelFormat.NumberFormat = "0.0%"; // Prozentformat festlegen
columnChart.Series[0].Labels.DefaultDataLabelFormat.TextFormat.PortionFormat.FontHeight = 10;
columnChart.Series[0].Labels.DefaultDataLabelFormat.TextFormat.PortionFormat.FillFormat.FillType = FillType.Solid;
columnChart.Series[0].Labels.DefaultDataLabelFormat.TextFormat.PortionFormat.FillFormat.SolidFillColor.Color = System.Drawing.Color.White;

// Eine weitere Serie "Blues" hinzufügen
series2 = columnChart.ChartData.Series.Add(dataWorkbook.GetCell(defaultWorksheetIndex, 0, 2, "Blues"), chart.Type);
series2.DataPoints.AddDataPointForBarSeries(dataWorkbook.GetCell(defaultWorksheetIndex, 1, 2, 0.70));
series2.DataPoints.AddDataPointForBarSeries(dataWorkbook.GetCell(defaultWorksheetIndex, 2, 2, 0.50));
series2.DataPoints.AddDataPointForBarSeries(dataWorkbook.GetCell(defaultWorksheetIndex, 3, 2, 0.20));
series2.DataPoints.AddDataPointForBarSeries(dataWorkbook.GetCell(defaultWorksheetIndex, 4, 2, 0.35));

// Legen Sie die Füllfarbe für die Serie auf Blau fest
series2.Format.Fill.FillType = FillType.Solid;
series2.Format.Fill.SolidFillColor.Color = System.Drawing.Color.Blue;
series2.Labels.DefaultDataLabelFormat.ShowValue = true;
columnChart.Series[1].Labels.DefaultDataLabelFormat.IsNumberFormatLinkedToSource = false;
series2.Labels.DefaultDataLabelFormat.NumberFormat = "0.0%"; // Prozentformat festlegen
columnChart.Series[1].Labels.DefaultDataLabelFormat.TextFormat.PortionFormat.FontHeight = 10;
columnChart.Series[1].Labels.DefaultDataLabelFormat.TextFormat.PortionFormat.FillFormat.FillType = FillType.Solid;
columnChart.Series[1].Labels.DefaultDataLabelFormat.TextFormat.PortionFormat.FillFormat.SolidFillColor.Color = System.Drawing.Color.White;
```

#### Speichern der Präsentation
Speichern Sie Ihre Präsentation in einer Datei:
```csharp
// Speichern Sie die Präsentation im PPTX-Format
document.Save("YOUR_OUTPUT_DIRECTORY/SetDataLabelsPercentageSign_out.pptx");
```

### Tipps zur Fehlerbehebung
- Stellen Sie sicher, dass alle Namespaces korrekt importiert werden.
- Suchen Sie nach Tippfehlern in Eigenschaftsnamen und Methodenaufrufen.
- Überprüfen Sie, ob Ihre Pfade zum Speichern von Dateien vorhanden sind und über die richtigen Berechtigungen verfügen.

## Praktische Anwendungen

Hier sind einige Szenarien, in denen prozentbasierte gestapelte Säulendiagramme hilfreich sein können:
1. **Verkaufsanalyse**: Visualisieren Sie die Produktleistung in verschiedenen Regionen als Anteil am Gesamtumsatz.
2. **Budgetzuweisung**: Zeigen Sie, wie Abteilungen ihr Budget im Verhältnis zu den Gesamtausgaben des Unternehmens verteilen.
3. **Marktforschung**: Vergleichen Sie die Verbraucherpräferenzen für verschiedene Produktkategorien im Zeitverlauf.
4. **Bildungsdaten**: Zeigt die Verteilung der Schülernoten in verschiedenen Fächern an.
5. **Gesundheitsstatistik**: Stellen Sie die Patientendemografie über mehrere Gesundheitszustände hinweg dar.

## Überlegungen zur Leistung

Für eine optimale Leistung sollten Sie Folgendes beachten:
- Beschränkung der Anzahl der Datenpunkte auf das Notwendige.
- Vorabladen von Daten, um die Laufzeitverarbeitung zu minimieren.
- Verwenden effizienter Speicherverwaltungspraktiken mit Aspose.Slides für .NET.

## Abschluss

Herzlichen Glückwunsch! Sie haben erfolgreich gelernt, wie Sie mit Aspose.Slides für .NET ein prozentbasiertes gestapeltes Säulendiagramm erstellen. Dieses Tool verbessert Präsentationen, indem es komplexe Daten verständlicher und optisch ansprechender macht.

Nächste Schritte? Entdecken Sie weitere Diagrammtypen in Aspose.Slides oder integrieren Sie diese Funktionalität in größere Anwendungen. Viel Spaß beim Programmieren!

## FAQ-Bereich

**F1: Kann ich Aspose.Slides kostenlos nutzen?**
A1: Ja, Sie können mit einer kostenlosen Testversion beginnen, um die Funktionen von Aspose.Slides zu testen.

**F2: Welche Diagrammtypen werden von Aspose.Slides für .NET unterstützt?**
A2: Es unterstützt verschiedene Diagramme wie Kreis-, Balken-, Säulen-, Liniendiagramme und mehr.

**F3: Wie beginne ich mit Aspose.Slides für .NET?**
A3: Installieren Sie die Bibliothek wie oben beschrieben mit NuGet oder .NET CLI. Folgen Sie unserer Dokumentation, um Ihr erstes Diagramm zu erstellen.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}