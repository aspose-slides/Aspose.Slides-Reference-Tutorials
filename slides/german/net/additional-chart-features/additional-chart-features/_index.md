---
title: Erkunden erweiterter Diagrammfunktionen mit Aspose.Slides für .NET
linktitle: Zusätzliche Diagrammfunktionen in Aspose.Slides
second_title: Aspose.Slides .NET PowerPoint-Verarbeitungs-API
description: Lernen Sie erweiterte Diagrammfunktionen in Aspose.Slides für .NET kennen, um Ihre PowerPoint-Präsentationen zu verbessern. Löschen Sie Datenpunkte, stellen Sie Arbeitsmappen wieder her und mehr!
weight: 10
url: /de/net/additional-chart-features/additional-chart-features/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}


In der Welt der Datenvisualisierung und des Präsentationsdesigns ist Aspose.Slides für .NET ein leistungsstarkes Tool zum Erstellen beeindruckender Diagramme und zum Verbessern Ihrer PowerPoint-Präsentationen. Diese Schritt-für-Schritt-Anleitung führt Sie durch die verschiedenen erweiterten Diagrammfunktionen, die Aspose.Slides für .NET bietet. Egal, ob Sie Entwickler oder Präsentationsliebhaber sind, dieses Tutorial hilft Ihnen, das volle Potenzial dieser Bibliothek auszuschöpfen.

## Voraussetzungen

Bevor wir uns in die detaillierten Beispiele vertiefen, stellen Sie sicher, dass die folgenden Voraussetzungen erfüllt sind:

1.  Aspose.Slides für .NET: Sie müssen Aspose.Slides für .NET installiert haben. Wenn Sie es noch nicht haben, können Sie es herunterladen[Hier](https://releases.aspose.com/slides/net/).

2. Visual Studio: Sie sollten Visual Studio oder eine andere geeignete C#-Entwicklungsumgebung installiert haben, um den Codebeispielen folgen zu können.

3. Grundkenntnisse in C#: Um den Code zu verstehen und nach Bedarf zu ändern, sind Kenntnisse in der C#-Programmierung erforderlich.

Nachdem Sie nun die Voraussetzungen erfüllt haben, schauen wir uns einige erweiterte Diagrammfunktionen in Aspose.Slides für .NET an.

## Erforderliche Namespaces importieren

Importieren wir zunächst die erforderlichen Namespaces, um in Ihrem C#-Projekt auf die Aspose.Slides-Funktionalität zuzugreifen.

### Beispiel 1: Namespaces importieren

```csharp
using Aspose.Slides;
using Aspose.Slides.Charts;
using System;
```

## Beispiel 1: Diagrammdatenbereich abrufen

In diesem Beispiel zeigen wir, wie Sie mit Aspose.Slides für .NET den Datenbereich aus einem Diagramm in einer PowerPoint-Präsentation abrufen.

### Schritt 1: Initialisieren der Präsentation

Erstellen Sie zunächst mit Aspose.Slides eine neue PowerPoint-Präsentation.

```csharp
// Der Pfad zum Dokumentverzeichnis.
string dataDir = "Your Document Directory";

using (Presentation pres = new Presentation())
{
    // Fügen Sie der ersten Folie ein gruppiertes Säulendiagramm hinzu.
    IChart chart = pres.Slides[0].Shapes.AddChart(ChartType.ClusteredColumn, 10, 10, 400, 300);
    string result = chart.ChartData.GetRange();
    Console.WriteLine("GetRange result: {0}", result);
}
```

In diesem Codeausschnitt erstellen wir eine neue Präsentation und fügen der ersten Folie ein gruppiertes Säulendiagramm hinzu. Anschließend ermitteln wir den Datenbereich des Diagramms mit`chart.ChartData.GetRange()` und zeigen Sie es an.

## Beispiel 2: Arbeitsmappe aus Diagramm wiederherstellen

Sehen wir uns nun an, wie Sie aus einem Diagramm in einer PowerPoint-Präsentation eine Arbeitsmappe wiederherstellen.

### Schritt 1: Präsentation mit Diagramm laden

Laden Sie zunächst eine PowerPoint-Präsentation, die ein Diagramm enthält.

```csharp
// Der Pfad zum Dokumentverzeichnis.
string dataDir = "Your Document Directory";

string pptxFile = Path.Combine(dataDir, "ExternalWB.pptx");
string outPptxFile = Path.Combine(RunExamples.OutPath, "ExternalWB_out.pptx");

LoadOptions lo = new LoadOptions();
lo.SpreadsheetOptions.RecoverWorkbookFromChartCache = true;

using (Presentation pres = new Presentation(pptxFile, lo))
{
    IChart chart = pres.Slides[0].Shapes[0] as IChart;
    IChartDataWorkbook wb = chart.ChartData.ChartDataWorkbook;

    // Speichern Sie die geänderte Präsentation mit der wiederhergestellten Arbeitsmappe.
    pres.Save(outPptxFile, SaveFormat.Pptx);
}
```

In diesem Beispiel laden wir eine PowerPoint-Präsentation (`ExternalWB.pptx` ) und geben Sie Optionen zum Wiederherstellen der Arbeitsmappe aus einem Diagramm an. Nach der Wiederherstellung der Arbeitsmappe speichern wir die geänderte Präsentation als`ExternalWB_out.pptx`.

## Beispiel 3: Bestimmte Datenpunkte einer Diagrammreihe löschen

Sehen wir uns nun an, wie Sie bestimmte Datenpunkte aus einer Diagrammreihe in einer PowerPoint-Präsentation löschen.

### Schritt 1: Präsentation mit Diagramm laden

Laden Sie zunächst eine PowerPoint-Präsentation, die ein Diagramm mit Datenpunkten enthält.

```csharp
// Der Pfad zum Dokumentverzeichnis.
string dataDir = "Your Document Directory";

using (Presentation pres = new Presentation(dataDir + "TestChart.pptx"))
{
    ISlide sl = pres.Slides[0];
    IChart chart = (IChart)sl.Shapes[0];

    //Iterieren Sie durch jeden Datenpunkt in der ersten Reihe und löschen Sie die X- und Y-Werte.
    foreach (IChartDataPoint dataPoint in chart.ChartData.Series[0].DataPoints)
    {
        dataPoint.XValue.AsCell.Value = null;
        dataPoint.YValue.AsCell.Value = null;
    }

    // Löschen Sie alle Datenpunkte aus der ersten Reihe.
    chart.ChartData.Series[0].DataPoints.Clear();

    // Speichern Sie die geänderte Präsentation.
    pres.Save(dataDir + "ClearSpecificChartSeriesDataPointsData.pptx", SaveFormat.Pptx);
}
```

In diesem Beispiel laden wir eine PowerPoint-Präsentation (`TestChart.pptx` ) und löschen bestimmte Datenpunkte aus der ersten Reihe des Diagramms. Wir durchlaufen jeden Datenpunkt, löschen die X- und Y-Werte und löschen schließlich alle Datenpunkte aus der Reihe. Die geänderte Präsentation wird gespeichert als`ClearSpecificChartSeriesDataPointsData.pptx`.

# Abschluss

Aspose.Slides für .NET bietet eine robuste Plattform für die Arbeit mit Diagrammen in PowerPoint-Präsentationen. Mit den in diesem Tutorial demonstrierten erweiterten Funktionen können Sie Ihre Datenvisualisierung und Ihr Präsentationsdesign auf die nächste Ebene bringen. Egal, ob Sie Daten extrahieren, Arbeitsmappen wiederherstellen oder Diagrammdatenpunkte bearbeiten müssen, Aspose.Slides für .NET bietet alles.

Indem Sie den bereitgestellten Codebeispielen und Schritten folgen, können Sie die Leistungsfähigkeit von Aspose.Slides für .NET nutzen, um Ihre PowerPoint-Präsentationen zu verbessern und eindrucksvolle datengesteuerte Visualisierungen zu erstellen.

## FAQs (Häufig gestellte Fragen)

### Ist Aspose.Slides für .NET sowohl für Anfänger als auch für erfahrene Entwickler geeignet?
   
Ja, Aspose.Slides für .NET richtet sich an Entwickler aller Niveaus, vom Anfänger bis zum Experten. Die Bibliothek bietet eine benutzerfreundliche Oberfläche und erweiterte Funktionen für erfahrene Entwickler.

### Kann ich Aspose.Slides für .NET verwenden, um Diagramme in anderen Dokumentformaten wie PDF oder Bildern zu erstellen?

Ja, Sie können Aspose.Slides für .NET verwenden, um Diagramme in verschiedenen Formaten zu erstellen, darunter PDF, Bilder und mehr. Die Bibliothek bietet vielseitige Exportoptionen.

### Wo finde ich umfassende Dokumentation für Aspose.Slides für .NET?

 Detaillierte Dokumentation und Ressourcen für Aspose.Slides für .NET finden Sie unter[Dokumentation](https://reference.aspose.com/slides/net/).

### Gibt es eine Testversion für Aspose.Slides für .NET?

 Ja, Sie können die Bibliothek mit einer kostenlosen Testversion erkunden, die unter verfügbar ist[Hier](https://releases.aspose.com/). So können Sie die Funktionen beurteilen, bevor Sie einen Kauf tätigen.

### Wie kann ich Support oder Hilfe zu Aspose.Slides für .NET erhalten?

Bei technischen Fragen oder für Support kontaktieren Sie bitte die[Aspose.Slides-Forum](https://forum.aspose.com/), wo Sie Antworten auf häufig gestellte Fragen finden und Hilfe von der Community erhalten.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
