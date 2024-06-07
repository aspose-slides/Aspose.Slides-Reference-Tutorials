---
title: Baumdiagramm in Java-Folien
linktitle: Baumdiagramm in Java-Folien
second_title: Aspose.Slides Java PowerPoint-Verarbeitungs-API
description: Erstellen Sie Tree Map-Diagramme in Java Slides mit Aspose.Slides für Java. Schritt-für-Schritt-Anleitung mit Quellcode zur Visualisierung hierarchischer Daten.
type: docs
weight: 13
url: /de/java/chart-creation/tree-map-chart-java-slides/
---

## Einführung in das Tree Map-Diagramm in Java-Folien

In diesem Tutorial zeigen wir, wie Sie mit der Aspose.Slides-Bibliothek für Java ein Tree Map-Diagramm in einer PowerPoint-Präsentation erstellen. Tree Map-Diagramme sind eine effektive Möglichkeit, hierarchische Daten zu visualisieren.

## Voraussetzungen

Stellen Sie vor dem Beginn sicher, dass Sie die Bibliothek Aspose.Slides für Java in Ihrem Java-Projekt eingerichtet haben.

## Schritt 1: Erforderliche Bibliotheken importieren

```java
import com.aspose.slides.*;
```

## Schritt 2: Laden Sie die Präsentation

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "test.pptx");
```

## Schritt 3: Erstellen Sie ein Tree Map-Diagramm

```java
try {
    IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.Treemap, 50, 50, 500, 400);
    chart.getChartData().getCategories().clear();
    chart.getChartData().getSeries().clear();
    IChartDataWorkbook wb = chart.getChartData().getChartDataWorkbook();
    wb.clear(0);

    // Filiale 1 erstellen
    IChartCategory leaf = chart.getChartData().getCategories().add(wb.getCell(0, "C1", "Leaf1"));
    leaf.getGroupingLevels().setGroupingItem(1, "Stem1");
    leaf.getGroupingLevels().setGroupingItem(2, "Branch1");

    chart.getChartData().getCategories().add(wb.getCell(0, "C2", "Leaf2"));

    leaf = chart.getChartData().getCategories().add(wb.getCell(0, "C3", "Leaf3"));
    leaf.getGroupingLevels().setGroupingItem(1, "Stem2");

    chart.getChartData().getCategories().add(wb.getCell(0, "C4", "Leaf4"));

    // Filiale 2 erstellen
    leaf = chart.getChartData().getCategories().add(wb.getCell(0, "C5", "Leaf5"));
    leaf.getGroupingLevels().setGroupingItem(1, "Stem3");
    leaf.getGroupingLevels().setGroupingItem(2, "Branch2");

    chart.getChartData().getCategories().add(wb.getCell(0, "C6", "Leaf6"));

    leaf = chart.getChartData().getCategories().add(wb.getCell(0, "C7", "Leaf7"));
    leaf.getGroupingLevels().setGroupingItem(1, "Stem4");

    chart.getChartData().getCategories().add(wb.getCell(0, "C8", "Leaf8"));

    // Datenpunkte hinzufügen
    IChartSeries series = chart.getChartData().getSeries().add(ChartType.Treemap);
    series.getLabels().getDefaultDataLabelFormat().setShowCategoryName(true);

    series.getDataPoints().addDataPointForTreemapSeries(wb.getCell(0, "D1", 4));
    series.getDataPoints().addDataPointForTreemapSeries(wb.getCell(0, "D2", 5));
    series.getDataPoints().addDataPointForTreemapSeries(wb.getCell(0, "D3", 3));
    series.getDataPoints().addDataPointForTreemapSeries(wb.getCell(0, "D4", 6));
    series.getDataPoints().addDataPointForTreemapSeries(wb.getCell(0, "D5", 9));
    series.getDataPoints().addDataPointForTreemapSeries(wb.getCell(0, "D6", 9));
    series.getDataPoints().addDataPointForTreemapSeries(wb.getCell(0, "D7", 4));
    series.getDataPoints().addDataPointForTreemapSeries(wb.getCell(0, "D8", 3));

    series.setParentLabelLayout(ParentLabelLayoutType.Overlapping);

    // Speichern Sie die Präsentation mit dem Tree Map-Diagramm
    pres.save("Treemap.pptx", SaveFormat.Pptx);
} finally {
    if (pres != null) pres.dispose();
}
```

## Vollständiger Quellcode für Tree Map-Diagramm in Java-Folien
```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "test.pptx");
try
{
	IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.Treemap, 50, 50, 500, 400);
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
	IChartSeries series = chart.getChartData().getSeries().add(ChartType.Treemap);
	series.getLabels().getDefaultDataLabelFormat().setShowCategoryName(true);
	series.getDataPoints().addDataPointForTreemapSeries(wb.getCell(0, "D1", 4));
	series.getDataPoints().addDataPointForTreemapSeries(wb.getCell(0, "D2", 5));
	series.getDataPoints().addDataPointForTreemapSeries(wb.getCell(0, "D3", 3));
	series.getDataPoints().addDataPointForTreemapSeries(wb.getCell(0, "D4", 6));
	series.getDataPoints().addDataPointForTreemapSeries(wb.getCell(0, "D5", 9));
	series.getDataPoints().addDataPointForTreemapSeries(wb.getCell(0, "D6", 9));
	series.getDataPoints().addDataPointForTreemapSeries(wb.getCell(0, "D7", 4));
	series.getDataPoints().addDataPointForTreemapSeries(wb.getCell(0, "D8", 3));
	series.setParentLabelLayout(ParentLabelLayoutType.Overlapping);
	pres.save("Treemap.pptx", SaveFormat.Pptx);
}
finally
{
	if (pres != null) pres.dispose();
}
```

## Abschluss

In diesem Tutorial haben Sie gelernt, wie Sie mithilfe der Aspose.Slides-Bibliothek für Java ein Tree Map-Diagramm in einer PowerPoint-Präsentation erstellen. Tree Map-Diagramme sind ein wertvolles Tool zur Visualisierung hierarchischer Daten und machen Ihre Präsentationen informativer und ansprechender.

## Häufig gestellte Fragen

### Wie füge ich Daten zum Treemap-Diagramm hinzu?

 Um Daten zum Tree Map-Diagramm hinzuzufügen, verwenden Sie das`series.getDataPoints().addDataPointForTreemapSeries()` Methode, bei der die Datenwerte als Parameter übergeben werden.

### Wie kann ich das Erscheinungsbild des TreeMap-Diagramms anpassen?

 Sie können das Erscheinungsbild des Tree Map-Diagramms anpassen, indem Sie verschiedene Eigenschaften des`chart` Und`series` Objekte wie Farben, Beschriftungen und Layouts.

### Kann ich mehrere TreeMap-Diagramme in einer einzigen Präsentation erstellen?

Ja, Sie können mehrere TreeMap-Diagramme in einer einzigen Präsentation erstellen, indem Sie dieselben Schritte ausführen und unterschiedliche Folienpositionen angeben.

### Wie speichere ich die Präsentation mit dem Tree Map-Diagramm?

 Verwenden Sie die`pres.save()` Methode, um die Präsentation mit dem Tree Map-Diagramm im gewünschten Format (z. B. PPTX) zu speichern.