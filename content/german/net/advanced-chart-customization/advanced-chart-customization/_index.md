---
title: Erweiterte Diagrammanpassung in Aspose.Slides
linktitle: Erweiterte Diagrammanpassung in Aspose.Slides
second_title: Aspose.Slides .NET PowerPoint-Verarbeitungs-API
description: Lernen Sie die erweiterte Diagrammanpassung in Aspose.Slides für .NET kennen. Erstellen Sie optisch ansprechende Diagramme mit Schritt-für-Schritt-Anleitung.
type: docs
weight: 10
url: /de/net/advanced-chart-customization/advanced-chart-customization/
---

Die Erstellung optisch ansprechender und informativer Diagramme ist in vielen Anwendungen ein wesentlicher Bestandteil der Datenpräsentation. Aspose.Slides für .NET bietet robuste Tools zur Diagrammanpassung, mit denen Sie jeden Aspekt Ihrer Diagramme optimieren können. In diesem Tutorial erkunden wir erweiterte Diagrammanpassungstechniken mit Aspose.Slides für .NET.

## Voraussetzungen

Bevor Sie mit Aspose.Slides für .NET in die erweiterte Diagrammanpassung eintauchen, stellen Sie sicher, dass die folgenden Voraussetzungen erfüllt sind:

1. Aspose.Slides für .NET-Bibliothek: Die Aspose.Slides-Bibliothek muss in Ihrem .NET-Projekt installiert und ordnungsgemäß konfiguriert sein. Sie können es herunterladen unter[Hier](https://releases.aspose.com/slides/net/).

2. Eine .NET-Entwicklungsumgebung: Sie sollten eine .NET-Entwicklungsumgebung eingerichtet haben, einschließlich Visual Studio oder einer anderen IDE Ihrer Wahl.

3. Grundkenntnisse in C#: Vertrautheit mit der Programmiersprache C# ist hilfreich, da wir C#-Code für die Arbeit mit Aspose.Slides schreiben werden.

Lassen Sie uns nun die erweiterte Diagrammanpassung in mehrere Schritte unterteilen, um Sie durch den Prozess zu führen.

## Schritt 1: Erstellen Sie eine Präsentation

Erstellen Sie zunächst eine neue Präsentation mit Aspose.Slides.

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

In diesem Schritt initiieren wir eine neue Präsentation, die unser Diagramm enthält.

## Schritt 2: Greifen Sie auf die erste Folie zu

Rufen Sie als Nächstes die erste Folie in der Präsentation auf, auf der Sie das Diagramm hinzufügen möchten.

```csharp
// Zugriff auf die erste Folie
ISlide slide = pres.Slides[0];
```

Mit diesem Codeausschnitt können Sie mit der ersten Folie in der Präsentation arbeiten.

## Schritt 3: Beispieldiagramm hinzufügen

Fügen wir nun der Folie ein Beispieldiagramm hinzu. In diesem Beispiel erstellen wir ein Liniendiagramm mit Markierungen.

```csharp
// Beispieldiagramm hinzufügen
IChart chart = slide.Shapes.AddChart(ChartType.LineWithMarkers, 50, 50, 500, 400);
```

Hier geben wir den Diagrammtyp (LineWithMarkers) sowie seine Position und Abmessungen auf der Folie an.

## Schritt 4: Diagrammtitel festlegen

Legen wir einen Titel für das Diagramm fest, um den Kontext bereitzustellen.

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

Dieser Code legt einen Titel für das Diagramm fest und gibt dessen Text, Aussehen und Schriftart an.

## Schritt 5: Passen Sie die wichtigsten Rasterlinien an

Passen wir nun die Hauptgitterlinien für die Werteachse an.

```csharp
// Festlegen des Formats der Hauptgitterlinien für die Werteachse
chart.Axes.VerticalAxis.MajorGridLinesFormat.Line.FillFormat.FillType = FillType.Solid;
chart.Axes.VerticalAxis.MajorGridLinesFormat.Line.FillFormat.SolidFillColor.Color = Color.Blue;
chart.Axes.VerticalAxis.MajorGridLinesFormat.Line.Width = 5;
chart.Axes.VerticalAxis.MajorGridLinesFormat.Line.DashStyle = LineDashStyle.DashDot;
```

In diesem Schritt wird das Erscheinungsbild der Hauptgitterlinien auf der Werteachse konfiguriert.

## Schritt 6: Passen Sie die Nebengitterlinien an

Ebenso können wir die Nebengitterlinien für die Werteachse anpassen.

```csharp
// Festlegen des Formats der Nebengitterlinien für die Werteachse
chart.Axes.VerticalAxis.MinorGridLinesFormat.Line.FillFormat.FillType = FillType.Solid;
chart.Axes.VerticalAxis.MinorGridLinesFormat.Line.FillFormat.SolidFillColor.Color = Color.Red;
chart.Axes.VerticalAxis.MinorGridLinesFormat.Line.Width = 3;
```

Dieser Code passt das Erscheinungsbild kleinerer Gitterlinien auf der Werteachse an.

## Schritt 7: Definieren Sie das Zahlenformat der Wertachse

Passen Sie das Zahlenformat für die Werteachse an.

```csharp
// Einstellen des Zahlenformats der Wertachse
chart.Axes.VerticalAxis.IsNumberFormatLinkedToSource = false;
chart.Axes.VerticalAxis.DisplayUnit = DisplayUnitType.Thousands;
chart.Axes.VerticalAxis.NumberFormat = "0.0%";
```

Mit diesem Schritt können Sie die auf der Werteachse angezeigten Zahlen formatieren.

## Schritt 8: Legen Sie die Maximal- und Minimalwerte des Diagramms fest

Definieren Sie die Maximal- und Minimalwerte für das Diagramm.

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

Hier legen Sie den Wertebereich fest, den die Diagrammachse anzeigen soll.

## Schritt 9: Passen Sie die Texteigenschaften der Wertachse an

Sie können auch die Texteigenschaften der Werteachse anpassen.

```csharp
// Festlegen der Texteigenschaften der Wertachse
IChartPortionFormat txtVal = chart.Axes.VerticalAxis.TextFormat.PortionFormat;
txtVal.FontBold = NullableBool.True;
txtVal.FontHeight = 16;
txtVal.FontItalic = NullableBool.True;
txtVal.FillFormat.FillType = FillType.Solid;
txtVal.FillFormat.SolidFillColor.Color = Color.DarkGreen;
txtVal.LatinFont = new FontData("Times New Roman");
```

Mit diesem Code können Sie den Schriftstil und das Erscheinungsbild der Werteachsenbeschriftungen anpassen.

## Schritt 10: Fügen Sie den Titel der Wertachse hinzu

Wenn Ihr Diagramm einen Titel für die Werteachse benötigt, können Sie ihn mit diesem Schritt hinzufügen.

```csharp
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

In diesem Schritt können Sie einen Titel für die Werteachse festlegen.

## Schritt 11: Passen Sie die Hauptgitterlinien für die Kategorieachse an

Konzentrieren wir uns nun auf die Hauptgitterlinien für die Kategorieachse.

```csharp
// Festlegen des Formats der Hauptgitterlinien für die Kategorieachse
chart.Axes.HorizontalAxis.MajorGridLinesFormat.Line.FillFormat.FillType = FillType.Solid;
chart.Axes

.HorizontalAxis.MajorGridLinesFormat.Line.FillFormat.SolidFillColor.Color = Color.Green;
chart.Axes.HorizontalAxis.MajorGridLinesFormat.Line.Width = 5;
```

Dieser Code konfiguriert die Darstellung der Hauptgitterlinien auf der Kategorieachse.

## Schritt 12: Passen Sie die Nebengitterlinien für die Kategorieachse an

Ähnlich wie bei der Werteachse können Sie die Nebengitterlinien für die Kategorieachse anpassen.

```csharp
//Festlegen des Formats der Nebengitterlinien für die Kategorieachse
chart.Axes.HorizontalAxis.MinorGridLinesFormat.Line.FillFormat.FillType = FillType.Solid;
chart.Axes.HorizontalAxis.MinorGridLinesFormat.Line.FillFormat.SolidFillColor.Color = Color.Yellow;
chart.Axes.HorizontalAxis.MinorGridLinesFormat.Line.Width = 3;
```

Hier passen Sie das Erscheinungsbild der Nebengitterlinien auf der Kategorieachse an.

## Schritt 13: Passen Sie die Texteigenschaften der Kategorieachse an

Passen Sie die Texteigenschaften für die Kategorieachsenbeschriftungen an.

```csharp
// Festlegen der Texteigenschaften der Kategorieachse
IChartPortionFormat txtCat = chart.Axes.HorizontalAxis.TextFormat.PortionFormat;
txtCat.FontBold = NullableBool.True;
txtCat.FontHeight = 16;
txtCat.FontItalic = NullableBool.True;
txtCat.FillFormat.FillType = FillType.Solid;
txtCat.FillFormat.SolidFillColor.Color = Color.Blue;
txtCat.LatinFont = new FontData("Arial");
```

Mit diesem Code können Sie den Schriftstil und das Erscheinungsbild der Kategorieachsenbeschriftungen anpassen.

## Schritt 14: Kategorieachsentitel hinzufügen

Bei Bedarf können Sie der Kategorieachse auch einen Titel hinzufügen.

```csharp
// Festlegen des Kategorietitels
chart.Axes.HorizontalAxis.HasTitle = true;
chart.Axes.HorizontalAxis.Title.AddTextFrameForOverriding("");

IPortion catTitle = chart.Axes.HorizontalAxis.Title.TextFrameForOverriding.Paragraphs[0].Portions[0];
catTitle.Text = "Sample Category";
catTitle.PortionFormat.FillFormat.FillType = FillType.Solid;
catTitle.PortionFormat.FillFormat.SolidFillColor.Color = Color.Gray;
catTitle.PortionFormat.FontHeight = 20;
catTitle.PortionFormat.FontBold = NullableBool.True;
catTitle.PortionFormat.FontItalic = NullableBool.True;
```

In diesem Schritt können Sie einen Titel für die Kategorieachse festlegen.

## Schritt 15: Zusätzliche Anpassungen

Sie können weitere Anpassungen erkunden, z. B. Legenden, Farben der Kartenrückwand, des Bodens und des Plotbereichs. Mit diesen Anpassungen können Sie die visuelle Attraktivität Ihres Diagramms verbessern.

```csharp
// Zusätzliche Anpassungen (optional)

// Festlegen der Texteigenschaften für Legenden
IChartPortionFormat txtleg = chart.Legend.TextFormat.PortionFormat;
txtleg.FontBold = NullableBool.True;
txtleg.FontHeight = 16;
txtleg.FontItalic = NullableBool.True;
txtleg.FillFormat.FillType = FillType.Solid;
txtleg.FillFormat.SolidFillColor.Color = Color.DarkRed;

// Legen Sie fest, dass Diagrammlegenden ohne überlappende Diagramme angezeigt werden
chart.Legend.Overlay = true;

// Zeichnen der ersten Reihe auf der sekundären Wertachse (falls erforderlich)
// Chart.ChartData.Series[0].PlotOnSecondAxis = true;

// Einstellung der Farbe der Rückwand der Tabelle
chart.BackWall.Thickness = 1;
chart.BackWall.Format.Fill.FillType = FillType.Solid;
chart.BackWall.Format.Fill.SolidFillColor.Color = Color.Orange;

// Festlegen der Bodenfarbe des Diagramms
chart.Floor.Format.Fill.FillType = FillType.Solid;
chart.Floor.Format.Fill.SolidFillColor.Color = Color.Red;

// Festlegen der Farbe des Plotbereichs
chart.PlotArea.Format.Fill.FillType = FillType.Solid;
chart.PlotArea.Format.Fill.SolidFillColor.Color = Color.LightCyan;

// Speichern Sie die Präsentation
pres.Save(dataDir + "FormattedChart_out.pptx", SaveFormat.Pptx);
```

Diese zusätzlichen Anpassungen sind optional und können basierend auf Ihren spezifischen Anforderungen an das Diagrammdesign angewendet werden.

## Abschluss

In dieser Schritt-für-Schritt-Anleitung haben wir die erweiterte Diagrammanpassung mit Aspose.Slides für .NET untersucht. Sie haben gelernt, wie Sie eine Präsentation erstellen, ein Diagramm hinzufügen und dessen Erscheinungsbild optimieren, einschließlich Gitterlinien, Achsenbeschriftungen und anderen visuellen Elementen. Mit den leistungsstarken Anpassungsoptionen von Aspose.Slides können Sie Diagramme erstellen, die Ihre Daten effektiv vermitteln und Ihr Publikum ansprechen.

 Wenn Sie bei der Arbeit mit Aspose.Slides für .NET Fragen haben oder auf Herausforderungen stoßen, können Sie sich gerne die Dokumentation ansehen[Hier](https://reference.aspose.com/slides/net/) oder suchen Sie Hilfe in den Aspose.Slides[Forum](https://forum.aspose.com/).

## FAQs

### Welche Versionen von .NET werden von Aspose.Slides für .NET unterstützt?
Aspose.Slides für .NET unterstützt verschiedene .NET-Versionen, einschließlich .NET Framework und .NET Core. Die vollständige Liste der unterstützten Versionen finden Sie in der Dokumentation.

### Kann ich mit Aspose.Slides für .NET Diagramme aus Datenquellen wie Excel-Dateien erstellen?
Ja, mit Aspose.Slides für .NET können Sie Diagramme aus externen Datenquellen wie Excel-Tabellen erstellen. Detaillierte Beispiele finden Sie in der Dokumentation.

### Wie kann ich meiner Diagrammserie benutzerdefinierte Datenbeschriftungen hinzufügen?
 Um Ihrer Diagrammreihe benutzerdefinierte Datenbeschriftungen hinzuzufügen, können Sie auf zugreifen`DataLabels` Eigenschaft der Serie und passen Sie die Beschriftungen nach Bedarf an. Codebeispiele und Beispiele finden Sie in der Dokumentation.

### Ist es möglich, das Diagramm in verschiedene Dateiformate wie PDF oder Bildformate zu exportieren?
Ja, Aspose.Slides für .NET bietet Optionen zum Exportieren Ihrer Präsentation mit Diagrammen in verschiedene Formate, einschließlich PDF- und Bildformate. Mithilfe der Bibliothek können Sie Ihre Arbeit im gewünschten Ausgabeformat speichern.

### Wo finde ich weitere Tutorials und Beispiele für Aspose.Slides für .NET?
 Auf den Aspose.Slides finden Sie zahlreiche Tutorials, Codebeispiele und Dokumentationen[Webseite](https://reference.aspose.com/slides/net/).