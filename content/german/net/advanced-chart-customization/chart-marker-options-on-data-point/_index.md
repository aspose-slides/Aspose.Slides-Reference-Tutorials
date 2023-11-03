---
title: Verwenden von Diagrammmarkierungsoptionen für Datenpunkte in Aspose.Slides .NET
linktitle: Diagrammmarkierungsoptionen für Datenpunkte
second_title: Aspose.Slides .NET PowerPoint-Verarbeitungs-API
description: Erfahren Sie, wie Sie Ihre PowerPoint-Diagramme mit Aspose.Slides für .NET verbessern. Passen Sie Datenpunktmarkierungen mit Bildern an. Erstellen Sie ansprechende Präsentationen.
type: docs
weight: 11
url: /de/net/advanced-chart-customization/chart-marker-options-on-data-point/
---

Bei der Arbeit mit Präsentationen und Datenvisualisierung bietet Aspose.Slides für .NET eine breite Palette leistungsstarker Funktionen zum Erstellen, Anpassen und Bearbeiten von Diagrammen. In diesem Tutorial erfahren Sie, wie Sie Diagrammmarkierungsoptionen für Datenpunkte verwenden, um Ihre Diagrammpräsentationen zu verbessern. Diese Schritt-für-Schritt-Anleitung führt Sie durch den Prozess, angefangen bei den Voraussetzungen und dem Importieren von Namespaces bis hin zur Aufteilung jedes Beispiels in mehrere Schritte.

## Voraussetzungen

Bevor wir uns mit der Verwendung von Diagrammmarkierungsoptionen für Datenpunkte befassen, stellen Sie sicher, dass die folgenden Voraussetzungen erfüllt sind:

-  Aspose.Slides für .NET: Stellen Sie sicher, dass Aspose.Slides für .NET installiert ist. Sie können es hier herunterladen[Webseite](https://releases.aspose.com/slides/net/).

- Beispielpräsentation: Für dieses Tutorial verwenden wir eine Beispielpräsentation mit dem Namen „Test.pptx“. Sie sollten diese Präsentation in Ihrem Dokumentenverzeichnis haben.

Beginnen wir nun mit dem Import der erforderlichen Namespaces.

## Namespaces importieren

```csharp
﻿using Aspose.Slides;
using Aspose.Slides.Charts;
using Aspose.Slides.Export;
```

Wir haben die erforderlichen Namespaces importiert und unsere Präsentation initialisiert. Fahren wir nun mit der Verwendung der Diagrammmarkierungsoptionen für Datenpunkte fort.

## Schritt 1: Erstellen des Standarddiagramms

```csharp

// Der Pfad zum Dokumentenverzeichnis.
string dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "Test.pptx");

ISlide slide = pres.Slides[0];

// Erstellen des Standarddiagramms
IChart chart = slide.Shapes.AddChart(ChartType.LineWithMarkers, 0, 0, 400, 400);
```

Wir erstellen auf der Folie ein Standarddiagramm vom Typ „LineWithMarkers“ an einer bestimmten Position und Größe.

## Schritt 2: Abrufen des Standard-Diagrammdaten-Arbeitsblattindex

```csharp
// Abrufen des Standard-Arbeitsblattindex für Diagrammdaten
int defaultWorksheetIndex = 0;
```

Hier erhalten wir den Index des Standard-Diagrammdaten-Arbeitsblatts.

## Schritt 3: Abrufen des Diagrammdaten-Arbeitsblatts

```csharp
//Abrufen des Diagrammdaten-Arbeitsblatts
IChartDataWorkbook fact = chart.ChartData.ChartDataWorkbook;
```

Wir rufen die Diagrammdaten-Arbeitsmappe ab, um mit Diagrammdaten zu arbeiten.

## Schritt 4: Ändern der Diagrammreihe

```csharp
// Demoserie löschen
chart.ChartData.Series.Clear();

// Neue Serie hinzufügen
chart.ChartData.Series.Add(fact.GetCell(defaultWorksheetIndex, 1, 1, "Series 1"), chart.Type);
```

In diesem Schritt entfernen wir alle vorhandenen Demoserien und fügen dem Diagramm eine neue Serie mit dem Namen „Serie 1“ hinzu.

## Schritt 5: Bildfüllung für Datenpunkte festlegen

```csharp
// Legen Sie das Bild für die Markierungen fest
System.Drawing.Image img1 = (System.Drawing.Image)new Bitmap(dataDir + "aspose-logo.jpg");
IPPImage imgx1 = pres.Images.AddImage(img1);

System.Drawing.Image img2 = (System.Drawing.Image)new Bitmap(dataDir + "Tulips.jpg");
IPPImage imgx2 = pres.Images.AddImage(img2);

// Nehmen Sie die erste Chartserie
IChartSeries series = chart.ChartData.Series[0];

// Fügen Sie neue Datenpunkte mit Bildfüllung hinzu
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

## Schritt 6: Ändern der Größe der Diagrammreihenmarkierung

```csharp
//Ändern der Größe der Diagrammserienmarkierung
series.Marker.Size = 15;
```

Hier passen wir die Größe der Diagrammreihenmarkierung an, um sie optisch ansprechend zu gestalten.

## Schritt 7: Speichern der Präsentation

```csharp
pres.Save(dataDir + "AsposeScatterChart.pptx", SaveFormat.Pptx);
```

Abschließend speichern wir die Präsentation mit den neuen Diagrammeinstellungen.

## Abschluss

Mit Aspose.Slides für .NET können Sie beeindruckende Diagrammpräsentationen mit verschiedenen Anpassungsoptionen erstellen. In diesem Tutorial haben wir uns auf die Verwendung von Diagrammmarkierungsoptionen für Datenpunkte konzentriert, um die visuelle Darstellung Ihrer Daten zu verbessern. Mit Aspose.Slides für .NET können Sie Ihre Präsentationen auf die nächste Stufe heben und sie ansprechender und informativer gestalten.

 Wenn Sie Fragen haben oder Hilfe zu Aspose.Slides für .NET benötigen, besuchen Sie bitte die[Aspose.Slides-Dokumentation](https://reference.aspose.com/slides/net/) oder wenden Sie sich an die[Aspose-Gemeinschaft](https://forum.aspose.com/) zur Unterstützung.

## Häufig gestellte Fragen (FAQs)

### Kann ich benutzerdefinierte Bilder als Markierungen für Datenpunkte in Aspose.Slides für .NET verwenden?
Ja, Sie können benutzerdefinierte Bilder als Markierungen für Datenpunkte in Aspose.Slides für .NET verwenden, wie in diesem Tutorial gezeigt.

### Wie kann ich den Diagrammtyp in Aspose.Slides für .NET ändern?
Sie können den Diagrammtyp ändern, indem Sie einen anderen angeben`ChartType` beim Erstellen des Diagramms, z. B. „Balken“, „Kreis“ oder „Fläche“.

### Ist Aspose.Slides für .NET mit den neuesten Versionen von PowerPoint kompatibel?
Aspose.Slides für .NET ist für die Verwendung mit verschiedenen PowerPoint-Formaten konzipiert und wird regelmäßig aktualisiert, um die Kompatibilität mit den neuesten PowerPoint-Versionen sicherzustellen.

### Wo finde ich weitere Tutorials und Ressourcen für Aspose.Slides für .NET?
 Weitere Tutorials und Ressourcen finden Sie im[Aspose.Slides-Dokumentation](https://reference.aspose.com/slides/net/).

### Gibt es eine Testversion von Aspose.Slides für .NET?
 Ja, Sie können Aspose.Slides für .NET ausprobieren, indem Sie eine kostenlose Testversion von herunterladen[Hier](https://releases.aspose.com/).