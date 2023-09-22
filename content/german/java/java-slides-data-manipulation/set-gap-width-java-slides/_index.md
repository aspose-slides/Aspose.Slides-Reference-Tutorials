---
title: Legen Sie die Lückenbreite in Java-Folien fest
linktitle: Legen Sie die Lückenbreite in Java-Folien fest
second_title: Aspose.Slides Java PowerPoint-Verarbeitungs-API
description: Erfahren Sie, wie Sie mit Aspose.Slides für Java die Lückenbreite in Java-Folien festlegen. Verbessern Sie Diagrammvisualisierungen für Ihre PowerPoint-Präsentationen.
type: docs
weight: 21
url: /de/java/data-manipulation/set-gap-width-java-slides/
---

## Einführung in das Festlegen der Lückenbreite in Aspose.Slides für Java

In diesem Tutorial führen wir Sie durch den Prozess des Festlegens der Lückenbreite für ein Diagramm in einer PowerPoint-Präsentation mit Aspose.Slides für Java. Die Lückenbreite bestimmt den Abstand zwischen den Säulen oder Balken in einem Diagramm und ermöglicht Ihnen so die Steuerung des visuellen Erscheinungsbilds des Diagramms.

## Voraussetzungen

Bevor Sie beginnen, stellen Sie sicher, dass die Aspose.Slides for Java-Bibliothek installiert ist. Sie können es von der Aspose-Website herunterladen[Hier](https://releases.aspose.com/slides/java/).

## Schritt für Schritt Anleitung

Befolgen Sie diese Schritte, um die Lückenbreite in einem Diagramm mit Aspose.Slides für Java festzulegen:

### 1. Erstellen Sie eine leere Präsentation

```java
// Der Pfad zum Dokumentenverzeichnis.
String dataDir = "Your Document Directory";

// Erstellen einer leeren Präsentation
Presentation presentation = new Presentation();
```

### 2. Greifen Sie auf die erste Folie zu

```java
// Greifen Sie auf die erste Folie zu
ISlide slide = presentation.getSlides().get_Item(0);
```

### 3. Fügen Sie ein Diagramm mit Standarddaten hinzu

```java
// Fügen Sie ein Diagramm mit Standarddaten hinzu
IChart chart = slide.getShapes().addChart(ChartType.StackedColumn, 0, 0, 500, 500);
```

### 4. Legen Sie den Index des Diagrammdatenblatts fest

```java
// Festlegen des Index des Diagrammdatenblatts
int defaultWorksheetIndex = 0;
```

### 5. Holen Sie sich die Diagrammdaten-Arbeitsmappe

```java
// Abrufen des Diagrammdaten-Arbeitsblatts
IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
```

### 6. Fügen Sie dem Diagramm Serien hinzu

```java
// Fügen Sie dem Diagramm Reihen hinzu
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 1, "Series 1"), chart.getType());
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 2, "Series 2"), chart.getType());
```

### 7. Fügen Sie dem Diagramm Kategorien hinzu

```java
// Fügen Sie dem Diagramm Kategorien hinzu
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 1, 0, "Category 1"));
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 2, 0, "Category 2"));
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 3, 0, "Category 3"));
```

### 8. Füllen Sie die Seriendaten aus

```java
// Füllen Sie Seriendaten aus
IChartSeries series = chart.getChartData().getSeries().get_Item(1);

// Füllen von Seriendatenpunkten
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 1, 20));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 50));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 30));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 2, 30));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 2, 10));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 2, 60));
```

### 9. Stellen Sie die Spaltbreite ein

```java
// Legen Sie den Wert für die Lückenbreite fest
series.getParentSeriesGroup().setGapWidth(50);
```

### 10. Speichern Sie die Präsentation

```java
// Speichern Sie die Präsentation mit dem Diagramm
presentation.save(dataDir + "GapWidth_out.pptx", SaveFormat.Pptx);
```

## Vollständiger Quellcode zum Festlegen der Lückenbreite in Java-Folien

```java
// Der Pfad zum Dokumentenverzeichnis.
String dataDir = "Your Document Directory";
// Leere Präsentation erstellen
Presentation presentation = new Presentation();
// Greifen Sie auf die erste Folie zu
ISlide slide = presentation.getSlides().get_Item(0);
// Diagramm mit Standarddaten hinzufügen
IChart chart = slide.getShapes().addChart(ChartType.StackedColumn, 0, 0, 500, 500);
// Festlegen des Index des Diagrammdatenblatts
int defaultWorksheetIndex = 0;
// Abrufen des Diagrammdaten-Arbeitsblatts
IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
// Serie hinzufügen
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 1, "Series 1"), chart.getType());
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 2, "Series 2"), chart.getType());
// Kategorien hinzufügen
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 1, 0, "Caetegoty 1"));
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 2, 0, "Caetegoty 2"));
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 3, 0, "Caetegoty 3"));
// Nehmen Sie die zweite Chartserie
IChartSeries series = chart.getChartData().getSeries().get_Item(1);
// Jetzt werden Seriendaten ausgefüllt
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 1, 20));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 50));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 30));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 2, 30));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 2, 10));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 2, 60));
// Legen Sie den GapWidth-Wert fest
series.getParentSeriesGroup().setGapWidth(50);
// Präsentation mit Diagramm speichern
presentation.save(dataDir + "GapWidth_out.pptx", SaveFormat.Pptx);
```

## Abschluss

In diesem Tutorial haben Sie gelernt, wie Sie mit Aspose.Slides für Java die Lückenbreite für ein Diagramm in einer PowerPoint-Präsentation festlegen. Durch Anpassen der Lückenbreite können Sie den Abstand zwischen Spalten oder Balken in Ihrem Diagramm steuern und so die visuelle Darstellung Ihrer Daten verbessern.

## FAQs

### Wie ändere ich den Wert für die Lückenbreite?

 Um die Spaltbreite zu ändern, verwenden Sie die`setGapWidth` Methode auf der`ParentSeriesGroup` der Chartreihe. Im bereitgestellten Beispiel haben wir die Lückenbreite auf 50 eingestellt, Sie können diesen Wert jedoch an Ihren gewünschten Abstand anpassen.

### Kann ich andere Diagrammeigenschaften anpassen?

Ja, Aspose.Slides für Java bietet umfangreiche Möglichkeiten zur Diagrammanpassung. Sie können verschiedene Diagrammeigenschaften ändern, z. B. Farben, Beschriftungen, Titel und mehr. Ausführliche Informationen zu Diagrammanpassungsoptionen finden Sie in der API-Referenz.

### Wo finde ich weitere Ressourcen und Dokumentation?

 Eine umfassende Dokumentation und zusätzliche Ressourcen zu Aspose.Slides für Java finden Sie unter[Aspose-Website](https://reference.aspose.com/slides/java/).