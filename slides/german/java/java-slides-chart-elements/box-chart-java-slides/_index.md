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

In diesem Tutorial führen wir Sie durch den Prozess der Erstellung eines Boxdiagramms mit Aspose.Slides für Java. Boxdiagramme sind nützlich, um statistische Daten mit verschiedenen Quartilen und Ausreißern zu visualisieren. Wir stellen Ihnen Schritt-für-Schritt-Anleitungen sowie Quellcode zur Verfügung, um Ihnen den Einstieg zu erleichtern.

## Voraussetzungen

Bevor Sie beginnen, stellen Sie sicher, dass Sie über Folgendes verfügen:

- Aspose.Slides für die Java-Bibliothek installiert und konfiguriert.
- Eine Java-Entwicklungsumgebung wurde eingerichtet.

## Schritt 1: Initialisieren der Präsentation

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "test.pptx");
```

In diesem Schritt initialisieren wir ein Präsentationsobjekt mit dem Pfad zu einer vorhandenen PowerPoint-Datei (in diesem Beispiel „test.pptx“).

## Schritt 2: Erstellen Sie das Boxdiagramm

```java
try {
    IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.BoxAndWhisker, 50, 50, 500, 400);
    chart.getChartData().getCategories().clear();
    chart.getChartData().getSeries().clear();
```

In diesem Schritt erstellen wir auf der ersten Folie der Präsentation eine Boxdiagrammform. Wir löschen außerdem alle vorhandenen Kategorien und Reihen aus dem Diagramm.

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

 In diesem Schritt definieren wir die Kategorien für das Boxdiagramm. Wir verwenden die`IChartDataWorkbook` um Kategorien hinzuzufügen und sie entsprechend zu beschriften.

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

In diesem Schritt fügen wir der BoxAndWhisker-Reihe Datenpunkte hinzu. Diese Datenpunkte stellen die statistischen Daten für das Diagramm dar.

## Schritt 6: Speichern Sie die Präsentation

```java
    pres.save("BoxAndWhisker.pptx", SaveFormat.Pptx);
} finally {
    if (pres != null) pres.dispose();
}
```

Abschließend speichern wir die Präsentation mit dem Boxdiagramm in einer neuen PowerPoint-Datei mit dem Namen „BoxAndWhisker.pptx“.

Herzlichen Glückwunsch! Sie haben erfolgreich ein Boxdiagramm mit Aspose.Slides für Java erstellt. Sie können das Diagramm weiter anpassen, indem Sie verschiedene Eigenschaften anpassen und bei Bedarf weitere Datenpunkte hinzufügen.

## Vollständiger Quellcode für Boxdiagramm in Java-Folien

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

In diesem Tutorial haben wir gelernt, wie man mit Aspose.Slides für Java ein Boxdiagramm erstellt. Boxdiagramme sind wertvolle Tools zur Visualisierung statistischer Daten, einschließlich Quartilen und Ausreißern. Wir haben eine Schritt-für-Schritt-Anleitung zusammen mit Quellcode bereitgestellt, um Ihnen den Einstieg in die Erstellung von Boxdiagrammen in Ihren Java-Anwendungen zu erleichtern.

## Häufig gestellte Fragen

### Wie kann ich das Erscheinungsbild des Boxdiagramms ändern?

Sie können das Erscheinungsbild des Boxdiagramms anpassen, indem Sie Eigenschaften wie Linienstile, Farben und Schriftarten ändern. Weitere Informationen zur Diagrammanpassung finden Sie in der Dokumentation zu Aspose.Slides für Java.

### Kann ich dem Boxdiagramm zusätzliche Datenreihen hinzufügen?

 Ja, Sie können dem Boxdiagramm mehrere Datenreihen hinzufügen, indem Sie zusätzliche`IChartSeries` Objekte und Hinzufügen von Datenpunkten zu ihnen.

### Was bedeutet QuartileMethodType.Exclusive?

 Der`QuartileMethodType.Exclusive` Die Einstellung gibt an, dass die Quartilberechnungen mit der exklusiven Methode durchgeführt werden sollen. Sie können je nach Ihren Daten und Anforderungen unterschiedliche Quartilberechnungsmethoden wählen.