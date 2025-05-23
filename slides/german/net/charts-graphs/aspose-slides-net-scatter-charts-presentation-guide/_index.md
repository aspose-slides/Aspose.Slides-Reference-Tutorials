---
"date": "2025-04-15"
"description": "Erfahren Sie, wie Sie Ihre Präsentationen mit Aspose.Slides für .NET mit Streudiagrammen optimieren. Folgen Sie dieser umfassenden Anleitung, um Diagramme effektiv zu erstellen und anzupassen."
"title": "Hinzufügen von Streudiagrammen zu Präsentationen mit Aspose.Slides .NET – Eine Schritt-für-Schritt-Anleitung"
"url": "/de/net/charts-graphs/aspose-slides-net-scatter-charts-presentation-guide/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Hinzufügen von Streudiagrammen zu Präsentationen mit Aspose.Slides .NET: Eine Schritt-für-Schritt-Anleitung

## Einführung
Möchten Sie Ihre Präsentationen durch die mühelose Integration von Streudiagrammen verbessern? Mit Aspose.Slides für .NET wird das Erstellen und Anpassen von Diagrammen zum Kinderspiel. Dieses Tutorial führt Sie durch das Hinzufügen von Streudiagrammen zu Ihren Folien mit Aspose.Slides für .NET. Mit diesen Techniken präsentieren Sie Daten effektiver und erstellen optisch ansprechende Präsentationen.

**Was Sie lernen werden:**
- Einrichten von Aspose.Slides für .NET in Ihrem Projekt
- Erstellen einer neuen Präsentation und Zugreifen auf die erste Folie
- Hinzufügen von Streudiagrammen mit glatten Linien zu Folien
- Löschen vorhandener Reihen und Hinzufügen neuer Reihen zu Diagrammen
- Ändern von Datenpunkten und Markierungsstilen für eine verbesserte Visualisierung
- Speichern der Präsentation in einem angegebenen Verzeichnis

Beginnen wir mit der Überprüfung der Voraussetzungen.

## Voraussetzungen
Stellen Sie vor der Implementierung von Aspose.Slides für .NET sicher, dass Sie über Folgendes verfügen:
- **Aspose.Slides für die .NET-Bibliothek**: Version 23.7 oder höher.
- **Entwicklungsumgebung**: Visual Studio 2019 oder neuer mit .NET Framework 4.6.1+ oder .NET Core/5+.
- **Grundlegende C#-Kenntnisse**: Vertrautheit mit objektorientierter Programmierung in C#.

## Einrichten von Aspose.Slides für .NET
Um Aspose.Slides verwenden zu können, müssen Sie die Bibliothek in Ihrem Projekt installieren. So geht's:

**Verwenden der .NET-CLI:**
```bash
dotnet add package Aspose.Slides
```

**Verwenden der Paketmanager-Konsole:**
```powershell
Install-Package Aspose.Slides
```

**NuGet-Paket-Manager-Benutzeroberfläche:**
- Suchen Sie nach „Aspose.Slides“ und installieren Sie die neueste Version.

### Lizenzerwerb
Sie können mit einer kostenlosen Testversion beginnen oder eine temporäre Lizenz beantragen, um alle Funktionen zu testen. Gehen Sie zum Kauf folgendermaßen vor:
1. Besuchen [Aspose.Slides kaufen](https://purchase.aspose.com/buy) um eine Volllizenz zu kaufen.
2. Für eine temporäre Lizenz besuchen Sie [Seite „Temporäre Lizenz“](https://purchase.aspose.com/temporary-license/).

Sobald Sie Ihre Lizenzdatei erhalten haben, fügen Sie sie Ihrem Projekt hinzu, indem Sie Folgendes verwenden:
```csharp
Aspose.Slides.License license = new Aspose.Slides.License();
license.SetLicense("Aspose.Slides.lic");
```

## Implementierungshandbuch
Wir unterteilen die Implementierung basierend auf den Funktionen in logische Abschnitte.

### Präsentation erstellen und Folie hinzufügen
In diesem Abschnitt wird gezeigt, wie Sie eine Präsentation erstellen und auf die erste Folie zugreifen.

#### Überblick
Beginnen Sie mit der Erstellung einer Instanz des `Presentation` -Klasse, die Ihre PowerPoint-Datei darstellt. Mit diesem Objektmodell ist der Zugriff auf Folien unkompliziert.

#### Implementierungsschritte
**Schritt 1: Präsentation initialisieren**
```csharp
using Aspose.Slides;

// Erstellen einer neuen Präsentation
t Presentation pres = new Presentation();
```
Dieser Code initialisiert ein neues Präsentationsdokument.

**Schritt 2: Zugriff auf die erste Folie**
```csharp
// Greifen Sie auf die erste Folie der Präsentation zu
ISlide slide = pres.Slides[0];
```
Hier, `pres.Slides[0]` greift auf die allererste Folie zu. 

### Streudiagramm zur Folie hinzufügen
Fügen wir Ihrer Präsentation nun ein Streudiagramm hinzu.

#### Überblick
Diagramme helfen Ihnen, Daten in Präsentationen visuell darzustellen. Aspose.Slides vereinfacht die Einbindung verschiedener Diagrammtypen, einschließlich Streudiagrammen.

#### Implementierungsschritte
**Schritt 1: Streudiagramm erstellen und hinzufügen**
```csharp
using Aspose.Slides.Charts;

// Erstellen und Hinzufügen eines Standardstreudiagramms mit glatten Linien
IChart chart = slide.Shapes.AddChart(ChartType.ScatterWithSmoothLines, 0, 0, 400, 400);
```
Dieses Snippet fügt an der angegebenen Position und Größe ein Streudiagramm hinzu.

### Löschen und Hinzufügen von Reihen zu Diagrammdaten
#### Überblick
Möglicherweise müssen Sie Ihr Diagramm anpassen, indem Sie vorhandene Reihen löschen und neue hinzufügen. Dieser Abschnitt behandelt diese Funktion.

#### Implementierungsschritte
**Schritt 1: Zugriff auf die Arbeitsmappe mit Diagrammdaten**
```csharp
int defaultWorksheetIndex = 0;
IChartDataWorkbook fact = chart.ChartData.ChartDataWorkbook;

// Löschen Sie alle bereits vorhandenen Serien
chart.ChartData.Series.Clear();
```
Dieser Code löscht vorhandene Daten, um mit neuen Reihen neu zu beginnen.

**Schritt 2: Neue Serie hinzufügen**
```csharp
// Fügen Sie eine neue Serie mit dem Namen „Serie 1“ hinzu
chart.ChartData.Series.Add(fact.GetCell(defaultWorksheetIndex, 1, 1, "Series 1"), chart.Type);

// Fügen Sie eine weitere Serie mit dem Namen „Serie 2“ hinzu
chart.ChartData.Series.Add(fact.GetCell(defaultWorksheetIndex, 1, 3, "Series 2"), chart.Type);
```
Diese Schritte fügen dem Diagramm zwei neue Reihen hinzu.

### Datenpunkte und Markierungsstil der ersten Serie ändern
#### Überblick
Passen Sie Datenpunkte und Markierungsstile an, um Ihre Streudiagramme besser zu visualisieren.

#### Implementierungsschritte
**Schritt 1: Auf Datenpunkte zugreifen und diese hinzufügen**
```csharp
IChartSeries series = chart.ChartData.Series[0];

// Datenpunkte (1, 3) und (2, 10) hinzufügen
series.DataPoints.AddDataPointForScatterSeries(fact.GetCell(defaultWorksheetIndex, 2, 1, 1), fact.GetCell(defaultWorksheetIndex, 2, 2, 3));
series.DataPoints.AddDataPointForScatterSeries(fact.GetCell(defaultWorksheetIndex, 3, 1, 2), fact.GetCell(defaultWorksheetIndex, 3, 2, 10));
```
**Schritt 2: Markierungsstil ändern**
```csharp
// Ändern des Serientyps und Modifizieren des Markierungsstils
series.Type = ChartType.ScatterWithStraightLinesAndMarkers;
series.Marker.Size = 10;
series.Marker.Symbol = MarkerStyleType.Star;
```
### Datenpunkte und Markierungsstil der zweiten Serie ändern
#### Überblick
Passen Sie die zweite Serie auf ähnliche Weise an Ihre Präsentationsanforderungen an.

#### Implementierungsschritte
**Schritt 1: Zugriff auf mehrere Datenpunkte und Hinzufügen**
```csharp
// Zugriff auf die zweite Diagrammreihe
series = chart.ChartData.Series[1];

// Mehrere Datenpunkte hinzufügen
series.DataPoints.AddDataPointForScatterSeries(fact.GetCell(defaultWorksheetIndex, 2, 3, 5), fact.GetCell(defaultWorksheetIndex, 2, 4, 2));
series.DataPoints.AddDataPointForScatterSeries(fact.GetCell(defaultWorksheetIndex, 3, 3, 3), fact.GetCell(defaultWorksheetIndex, 3, 4, 1));
series.DataPoints.AddDataPointForScatterSeries(fact.GetCell(defaultWorksheetIndex, 4, 3, 2), fact.GetCell(defaultWorksheetIndex, 4, 4, 2));
series.DataPoints.AddDataPointForScatterSeries(fact.GetCell(defaultWorksheetIndex, 5, 3, 5), fact.GetCell(defaultWorksheetIndex, 5, 4, 1));
```
**Schritt 2: Markierungsstil ändern**
```csharp
// Ändern Sie die Markierungsgröße und das Symbol für die zweite Serie
series.Marker.Size = 10;
series.Marker.Symbol = MarkerStyleType.Circle;
```
### Präsentation speichern
Speichern Sie Ihre Präsentation abschließend in einem angegebenen Verzeichnis.

#### Implementierungsschritte
**Schritt 1: Verzeichnis definieren**
Stellen Sie sicher, dass das Ausgabeverzeichnis vorhanden ist. Falls nicht, erstellen Sie es:
```csharp
using Aspose.Slides.Export;
using System.IO;

string YOUR_DOCUMENT_DIRECTORY = "YOUR_DOCUMENT_DIRECTORY";
bool isExists = Directory.Exists(YOUR_DOCUMENT_DIRECTORY);
if (!isExists) 
    Directory.CreateDirectory(YOUR_DOCUMENT_DIRECTORY);

// Speichern der Präsentation
pres.Save(YOUR_DOCUMENT_DIRECTORY + "\AsposeChart_out.pptx", SaveFormat.Pptx);
```
Dieser Code speichert Ihre Präsentationsdatei an einem angegebenen Ort.

## Abschluss
Sie haben Ihren Präsentationen nun erfolgreich Streudiagramme mit Aspose.Slides für .NET hinzugefügt. Entdecken Sie weitere Funktionen und Anpassungsmöglichkeiten in der Bibliothek, um Ihre Datenvisualisierungsfähigkeiten zu verbessern.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}