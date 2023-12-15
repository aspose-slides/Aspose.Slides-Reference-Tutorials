---
title: Erkunden von Diagrammtrendlinien in Aspose.Slides für .NET
linktitle: Trendlinien im Diagramm
second_title: Aspose.Slides .NET PowerPoint-Verarbeitungs-API
description: Erfahren Sie in dieser Schritt-für-Schritt-Anleitung, wie Sie mit Aspose.Slides für .NET verschiedene Trendlinien zu Diagrammen hinzufügen. Verbessern Sie ganz einfach Ihre Datenvisualisierungsfähigkeiten!
type: docs
weight: 12
url: /de/net/advanced-chart-customization/chart-trend-lines/
---

In der Welt der Datenvisualisierung und -präsentation kann die Einbindung von Diagrammen eine wirkungsvolle Möglichkeit sein, Informationen effektiv zu vermitteln. Aspose.Slides für .NET bietet eine Reihe funktionsreicher Tools für die Arbeit mit Diagrammen, einschließlich der Möglichkeit, Trendlinien zu Ihren Diagrammen hinzuzufügen. In diesem Tutorial befassen wir uns Schritt für Schritt mit dem Prozess des Hinzufügens von Trendlinien zu einem Diagramm mithilfe von Aspose.Slides für .NET. 

## Voraussetzungen

Bevor wir mit Aspose.Slides für .NET arbeiten, müssen Sie sicherstellen, dass die folgenden Voraussetzungen erfüllt sind:

1.  Aspose.Slides für .NET: Um auf die Bibliothek zuzugreifen und sie zu verwenden, muss Aspose.Slides für .NET installiert sein. Sie können die Bibliothek von der erhalten[Download-Seite](https://releases.aspose.com/slides/net/).

2. Entwicklungsumgebung: Sie sollten eine Entwicklungsumgebung eingerichtet haben, vorzugsweise unter Verwendung einer integrierten .NET-Entwicklungsumgebung wie Visual Studio.

3. Grundkenntnisse in C#: Ein grundlegendes Verständnis der C#-Programmierung ist von Vorteil, da wir C# für die Arbeit mit Aspose.Slides für .NET verwenden werden.

Nachdem wir nun die Voraussetzungen abgedeckt haben, wollen wir den Prozess des Hinzufügens von Trendlinien zu einem Diagramm Schritt für Schritt aufschlüsseln.

## Namespaces importieren

Stellen Sie zunächst sicher, dass Sie die erforderlichen Namespaces in Ihr C#-Projekt importieren. Diese Namespaces sind für die Arbeit mit Aspose.Slides für .NET unerlässlich.

```csharp
using Aspose.Slides;
using Aspose.Slides.Charts;
using Aspose.Slides.Export;
```

## Schritt 1: Erstellen Sie eine Präsentation

In diesem Schritt erstellen wir eine leere Präsentation, mit der wir arbeiten können.

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

Jetzt fügen wir der Diagrammreihe verschiedene Arten von Trendlinien hinzu.

### Hinzufügen einer exponentiellen Trendlinie

```csharp
// Hinzufügen einer exponentiellen Trendlinie für Diagrammserie 1
ITrendline tredLineExp = chart.ChartData.Series[0].TrendLines.Add(TrendlineType.Exponential);
tredLineExp.DisplayEquation = false;
tredLineExp.DisplayRSquaredValue = false;
```

### Hinzufügen einer linearen Trendlinie

```csharp
// Hinzufügen einer linearen Trendlinie für Diagrammserie 1
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

### Hinzufügen einer Trendlinie für den gleitenden Durchschnitt

```csharp
// Hinzufügen einer Trendlinie des gleitenden Durchschnitts für Diagrammserie 2
ITrendline tredLineMovAvg = chart.ChartData.Series[1].TrendLines.Add(TrendlineType.MovingAverage);
tredLineMovAvg.Period = 3;
tredLineMovAvg.TrendlineName = "New TrendLine Name";
```

### Hinzufügen einer polynomialen Trendlinie

```csharp
// Hinzufügen einer polynomialen Trendlinie für Diagrammserie 3
ITrendline tredLinePol = chart.ChartData.Series[2].TrendLines.Add(TrendlineType.Polynomial);
tredLinePol.Forward = 1;
tredLinePol.Order = 3;
```

### Hinzufügen einer Power-Trendlinie

```csharp
// Leistungstrendlinie für Diagrammserie 3 hinzugefügt
ITrendline tredLinePower = chart.ChartData.Series[1].TrendLines.Add(TrendlineType.Power);
tredLinePower.Backward = 1;
```

## Schritt 4: Speichern Sie die Präsentation

Speichern Sie die Präsentation, nachdem Sie dem Diagramm Trendlinien hinzugefügt haben.

```csharp
// Präsentation speichern
pres.Save(dataDir + "ChartTrendLines_out.pptx", SaveFormat.Pptx);
```

Das ist es! Sie haben mit Aspose.Slides für .NET erfolgreich verschiedene Trendlinien zu Ihrem Diagramm hinzugefügt.

## Abschluss

Aspose.Slides für .NET ist eine vielseitige Bibliothek, mit der Sie Diagramme problemlos erstellen und bearbeiten können. Wenn Sie dieser Schritt-für-Schritt-Anleitung folgen, können Sie Ihren Diagrammen verschiedene Arten von Trendlinien hinzufügen und so die visuelle Darstellung Ihrer Daten verbessern.

### FAQs

### Wo finde ich die Dokumentation für Aspose.Slides für .NET?
 Sie können auf die Dokumentation zugreifen[Hier](https://reference.aspose.com/slides/net/).

### Wie kann ich Aspose.Slides für .NET herunterladen?
 Sie können Aspose.Slides für .NET von der Download-Seite herunterladen[Hier](https://releases.aspose.com/slides/net/).

### Gibt es eine kostenlose Testversion für Aspose.Slides für .NET?
 Ja, Sie können Aspose.Slides für .NET kostenlos testen, indem Sie hier klicken[dieser Link](https://releases.aspose.com/).

### Wo kann ich Aspose.Slides für .NET kaufen?
 Um Aspose.Slides für .NET zu kaufen, besuchen Sie die Kaufseite[Hier](https://purchase.aspose.com/buy).

### Benötige ich eine temporäre Lizenz für Aspose.Slides für .NET?
 Eine temporäre Lizenz für Aspose.Slides für .NET erhalten Sie bei[dieser Link](https://purchase.aspose.com/temporary-license/).