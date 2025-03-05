---
title: Erweiterte Diagrammanpassung in Aspose.Slides
linktitle: Erweiterte Diagrammanpassung in Aspose.Slides
second_title: Aspose.Slides .NET PowerPoint-Verarbeitungs-API
description: Erfahren Sie mehr über die erweiterte Diagrammanpassung in Aspose.Slides für .NET. Erstellen Sie optisch ansprechende Diagramme mit Schritt-für-Schritt-Anleitung.
type: docs
weight: 10
url: /de/net/advanced-chart-customization/advanced-chart-customization/
---

Das Erstellen optisch ansprechender und informativer Diagramme ist in vielen Anwendungen ein wesentlicher Bestandteil der Datenpräsentation. Aspose.Slides für .NET bietet robuste Tools zur Diagrammanpassung, mit denen Sie jeden Aspekt Ihrer Diagramme optimieren können. In diesem Tutorial erkunden wir erweiterte Diagrammanpassungstechniken mit Aspose.Slides für .NET.

## Voraussetzungen

Bevor Sie mit der erweiterten Diagrammanpassung mit Aspose.Slides für .NET beginnen, stellen Sie sicher, dass die folgenden Voraussetzungen erfüllt sind:

1. Aspose.Slides für .NET-Bibliothek: Sie müssen die Aspose.Slides-Bibliothek in Ihrem .NET-Projekt installiert und richtig konfiguriert haben. Sie können sie hier herunterladen:[Hier](https://releases.aspose.com/slides/net/).

2. Eine .NET-Entwicklungsumgebung: Sie sollten eine .NET-Entwicklungsumgebung eingerichtet haben, einschließlich Visual Studio oder einer anderen IDE Ihrer Wahl.

3. Grundkenntnisse in C#: Vertrautheit mit der Programmiersprache C# ist hilfreich, da wir C#-Code für die Arbeit mit Aspose.Slides schreiben werden.

Lassen Sie uns nun die erweiterte Diagrammanpassung in mehrere Schritte aufteilen, um Sie durch den Prozess zu führen.

## Schritt 1: Erstellen Sie eine Präsentation

Erstellen Sie zunächst eine neue Präsentation mit Aspose.Slides.

```csharp
// Der Pfad zum Dokumentverzeichnis.
string dataDir = "Your Document Directory";

// Erstellen Sie ein Verzeichnis, falls es noch nicht vorhanden ist.
bool IsExists = System.IO.Directory.Exists(dataDir);
if (!IsExists)
    System.IO.Directory.CreateDirectory(dataDir);

// Instanziieren der Präsentation
Presentation pres = new Presentation();
```

In diesem Schritt initiieren wir eine neue Präsentation, die unser Diagramm enthalten wird.

## Schritt 2: Zugriff auf die erste Folie

Rufen Sie als Nächstes die erste Folie in der Präsentation auf, der Sie das Diagramm hinzufügen möchten.

```csharp
// Zugriff auf die erste Folie
ISlide slide = pres.Slides[0];
```

Mit diesem Code-Schnipsel können Sie mit der ersten Folie der Präsentation arbeiten.

## Schritt 3: Hinzufügen eines Beispieldiagramms

Fügen wir der Folie nun ein Beispieldiagramm hinzu. In diesem Beispiel erstellen wir ein Liniendiagramm mit Markierungen.

```csharp
// Hinzufügen des Beispieldiagramms
IChart chart = slide.Shapes.AddChart(ChartType.LineWithMarkers, 50, 50, 500, 400);
```

Hier geben wir den Diagrammtyp (LineWithMarkers) sowie seine Position und Abmessungen auf der Folie an.

## Schritt 4: Diagrammtitel festlegen

Legen wir einen Titel für das Diagramm fest, um Kontext bereitzustellen.

```csharp
// Festlegen des Diagrammtitels
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

Dieser Code legt einen Titel für das Diagramm fest und gibt dessen Text, Erscheinungsbild und Schriftstil an.

## Schritt 5: Hauptrasterlinien anpassen

Passen wir nun die Hauptrasterlinien für die Werteachse an.

```csharp
// Festlegen des Formats der Hauptrasterlinien für die Werteachse
chart.Axes.VerticalAxis.MajorGridLinesFormat.Line.FillFormat.FillType = FillType.Solid;
chart.Axes.VerticalAxis.MajorGridLinesFormat.Line.FillFormat.SolidFillColor.Color = Color.Blue;
chart.Axes.VerticalAxis.MajorGridLinesFormat.Line.Width = 5;
chart.Axes.VerticalAxis.MajorGridLinesFormat.Line.DashStyle = LineDashStyle.DashDot;
```

Dieser Schritt konfiguriert die Darstellung der Hauptrasterlinien auf der Werteachse.

## Schritt 6: Kleinere Gitternetzlinien anpassen

In ähnlicher Weise können wir die Nebenrasterlinien für die Werteachse anpassen.

```csharp
// Festlegen des Formats für Nebenrasterlinien für die Werteachse
chart.Axes.VerticalAxis.MinorGridLinesFormat.Line.FillFormat.FillType = FillType.Solid;
chart.Axes.VerticalAxis.MinorGridLinesFormat.Line.FillFormat.SolidFillColor.Color = Color.Red;
chart.Axes.VerticalAxis.MinorGridLinesFormat.Line.Width = 3;
```

Dieser Code passt die Darstellung der Nebengitterlinien auf der Werteachse an.

## Schritt 7: Zahlenformat der Werteachse definieren

Passen Sie das Zahlenformat für die Werteachse an.

```csharp
// Zahlenformat der Werteachse festlegen
chart.Axes.VerticalAxis.IsNumberFormatLinkedToSource = false;
chart.Axes.VerticalAxis.DisplayUnit = DisplayUnitType.Thousands;
chart.Axes.VerticalAxis.NumberFormat = "0.0%";
```

Mit diesem Schritt können Sie die auf der Werteachse angezeigten Zahlen formatieren.

## Schritt 8: Maximal- und Minimalwerte des Diagramms festlegen

Definieren Sie die Maximal- und Minimalwerte für das Diagramm.

```csharp
// Einstelldiagramm Maximal-, Minimalwerte
chart.Axes.VerticalAxis.IsAutomaticMajorUnit = false;
chart.Axes.VerticalAxis.IsAutomaticMaxValue = false;
chart.Axes.VerticalAxis.IsAutomaticMinorUnit = false;
chart.Axes.VerticalAxis.IsAutomaticMinValue = false;

chart.Axes.VerticalAxis.MaxValue = 15f;
chart.Axes.VerticalAxis.MinValue = -2f;
chart.Axes.VerticalAxis.MinorUnit = 0.5f;
chart.Axes.VerticalAxis.MajorUnit = 2.0f;
```

Geben Sie hier den Wertebereich an, den die Diagrammachse anzeigen soll.

## Schritt 9: Texteigenschaften der Werteachse anpassen

Sie können auch die Texteigenschaften der Werteachse anpassen.

```csharp
// Festlegen der Texteigenschaften der Werteachse
IChartPortionFormat txtVal = chart.Axes.VerticalAxis.TextFormat.PortionFormat;
txtVal.FontBold = NullableBool.True;
txtVal.FontHeight = 16;
txtVal.FontItalic = NullableBool.True;
txtVal.FillFormat.FillType = FillType.Solid;
txtVal.FillFormat.SolidFillColor.Color = Color.DarkGreen;
txtVal.LatinFont = new FontData("Times New Roman");
```

Mit diesem Code können Sie den Schriftstil und das Erscheinungsbild der Werteachsenbeschriftungen anpassen.

## Schritt 10: Titel der Werteachse hinzufügen

Wenn Ihr Diagramm einen Titel für die Werteachse benötigt, können Sie ihn mit diesem Schritt hinzufügen.

```csharp
// Festlegen des Titels der Werteachse
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

## Schritt 11: Hauptrasterlinien für die Kategorieachse anpassen

Konzentrieren wir uns nun auf die Hauptrasterlinien der Kategorieachse.

```csharp
// Festlegen des Formats der Hauptrasterlinien für die Kategorieachse
chart.Axes.HorizontalAxis.MajorGridLinesFormat.Line.FillFormat.FillType = FillType.Solid;
chart.Axes

.HorizontalAxis.MajorGridLinesFormat.Line.FillFormat.SolidFillColor.Color = Color.Green;
chart.Axes.HorizontalAxis.MajorGridLinesFormat.Line.Width = 5;
```

Dieser Code konfiguriert die Darstellung der Hauptrasterlinien auf der Kategorieachse.

## Schritt 12: Anpassen der Nebengitterlinien für die Kategorieachse

Ähnlich wie bei der Werteachse können Sie die Nebenrasterlinien für die Kategorieachse anpassen.

```csharp
// Festlegen des Formats für Nebengitterlinien für die Kategorieachse
chart.Axes.HorizontalAxis.MinorGridLinesFormat.Line.FillFormat.FillType = FillType.Solid;
chart.Axes.HorizontalAxis.MinorGridLinesFormat.Line.FillFormat.SolidFillColor.Color = Color.Yellow;
chart.Axes.HorizontalAxis.MinorGridLinesFormat.Line.Width = 3;
```

Hier passen Sie die Darstellung der Nebengitterlinien auf der Kategorieachse an.

## Schritt 13: Texteigenschaften der Kategorieachse anpassen

Passen Sie die Texteigenschaften für die Beschriftungen der Kategorieachsen an.

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

Mit diesem Code können Sie den Schriftstil und das Erscheinungsbild der Beschriftungen der Kategorieachsen anpassen.

## Schritt 14: Titel der Kategorieachse hinzufügen

Sie können der Kategorieachse bei Bedarf auch einen Titel hinzufügen.

```csharp
// Kategorietitel festlegen
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

## Schritt 15: Weitere Anpassungen

Sie können weitere Anpassungen erkunden, z. B. Legenden, Diagrammrückwand, Boden und Plotbereichsfarben. Mit diesen Anpassungen können Sie die visuelle Attraktivität Ihres Diagramms verbessern.

```csharp
// Zusätzliche Anpassungen (optional)

// Festlegen der Texteigenschaften für Legenden
IChartPortionFormat txtleg = chart.Legend.TextFormat.PortionFormat;
txtleg.FontBold = NullableBool.True;
txtleg.FontHeight = 16;
txtleg.FontItalic = NullableBool.True;
txtleg.FillFormat.FillType = FillType.Solid;
txtleg.FillFormat.SolidFillColor.Color = Color.DarkRed;

// Legen Sie fest, ob Diagrammlegenden ohne überlappende Diagramme angezeigt werden sollen.
chart.Legend.Overlay = true;

// Aufzeichnen der ersten Reihe auf der sekundären Werteachse (falls erforderlich)
// Chart.ChartData.Series[0].PlotOnSecondAxis = true;

// Farbschema für die Rückwand festlegen
chart.BackWall.Thickness = 1;
chart.BackWall.Format.Fill.FillType = FillType.Solid;
chart.BackWall.Format.Fill.SolidFillColor.Color = Color.Orange;

// Festlegen der Diagrammbodenfarbe
chart.Floor.Format.Fill.FillType = FillType.Solid;
chart.Floor.Format.Fill.SolidFillColor.Color = Color.Red;

//Festlegen der Farbe des Plotbereichs
chart.PlotArea.Format.Fill.FillType = FillType.Solid;
chart.PlotArea.Format.Fill.SolidFillColor.Color = Color.LightCyan;

// Speichern der Präsentation
pres.Save(dataDir + "FormattedChart_out.pptx", SaveFormat.Pptx);
```

Diese zusätzlichen Anpassungen sind optional und können basierend auf Ihren spezifischen Diagrammdesignanforderungen angewendet werden.

## Abschluss

In dieser Schritt-für-Schritt-Anleitung haben wir die erweiterte Diagrammanpassung mit Aspose.Slides für .NET erkundet. Sie haben gelernt, wie Sie eine Präsentation erstellen, ein Diagramm hinzufügen und sein Erscheinungsbild optimieren, einschließlich Gitternetzlinien, Achsenbeschriftungen und anderen visuellen Elementen. Mit den leistungsstarken Anpassungsoptionen von Aspose.Slides können Sie Diagramme erstellen, die Ihre Daten effektiv vermitteln und Ihr Publikum fesseln.

 Wenn Sie Fragen haben oder bei der Arbeit mit Aspose.Slides für .NET auf Herausforderungen stoßen, können Sie gerne die Dokumentation durchsehen.[Hier](https://reference.aspose.com/slides/net/) oder suchen Sie Hilfe in den Aspose.Slides[Forum](https://forum.aspose.com/).

## FAQs

### Welche .NET-Versionen werden von Aspose.Slides für .NET unterstützt?
Aspose.Slides für .NET unterstützt verschiedene .NET-Versionen, darunter .NET Framework und .NET Core. Die vollständige Liste der unterstützten Versionen finden Sie in der Dokumentation.

### Kann ich mit Aspose.Slides für .NET Diagramme aus Datenquellen wie Excel-Dateien erstellen?
Ja, mit Aspose.Slides für .NET können Sie Diagramme aus externen Datenquellen wie Excel-Tabellen erstellen. Detaillierte Beispiele finden Sie in der Dokumentation.

### Wie kann ich meiner Diagrammreihe benutzerdefinierte Datenbeschriftungen hinzufügen?
 Um Ihrer Diagrammreihe benutzerdefinierte Datenbeschriftungen hinzuzufügen, können Sie auf das`DataLabels` Eigenschaft der Serie und passen Sie die Beschriftungen nach Bedarf an. Codebeispiele und Beispiele finden Sie in der Dokumentation.

### Ist es möglich, das Diagramm in andere Dateiformate wie etwa PDF oder Bildformate zu exportieren?
Ja, Aspose.Slides für .NET bietet Optionen zum Exportieren Ihrer Präsentation mit Diagrammen in verschiedene Formate, einschließlich PDF und Bildformate. Sie können die Bibliothek verwenden, um Ihre Arbeit im gewünschten Ausgabeformat zu speichern.

### Wo finde ich weitere Tutorials und Beispiele für Aspose.Slides für .NET?
 Sie finden eine Fülle von Tutorials, Codebeispielen und Dokumentationen auf den Aspose.Slides[Webseite](https://reference.aspose.com/slides/net/).