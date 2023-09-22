---
title: Sunburst-Diagramm in Java-Folien
linktitle: Sunburst-Diagramm in Java-Folien
second_title: Aspose.Slides Java PowerPoint-Verarbeitungs-API
description: Erstellen Sie mit Aspose.Slides atemberaubende Sunburst-Diagramme in Java-Folien. Erfahren Sie Schritt für Schritt, wie Sie Diagramme erstellen und Daten bearbeiten.
type: docs
weight: 16
url: /de/java/chart-elements/sunburst-chart-java-slides/
---

## Einführung in Sunburst-Diagramme in Java Slides mit Aspose.Slides

In diesem Tutorial erfahren Sie, wie Sie mithilfe der Aspose.Slides für Java-API ein Sunburst-Diagramm in einer PowerPoint-Präsentation erstellen. Ein Sunburst-Diagramm ist ein radiales Diagramm, das zur Darstellung hierarchischer Daten verwendet wird. Wir stellen Schritt-für-Schritt-Anleitungen zusammen mit dem Quellcode zur Verfügung.

## Voraussetzungen

Bevor Sie beginnen, stellen Sie sicher, dass die Aspose.Slides for Java-Bibliothek in Ihrem Java-Projekt installiert und konfiguriert ist. Sie können die Bibliothek herunterladen unter[Hier](https://releases.aspose.com/slides/java/).

## Schritt 1: Erforderliche Bibliotheken importieren

Importieren Sie zunächst die für die Arbeit mit Aspose.Slides erforderlichen Bibliotheken und erstellen Sie ein Sunburst-Diagramm in Ihrer Java-Anwendung.

```java
import com.aspose.slides.*;
```

## Schritt 2: Initialisieren Sie die Präsentation

Initialisieren Sie eine PowerPoint-Präsentation und geben Sie das Verzeichnis an, in dem Ihre Präsentationsdatei gespeichert werden soll.

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "test.pptx");
```

## Schritt 3: Erstellen Sie das Sunburst-Diagramm

Erstellen Sie ein Sunburst-Diagramm auf einer Folie. Wir geben die Position (X, Y) und die Abmessungen (Breite, Höhe) des Diagramms an.

```java
IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.Sunburst, 50, 50, 500, 400);
```

## Schritt 4: Diagrammdaten vorbereiten

Löschen Sie alle vorhandenen Kategorien und Reihendaten aus dem Diagramm und erstellen Sie eine Datenarbeitsmappe für das Diagramm.

```java
chart.getChartData().getCategories().clear();
chart.getChartData().getSeries().clear();
IChartDataWorkbook wb = chart.getChartData().getChartDataWorkbook();
wb.clear(0);
```

## Schritt 5: Definieren Sie die Diagrammhierarchie

Definieren Sie die hierarchische Struktur des Sunburst-Diagramms. Sie können Zweige, Stängel und Blätter als Kategorien hinzufügen.

```java
// Zweig 1
IChartCategory leaf = chart.getChartData().getCategories().add(wb.getCell(0, "C1", "Leaf1"));
leaf.getGroupingLevels().setGroupingItem(1, "Stem1");
leaf.getGroupingLevels().setGroupingItem(2, "Branch1");
chart.getChartData().getCategories().add(wb.getCell(0, "C2", "Leaf2"));
leaf = chart.getChartData().getCategories().add(wb.getCell(0, "C3", "Leaf3"));
leaf.getGroupingLevels().setGroupingItem(1, "Stem2");
chart.getChartData().getCategories().add(wb.getCell(0, "C4", "Leaf4"));

// Zweig 2
leaf = chart.getChartData().getCategories().add(wb.getCell(0, "C5", "Leaf5"));
leaf.getGroupingLevels().setGroupingItem(1, "Stem3");
leaf.getGroupingLevels().setGroupingItem(2, "Branch2");
chart.getChartData().getCategories().add(wb.getCell(0, "C6", "Leaf6"));
leaf = chart.getChartData().getCategories().add(wb.getCell(0, "C7", "Leaf7"));
leaf.getGroupingLevels().setGroupingItem(1, "Stem4");
chart.getChartData().getCategories().add(wb.getCell(0, "C8", "Leaf8"));
```

## Schritt 6: Daten zum Diagramm hinzufügen

Fügen Sie Datenpunkte zur Sunburst-Diagrammserie hinzu.

```java
IChartSeries series = chart.getChartData().getSeries().add(ChartType.Sunburst);
series.getLabels().getDefaultDataLabelFormat().setShowCategoryName(true);
series.getDataPoints().addDataPointForSunburstSeries(wb.getCell(0, "D1", 4));
series.getDataPoints().addDataPointForSunburstSeries(wb.getCell(0, "D2", 5));
series.getDataPoints().addDataPointForSunburstSeries(wb.getCell(0, "D3", 3));
series.getDataPoints().addDataPointForSunburstSeries(wb.getCell(0, "D4", 6));
series.getDataPoints().addDataPointForSunburstSeries(wb.getCell(0, "D5", 9));
series.getDataPoints().addDataPointForSunburstSeries(wb.getCell(0, "D6", 9));
series.getDataPoints().addDataPointForSunburstSeries(wb.getCell(0, "D7", 4));
series.getDataPoints().addDataPointForSunburstSeries(wb.getCell(0, "D8", 3));
```

## Schritt 7: Speichern Sie die Präsentation

Speichern Sie abschließend die Präsentation mit dem Sunburst-Diagramm.

```java
pres.save("Sunburst.pptx", SaveFormat.Pptx);
```

## Vollständiger Quellcode für Sunburst-Diagramm in Java-Folien

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "test.pptx");
try
{
	IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.Sunburst, 50, 50, 500, 400);
	chart.getChartData().getCategories().clear();
	chart.getChartData().getSeries().clear();
	IChartDataWorkbook wb = chart.getChartData().getChartDataWorkbook();
	wb.clear(0);
	//Zweig 1
	IChartCategory leaf = chart.getChartData().getCategories().add(wb.getCell(0, "C1", "Leaf1"));
	leaf.getGroupingLevels().setGroupingItem(1, "Stem1");
	leaf.getGroupingLevels().setGroupingItem(2, "Branch1");
	chart.getChartData().getCategories().add(wb.getCell(0, "C2", "Leaf2"));
	leaf = chart.getChartData().getCategories().add(wb.getCell(0, "C3", "Leaf3"));
	leaf.getGroupingLevels().setGroupingItem(1, "Stem2");
	chart.getChartData().getCategories().add(wb.getCell(0, "C4", "Leaf4"));
	//Zweig 2
	leaf = chart.getChartData().getCategories().add(wb.getCell(0, "C5", "Leaf5"));
	leaf.getGroupingLevels().setGroupingItem(1, "Stem3");
	leaf.getGroupingLevels().setGroupingItem(2, "Branch2");
	chart.getChartData().getCategories().add(wb.getCell(0, "C6", "Leaf6"));
	leaf = chart.getChartData().getCategories().add(wb.getCell(0, "C7", "Leaf7"));
	leaf.getGroupingLevels().setGroupingItem(1, "Stem4");
	chart.getChartData().getCategories().add(wb.getCell(0, "C8", "Leaf8"));
	IChartSeries series = chart.getChartData().getSeries().add(ChartType.Sunburst);
	series.getLabels().getDefaultDataLabelFormat().setShowCategoryName(true);
	series.getDataPoints().addDataPointForSunburstSeries(wb.getCell(0, "D1", 4));
	series.getDataPoints().addDataPointForSunburstSeries(wb.getCell(0, "D2", 5));
	series.getDataPoints().addDataPointForSunburstSeries(wb.getCell(0, "D3", 3));
	series.getDataPoints().addDataPointForSunburstSeries(wb.getCell(0, "D4", 6));
	series.getDataPoints().addDataPointForSunburstSeries(wb.getCell(0, "D5", 9));
	series.getDataPoints().addDataPointForSunburstSeries(wb.getCell(0, "D6", 9));
	series.getDataPoints().addDataPointForSunburstSeries(wb.getCell(0, "D7", 4));
	series.getDataPoints().addDataPointForSunburstSeries(wb.getCell(0, "D8", 3));
	pres.save("Sunburst.pptx", SaveFormat.Pptx);
}
finally
{
	if (pres != null) pres.dispose();
}
```

## Abschluss

In diesem Tutorial haben Sie gelernt, wie Sie mithilfe der Aspose.Slides für Java-API ein Sunburst-Diagramm in einer PowerPoint-Präsentation erstellen. Sie haben gesehen, wie Sie die Präsentation initialisieren, das Diagramm erstellen, die Diagrammhierarchie definieren, Datenpunkte hinzufügen und die Präsentation speichern. Sie können dieses Wissen nun nutzen, um interaktive und informative Sunburst-Diagramme in Ihren Java-Anwendungen zu erstellen.

## FAQs

### Wie kann ich das Erscheinungsbild des Sunburst-Diagramms anpassen?

Sie können das Erscheinungsbild des Sunburst-Diagramms anpassen, indem Sie Eigenschaften wie Farben, Beschriftungen und Stile ändern. Ausführliche Anpassungsoptionen finden Sie in der Aspose.Slides-Dokumentation.

### Kann ich dem Diagramm weitere Datenpunkte hinzufügen?

 Ja, Sie können dem Diagramm weitere Datenpunkte hinzufügen, indem Sie verwenden`series.getDataPoints().addDataPointForSunburstSeries()` Methode für jeden Datenpunkt, den Sie einbeziehen möchten.

### Wie kann ich Tooltips zum Sunburst-Diagramm hinzufügen?

Um QuickInfos zum Sunburst-Diagramm hinzuzufügen, können Sie das Datenbeschriftungsformat so einstellen, dass zusätzliche Informationen wie Werte oder Beschreibungen angezeigt werden, wenn Sie mit der Maus über Diagrammsegmente fahren.

### Ist es möglich, interaktive Sunburst-Diagramme mit Hyperlinks zu erstellen?

Ja, Sie können interaktive Sunburst-Diagramme mit Hyperlinks erstellen, indem Sie Hyperlinks zu bestimmten Diagrammelementen oder -segmenten hinzufügen. Einzelheiten zum Hinzufügen von Hyperlinks finden Sie in der Aspose.Slides-Dokumentation.