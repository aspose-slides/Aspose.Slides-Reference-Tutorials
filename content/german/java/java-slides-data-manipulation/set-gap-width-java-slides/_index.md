---
title: Lückenbreite in Java-Folien festlegen
linktitle: Lückenbreite in Java-Folien festlegen
second_title: Aspose.Slides Java PowerPoint-Verarbeitungs-API
description: Erfahren Sie, wie Sie mit Aspose.Slides für Java die Lückenbreite in Java-Folien festlegen. Verbessern Sie die Diagrammdarstellung Ihrer PowerPoint-Präsentationen.
type: docs
weight: 21
url: /de/java/data-manipulation/set-gap-width-java-slides/
---

## Einführung in das Einstellen der Lückenbreite in Aspose.Slides für Java

In diesem Tutorial führen wir Sie durch den Prozess zum Festlegen der Lückenbreite für ein Diagramm in einer PowerPoint-Präsentation mit Aspose.Slides für Java. Die Lückenbreite bestimmt den Abstand zwischen den Spalten oder Balken in einem Diagramm und ermöglicht Ihnen, das visuelle Erscheinungsbild des Diagramms zu steuern.

## Voraussetzungen

 Bevor Sie beginnen, stellen Sie sicher, dass Sie die Aspose.Slides für Java-Bibliothek installiert haben. Sie können sie von der Aspose-Website herunterladen.[Hier](https://releases.aspose.com/slides/java/).

## Schritt für Schritt Anleitung

Befolgen Sie diese Schritte, um die Lückenbreite in einem Diagramm mit Aspose.Slides für Java festzulegen:

### 1. Erstellen Sie eine leere Präsentation

```java
// Der Pfad zum Dokumentverzeichnis.
String dataDir = "Your Document Directory";

// Erstellen einer leeren Präsentation
Presentation presentation = new Presentation();
```

### 2. Zugriff auf die erste Folie

```java
// Greifen Sie auf die erste Folie zu
ISlide slide = presentation.getSlides().get_Item(0);
```

### 3. Fügen Sie ein Diagramm mit Standarddaten hinzu

```java
// Hinzufügen eines Diagramms mit Standarddaten
IChart chart = slide.getShapes().addChart(ChartType.StackedColumn, 0, 0, 500, 500);
```

### 4. Legen Sie den Index des Diagrammdatenblatts fest

```java
// Festlegen des Indexes des Diagrammdatenblattes
int defaultWorksheetIndex = 0;
```

### 5. Holen Sie sich die Arbeitsmappe mit Diagrammdaten

```java
// Abrufen des Arbeitsblatts mit den Diagrammdaten
IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
```

### 6. Serien zum Diagramm hinzufügen

```java
// Hinzufügen von Reihen zum Diagramm
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 1, "Series 1"), chart.getType());
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 2, "Series 2"), chart.getType());
```

### 7. Kategorien zum Diagramm hinzufügen

```java
// Hinzufügen von Kategorien zum Diagramm
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 1, 0, "Category 1"));
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 2, 0, "Category 2"));
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 3, 0, "Category 3"));
```

### 8. Seriendaten auffüllen

```java
// Auffüllen von Reihendaten
IChartSeries series = chart.getChartData().getSeries().get_Item(1);

// Datenpunkte einer Reihe auffüllen
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
// Der Pfad zum Dokumentverzeichnis.
String dataDir = "Your Document Directory";
// Leere Präsentation erstellen
Presentation presentation = new Presentation();
// Zur ersten Folie
ISlide slide = presentation.getSlides().get_Item(0);
// Diagramm mit Standarddaten hinzufügen
IChart chart = slide.getShapes().addChart(ChartType.StackedColumn, 0, 0, 500, 500);
// Festlegen des Indexes des Diagrammdatenblattes
int defaultWorksheetIndex = 0;
// Abrufen des Arbeitsblatts mit den Diagrammdaten
IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
// Serie hinzufügen
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 1, "Series 1"), chart.getType());
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 2, "Series 2"), chart.getType());
// Kategorien hinzufügen
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 1, 0, "Caetegoty 1"));
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 2, 0, "Caetegoty 2"));
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 3, 0, "Caetegoty 3"));
// Nehmen Sie die zweite Diagrammreihe
IChartSeries series = chart.getChartData().getSeries().get_Item(1);
//Jetzt werden Seriendaten gefüllt
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

In diesem Tutorial haben Sie gelernt, wie Sie die Lückenbreite für ein Diagramm in einer PowerPoint-Präsentation mit Aspose.Slides für Java festlegen. Durch Anpassen der Lückenbreite können Sie den Abstand zwischen Spalten oder Balken in Ihrem Diagramm steuern und so die visuelle Darstellung Ihrer Daten verbessern.

## Häufig gestellte Fragen

### Wie ändere ich den Wert für die Lückenbreite?

 Um die Lückenbreite zu ändern, verwenden Sie die`setGapWidth` Methode auf der`ParentSeriesGroup`der Diagrammreihe. Im angegebenen Beispiel haben wir die Lückenbreite auf 50 gesetzt, aber Sie können diesen Wert an den gewünschten Abstand anpassen.

### Kann ich andere Diagrammeigenschaften anpassen?

Ja, Aspose.Slides für Java bietet umfangreiche Möglichkeiten zur Diagrammanpassung. Sie können verschiedene Diagrammeigenschaften wie Farben, Beschriftungen, Titel und mehr ändern. Ausführliche Informationen zu den Optionen zur Diagrammanpassung finden Sie in der API-Referenz.

### Wo finde ich weitere Ressourcen und Dokumentation?

 Eine umfassende Dokumentation und weitere Ressourcen zu Aspose.Slides für Java finden Sie auf der[Aspose-Website](https://reference.aspose.com/slides/java/).