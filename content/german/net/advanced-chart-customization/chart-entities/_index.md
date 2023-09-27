---
title: Diagrammelemente und Formatierung
linktitle: Diagrammelemente und Formatierung
second_title: Aspose.Slides .NET PowerPoint-Verarbeitungs-API
description: Erfahren Sie, wie Sie mit Aspose.Slides für .NET dynamische Diagramme in PowerPoint erstellen und formatieren. Schritt-für-Schritt-Anleitung mit Quellcode.
type: docs
weight: 13
url: /de/net/advanced-chart-customization/chart-entities/
---

## Einführung in Aspose.Slides und Diagrammmanipulation

Aspose.Slides für .NET ist eine umfassende Bibliothek, die es Entwicklern ermöglicht, PowerPoint-Präsentationen programmgesteuert zu erstellen, zu bearbeiten und zu manipulieren. Wenn es um Diagramme geht, bietet Aspose.Slides eine breite Palette von Funktionen zum Hinzufügen, Ändern und Formatieren von Diagrammen in Präsentationsfolien.

## Einrichten Ihrer Entwicklungsumgebung

 Stellen Sie zunächst sicher, dass Sie über eine funktionierende Entwicklungsumgebung verfügen, in der Aspose.Slides für .NET installiert ist. Sie können die Bibliothek herunterladen unter[Hier](https://releases.aspose.com/slides/net/).

## Hinzufügen eines Diagramms zu einer Folie

Beginnen wir mit dem Hinzufügen eines Diagramms zu einer Folie. Der folgende Code zeigt, wie Sie eine neue Präsentation erstellen, eine Folie hinzufügen und ein Diagramm darauf einfügen:

```csharp
// Instanziieren Sie ein Präsentationsobjekt
Presentation presentation = new Presentation();

// Fügen Sie eine Folie hinzu
ISlide slide = presentation.Slides.AddEmptySlide();

//Fügen Sie der Folie ein Diagramm hinzu
IChart chart = slide.Shapes.AddChart(ChartType.ClusteredColumn, 100, 100, 500, 300);
```

## Diagrammdaten ändern

Diagramme sind nichts ohne Daten. Mit Aspose.Slides können Sie Diagramme einfach mit Daten füllen. So können Sie die Diagrammdaten ändern:

```csharp
// Greifen Sie auf die Arbeitsmappe des Diagramms zu
IChartDataWorkbook workbook = chart.ChartData.ChartDataWorkbook;

// Greifen Sie auf das Arbeitsblatt des Diagramms zu
IChartDataWorksheet worksheet = workbook.Worksheets[0];

// Diagrammdaten füllen
worksheet.Cells["A1"].Value = "Category";
worksheet.Cells["A2"].Value = "Apple";
worksheet.Cells["A3"].Value = "Banana";
// ...

worksheet.Cells["B1"].Value = "Value";
worksheet.Cells["B2"].Value = 25;
worksheet.Cells["B3"].Value = 40;
// ...
```

## Anpassen der Diagrammdarstellung

Durch die Formatierung eines Diagramms wird seine visuelle Attraktivität erhöht. Sehen wir uns an, wie man verschiedene Aspekte eines Diagramms formatiert:

## Diagrammtitel und Achsen formatieren

Sie können den Diagrammtitel und die Achsen mit dem folgenden Code formatieren:

```csharp
chart.HasTitle = true;
chart.ChartTitle.TextFrame.Text = "Sales Report";

chart.Axes.HorizontalAxis.Title.TextFrame.Text = "Fruits";
chart.Axes.VerticalAxis.Title.TextFrame.Text = "Quantity";
```

## Anwenden von Diagrammstilen

Wenden Sie vordefinierte Diagrammstile an, um Ihr Diagramm ansprechender zu gestalten:

```csharp
chart.ChartStyle = ChartStylePreset.Style2;
```

## Datenbeschriftungen anpassen

Datenbeschriftungen liefern Kontext zum Diagramm. Ändern Sie sie wie folgt:

```csharp
IDataLabel label = chart.Series[0].DataPoints[0].Label;
label.ShowValue = true;
label.DataLabelFormat.TextFormat.PortionFormat.FontBold = NullableBool.True;
```

## Arbeiten mit Diagrammelementen

Durch die Verwaltung von Diagrammelementen haben Sie mehr Kontrolle über die visuelle Darstellung des Diagramms. Lassen Sie uns einige Techniken erkunden:

## Datenreihen verwalten

Sie können Datenreihen wie folgt hinzufügen, entfernen und bearbeiten:

```csharp
IChartSeries series = chart.ChartData.Series.Add(worksheet.Cells, "A2:A3", "B2:B3");
```

## Umgang mit Diagrammlegenden

Legenden liefern wichtige Informationen zu den Komponenten des Diagramms:

```csharp
chart.Legend.Position = LegendPosition.Bottom;
```

## Datenpunkte manipulieren

Passen Sie Datenpunkte individuell an, um sie hervorzuheben:

```csharp
chart.Series[0].DataPoints[0].Format.Fill.FillType = FillType.Solid;
chart.Series[0].DataPoints[0].Format.Fill.SolidFillColor.Color = Color.Red;
```

## Exportieren und Speichern der geänderten Präsentation

Sobald Sie die gewünschten Diagrammänderungen vorgenommen haben, können Sie die Präsentation speichern:

```csharp
presentation.Save("ModifiedPresentation.pptx", SaveFormat.Pptx);
```

## Abschluss

In diesem Leitfaden haben wir die faszinierende Welt der Diagrammelemente und Formatierung mit Aspose.Slides für .NET erkundet. Wir begannen mit den Grundlagen des Hinzufügens und Änderns von Diagrammen, vertieften uns in die Anpassung ihres Erscheinungsbilds und verwalteten sogar verschiedene Diagrammelemente. Aspose.Slides bietet Entwicklern ein leistungsstarkes Toolkit zum programmgesteuerten Erstellen visuell ansprechender und informativer Diagramme.

## FAQs

### Wie installiere ich Aspose.Slides für .NET?

 Sie können Aspose.Slides für .NET unter herunterladen[Hier](https://releases.aspose.com/slides/net/).

### Kann ich benutzerdefinierte Stile auf Diagramme anwenden?

Ja, Sie können benutzerdefinierte Stile auf Diagramme anwenden, indem Sie verschiedene Diagrammeigenschaften bearbeiten.

### Wie füge ich Diagrammdatenpunkten Datenbeschriftungen hinzu?

 Mit können Sie Diagrammdatenpunkten Datenbeschriftungen hinzufügen`DataLabel` Eigenschaft eines Datenpunkts.

### Ist Aspose.Slides nur für fortgeschrittene Entwickler geeignet?

Nein, Aspose.Slides richtet sich an Entwickler aller Niveaus, vom Anfänger bis zum Experten.

### Kann ich Diagramme mit Aspose.Slides in verschiedene Formate exportieren?

Absolut! Aspose.Slides unterstützt den Export von Präsentationen in verschiedene Formate, einschließlich PowerPoint und PDF.