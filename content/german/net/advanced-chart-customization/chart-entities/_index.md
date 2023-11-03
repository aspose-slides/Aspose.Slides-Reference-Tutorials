---
title: Erstellen schöner Diagramme mit Aspose.Slides für .NET
linktitle: Diagrammelemente und Formatierung
second_title: Aspose.Slides .NET PowerPoint-Verarbeitungs-API
description: Erfahren Sie, wie Sie mit Aspose.Slides für .NET beeindruckende Diagramme erstellen. Verbessern Sie Ihr Datenvisualisierungsspiel mit unserer Schritt-für-Schritt-Anleitung.
type: docs
weight: 13
url: /de/net/advanced-chart-customization/chart-entities/
---

In der heutigen datengesteuerten Welt ist eine effektive Datenvisualisierung der Schlüssel zur Vermittlung von Informationen an Ihr Publikum. Aspose.Slides für .NET ist eine leistungsstarke Bibliothek, mit der Sie beeindruckende Präsentationen und Folien, einschließlich auffälliger Diagramme, erstellen können. In diesem Tutorial führen wir Sie durch den Prozess der Erstellung schöner Diagramme mit Aspose.Slides für .NET. Wir werden jedes Beispiel in mehrere Schritte unterteilen, um Ihnen das Verständnis und die Implementierung von Diagrammelementen und Formatierungen zu erleichtern. Also lasst uns anfangen!

## Voraussetzungen

Bevor wir uns mit der Erstellung schöner Diagramme mit Aspose.Slides für .NET befassen, müssen Sie sicherstellen, dass die folgenden Voraussetzungen erfüllt sind:

1.  Aspose.Slides für .NET: Stellen Sie sicher, dass die Aspose.Slides für .NET-Bibliothek installiert ist. Sie können es hier herunterladen[Webseite](https://releases.aspose.com/slides/net/).

2. Entwicklungsumgebung: Sie sollten über eine funktionierende Entwicklungsumgebung mit Visual Studio oder einer anderen IDE verfügen, die die .NET-Entwicklung unterstützt.

3. Grundlegende C#-Kenntnisse: Vertrautheit mit der C#-Programmierung ist für dieses Tutorial unerlässlich.

Nachdem wir nun unsere Voraussetzungen geklärt haben, können wir mit der Erstellung schöner Diagramme mit Aspose.Slides für .NET fortfahren.

## Namespaces importieren

Zunächst müssen Sie die erforderlichen Namespaces importieren, um mit Aspose.Slides für .NET zu arbeiten:

```csharp
using System.IO;
using Aspose.Slides;
using System.Drawing;
using Aspose.Slides.Export;
using Aspose.Slides.Charts;
```

## Schritt 1: Erstellen Sie eine Präsentation

Wir beginnen mit der Erstellung einer neuen Präsentation, mit der wir arbeiten können. Diese Präsentation dient als Leinwand für unser Diagramm.

```csharp
// Der Pfad zum Dokumentenverzeichnis.
string dataDir = "Your Document Directory";

// Erstellen Sie ein Verzeichnis, falls es noch nicht vorhanden ist.
bool IsExists = System.IO.Directory.Exists(dataDir);
if (!IsExists)
    System.IO.Directory.CreateDirectory(dataDir);

// Instanziierende Präsentation
Presentation pres = new Presentation();
```

## Schritt 2: Greifen Sie auf die erste Folie zu

Rufen wir die erste Folie der Präsentation auf, auf der wir unser Diagramm platzieren.

```csharp
// Zugriff auf die erste Folie
ISlide slide = pres.Slides[0];
```

## Schritt 3: Fügen Sie ein Beispieldiagramm hinzu

Jetzt fügen wir unserer Folie ein Beispieldiagramm hinzu. In diesem Beispiel erstellen wir ein Liniendiagramm mit Markierungen.

```csharp
// Beispieldiagramm hinzufügen
IChart chart = slide.Shapes.AddChart(ChartType.LineWithMarkers, 50, 50, 500, 400);
```

## Schritt 4: Legen Sie den Diagrammtitel fest

Wir geben unserem Diagramm einen Titel, um es informativer und optisch ansprechender zu gestalten.

```csharp
// Diagrammtitel festlegen
chart.HasTitle = true;
chart.ChartTitle.AddTextFrameForOverriding("");
IPortion chartTitle = chart.ChartTitle.TextFrameForOverriding.Paragraphs[0].Portions[0];
chartTitle.Text = "Sample Chart";
chartTitle.PortionFormat.FillFormat.FillType = FillType.Solid;
chartTitle.PortionFormat.FillFormat.SolidFillColor.Color = Color.Gray;
chartTitle.PortionFormat.FontHeight = 20;
chartTitle.PortionFormat.FontBold = NullableBool.True;
chartTitle.PortionFormat.FontItalic = NullableBool.True;
```

## Schritt 5: Passen Sie die Rasterlinien der vertikalen Achsen an

In diesem Schritt passen wir die Rasterlinien der vertikalen Achse an, um unser Diagramm optisch ansprechender zu gestalten.

```csharp
// Festlegen des Formats der Hauptgitterlinien für die Werteachse
chart.Axes.VerticalAxis.MajorGridLinesFormat.Line.FillFormat.FillType = FillType.Solid;
chart.Axes.VerticalAxis.MajorGridLinesFormat.Line.FillFormat.SolidFillColor.Color = Color.Blue;
chart.Axes.VerticalAxis.MajorGridLinesFormat.Line.Width = 5;
chart.Axes.VerticalAxis.MajorGridLinesFormat.Line.DashStyle = LineDashStyle.DashDot;

// Festlegen des Formats der Nebengitterlinien für die Werteachse
chart.Axes.VerticalAxis.MinorGridLinesFormat.Line.FillFormat.FillType = FillType.Solid;
chart.Axes.VerticalAxis.MinorGridLinesFormat.Line.FillFormat.SolidFillColor.Color = Color.Red;
chart.Axes.VerticalAxis.MinorGridLinesFormat.Line.Width = 3;

// Einstellen des Zahlenformats der Wertachse
chart.Axes.VerticalAxis.IsNumberFormatLinkedToSource = false;
chart.Axes.VerticalAxis.DisplayUnit = DisplayUnitType.Thousands;
chart.Axes.VerticalAxis.NumberFormat = "0.0%";
```

## Schritt 6: Definieren Sie den vertikalen Achsenbereich

In diesem Schritt legen wir die Maximal-, Minimal- und Einheitswerte für die vertikale Achse fest.

```csharp
// Maximal- und Minimalwerte der Einstelltabelle
chart.Axes.VerticalAxis.IsAutomaticMajorUnit = false;
chart.Axes.VerticalAxis.IsAutomaticMaxValue = false;
chart.Axes.VerticalAxis.IsAutomaticMinorUnit = false;
chart.Axes.VerticalAxis.IsAutomaticMinValue = false;

chart.Axes.VerticalAxis.MaxValue = 15f;
chart.Axes.VerticalAxis.MinValue = -2f;
chart.Axes.VerticalAxis.MinorUnit = 0.5f;
chart.Axes.VerticalAxis.MajorUnit = 2.0f;
```

## Schritt 7: Passen Sie den vertikalen Achsentext an

Wir werden nun die Darstellung des Textes auf der vertikalen Achse anpassen.

```csharp
// Festlegen der Texteigenschaften der Wertachse
IChartPortionFormat txtVal = chart.Axes.VerticalAxis.TextFormat.PortionFormat;
txtVal.FontBold = NullableBool.True;
txtVal.FontHeight = 16;
txtVal.FontItalic = NullableBool.True;
txtVal.FillFormat.FillType = FillType.Solid;
txtVal.FillFormat.SolidFillColor.Color = Color.DarkGreen;
txtVal.LatinFont = new FontData("Times New Roman");

// Titel der Wertachse festlegen
chart.Axes.VerticalAxis.HasTitle = true;
chart.Axes.VerticalAxis.Title.AddTextFrameForOverriding("");
IPortion valtitle = chart.Axes.VerticalAxis.Title.TextFrameForOverriding.Paragraphs[0].Portions[0];
valtitle.Text = "Primary Axis";
valtitle.PortionFormat.FillFormat.FillType = FillType.Solid;
valtitle.PortionFormat.FillFormat.SolidFillColor.Color = Color.Gray;
valtitle.PortionFormat.FontHeight = 20;
valtitle.PortionFormat.FontBold = NullableBool.True;
valtitle.PortionFormat.FontItalic = NullableBool.True;
```

## Schritt 8: Passen Sie die Rasterlinien der horizontalen Achsen an

Passen wir nun die Gitterlinien für die horizontale Achse an.

```csharp
// Festlegen des Formats der Hauptgitterlinien für die Kategorieachse
chart.Axes.HorizontalAxis.MajorGridLinesFormat.Line.FillFormat.FillType = FillType.Solid;
chart.Axes.HorizontalAxis.MajorGridLinesFormat.Line.FillFormat.SolidFillColor.Color = Color.Green;
chart.Axes.HorizontalAxis.MajorGridLinesFormat.Line.Width = 5;

//Festlegen des Formats der Nebengitterlinien für die Kategorieachse
chart.Axes.HorizontalAxis.MinorGridLinesFormat.Line.FillFormat.FillType = FillType.Solid;
chart.Axes.HorizontalAxis.MinorGridLinesFormat.Line.FillFormat.SolidFillColor.Color = Color.Yellow;
chart.Axes.HorizontalAxis.MinorGridLinesFormat.Line.Width = 3;

// Festlegen der Texteigenschaften der Kategorieachse
IChartPortionFormat txtCat = chart.Axes.HorizontalAxis.TextFormat.PortionFormat;
txtCat.FontBold = NullableBool.True;
txtCat.FontHeight = 16;
txtCat.FontItalic = NullableBool.True;
txtCat.FillFormat.Fill

Type = FillType.Solid;
txtCat.FillFormat.SolidFillColor.Color = Color.Blue;
txtCat.LatinFont = new FontData("Arial");
```

## Schritt 9: Passen Sie die Beschriftungen der horizontalen Achsen an

In diesem Schritt passen wir die Position und Drehung der horizontalen Achsenbeschriftungen an.

```csharp
// Festlegen der Position der Kategorieachsenbeschriftung
chart.Axes.HorizontalAxis.TickLabelPosition = TickLabelPositionType.Low;

// Festlegen des Rotationswinkels der Kategorieachsenbeschriftung
chart.Axes.HorizontalAxis.TickLabelRotationAngle = 45;
```

## Schritt 10: Legenden anpassen

Lassen Sie uns die Legenden in unserem Diagramm verbessern, um die Lesbarkeit zu verbessern.

```csharp
// Festlegen der Texteigenschaften für Legenden
IChartPortionFormat txtleg = chart.Legend.TextFormat.PortionFormat;
txtleg.FontBold = NullableBool.True;
txtleg.FontHeight = 16;
txtleg.FontItalic = NullableBool.True;
txtleg.FillFormat.FillType = FillType.Solid;
txtleg.FillFormat.SolidFillColor.Color = Color.DarkRed;

// Legen Sie fest, dass Diagrammlegenden ohne überlappende Diagramme angezeigt werden
chart.Legend.Overlay = true;
```

## Schritt 11: Diagrammhintergrund anpassen

Wir passen die Hintergrundfarben des Diagramms, der Rückwand und des Bodens an.

```csharp
// Einstellung der Farbe der Rückwand der Tabelle
chart.BackWall.Thickness = 1;
chart.BackWall.Format.Fill.FillType = FillType.Solid;
chart.BackWall.Format.Fill.SolidFillColor.Color = Color.Orange;

chart.Floor.Format.Fill.FillType = FillType.Solid;
chart.Floor.Format.Fill.SolidFillColor.Color = Color.Red;

// Festlegen der Farbe des Plotbereichs
chart.PlotArea.Format.Fill.FillType = FillType.Solid;
chart.PlotArea.Format.Fill.SolidFillColor.Color = Color.LightCyan;
```

## Schritt 12: Speichern Sie die Präsentation

Abschließend speichern wir unsere Präsentation mit dem formatierten Diagramm.

```csharp
// Präsentation speichern
pres.Save(dataDir + "FormattedChart_out.pptx", SaveFormat.Pptx);
```

## Abschluss

Mit Aspose.Slides für .NET ist das Erstellen schöner und informativer Diagramme in Ihren Präsentationen jetzt einfacher als je zuvor. In diesem Tutorial haben wir die wesentlichen Schritte zum Anpassen verschiedener Aspekte eines Diagramms behandelt, um es optisch ansprechend und informativ zu gestalten. Mit diesen Techniken können Sie beeindruckende Diagramme erstellen, die Ihre Daten Ihrem Publikum effektiv vermitteln.

Beginnen Sie mit Aspose.Slides für .NET zu experimentieren und bringen Sie Ihre Datenvisualisierung auf die nächste Stufe!

## Häufig gestellte Fragen

### 1. Was ist Aspose.Slides für .NET?

Aspose.Slides für .NET ist eine leistungsstarke Bibliothek, die es .NET-Entwicklern ermöglicht, Microsoft PowerPoint-Präsentationen zu erstellen, zu bearbeiten und zu konvertieren. Es bietet zahlreiche Funktionen für die Arbeit mit Folien, Formen, Diagrammen und mehr.

### 2. Wo kann ich Aspose.Slides für .NET herunterladen?

 Sie können Aspose.Slides für .NET von der Website herunterladen[Hier](https://releases.aspose.com/slides/net/).

### 3. Gibt es eine kostenlose Testversion für Aspose.Slides für .NET?

Ja, Sie können eine kostenlose Testversion von Aspose.Slides für .NET unter erhalten[Hier](https://releases.aspose.com/).

### 4. Wie kann ich eine temporäre Lizenz für Aspose.Slides für .NET erhalten?

 Wenn Sie eine temporäre Lizenz benötigen, können Sie diese bei erhalten[dieser Link](https://purchase.aspose.com/temporary-license/).

### 5. Gibt es eine Community oder ein Support-Forum für Aspose.Slides für .NET?

 Ja, Sie können die Aspose.Slides-Community und das Support-Forum finden[Hier](https://forum.aspose.com/).
