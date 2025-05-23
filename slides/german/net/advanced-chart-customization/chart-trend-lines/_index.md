---
"description": "Erfahren Sie in dieser Schritt-für-Schritt-Anleitung, wie Sie mit Aspose.Slides für .NET verschiedene Trendlinien zu Diagrammen hinzufügen. Verbessern Sie mühelos Ihre Datenvisualisierungsfähigkeiten!"
"linktitle": "Diagramm-Trendlinien"
"second_title": "Aspose.Slides .NET PowerPoint-Verarbeitungs-API"
"title": "Erkunden von Diagramm-Trendlinien in Aspose.Slides für .NET"
"url": "/de/net/advanced-chart-customization/chart-trend-lines/"
"weight": 12
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Erkunden von Diagramm-Trendlinien in Aspose.Slides für .NET


In der Welt der Datenvisualisierung und -präsentation kann die Einbindung von Diagrammen eine wirkungsvolle Möglichkeit zur effektiven Informationsvermittlung sein. Aspose.Slides für .NET bietet umfangreiche Tools für die Arbeit mit Diagrammen, darunter die Möglichkeit, Trendlinien hinzuzufügen. In diesem Tutorial erfahren Sie Schritt für Schritt, wie Sie mit Aspose.Slides für .NET Trendlinien zu einem Diagramm hinzufügen. 

## Voraussetzungen

Bevor wir mit der Arbeit mit Aspose.Slides für .NET beginnen, müssen Sie sicherstellen, dass die folgenden Voraussetzungen erfüllt sind:

1. Aspose.Slides für .NET: Um auf die Bibliothek zugreifen und sie verwenden zu können, muss Aspose.Slides für .NET installiert sein. Sie finden die Bibliothek unter [Download-Seite](https://releases.aspose.com/slides/net/).

2. Entwicklungsumgebung: Sie sollten eine Entwicklungsumgebung eingerichtet haben, vorzugsweise eine integrierte .NET-Entwicklungsumgebung wie Visual Studio.

3. Grundkenntnisse in C#: Grundlegende Kenntnisse der C#-Programmierung sind von Vorteil, da wir C# für die Arbeit mit Aspose.Slides für .NET verwenden werden.

Nachdem wir nun die Voraussetzungen abgedeckt haben, wollen wir den Vorgang des Hinzufügens von Trendlinien zu einem Diagramm Schritt für Schritt aufschlüsseln.

## Namespaces importieren

Stellen Sie zunächst sicher, dass Sie die erforderlichen Namespaces in Ihr C#-Projekt importieren. Diese Namespaces sind für die Arbeit mit Aspose.Slides für .NET unerlässlich.

```csharp
using Aspose.Slides;
using Aspose.Slides.Charts;
using Aspose.Slides.Export;
```

## Schritt 1: Erstellen Sie eine Präsentation

In diesem Schritt erstellen wir eine leere Präsentation zum Arbeiten.

```csharp
// Der Pfad zum Dokumentenverzeichnis.
string dataDir = "Your Document Directory";

// Erstellen Sie ein Verzeichnis, falls es noch nicht vorhanden ist.
bool IsExists = System.IO.Directory.Exists(dataDir);
if (!IsExists)
    System.IO.Directory.CreateDirectory(dataDir);

// Leere Präsentation erstellen
Presentation pres = new Presentation();
```

## Schritt 2: Fügen Sie der Folie ein Diagramm hinzu

Als Nächstes fügen wir einer Folie ein gruppiertes Säulendiagramm hinzu.

```csharp
// Erstellen eines gruppierten Säulendiagramms
IChart chart = pres.Slides[0].Shapes.AddChart(ChartType.ClusteredColumn, 20, 20, 500, 400);
```

## Schritt 3: Trendlinien zum Diagramm hinzufügen

Nun fügen wir der Diagrammreihe verschiedene Arten von Trendlinien hinzu.

### Hinzufügen einer exponentiellen Trendlinie

```csharp
// Hinzufügen einer exponentiellen Trendlinie für Diagrammreihe 1
ITrendline tredLineExp = chart.ChartData.Series[0].TrendLines.Add(TrendlineType.Exponential);
tredLineExp.DisplayEquation = false;
tredLineExp.DisplayRSquaredValue = false;
```

### Hinzufügen einer linearen Trendlinie

```csharp
// Hinzufügen einer linearen Trendlinie für Diagrammreihe 1
ITrendline tredLineLin = chart.ChartData.Series[0].TrendLines.Add(TrendlineType.Linear);
tredLineLin.Format.Line.FillFormat.FillType = FillType.Solid;
tredLineLin.Format.Line.FillFormat.SolidFillColor.Color = Color.Red;
```

### Hinzufügen einer logarithmischen Trendlinie

```csharp
// Hinzufügen einer logarithmischen Trendlinie für Diagrammserie 2
ITrendline tredLineLog = chart.ChartData.Series[1].TrendLines.Add(TrendlineType.Logarithmic);
tredLineLog.AddTextFrameForOverriding("New log trend line");
```

### Hinzufügen einer gleitenden Durchschnittstrendlinie

```csharp
// Hinzufügen einer gleitenden Durchschnittstrendlinie für Diagrammserie 2
ITrendline tredLineMovAvg = chart.ChartData.Series[1].TrendLines.Add(TrendlineType.MovingAverage);
tredLineMovAvg.Period = 3;
tredLineMovAvg.TrendlineName = "New TrendLine Name";
```

### Hinzufügen einer polynomischen Trendlinie

```csharp
// Hinzufügen einer polynomischen Trendlinie für Diagrammserie 3
ITrendline tredLinePol = chart.ChartData.Series[2].TrendLines.Add(TrendlineType.Polynomial);
tredLinePol.Forward = 1;
tredLinePol.Order = 3;
```

### Hinzufügen einer Power-Trendlinie

```csharp
// Hinzufügen einer Power-Trendlinie für Diagrammserie 3
ITrendline tredLinePower = chart.ChartData.Series[1].TrendLines.Add(TrendlineType.Power);
tredLinePower.Backward = 1;
```

## Schritt 4: Speichern Sie die Präsentation

Speichern Sie die Präsentation, nachdem Sie dem Diagramm Trendlinien hinzugefügt haben.

```csharp
// Präsentation speichern
pres.Save(dataDir + "ChartTrendLines_out.pptx", SaveFormat.Pptx);
```

Das war's! Sie haben Ihrem Diagramm mit Aspose.Slides für .NET erfolgreich verschiedene Trendlinien hinzugefügt.

## Abschluss

Aspose.Slides für .NET ist eine vielseitige Bibliothek, mit der Sie Diagramme mühelos erstellen und bearbeiten können. Mit dieser Schritt-für-Schritt-Anleitung können Sie Ihren Diagrammen verschiedene Trendlinien hinzufügen und so die visuelle Darstellung Ihrer Daten verbessern.

### FAQs

### Wo finde ich die Dokumentation für Aspose.Slides für .NET?
Sie können auf die Dokumentation zugreifen [Hier](https://reference.aspose.com/slides/net/).

### Wie kann ich Aspose.Slides für .NET herunterladen?
Sie können Aspose.Slides für .NET von der Download-Seite herunterladen [Hier](https://releases.aspose.com/slides/net/).

### Gibt es eine kostenlose Testversion für Aspose.Slides für .NET?
Ja, Sie können Aspose.Slides für .NET kostenlos testen, indem Sie [dieser Link](https://releases.aspose.com/).

### Wo kann ich Aspose.Slides für .NET kaufen?
Um Aspose.Slides für .NET zu kaufen, besuchen Sie die Kaufseite [Hier](https://purchase.aspose.com/buy).

### Benötige ich eine temporäre Lizenz für Aspose.Slides für .NET?
Sie können eine temporäre Lizenz für Aspose.Slides für .NET erhalten von [dieser Link](https://purchase.aspose.com/temporary-license/).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}