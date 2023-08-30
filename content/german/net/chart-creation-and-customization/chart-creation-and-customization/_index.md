---
title: Diagrammerstellung und -anpassung in Aspose.Slides
linktitle: Diagrammerstellung und -anpassung in Aspose.Slides
second_title: Aspose.Slides .NET PowerPoint-Verarbeitungs-API
description: Erfahren Sie, wie Sie mit Aspose.Slides für .NET beeindruckende Diagramme erstellen und anpassen. Schritt-für-Schritt-Anleitung mit Codebeispielen.
type: docs
weight: 10
url: /de/net/chart-creation-and-customization/chart-creation-and-customization/
---

## Einführung in Aspose.Slides

Aspose.Slides ist eine robuste Bibliothek, die APIs für die Arbeit mit PowerPoint-Präsentationen in verschiedenen Programmiersprachen, einschließlich .NET, bereitstellt. Es ermöglicht Entwicklern, verschiedene Elemente von Präsentationen wie Folien, Formen, Text und Diagramme zu erstellen, zu bearbeiten und zu verwalten.

## Einrichten Ihres Projekts

Bevor wir beginnen, stellen Sie sicher, dass die Aspose.Slides-Bibliothek in Ihrem .NET-Projekt installiert ist. Sie können es von der Aspose-Website herunterladen oder über den NuGet-Paketmanager installieren.

```csharp
// Installieren Sie Aspose.Slides über NuGet
Install-Package Aspose.Slides
```

## Erstellen eines Diagramms

Um ein Diagramm mit Aspose.Slides zu erstellen, gehen Sie folgendermaßen vor:

1. Importieren Sie die erforderlichen Namespaces:
```csharp
using Aspose.Slides;
using Aspose.Slides.Charts;
```

2. Initialisieren Sie eine Präsentation:
```csharp
Presentation presentation = new Presentation();
ISlide slide = presentation.Slides.AddEmptySlide();
```

3. Fügen Sie der Folie ein Diagramm hinzu:
```csharp
IChart chart = slide.Shapes.AddChart(ChartType.Column, 100, 100, 500, 300);
```

## Daten zum Diagramm hinzufügen

Als nächstes fügen wir Daten zu unserem Diagramm hinzu:

1. Greifen Sie auf die Arbeitsmappe des Diagramms zu:
```csharp
IChartDataWorkbook workbook = chart.ChartData.ChartDataWorkbook;
```

2. Kategorien und Serien hinzufügen:
```csharp
workbook.AddCell(0, 1, "Category 1");
workbook.AddCell(0, 2, "Category 2");

IChartSeries series = chart.ChartData.Series.Add(workbook.GetCell(0, 1), chart.Type);
```

3. Werte für die Serie festlegen:
```csharp
series.DataPoints.AddDataPointForBarSeries(workbook.GetCell(0, 2));
```

## Anpassen von Diagrammelementen

Sie können verschiedene Diagrammelemente anpassen:

1. Diagrammtitel anpassen:
```csharp
chart.HasTitle = true;
chart.ChartTitle.Text.Text = "Sales Data";
```

2. Achseneigenschaften ändern:
```csharp
chart.Axes.HorizontalAxis.HasTitle = true;
chart.Axes.HorizontalAxis.Title.Text.Text = "Months";
```

3. Gitternetzlinien und Häkchen anpassen:
```csharp
chart.Axes.VerticalAxis.MajorGridLinesFormat.Line.FillFormat.FillType = FillType.Solid;
chart.Axes.VerticalAxis.MajorGridLinesFormat.Line.FillFormat.SolidFillColor.Color = Color.Gray;
```

## Anwenden von Stilen und Farben

Verbessern Sie das Erscheinungsbild Ihres Diagramms:

1. Diagrammstil anwenden:
```csharp
chart.ChartStyle = 5; // Wählen Sie einen gewünschten Stil
```

2. Serienfarben einstellen:
```csharp
series.Format.Fill.FillType = FillType.Solid;
series.Format.Fill.SolidFillColor.Color = Color.Blue;
```

## Achsen und Beschriftungen formatieren

Formatierung und Beschriftung der Steuerachsen:

1. Achsenwerte formatieren:
```csharp
chart.Axes.HorizontalAxis.NumberFormat.FormatCode = "mm/dd";
```

2. Achsenbeschriftungen drehen:
```csharp
chart.Axes.HorizontalAxis.TextFormat.RotationAngle = 45;
```

## Titel und Legenden hinzufügen

Fügen Sie Titel und Legenden hinzu, um die Übersichtlichkeit zu verbessern:

1. Legendeneigenschaften anpassen:
```csharp
chart.Legend.Position = LegendPosition.Bottom;
chart.Legend.TextFormat.PortionFormat.FontBold = NullableBool.True;
```

2. Achsentitel festlegen:
```csharp
chart.Axes.VerticalAxis.Title.Text.Text = "Sales";
```

## Arbeiten mit mehreren Serien

Integrieren Sie mehrere Reihen für eine umfassende Datendarstellung:

1. Weitere Serien hinzufügen:
```csharp
IChartSeries series2 = chart.ChartData.Series.Add(workbook.GetCell(0, 2), chart.Type);
```

2. Werte für die neue Serie festlegen:
```csharp
series2.DataPoints.AddDataPointForBarSeries(workbook.GetCell(0, 3));
```

## Speichern und Exportieren der Präsentation

Speichern und exportieren Sie abschließend Ihre Präsentation:

```csharp
presentation.Save("ChartPresentation.pptx", SaveFormat.Pptx);
```
## Abschluss

In diesem Tutorial haben wir untersucht, wie Sie Diagramme mithilfe der Aspose.Slides-Bibliothek für .NET erstellen, anpassen und bearbeiten. Aspose.Slides bietet eine umfassende Reihe von Funktionen, die es Entwicklern ermöglichen, programmgesteuert mit PowerPoint-Präsentationen zu arbeiten und diagrammbezogene Aufgaben effizient zu bearbeiten.

## FAQs

### Wie kann ich den Diagrammtyp ändern, nachdem er erstellt wurde?

 Sie können den Diagrammtyp mithilfe von ändern`ChangeType` -Methode auf das Diagrammobjekt anwenden und das gewünschte bereitstellen`ChartType` Aufzählungswert.

### Kann ich 3D-Effekte auf mein Diagramm anwenden?

 Ja, Sie können Ihrem Diagramm 3D-Effekte hinzufügen, indem Sie das konfigurieren`Format.ThreeDFormat` Eigenschaften der Diagrammreihe.

### Ist es möglich, Diagramme in Webanwendungen einzubetten?

Absolut! Sie können mit Aspose.Slides Diagramme erstellen und diese dann in Webanwendungen anzeigen, indem Sie die Folien als Bilder oder interaktives HTML exportieren.

### Kann ich das Erscheinungsbild einzelner Datenpunkte anpassen?

 Sicherlich! Auf einzelne Datenpunkte können Sie über zugreifen`DataPoints`Sammlung und wenden Sie Formatierungen auf sie an.

### Wo finde ich weitere Informationen zu Aspose.Slides für .NET?

 Eine ausführliche Dokumentation und Beispiele finden Sie unter[Aspose.Slides für .NET-Dokumentation](https://reference.aspose.com/slides/net).