---
title: Histogrammdiagramm in Java-Folien
linktitle: Histogrammdiagramm in Java-Folien
second_title: Aspose.Slides Java PowerPoint-Verarbeitungs-API
description: Erfahren Sie, wie Sie mit Aspose.Slides für Java Histogrammdiagramme in PowerPoint-Präsentationen erstellen. Schritt-für-Schritt-Anleitung mit Quellcode zur Datenvisualisierung.
type: docs
weight: 19
url: /de/java/chart-data-manipulation/histogram-chart-java-slides/
---

## Einführung in das Histogrammdiagramm in Java Slides mit Aspose.Slides

In diesem Tutorial führen wir Sie durch den Prozess der Erstellung eines Histogrammdiagramms in einer PowerPoint-Präsentation mithilfe der Aspose.Slides für Java-API. Ein Histogrammdiagramm wird verwendet, um die Verteilung von Daten über ein kontinuierliches Intervall darzustellen.

## Voraussetzungen

 Bevor Sie beginnen, stellen Sie sicher, dass Sie die Aspose.Slides für Java-Bibliothek installiert haben. Sie können sie von der[Aspose-Website](https://releases.aspose.com/slides/java/).

## Schritt 1: Initialisieren Sie Ihr Projekt

Erstellen Sie ein Java-Projekt und schließen Sie die Aspose.Slides-Bibliothek in die Abhängigkeiten Ihres Projekts ein.

## Schritt 2: Erforderliche Bibliotheken importieren

```java
import com.aspose.slides.*;
```

## Schritt 3: Eine vorhandene Präsentation laden

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "test.pptx");
```

 Ersetzen Sie unbedingt`"Your Document Directory"` durch den tatsächlichen Pfad zu Ihrem PowerPoint-Dokument.

## Schritt 4: Erstellen Sie ein Histogramm

Lassen Sie uns nun auf einer Folie der Präsentation ein Histogramm erstellen.

```java
try {
    IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.Histogram, 50, 50, 500, 400);
    chart.getChartData().getCategories().clear();
    chart.getChartData().getSeries().clear();
    IChartDataWorkbook wb = chart.getChartData().getChartDataWorkbook();
    
    // Datenpunkte zur Reihe hinzufügen
    IChartSeries series = chart.getChartData().getSeries().add(ChartType.Histogram);
    series.getDataPoints().addDataPointForHistogramSeries(wb.getCell(0, "A1", 15));
    series.getDataPoints().addDataPointForHistogramSeries(wb.getCell(0, "A2", -41));
    series.getDataPoints().addDataPointForHistogramSeries(wb.getCell(0, "A3", 16));
    series.getDataPoints().addDataPointForHistogramSeries(wb.getCell(0, "A4", 10));
    series.getDataPoints().addDataPointForHistogramSeries(wb.getCell(0, "A5", -23));
    series.getDataPoints().addDataPointForHistogramSeries(wb.getCell(0, "A6", 16));
    
    // Stellen Sie den Aggregationstyp der horizontalen Achse auf Automatisch ein.
    chart.getAxes().getHorizontalAxis().setAggregationType(AxisAggregationType.Automatic);
    
    // Speichern der Präsentation
    pres.save(dataDir + "Histogram.pptx", SaveFormat.Pptx);
} finally {
    if (pres != null) pres.dispose();
}
```

In diesem Code löschen wir zunächst alle vorhandenen Kategorien und Reihen aus dem Diagramm. Dann fügen wir der Reihe Datenpunkte hinzu, indem wir`getDataPoints().addDataPointForHistogramSeries` Methode. Schließlich setzen wir den Aggregationstyp der horizontalen Achse auf Automatisch und speichern die Präsentation.

## Vollständiger Quellcode für Histogrammdiagramme in Java-Folien

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "test.pptx");
try
{
	IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.Histogram, 50, 50, 500, 400);
	chart.getChartData().getCategories().clear();
	chart.getChartData().getSeries().clear();
	IChartDataWorkbook wb = chart.getChartData().getChartDataWorkbook();
	wb.clear(0);
	IChartSeries series = chart.getChartData().getSeries().add(ChartType.Histogram);
	series.getDataPoints().addDataPointForHistogramSeries(wb.getCell(0, "A1", 15));
	series.getDataPoints().addDataPointForHistogramSeries(wb.getCell(0, "A2", -41));
	series.getDataPoints().addDataPointForHistogramSeries(wb.getCell(0, "A3", 16));
	series.getDataPoints().addDataPointForHistogramSeries(wb.getCell(0, "A4", 10));
	series.getDataPoints().addDataPointForHistogramSeries(wb.getCell(0, "A5", -23));
	series.getDataPoints().addDataPointForHistogramSeries(wb.getCell(0, "A6", 16));
	chart.getAxes().getHorizontalAxis().setAggregationType(AxisAggregationType.Automatic);
	pres.save(dataDir + "Histogram.pptx", SaveFormat.Pptx);
}
finally
{
	if (pres != null) pres.dispose();
}
```

## Abschluss

In diesem Tutorial haben wir untersucht, wie man mithilfe der Aspose.Slides für Java-API ein Histogramm in einer PowerPoint-Präsentation erstellt. Histogramme sind wertvolle Tools zur Visualisierung der Datenverteilung über einen kontinuierlichen Zeitraum und können eine leistungsstarke Ergänzung Ihrer Präsentationen sein, insbesondere wenn es um statistische oder analytische Inhalte geht.

## Häufig gestellte Fragen

### Wie installiere ich Aspose.Slides für Java?

 Sie können die Aspose.Slides für Java-Bibliothek herunterladen von[Hier](https://releases.aspose.com/slides/java/). Befolgen Sie die Installationsanweisungen auf der Website.

### Wofür wird ein Histogrammdiagramm verwendet?

Ein Histogramm wird verwendet, um die Verteilung von Daten über ein kontinuierliches Intervall zu visualisieren. Es wird in der Statistik häufig verwendet, um Häufigkeitsverteilungen darzustellen.

### Kann ich das Erscheinungsbild des Histogrammdiagramms anpassen?

Ja, Sie können das Erscheinungsbild des Diagramms, einschließlich seiner Farben, Beschriftungen und Achsen, mit der Aspose.Slides-API anpassen.