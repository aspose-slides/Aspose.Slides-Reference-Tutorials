---
title: Standardmarkierungen im Diagramm in Java-Folien
linktitle: Standardmarkierungen im Diagramm in Java-Folien
second_title: Aspose.Slides Java PowerPoint-Verarbeitungs-API
description: Erfahren Sie, wie Sie mit Aspose.Slides für Java Java-Folien mit Standardmarkierungen in Diagrammen erstellen. Schritt-für-Schritt-Anleitung mit Quellcode.
weight: 16
url: /de/java/chart-data-manipulation/default-markers-in-chart-java-slides/
---

{< blocks/products/pf/main-wrap-class >}
{< blocks/products/pf/main-container >}
{< blocks/products/pf/tutorial-page-section >}


## Einführung in Standardmarkierungen im Diagramm in Java-Folien

In diesem Tutorial erfahren Sie, wie Sie mit Aspose.Slides für Java ein Diagramm mit Standardmarkierungen erstellen. Standardmarkierungen sind Symbole oder Formen, die Datenpunkten in einem Diagramm hinzugefügt werden, um sie hervorzuheben. Wir erstellen ein Liniendiagramm mit Markierungen zur Visualisierung von Daten.

## Voraussetzungen

Stellen Sie vor dem Beginn sicher, dass Sie die Bibliothek Aspose.Slides für Java in Ihrem Java-Projekt installiert und eingerichtet haben.

## Schritt 1: Erstellen Sie eine Präsentation

Lassen Sie uns zunächst eine Präsentation erstellen und ihr eine Folie hinzufügen. Anschließend fügen wir der Folie ein Diagramm hinzu.

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
ISlide slide = pres.getSlides().get_Item(0);
```

## Schritt 2: Fügen Sie ein Liniendiagramm mit Markierungen hinzu

Fügen wir der Folie nun ein Liniendiagramm mit Markierungen hinzu. Wir löschen außerdem alle Standarddaten aus dem Diagramm.

```java
IChart chart = slide.getShapes().addChart(ChartType.LineWithMarkers, 10, 10, 400, 400);
chart.getChartData().getSeries().clear();
chart.getChartData().getCategories().clear();
```

## Schritt 3: Diagrammdaten auffüllen

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

## Schritt 4: Das Diagramm anpassen

Sie können das Diagramm weiter anpassen, beispielsweise eine Legende hinzufügen und sein Erscheinungsbild anpassen.

```java
chart.setLegend(true);
chart.getLegend().setOverlay(false);
```

## Schritt 5: Speichern Sie die Präsentation

Speichern Sie abschließend die Präsentation mit dem Diagramm am gewünschten Speicherort.

```java
pres.save(dataDir + "DefaultMarkersInChart.pptx", SaveFormat.Pptx);
```

Das ist es! Sie haben mit Aspose.Slides für Java ein Liniendiagramm mit Standardmarkierungen erstellt.

## Vollständiger Quellcode für Standardmarkierungen im Diagramm in Java-Folien

```java
        // Der Pfad zum Dokumentverzeichnis.
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
            //Nehmen Sie die zweite Diagrammreihe
            IChartSeries series2 = chart.getChartData().getSeries().get_Item(1);
            //Jetzt werden Seriendaten gefüllt
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

In diesem umfassenden Tutorial haben Sie gelernt, wie Sie mit Aspose.Slides für Java Java-Folien mit Standardmarkierungen in Diagrammen erstellen. Wir haben den gesamten Prozess abgedeckt, vom Einrichten einer Präsentation über das Anpassen des Erscheinungsbilds des Diagramms bis hin zum Speichern des Ergebnisses.

## Häufig gestellte Fragen

### Wie kann ich die Markierungssymbole ändern?

Sie können die Markierungssymbole anpassen, indem Sie den Markierungsstil für jeden Datenpunkt festlegen. Verwenden Sie`IDataPoint.setMarkerStyle()` , um das Markierungssymbol zu ändern.

### Wie passe ich die Farben des Diagramms an?

 Um die Farben des Diagramms zu ändern, können Sie die`IChartSeriesFormat` Und`IShapeFillFormat` Schnittstellen zum Festlegen von Füll- und Linieneigenschaften.

### Kann ich den Datenpunkten Beschriftungen hinzufügen?

 Ja, Sie können Datenpunkten Beschriftungen hinzufügen mit dem`IDataPoint.getLabel()` Methode und passen Sie sie nach Bedarf an.
{< /blocks/products/pf/tutorial-page-section >}

{< /blocks/products/pf/main-container >}
{< /blocks/products/pf/main-wrap-class >}

{< blocks/products/products-backtop-button >}
