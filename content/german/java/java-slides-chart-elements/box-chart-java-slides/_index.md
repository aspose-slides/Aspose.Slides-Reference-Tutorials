---
title: Boxdiagramm in Java-Folien
linktitle: Boxdiagramm in Java-Folien
second_title: Aspose.Slides Java PowerPoint-Verarbeitungs-API
description: Erfahren Sie, wie Sie mit Aspose.Slides Boxdiagramme in Java-Präsentationen erstellen. Schritt-für-Schritt-Anleitung und Quellcode für eine effektive Datenvisualisierung enthalten.
type: docs
weight: 10
url: /de/java/chart-elements/box-chart-java-slides/
---

## Einführung in das Boxdiagramm in Aspose.Slides für Java

In diesem Tutorial führen wir Sie durch den Prozess der Erstellung eines Boxdiagramms mit Aspose.Slides für Java. Boxdiagramme eignen sich zur Visualisierung statistischer Daten mit verschiedenen Quartilen und Ausreißern. Wir stellen Ihnen Schritt-für-Schritt-Anleitungen zusammen mit dem Quellcode zur Verfügung, um Ihnen den Einstieg zu erleichtern.

## Voraussetzungen

Bevor Sie beginnen, stellen Sie sicher, dass Sie über Folgendes verfügen:

- Aspose.Slides für Java-Bibliothek installiert und konfiguriert.
- Einrichtung einer Java-Entwicklungsumgebung.

## Schritt 1: Initialisieren Sie die Präsentation

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "test.pptx");
```

In diesem Schritt initialisieren wir ein Präsentationsobjekt mithilfe des Pfads zu einer vorhandenen PowerPoint-Datei („test.pptx“ in diesem Beispiel).

## Schritt 2: Erstellen Sie das Boxdiagramm

```java
try {
    IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.BoxAndWhisker, 50, 50, 500, 400);
    chart.getChartData().getCategories().clear();
    chart.getChartData().getSeries().clear();
```

In diesem Schritt erstellen wir eine Box-Chart-Form auf der ersten Folie der Präsentation. Wir löschen auch alle vorhandenen Kategorien und Serien aus dem Diagramm.

## Schritt 3: Kategorien definieren

```java
    IChartDataWorkbook wb = chart.getChartData().getChartDataWorkbook();
    wb.clear(0);
    chart.getChartData().getCategories().add(wb.getCell(0, "A1", "Category 1"));
    chart.getChartData().getCategories().add(wb.getCell(0, "A2", "Category 1"));
    chart.getChartData().getCategories().add(wb.getCell(0, "A3", "Category 1"));
    chart.getChartData().getCategories().add(wb.getCell(0, "A4", "Category 1"));
    chart.getChartData().getCategories().add(wb.getCell(0, "A5", "Category 1"));
    chart.getChartData().getCategories().add(wb.getCell(0, "A6", "Category 1"));
```

 In diesem Schritt definieren wir die Kategorien für das Box-Diagramm. Wir benutzen das`IChartDataWorkbook`um Kategorien hinzuzufügen und sie entsprechend zu beschriften.

## Schritt 4: Erstellen Sie die Serie

```java
    IChartSeries series = chart.getChartData().getSeries().add(ChartType.BoxAndWhisker);
    series.setQuartileMethod(QuartileMethodType.Exclusive);
    series.setShowMeanLine(true);
    series.setShowMeanMarkers(true);
    series.setShowInnerPoints(true);
    series.setShowOutlierPoints(true);
```

Hier erstellen wir eine BoxAndWhisker-Reihe für das Diagramm und konfigurieren verschiedene Optionen wie Quartilmethode, Mittellinie, Mittelwertmarkierungen, innere Punkte und Ausreißerpunkte.

## Schritt 5: Datenpunkte hinzufügen

```java
    series.getDataPoints().addDataPointForBoxAndWhiskerSeries(wb.getCell(0, "B1", 15));
    series.getDataPoints().addDataPointForBoxAndWhiskerSeries(wb.getCell(0, "B2", 41));
    series.getDataPoints().addDataPointForBoxAndWhiskerSeries(wb.getCell(0, "B3", 16));
    series.getDataPoints().addDataPointForBoxAndWhiskerSeries(wb.getCell(0, "B4", 10));
    series.getDataPoints().addDataPointForBoxAndWhiskerSeries(wb.getCell(0, "B5", 23));
    series.getDataPoints().addDataPointForBoxAndWhiskerSeries(wb.getCell(0, "B6", 16));
```

In diesem Schritt fügen wir Datenpunkte zur BoxAndWhisker-Reihe hinzu. Diese Datenpunkte stellen die statistischen Daten für das Diagramm dar.

## Schritt 6: Speichern Sie die Präsentation

```java
    pres.save("BoxAndWhisker.pptx", SaveFormat.Pptx);
} finally {
    if (pres != null) pres.dispose();
}
```

Abschließend speichern wir die Präsentation mit dem Box-Diagramm in einer neuen PowerPoint-Datei mit dem Namen „BoxAndWhisker.pptx“.

Glückwunsch! Sie haben mit Aspose.Slides für Java erfolgreich ein Boxdiagramm erstellt. Sie können das Diagramm weiter anpassen, indem Sie verschiedene Eigenschaften anpassen und bei Bedarf weitere Datenpunkte hinzufügen.

## Vollständiger Quellcode für Box-Diagramm in Java-Folien

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "test.pptx");
try
{
	IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.BoxAndWhisker, 50, 50, 500, 400);
	chart.getChartData().getCategories().clear();
	chart.getChartData().getSeries().clear();
	IChartDataWorkbook wb = chart.getChartData().getChartDataWorkbook();
	wb.clear(0);
	chart.getChartData().getCategories().add(wb.getCell(0, "A1", "Category 1"));
	chart.getChartData().getCategories().add(wb.getCell(0, "A2", "Category 1"));
	chart.getChartData().getCategories().add(wb.getCell(0, "A3", "Category 1"));
	chart.getChartData().getCategories().add(wb.getCell(0, "A4", "Category 1"));
	chart.getChartData().getCategories().add(wb.getCell(0, "A5", "Category 1"));
	chart.getChartData().getCategories().add(wb.getCell(0, "A6", "Category 1"));
	IChartSeries series = chart.getChartData().getSeries().add(ChartType.BoxAndWhisker);
	series.setQuartileMethod(QuartileMethodType.Exclusive);
	series.setShowMeanLine(true);
	series.setShowMeanMarkers(true);
	series.setShowInnerPoints(true);
	series.setShowOutlierPoints(true);
	series.getDataPoints().addDataPointForBoxAndWhiskerSeries(wb.getCell(0, "B1", 15));
	series.getDataPoints().addDataPointForBoxAndWhiskerSeries(wb.getCell(0, "B2", 41));
	series.getDataPoints().addDataPointForBoxAndWhiskerSeries(wb.getCell(0, "B3", 16));
	series.getDataPoints().addDataPointForBoxAndWhiskerSeries(wb.getCell(0, "B4", 10));
	series.getDataPoints().addDataPointForBoxAndWhiskerSeries(wb.getCell(0, "B5", 23));
	series.getDataPoints().addDataPointForBoxAndWhiskerSeries(wb.getCell(0, "B6", 16));
	pres.save("BoxAndWhisker.pptx", SaveFormat.Pptx);
}
finally
{
	if (pres != null) pres.dispose();
}
```

## Abschluss

In diesem Tutorial haben wir gelernt, wie man mit Aspose.Slides für Java ein Boxdiagramm erstellt. Boxdiagramme sind wertvolle Werkzeuge zur Visualisierung statistischer Daten, einschließlich Quartilen und Ausreißern. Wir haben eine Schritt-für-Schritt-Anleitung zusammen mit dem Quellcode bereitgestellt, um Ihnen den Einstieg in die Erstellung von Boxdiagrammen in Ihren Java-Anwendungen zu erleichtern.

## FAQs

### Wie kann ich das Erscheinungsbild des Boxdiagramms ändern?

Sie können das Erscheinungsbild des Boxdiagramms anpassen, indem Sie Eigenschaften wie Linienstile, Farben und Schriftarten ändern. Einzelheiten zur Diagrammanpassung finden Sie in der Dokumentation zu Aspose.Slides für Java.

### Kann ich dem Boxdiagramm zusätzliche Datenreihen hinzufügen?

 Ja, Sie können dem Boxdiagramm mehrere Datenreihen hinzufügen, indem Sie zusätzliche erstellen`IChartSeries` Objekte und das Hinzufügen von Datenpunkten zu ihnen.

### Was bedeutet QuartileMethodType.Exclusive?

 Der`QuartileMethodType.Exclusive` Die Einstellung gibt an, dass die Quartilberechnungen mit der exklusiven Methode durchgeführt werden sollen. Abhängig von Ihren Daten und Anforderungen können Sie verschiedene Quartilberechnungsmethoden wählen.