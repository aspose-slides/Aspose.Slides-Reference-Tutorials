---
title: Diagramm mit mehreren Kategorien in Java-Folien
linktitle: Diagramm mit mehreren Kategorien in Java-Folien
second_title: Aspose.Slides Java PowerPoint-Verarbeitungs-API
description: Erstellen Sie Diagramme mit mehreren Kategorien in Java-Folien mit Aspose.Slides für Java. Schritt-für-Schritt-Anleitung mit Quellcode für eindrucksvolle Datenvisualisierung in Präsentationen.
type: docs
weight: 20
url: /de/java/chart-data-manipulation/multi-category-chart-java-slides/
---

## Einführung in Multi-Kategorie-Diagramme in Java Slides mit Aspose.Slides

In diesem Tutorial erfahren Sie, wie Sie mithilfe der Aspose.Slides für Java-API ein Diagramm mit mehreren Kategorien in Java-Folien erstellen. Dieses Handbuch enthält Schritt-für-Schritt-Anleitungen sowie Quellcode, die Ihnen beim Erstellen eines gruppierten Säulendiagramms mit mehreren Kategorien und Reihen helfen.

## Voraussetzungen
Bevor wir beginnen, stellen Sie sicher, dass die Aspose.Slides for Java-Bibliothek in Ihrer Java-Entwicklungsumgebung installiert und eingerichtet ist.

## Schritt 1: Einrichten der Umgebung
Importieren Sie zunächst die erforderlichen Klassen und erstellen Sie ein neues Präsentationsobjekt für die Arbeit mit Folien.

```java
// Der Pfad zum Dokumentenverzeichnis.
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
```

## Schritt 2: Folie und Diagramm hinzufügen
Erstellen Sie als Nächstes eine Folie und fügen Sie ein gruppiertes Säulendiagramm hinzu.

```java
ISlide slide = pres.getSlides().get_Item(0);
IChart ch = slide.getShapes().addChart(ChartType.ClusteredColumn, 100, 100, 600, 450);
```

## Schritt 3: Vorhandene Daten löschen
Löschen Sie alle vorhandenen Daten aus dem Diagramm.

```java
ch.getChartData().getSeries().clear();
ch.getChartData().getCategories().clear();
```

## Schritt 4: Datenkategorien einrichten
Nun richten wir Datenkategorien für das Diagramm ein. Wir werden mehrere Kategorien erstellen und sie gruppieren.

```java
IChartDataWorkbook fact = ch.getChartData().getChartDataWorkbook();
fact.clear(0);

int defaultWorksheetIndex = 0;

// Fügen Sie Kategorien hinzu und gruppieren Sie sie
IChartCategory category = ch.getChartData().getCategories().add(fact.getCell(0, "c2", "A"));
category.getGroupingLevels().setGroupingItem(1, "Group1");

category = ch.getChartData().getCategories().add(fact.getCell(0, "c3", "B"));

category = ch.getChartData().getCategories().add(fact.getCell(0, "c4", "C"));
category.getGroupingLevels().setGroupingItem(1, "Group2");

category = ch.getChartData().getCategories().add(fact.getCell(0, "c5", "D"));

category = ch.getChartData().getCategories().add(fact.getCell(0, "c6", "E"));
category.getGroupingLevels().setGroupingItem(1, "Group3");

category = ch.getChartData().getCategories().add(fact.getCell(0, "c7", "F"));

category = ch.getChartData().getCategories().add(fact.getCell(0, "c8", "G"));
category.getGroupingLevels().setGroupingItem(1, "Group4");

category = ch.getChartData().getCategories().add(fact.getCell(0, "c9", "H"));
```

## Schritt 5: Serie hinzufügen
Fügen wir nun dem Diagramm eine Reihe zusammen mit Datenpunkten hinzu.

```java
IChartSeries series = ch.getChartData().getSeries().add(fact.getCell(0, "D1", "Series 1"), ChartType.ClusteredColumn);

series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, "D2", 10));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, "D3", 20));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, "D4", 30));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, "D5", 40));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, "D6", 50));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, "D7", 60));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, "D8", 70));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, "D9", 80));
```

## Schritt 6: Speichern der Präsentation
Speichern Sie abschließend die Präsentation mit dem Diagramm.

```java
pres.save(dataDir + "AsposeChart_out.pptx", SaveFormat.Pptx);
```

Das ist es! Sie haben mit Aspose.Slides erfolgreich ein Diagramm mit mehreren Kategorien in einer Java-Folie erstellt. Sie können dieses Diagramm weiter an Ihre spezifischen Anforderungen anpassen.

## Vollständiger Quellcode für Diagramme mit mehreren Kategorien in Java-Folien

```java
// Der Pfad zum Dokumentenverzeichnis.
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
ISlide slide = pres.getSlides().get_Item(0);
IChart ch = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 100, 100, 600, 450);
ch.getChartData().getSeries().clear();
ch.getChartData().getCategories().clear();
IChartDataWorkbook fact = ch.getChartData().getChartDataWorkbook();
fact.clear(0);
int defaultWorksheetIndex = 0;
IChartCategory category = ch.getChartData().getCategories().add(fact.getCell(0, "c2", "A"));
category.getGroupingLevels().setGroupingItem(1, "Group1");
category = ch.getChartData().getCategories().add(fact.getCell(0, "c3", "B"));
category = ch.getChartData().getCategories().add(fact.getCell(0, "c4", "C"));
category.getGroupingLevels().setGroupingItem(1, "Group2");
category = ch.getChartData().getCategories().add(fact.getCell(0, "c5", "D"));
category = ch.getChartData().getCategories().add(fact.getCell(0, "c6", "E"));
category.getGroupingLevels().setGroupingItem(1, "Group3");
category = ch.getChartData().getCategories().add(fact.getCell(0, "c7", "F"));
category = ch.getChartData().getCategories().add(fact.getCell(0, "c8", "G"));
category.getGroupingLevels().setGroupingItem(1, "Group4");
category = ch.getChartData().getCategories().add(fact.getCell(0, "c9", "H"));
// Serien hinzufügen
IChartSeries series = ch.getChartData().getSeries().add(fact.getCell(0, "D1", "Series 1"),
		ChartType.ClusteredColumn);
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, "D2", 10));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, "D3", 20));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, "D4", 30));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, "D5", 40));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, "D6", 50));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, "D7", 60));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, "D8", 70));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, "D9", 80));
// Präsentation mit Diagramm speichern
pres.save(dataDir + "AsposeChart_out.pptx", SaveFormat.Pptx);
```

## Abschluss

In diesem Tutorial haben wir gelernt, wie man mithilfe der Aspose.Slides für Java-API ein Diagramm mit mehreren Kategorien in Java-Folien erstellt. Wir haben eine Schritt-für-Schritt-Anleitung mit Quellcode durchgearbeitet, um ein gruppiertes Säulendiagramm mit mehreren Kategorien und Reihen zu erstellen.

## FAQs

### Wie kann ich das Erscheinungsbild des Diagramms anpassen?

Sie können das Erscheinungsbild des Diagramms anpassen, indem Sie Eigenschaften wie Farben, Schriftarten und Stile ändern. Ausführliche Anpassungsoptionen finden Sie in der Aspose.Slides-Dokumentation.

### Kann ich dem Diagramm weitere Serien hinzufügen?

Ja, Sie können dem Diagramm weitere Reihen hinzufügen, indem Sie einem ähnlichen Vorgang wie in Schritt 5 folgen.

### Wie ändere ich den Diagrammtyp?

 Um den Diagrammtyp zu ändern, ersetzen Sie ihn`ChartType.ClusteredColumn` Geben Sie beim Hinzufügen des Diagramms in Schritt 2 den gewünschten Diagrammtyp ein.

### Wie kann ich dem Diagramm einen Titel hinzufügen?

 Sie können dem Diagramm einen Titel hinzufügen, indem Sie verwenden`ch.getChartTitle().getTextFrame().setText("Chart Title");` Methode.