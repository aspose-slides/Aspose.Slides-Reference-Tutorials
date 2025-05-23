---
"description": "Erfahren Sie, wie Sie mit Aspose.Slides für Java Histogramme in PowerPoint-Präsentationen erstellen. Schritt-für-Schritt-Anleitung mit Quellcode zur Datenvisualisierung."
"linktitle": "Histogrammdiagramm in Java-Folien"
"second_title": "Aspose.Slides Java PowerPoint-Verarbeitungs-API"
"title": "Histogrammdiagramm in Java-Folien"
"url": "/de/java/chart-data-manipulation/histogram-chart-java-slides/"
"weight": 19
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Histogrammdiagramm in Java-Folien


## Einführung in das Histogrammdiagramm in Java-Folien mit Aspose.Slides

In diesem Tutorial führen wir Sie durch die Erstellung eines Histogramms in einer PowerPoint-Präsentation mithilfe der Aspose.Slides für Java-API. Ein Histogramm dient zur Darstellung der Datenverteilung über ein kontinuierliches Intervall.

## Voraussetzungen

Bevor Sie beginnen, stellen Sie sicher, dass Sie die Aspose.Slides für Java-Bibliothek installiert haben. Sie können sie von der [Aspose-Website](https://releases.aspose.com/slides/java/).

## Schritt 1: Initialisieren Sie Ihr Projekt

Erstellen Sie ein Java-Projekt und schließen Sie die Aspose.Slides-Bibliothek in die Abhängigkeiten Ihres Projekts ein.

## Schritt 2: Erforderliche Bibliotheken importieren

```java
import com.aspose.slides.*;
```

## Schritt 3: Laden Sie eine vorhandene Präsentation

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "test.pptx");
```

Stellen Sie sicher, dass Sie `"Your Document Directory"` durch den tatsächlichen Pfad zu Ihrem PowerPoint-Dokument.

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
    
    // Legen Sie den Aggregationstyp der horizontalen Achse auf „Automatisch“ fest.
    chart.getAxes().getHorizontalAxis().setAggregationType(AxisAggregationType.Automatic);
    
    // Speichern der Präsentation
    pres.save(dataDir + "Histogram.pptx", SaveFormat.Pptx);
} finally {
    if (pres != null) pres.dispose();
}
```

In diesem Code löschen wir zunächst alle vorhandenen Kategorien und Reihen aus dem Diagramm. Anschließend fügen wir der Reihe Datenpunkte hinzu, indem wir `getDataPoints().addDataPointForHistogramSeries` Methode. Schließlich setzen wir den Aggregationstyp der horizontalen Achse auf Automatisch und speichern die Präsentation.

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

In diesem Tutorial haben wir gezeigt, wie Sie mithilfe der Aspose.Slides für Java-API ein Histogramm in einer PowerPoint-Präsentation erstellen. Histogramme sind wertvolle Werkzeuge zur Visualisierung der Datenverteilung über ein kontinuierliches Intervall und können eine leistungsstarke Ergänzung Ihrer Präsentationen sein, insbesondere bei statistischen oder analytischen Inhalten.

## Häufig gestellte Fragen

### Wie installiere ich Aspose.Slides für Java?

Sie können die Aspose.Slides für Java-Bibliothek herunterladen von [Hier](https://releases.aspose.com/slides/java/). Befolgen Sie die Installationsanweisungen auf der Website.

### Wofür wird ein Histogrammdiagramm verwendet?

Ein Histogramm dient zur Visualisierung der Datenverteilung über ein kontinuierliches Intervall. Es wird in der Statistik häufig zur Darstellung von Häufigkeitsverteilungen verwendet.

### Kann ich das Erscheinungsbild des Histogrammdiagramms anpassen?

Ja, Sie können das Erscheinungsbild des Diagramms, einschließlich seiner Farben, Beschriftungen und Achsen, mithilfe der Aspose.Slides-API anpassen.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}