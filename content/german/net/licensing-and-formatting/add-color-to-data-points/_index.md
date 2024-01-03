---
title: Diagrammkolorierung mit Aspose.Slides für .NET
linktitle: Fügen Sie den Datenpunkten im Diagramm Farbe hinzu
second_title: Aspose.Slides .NET PowerPoint-Verarbeitungs-API
description: Erfahren Sie, wie Sie mit Aspose.Slides für .NET Datenpunkten in einem Diagramm Farbe hinzufügen. Werten Sie Ihre Präsentationen optisch auf und binden Sie Ihr Publikum effektiv ein.
type: docs
weight: 12
url: /de/net/licensing-and-formatting/add-color-to-data-points/
---

In dieser Schritt-für-Schritt-Anleitung führen wir Sie durch den Prozess des Hinzufügens von Farbe zu Datenpunkten in einem Diagramm mit Aspose.Slides für .NET. Aspose.Slides ist eine leistungsstarke Bibliothek für die Arbeit mit PowerPoint-Präsentationen in .NET-Anwendungen. Durch das Hinzufügen von Farbe zu Datenpunkten in einem Diagramm können Ihre Präsentationen optisch ansprechender und verständlicher werden.

## Voraussetzungen

Bevor Sie beginnen, stellen Sie sicher, dass die folgenden Voraussetzungen erfüllt sind:

1. Visual Studio: Sie müssen Visual Studio auf Ihrem Computer installiert haben.

2. Aspose.Slides für .NET: Laden Sie Aspose.Slides für .NET von herunter und installieren Sie es[Download-Link](https://releases.aspose.com/slides/net/).

3. Ein grundlegendes Verständnis von C#: Sie sollten über Grundkenntnisse der C#-Programmierung verfügen.

4. Ihr Dokumentenverzeichnis: Ersetzen Sie „Ihr Dokumentenverzeichnis“ im Code durch den tatsächlichen Pfad zu Ihrem Dokumentenverzeichnis.

## Namensräume importieren

Bevor Sie mit Aspose.Slides für .NET arbeiten können, müssen Sie die erforderlichen Namespaces importieren. 

```csharp
﻿using Aspose.Slides.Charts;
using Aspose.Slides.Export;
using Aspose.Slides;
```


In diesem Beispiel fügen wir Datenpunkten in einem Diagramm Farbe hinzu, indem wir den Diagrammtyp „Sunburst“ verwenden.

```csharp
using (Presentation pres = new Presentation())
{
    // Der Pfad zum Dokumentenverzeichnis.
    string dataDir = "Your Document Directory";

    IChart chart = pres.Slides[0].Shapes.AddChart(ChartType.Sunburst, 100, 100, 450, 400);
    
    // Der Rest des Codes wird in den folgenden Schritten hinzugefügt.
}
```

## Schritt 1: Zugriff auf Datenpunkte

Um bestimmten Datenpunkten in einem Diagramm Farbe hinzuzufügen, müssen Sie auf diese Datenpunkte zugreifen. In diesem Beispiel zielen wir auf Datenpunkt 3 ab.

```csharp
IChartDataPointCollection dataPoints = chart.ChartData.Series[0].DataPoints;
dataPoints[3].DataPointLevels[0].Label.DataLabelFormat.ShowValue = true;
```

## Schritt 2: Datenbeschriftungen anpassen

Passen wir nun die Datenbeschriftungen für Datenpunkt 0 an. Wir blenden den Kategorienamen aus und zeigen den Seriennamen an.

```csharp
IDataLabel branch1Label = dataPoints[0].DataPointLevels[2].Label;
branch1Label.DataLabelFormat.ShowCategoryName = false;
branch1Label.DataLabelFormat.ShowSeriesName = true;
```

## Schritt 3: Textformat und Füllfarbe festlegen

Wir können das Erscheinungsbild der Datenbeschriftungen weiter verbessern, indem wir das Textformat und die Füllfarbe festlegen. In diesem Schritt setzen wir die Textfarbe für Datenpunkt 0 auf Gelb.

```csharp
branch1Label.DataLabelFormat.TextFormat.PortionFormat.FillFormat.FillType = FillType.Solid;
branch1Label.DataLabelFormat.TextFormat.PortionFormat.FillFormat.SolidFillColor.Color = Color.Yellow;
```

## Schritt 4: Anpassen der Datenpunkt-Füllfarbe

Jetzt ändern wir die Füllfarbe von Datenpunkt 9. Wir legen eine bestimmte Farbe fest.

```csharp
IFormat steam4Format = dataPoints[9].Format;
steam4Format.Fill.FillType = FillType.Solid;
steam4Format.Fill.SolidFillColor.Color = Color.FromArgb(0, 176, 240, 255);
```

## Schritt 5: Speichern der Präsentation

Nachdem Sie das Diagramm angepasst haben, können Sie die Präsentation mit den Änderungen speichern.

```csharp
pres.Save(dataDir + "AddColorToDataPoints.pptx", SaveFormat.Pptx);
```

Glückwunsch! Sie haben den Datenpunkten in einem Diagramm mit Aspose.Slides für .NET erfolgreich Farbe hinzugefügt. Dies kann die visuelle Attraktivität und Klarheit Ihrer Präsentationen erheblich verbessern.

## Abschluss

Das Hinzufügen von Farbe zu Datenpunkten in einem Diagramm ist eine wirksame Möglichkeit, Ihre Präsentationen ansprechender und informativer zu gestalten. Mit Aspose.Slides für .NET verfügen Sie über die Tools, um optisch ansprechende Diagramme zu erstellen, die Ihre Daten effektiv vermitteln.

## Häufig gestellte Fragen (FAQs)

### Was ist Aspose.Slides für .NET?
   Aspose.Slides für .NET ist eine Bibliothek, die es .NET-Entwicklern ermöglicht, programmgesteuert mit PowerPoint-Präsentationen zu arbeiten.

### Kann ich andere Diagrammeigenschaften mit Aspose.Slides anpassen?
   Ja, Sie können mit Aspose.Slides für .NET verschiedene Aspekte von Diagrammen anpassen, z. B. Datenbeschriftungen, Schriftarten, Farben und mehr.

### Wo finde ich Dokumentation für Aspose.Slides für .NET?
    Eine ausführliche Dokumentation finden Sie unter[Link zur Dokumentation](https://reference.aspose.com/slides/net/).

### Gibt es eine kostenlose Testversion für Aspose.Slides für .NET?
    Ja, Sie können eine kostenlose Testversion herunterladen[Hier](https://releases.aspose.com/).

### Wie erhalte ich Unterstützung für Aspose.Slides für .NET?
    Für Unterstützung und Diskussionen besuchen Sie die[Aspose.Slides-Forum](https://forum.aspose.com/).