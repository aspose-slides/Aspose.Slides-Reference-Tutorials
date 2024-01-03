---
title: Standardmarkierungen im Diagramm in Java-Folien
linktitle: Standardmarkierungen im Diagramm in Java-Folien
second_title: Aspose.Slides Java PowerPoint-Verarbeitungs-API
description: Erfahren Sie, wie Sie mit Aspose.Slides für Java Java-Folien mit Standardmarkierungen in Diagrammen erstellen. Schritt-für-Schritt-Anleitung mit Quellcode.
type: docs
weight: 16
url: /de/java/chart-data-manipulation/default-markers-in-chart-java-slides/
---

## Einführung in Standardmarkierungen im Diagramm in Java-Folien

In diesem Tutorial erfahren Sie, wie Sie mit Aspose.Slides für Java ein Diagramm mit Standardmarkierungen erstellen. Standardmarkierungen sind Symbole oder Formen, die Datenpunkten in einem Diagramm hinzugefügt werden, um sie hervorzuheben. Wir erstellen ein Liniendiagramm mit Markierungen zur Visualisierung der Daten.

## Voraussetzungen

Bevor Sie beginnen, stellen Sie sicher, dass die Aspose.Slides for Java-Bibliothek in Ihrem Java-Projekt installiert und eingerichtet ist.

## Schritt 1: Erstellen Sie eine Präsentation

Lassen Sie uns zunächst eine Präsentation erstellen und eine Folie hinzufügen. Anschließend fügen wir der Folie ein Diagramm hinzu.

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
ISlide slide = pres.getSlides().get_Item(0);
```

## Schritt 2: Fügen Sie ein Liniendiagramm mit Markierungen hinzu

Fügen wir nun der Folie ein Liniendiagramm mit Markierungen hinzu. Wir löschen außerdem alle Standarddaten aus dem Diagramm.

```java
IChart chart = slide.getShapes().addChart(ChartType.LineWithMarkers, 10, 10, 400, 400);
chart.getChartData().getSeries().clear();
chart.getChartData().getCategories().clear();
```

## Schritt 3: Diagrammdaten ausfüllen

Wir füllen das Diagramm mit Beispieldaten. In diesem Beispiel erstellen wir zwei Reihen mit Datenpunkten und Kategorien.

```java
IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();

// Serie 1
chart.getChartData().getSeries().add(fact.getCell(0, 0, 1, "Series 1"));
IChartSeries series = chart.getChartData().getSeries().get_Item(0);
chart.getChartData().getCategories().add(fact.getCell(0, 1, 0, "C1"));
series.getDataPoints().addDataPointForLineSeries(fact.getCell(0, 1, 1, 24));
chart.getChartData().getCategories().add(fact.getCell(0, 2, 0, "C2"));
series.getDataPoints().addDataPointForLineSeries(fact.getCell(0, 2, 1, 23));
chart.getChartData().getCategories().add(fact.getCell(0, 3, 0, "C3"));
series.getDataPoints().addDataPointForLineSeries(fact.getCell(0, 3, 1, -10));
chart.getChartData().getCategories().add(fact.getCell(0, 4, 0, "C4"));
series.getDataPoints().addDataPointForLineSeries(fact.getCell(0, 4, 1, null));

// Serie 2
chart.getChartData().getSeries().add(fact.getCell(0, 0, 2, "Series 2"));
IChartSeries series2 = chart.getChartData().getSeries().get_Item(1);

// Auffüllen von Seriendaten
series2.getDataPoints().addDataPointForLineSeries(fact.getCell(0, 1, 2, 30));
series2.getDataPoints().addDataPointForLineSeries(fact.getCell(0, 2, 2, 10));
series2.getDataPoints().addDataPointForLineSeries(fact.getCell(0, 3, 2, 60));
series2.getDataPoints().addDataPointForLineSeries(fact.getCell(0, 4, 2, 40));
```

## Schritt 4: Passen Sie das Diagramm an

Sie können das Diagramm weiter anpassen, z. B. eine Legende hinzufügen und sein Erscheinungsbild anpassen.

```java
chart.setLegend(true);
chart.getLegend().setOverlay(false);
```

## Schritt 5: Speichern Sie die Präsentation

Speichern Sie abschließend die Präsentation mit dem Diagramm an Ihrem gewünschten Ort.

```java
pres.save(dataDir + "DefaultMarkersInChart.pptx", SaveFormat.Pptx);
```

Das ist es! Sie haben mit Aspose.Slides für Java ein Liniendiagramm mit Standardmarkierungen erstellt.

## Vollständiger Quellcode für Standardmarkierungen im Diagramm in Java-Folien

```java
        // Der Pfad zum Dokumentenverzeichnis.
        String dataDir = "Your Document Directory";
        Presentation pres = new Presentation();
        try
        {
            ISlide slide = pres.getSlides().get_Item(0);
            IChart chart = slide.getShapes().addChart(ChartType.LineWithMarkers, 10, 10, 400, 400);
            chart.getChartData().getSeries().clear();
            chart.getChartData().getCategories().clear();
            IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
            chart.getChartData().getSeries().add(fact.getCell(0, 0, 1, "Series 1"), chart.getType());
            IChartSeries series = chart.getChartData().getSeries().get_Item(0);
            chart.getChartData().getCategories().add(fact.getCell(0, 1, 0, "C1"));
            series.getDataPoints().addDataPointForLineSeries(fact.getCell(0, 1, 1, 24));
            chart.getChartData().getCategories().add(fact.getCell(0, 2, 0, "C2"));
            series.getDataPoints().addDataPointForLineSeries(fact.getCell(0, 2, 1, 23));
            chart.getChartData().getCategories().add(fact.getCell(0, 3, 0, "C3"));
            series.getDataPoints().addDataPointForLineSeries(fact.getCell(0, 3, 1, -10));
            chart.getChartData().getCategories().add(fact.getCell(0, 4, 0, "C4"));
            series.getDataPoints().addDataPointForLineSeries(fact.getCell(0, 4, 1, null));
            chart.getChartData().getSeries().add(fact.getCell(0, 0, 2, "Series 2"), chart.getType());
            //Nehmen Sie die zweite Chartserie
            IChartSeries series2 = chart.getChartData().getSeries().get_Item(1);
            //Jetzt werden Seriendaten ausgefüllt
            series2.getDataPoints().addDataPointForLineSeries(fact.getCell(0, 1, 2, 30));
            series2.getDataPoints().addDataPointForLineSeries(fact.getCell(0, 2, 2, 10));
            series2.getDataPoints().addDataPointForLineSeries(fact.getCell(0, 3, 2, 60));
            series2.getDataPoints().addDataPointForLineSeries(fact.getCell(0, 4, 2, 40));
            chart.setLegend(true);
            chart.getLegend().setOverlay(false);
            pres.save(dataDir + "DefaultMarkersInChart.pptx", SaveFormat.Pptx);
        }
        finally
        {
            if (pres != null) pres.dispose();
        }
```
## Abschluss

In diesem umfassenden Tutorial haben Sie gelernt, wie Sie mit Aspose.Slides für Java Java-Folien mit Standardmarkierungen in Diagrammen erstellen. Wir haben den gesamten Prozess abgedeckt, vom Einrichten einer Präsentation über die Anpassung des Erscheinungsbilds des Diagramms bis hin zum Speichern des Ergebnisses.

## FAQs

### Wie kann ich die Markierungssymbole ändern?

 Sie können die Markierungssymbole anpassen, indem Sie den Markierungsstil für jeden Datenpunkt festlegen. Verwenden`IDataPoint.setMarkerStyle()` um das Markierungssymbol zu ändern.

### Wie kann ich die Farben des Diagramms anpassen?

 Um die Farben des Diagramms zu ändern, können Sie die verwenden`IChartSeriesFormat` Und`IShapeFillFormat` Schnittstellen zum Festlegen von Füll- und Linieneigenschaften.

### Kann ich den Datenpunkten Beschriftungen hinzufügen?

 Ja, Sie können Datenpunkten mithilfe von Beschriftungen hinzufügen`IDataPoint.getLabel()` Methode und passen Sie sie nach Bedarf an.