---
title: Arbeitsmappe aus Diagramm wiederherstellen
linktitle: Arbeitsmappe aus Diagramm wiederherstellen
second_title: Aspose.Slides .NET PowerPoint-Verarbeitungs-API
description: Erfahren Sie, wie Sie mit Aspose.Slides für .NET eine Arbeitsmappe aus einem Diagramm wiederherstellen. Extrahieren Sie Diagrammdaten und erstellen Sie programmgesteuert Excel-Arbeitsmappen.
type: docs
weight: 12
url: /de/net/additional-chart-features/chart-recover-workbook/
---

## Einführung

Es kann zu Unfällen kommen und Sie müssen möglicherweise eine Arbeitsmappe aus einem Diagramm wiederherstellen. Aspose.Slides für .NET hilft in solchen Situationen. Mit dieser leistungsstarken Bibliothek können Sie Daten aus Diagrammen in Präsentationen extrahieren und in eine neue Arbeitsmappe konvertieren. In dieser Schritt-für-Schritt-Anleitung führen wir Sie durch den Prozess der Wiederherstellung einer Arbeitsmappe aus einem Diagramm mit Aspose.Slides für .NET.

## Voraussetzungen

Bevor Sie beginnen, stellen Sie sicher, dass Folgendes vorhanden ist:

- Visual Studio: Laden Sie Visual Studio herunter und installieren Sie es, was für die .NET-Entwicklung unerlässlich ist.
-  Aspose.Slides für .NET: Sie können die Bibliothek herunterladen von[Hier](https://downloads.aspose.com/slides/net).

## Schritt 1: Installieren Sie Aspose.Slides für .NET

Wenn Sie es noch nicht getan haben, laden Sie Aspose.Slides für .NET herunter und installieren Sie es. Diese Bibliothek bietet umfassende Funktionen für die programmgesteuerte Arbeit mit PowerPoint-Präsentationen.

## Schritt 2: Laden Sie die Präsentation

Erstellen Sie zunächst ein neues C#-Projekt in Visual Studio. Fügen Sie Verweise auf die erforderlichen Aspose.Slides-Assemblys hinzu. Laden Sie die PowerPoint-Präsentation, die das Diagramm enthält, aus dem Sie Daten wiederherstellen möchten.

```csharp
// Laden Sie die Präsentation
Presentation presentation = new Presentation("your-presentation.pptx");
```

## Schritt 3: Identifizieren Sie das Diagramm

 Identifizieren Sie die Folie und das Diagramm, von denen Sie Daten wiederherstellen möchten. Sie können über die auf Folien zugreifen`presentation.Slides` Sammlung und Diagramme mit der`slide.Shapes` Sammlung.

```csharp
// Holen Sie sich die Folie mit dem Diagramm
ISlide slide = presentation.Slides[0];

// Holen Sie sich das Diagramm
IChart chart = null;
foreach (IShape shape in slide.Shapes)
{
    if (shape is IChart)
    {
        chart = (IChart)shape;
        break;
    }
}
```

## Schritt 4: Extrahieren Sie Daten aus dem Diagramm

Extrahieren Sie die Daten aus dem Diagramm mit der API von Aspose.Slides. Sie können Werte aus Diagrammreihen und Kategorien abrufen.

```csharp
// Diagrammdaten extrahieren
IChartData chartData = chart.ChartData;
```

## Schritt 5: Erstellen Sie eine neue Arbeitsmappe

Erstellen Sie eine neue Excel-Arbeitsmappe mit einer Bibliothek wie EPPlus oder ClosedXML.

```csharp
// Erstellen Sie eine neue Excel-Arbeitsmappe
using (var excelPackage = new ExcelPackage())
{
    var worksheet = excelPackage.Workbook.Worksheets.Add("Chart Data");
    // Fügen Sie hier Code hinzu, um die Arbeitsblattüberschriften zu füllen
}
```

## Schritt 6: Arbeitsmappe mit Diagrammdaten füllen

Füllen Sie das Excel-Arbeitsblatt mit den aus dem Diagramm extrahierten Daten.

```csharp
//Füllen Sie das Excel-Arbeitsblatt mit Diagrammdaten
int rowIndex = 2;
foreach (var series in chartData.Series)
{
    worksheet.Cells[rowIndex, 1].Value = series.Name;
    // Fügen Sie hier Code hinzu, um das Arbeitsblatt mit Seriendaten zu füllen
    rowIndex++;
}
```

## Schritt 7: Speichern Sie die Arbeitsmappe

Speichern Sie die Excel-Arbeitsmappe mit den wiederhergestellten Diagrammdaten.

```csharp
// Speichern Sie die Excel-Arbeitsmappe
excelPackage.SaveAs(new FileInfo("recovered-workbook.xlsx"));
```

## Abschluss

Das Wiederherstellen einer Arbeitsmappe aus einem Diagramm wird mit Aspose.Slides für .NET zum Kinderspiel. Wenn Sie diese Schritte befolgen, können Sie Daten aus einem Diagramm in einer PowerPoint-Präsentation programmgesteuert extrahieren und mit den wiederhergestellten Daten eine neue Excel-Arbeitsmappe erstellen. Dieser Prozess kann lebensrettend sein, wenn Unfälle passieren und Daten gerettet werden müssen.

## FAQs

### Wie installiere ich Aspose.Slides für .NET?

 Sie können Aspose.Slides für .NET unter herunterladen[Hier](https://downloads.aspose.com/slides/net).

### Kann ich Daten aus verschiedenen Diagrammtypen wiederherstellen?

Ja, Aspose.Slides für .NET unterstützt verschiedene Diagrammtypen, darunter Balkendiagramme, Liniendiagramme, Kreisdiagramme und mehr.

### Ist Aspose.Slides für .NET für den professionellen Einsatz geeignet?

Absolut! Aspose.Slides für .NET ist eine robuste Bibliothek, die von Entwicklern für die effiziente Arbeit mit PowerPoint-Präsentationen verwendet wird.

### Gibt es Lizenzanforderungen für die Verwendung von Aspose.Slides für .NET?

 Ja, Aspose.Slides für .NET erfordert eine gültige Lizenz für die kommerzielle Nutzung. Lizenzdetails finden Sie auf der[Aspose-Website](https://purchase.aspose.com).

### Kann ich das Erscheinungsbild der wiederhergestellten Excel-Arbeitsmappe anpassen?

Ja, Sie können das Erscheinungsbild und die Formatierung der Excel-Arbeitsmappe mithilfe von Bibliotheken wie EPPlus oder ClosedXML anpassen.