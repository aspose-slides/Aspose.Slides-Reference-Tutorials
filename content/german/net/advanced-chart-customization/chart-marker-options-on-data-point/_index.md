---
title: Verwenden von Diagrammmarkierungsoptionen für Datenpunkte in Aspose.Slides .NET
linktitle: Diagrammmarkierungsoptionen für Datenpunkte
second_title: Aspose.Slides .NET PowerPoint-Verarbeitungs-API
description: Erfahren Sie, wie Sie Ihre PowerPoint-Diagramme mit Aspose.Slides für .NET verbessern. Passen Sie Datenpunktmarkierungen mit Bildern an. Erstellen Sie ansprechende Präsentationen.
type: docs
weight: 11
url: /de/net/advanced-chart-customization/chart-marker-options-on-data-point/
---

Beim Arbeiten mit Präsentationen und Datenvisualisierung bietet Aspose.Slides für .NET eine breite Palette leistungsstarker Funktionen zum Erstellen, Anpassen und Bearbeiten von Diagrammen. In diesem Tutorial erfahren Sie, wie Sie Diagrammmarkierungsoptionen für Datenpunkte verwenden, um Ihre Diagrammpräsentationen zu verbessern. Diese Schritt-für-Schritt-Anleitung führt Sie durch den Prozess, angefangen bei den Voraussetzungen und dem Importieren von Namespaces bis hin zur Aufteilung jedes Beispiels in mehrere Schritte.

## Voraussetzungen

Bevor wir uns mit der Verwendung von Diagrammmarkierungsoptionen für Datenpunkte befassen, stellen Sie sicher, dass die folgenden Voraussetzungen erfüllt sind:

-  Aspose.Slides für .NET: Stellen Sie sicher, dass Sie Aspose.Slides für .NET installiert haben. Sie können es von der[Webseite](https://releases.aspose.com/slides/net/).

- Beispielpräsentation: Für dieses Tutorial verwenden wir eine Beispielpräsentation mit dem Namen „Test.pptx“. Sie sollten diese Präsentation in Ihrem Dokumentverzeichnis haben.

Beginnen wir nun mit dem Importieren der erforderlichen Namespaces.

## Namespaces importieren

```csharp
﻿using Aspose.Slides;
using Aspose.Slides.Charts;
using Aspose.Slides.Export;
```

Wir haben die erforderlichen Namespaces importiert und unsere Präsentation initialisiert. Nun fahren wir mit der Verwendung von Diagrammmarkierungsoptionen für Datenpunkte fort.

## Schritt 1: Erstellen des Standarddiagramms

```csharp

// Der Pfad zum Dokumentverzeichnis.
string dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "Test.pptx");

ISlide slide = pres.Slides[0];

// Erstellen des Standarddiagramms
IChart chart = slide.Shapes.AddChart(ChartType.LineWithMarkers, 0, 0, 400, 400);
```

Wir erstellen ein Standarddiagramm vom Typ „LinieMitMarkierungen“ auf der Folie an einer angegebenen Position und in einer angegebenen Größe.

## Schritt 2: Abrufen des Standard-Arbeitsblattindex für Diagrammdaten

```csharp
// Abrufen des Standardarbeitsblattindexes für Diagrammdaten
int defaultWorksheetIndex = 0;
```

Hier erhalten wir den Index des Standardarbeitsblatts mit Diagrammdaten.

## Schritt 3: Abrufen des Arbeitsblatts mit den Diagrammdaten

```csharp
// Abrufen des Arbeitsblatts mit den Diagrammdaten
IChartDataWorkbook fact = chart.ChartData.ChartDataWorkbook;
```

Wir holen die Diagrammdaten-Arbeitsmappe, um mit Diagrammdaten zu arbeiten.

## Schritt 4: Ändern der Diagrammserie

```csharp
// Demoserie löschen
chart.ChartData.Series.Clear();

// Neue Serie hinzufügen
chart.ChartData.Series.Add(fact.GetCell(defaultWorksheetIndex, 1, 1, "Series 1"), chart.Type);
```

In diesem Schritt entfernen wir alle vorhandenen Demoserien und fügen dem Diagramm eine neue Serie mit dem Namen „Serie 1“ hinzu.

## Schritt 5: Bildfüllung für Datenpunkte festlegen

```csharp
// Stellen Sie das Bild für die Markierungen ein
System.Drawing.Image img1 = (System.Drawing.Image)new Bitmap(dataDir + "aspose-logo.jpg");
IPPImage imgx1 = pres.Images.AddImage(img1);

System.Drawing.Image img2 = (System.Drawing.Image)new Bitmap(dataDir + "Tulips.jpg");
IPPImage imgx2 = pres.Images.AddImage(img2);

// Nehmen Sie die erste Chartserie
IChartSeries series = chart.ChartData.Series[0];

// Neue Datenpunkte mit Bildfüllung hinzufügen
IChartDataPoint point = series.DataPoints.AddDataPointForLineSeries(fact.GetCell(defaultWorksheetIndex, 1, 1, (double)4.5));
point.Marker.Format.Fill.FillType = FillType.Picture;
point.Marker.Format.Fill.PictureFillFormat.Picture.Image = imgx1;

point = series.DataPoints.AddDataPointForLineSeries(fact.GetCell(defaultWorksheetIndex, 2, 1, (double)2.5));
point.Marker.Format.Fill.FillType = FillType.Picture;
point.Marker.Format.Fill.PictureFillFormat.Picture.Image = imgx2;

point = series.DataPoints.AddDataPointForLineSeries(fact.GetCell(defaultWorksheetIndex, 3, 1, (double)3.5));
point.Marker.Format.Fill.FillType = FillType.Picture;
point.Marker.Format.Fill.PictureFillFormat.Picture.Image = imgx1;

point = series.DataPoints.AddDataPointForLineSeries(fact.GetCell(defaultWorksheetIndex, 4, 1, (double)4.5));
point.Marker.Format.Fill.FillType = FillType.Picture;
point.Marker.Format.Fill.PictureFillFormat.Picture.Image = imgx2;
```

Wir setzen Bildmarkierungen für Datenpunkte, sodass Sie anpassen können, wie jeder Datenpunkt im Diagramm angezeigt wird.

## Schritt 6: Ändern der Markierungsgröße der Diagrammreihe

```csharp
// Ändern der Markierungsgröße einer Diagrammreihe
series.Marker.Size = 15;
```

Hier passen wir die Größe der Diagrammreihenmarkierung an, um sie optisch ansprechend zu gestalten.

## Schritt 7: Speichern der Präsentation

```csharp
pres.Save(dataDir + "AsposeScatterChart.pptx", SaveFormat.Pptx);
```

Abschließend speichern wir die Präsentation mit den neuen Diagrammeinstellungen.

## Abschluss

Aspose.Slides für .NET ermöglicht Ihnen die Erstellung beeindruckender Diagrammpräsentationen mit verschiedenen Anpassungsoptionen. In diesem Tutorial haben wir uns auf die Verwendung von Diagrammmarkierungsoptionen für Datenpunkte konzentriert, um die visuelle Darstellung Ihrer Daten zu verbessern. Mit Aspose.Slides für .NET können Sie Ihre Präsentationen auf die nächste Ebene bringen und sie ansprechender und informativer gestalten.

 Wenn Sie Fragen haben oder Hilfe zu Aspose.Slides für .NET benötigen, besuchen Sie bitte die[Aspose.Slides-Dokumentation](https://reference.aspose.com/slides/net/) oder wenden Sie sich an die[Aspose-Gemeinschaft](https://forum.aspose.com/) zur Unterstützung.

## Häufig gestellte Fragen (FAQs)

### Kann ich benutzerdefinierte Bilder als Markierungen für Datenpunkte in Aspose.Slides für .NET verwenden?
Ja, Sie können benutzerdefinierte Bilder als Markierungen für Datenpunkte in Aspose.Slides für .NET verwenden, wie in diesem Tutorial gezeigt.

### Wie kann ich den Diagrammtyp in Aspose.Slides für .NET ändern?
Sie können den Diagrammtyp ändern, indem Sie einen anderen`ChartType` beim Erstellen des Diagramms, beispielsweise „Balken-“, „Kreis-“ oder „Flächendiagramm“.

### Ist Aspose.Slides für .NET mit den neuesten Versionen von PowerPoint kompatibel?
Aspose.Slides für .NET ist für die Arbeit mit verschiedenen PowerPoint-Formaten konzipiert und wird regelmäßig aktualisiert, um die Kompatibilität mit den neuesten PowerPoint-Versionen aufrechtzuerhalten.

### Wo finde ich weitere Tutorials und Ressourcen für Aspose.Slides für .NET?
 Weitere Tutorials und Ressourcen finden Sie im[Aspose.Slides-Dokumentation](https://reference.aspose.com/slides/net/).

### Gibt es eine Testversion von Aspose.Slides für .NET?
 Ja, Sie können Aspose.Slides für .NET ausprobieren, indem Sie eine kostenlose Testversion herunterladen von[Hier](https://releases.aspose.com/).