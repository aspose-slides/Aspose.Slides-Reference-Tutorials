---
title: Festlegen des Prozentzeichens für Datenbeschriftungen in Java-Folien
linktitle: Festlegen des Prozentzeichens für Datenbeschriftungen in Java-Folien
second_title: Aspose.Slides Java PowerPoint-Verarbeitungs-API
description: Erfahren Sie, wie Sie mit Aspose.Slides für Java Datenbeschriftungen mit Prozentzeichen in PowerPoint-Präsentationen festlegen. Erstellen Sie ansprechende Diagramme mit Schritt-für-Schritt-Anleitung und Quellcode.
type: docs
weight: 17
url: /de/java/data-manipulation/set-data-labels-percentage-sign-java-slides/
---

## Einführung in das Festlegen der Prozentangabe für Datenbeschriftungen in Aspose.Slides für Java

In dieser Anleitung führen wir Sie durch den Prozess des Festlegens von Datenbeschriftungen mit einem Prozentzeichen mithilfe von Aspose.Slides für Java. Wir erstellen eine PowerPoint-Präsentation mit einem gestapelten Säulendiagramm und konfigurieren Datenbeschriftungen zur Anzeige von Prozentsätzen.

## Voraussetzungen

 Bevor Sie beginnen, stellen Sie sicher, dass Ihrem Projekt die Aspose.Slides for Java-Bibliothek hinzugefügt wurde. Sie können es herunterladen unter[Hier](https://releases.aspose.com/slides/java/).

## Schritt 1: Erstellen Sie eine neue Präsentation

Zuerst erstellen wir mit Aspose.Slides eine neue PowerPoint-Präsentation.

```java
// Der Pfad zum Dokumentenverzeichnis.
String dataDir = "Your Document Directory";
// Erstellen Sie eine Instanz der Presentation-Klasse
Presentation presentation = new Presentation();
```

## Schritt 2: Fügen Sie eine Folie und ein Diagramm hinzu

Als Nächstes fügen wir der Präsentation eine Folie und ein gestapeltes Säulendiagramm hinzu.

```java
// Holen Sie sich eine Referenz der Folie
ISlide slide = presentation.getSlides().get_Item(0);

// Fügen Sie ein PercentsStackedColumn-Diagramm auf einer Folie hinzu
IChart chart = slide.getShapes().addChart(ChartType.PercentsStackedColumn, 20, 20, 500, 400);
```

## Schritt 3: Konfigurieren Sie das Achsennummernformat

Um Prozentsätze anzuzeigen, müssen wir das Zahlenformat für die vertikale Achse des Diagramms konfigurieren.

```java
//Legen Sie NumberFormatLinkedToSource auf false fest
chart.getAxes().getVerticalAxis().setNumberFormatLinkedToSource(false);
chart.getAxes().getVerticalAxis().setNumberFormat("0.00%");
```

## Schritt 4: Diagrammdaten hinzufügen

Wir fügen dem Diagramm Daten hinzu, indem wir Reihen und Datenpunkte erstellen. In diesem Beispiel fügen wir zwei Reihen mit ihren jeweiligen Datenpunkten hinzu.

```java
// Abrufen des Diagrammdaten-Arbeitsblatts
IChartDataWorkbook workbook = chart.getChartData().getChartDataWorkbook();

// Neue Serie hinzufügen
IChartSeries series = chart.getChartData().getSeries().add(workbook.getCell(defaultWorksheetIndex, 0, 1, "Reds"), chart.getType());
series.getDataPoints().addDataPointForBarSeries(workbook.getCell(defaultWorksheetIndex, 1, 1, 0.30));
series.getDataPoints().addDataPointForBarSeries(workbook.getCell(defaultWorksheetIndex, 2, 1, 0.50));
series.getDataPoints().addDataPointForBarSeries(workbook.getCell(defaultWorksheetIndex, 3, 1, 0.80));
series.getDataPoints().addDataPointForBarSeries(workbook.getCell(defaultWorksheetIndex, 4, 1, 0.65));

// Neue Serie hinzufügen
IChartSeries series2 = chart.getChartData().getSeries().add(workbook.getCell(defaultWorksheetIndex, 0, 2, "Blues"), chart.getType());
series2.getDataPoints().addDataPointForBarSeries(workbook.getCell(defaultWorksheetIndex, 1, 2, 0.70));
series2.getDataPoints().addDataPointForBarSeries(workbook.getCell(defaultWorksheetIndex, 2, 2, 0.50));
series2.getDataPoints().addDataPointForBarSeries(workbook.getCell(defaultWorksheetIndex, 3, 2, 0.20));
series2.getDataPoints().addDataPointForBarSeries(workbook.getCell(defaultWorksheetIndex, 4, 2, 0.35));
```

## Schritt 5: Datenbeschriftungen anpassen

Passen wir nun das Erscheinungsbild der Datenbeschriftungen an.

```java
// Festlegen von LabelFormat-Eigenschaften
series.getLabels().getDefaultDataLabelFormat().setShowValue(true);
series.getLabels().getDefaultDataLabelFormat().setNumberFormatLinkedToSource(false);
series.getLabels().getDefaultDataLabelFormat().setNumberFormat("0.0%");
series.getLabels().getDefaultDataLabelFormat().getTextFormat().getPortionFormat().setFontHeight(10);
series.getLabels().getDefaultDataLabelFormat().getTextFormat().getPortionFormat().getFillFormat().setFillType(FillType.Solid);
series.getLabels().getDefaultDataLabelFormat().getTextFormat().getPortionFormat().getFillFormat().getSolidFillColor().setColor(Color.WHITE);
series.getLabels().getDefaultDataLabelFormat().setShowValue(true);

series2.getLabels().getDefaultDataLabelFormat().setShowValue(true);
series2.getLabels().getDefaultDataLabelFormat().setNumberFormatLinkedToSource(false);
series2.getLabels().getDefaultDataLabelFormat().setNumberFormat("0.0%");
series2.getLabels().getDefaultDataLabelFormat().getTextFormat().getPortionFormat().setFontHeight(10);
series2.getLabels().getDefaultDataLabelFormat().getTextFormat().getPortionFormat().getFillFormat().setFillType(FillType.Solid);
series2.getLabels().getDefaultDataLabelFormat().getTextFormat().getPortionFormat().getFillFormat().getSolidFillColor().setColor(Color.WHITE);
```

## Schritt 6: Speichern Sie die Präsentation

Abschließend speichern wir die Präsentation in einer PowerPoint-Datei.

```java
// Präsentation auf Diskette schreiben
presentation.save(dataDir + "SetDataLabelsPercentageSign_out.pptx", SaveFormat.Pptx);
```

Das ist es! Sie haben mit Aspose.Slides für Java erfolgreich eine PowerPoint-Präsentation mit einem gestapelten Säulendiagramm erstellt und Datenbeschriftungen für die Anzeige von Prozentsätzen konfiguriert.

## Vollständiger Quellcode zum Festlegen von Datenbeschriftungen, Prozentzeichen in Java-Folien

```java
// Der Pfad zum Dokumentenverzeichnis.
String dataDir = "Your Document Directory";
// Erstellen Sie eine Instanz der Presentation-Klasse
Presentation presentation = new Presentation();
// Holen Sie sich eine Referenz der Folie
ISlide slide = presentation.getSlides().get_Item(0);
// Fügen Sie ein PercentsStackedColumn-Diagramm auf einer Folie hinzu
IChart chart = slide.getShapes().addChart(ChartType.PercentsStackedColumn, 20, 20, 500, 400);
//Legen Sie NumberFormatLinkedToSource auf false fest
chart.getAxes().getVerticalAxis().setNumberFormatLinkedToSource(false);
chart.getAxes().getVerticalAxis().setNumberFormat("0.00%");
chart.getChartData().getSeries().clear();
int defaultWorksheetIndex = 0;
// Abrufen des Diagrammdaten-Arbeitsblatts
IChartDataWorkbook workbook = chart.getChartData().getChartDataWorkbook();
// Neue Serie hinzufügen
IChartSeries series = chart.getChartData().getSeries().add(workbook.getCell(defaultWorksheetIndex, 0, 1, "Reds"), chart.getType());
series.getDataPoints().addDataPointForBarSeries(workbook.getCell(defaultWorksheetIndex, 1, 1, 0.30));
series.getDataPoints().addDataPointForBarSeries(workbook.getCell(defaultWorksheetIndex, 2, 1, 0.50));
series.getDataPoints().addDataPointForBarSeries(workbook.getCell(defaultWorksheetIndex, 3, 1, 0.80));
series.getDataPoints().addDataPointForBarSeries(workbook.getCell(defaultWorksheetIndex, 4, 1, 0.65));
// Festlegen der Füllfarbe der Serie
series.getFormat().getFill().setFillType(FillType.Solid);
series.getFormat().getFill().getSolidFillColor().setColor(Color.RED);
// Festlegen von LabelFormat-Eigenschaften
series.getLabels().getDefaultDataLabelFormat().setShowValue(true);
series.getLabels().getDefaultDataLabelFormat().setNumberFormatLinkedToSource(false);
series.getLabels().getDefaultDataLabelFormat().setNumberFormat("0.0%");
series.getLabels().getDefaultDataLabelFormat().getTextFormat().getPortionFormat().setFontHeight(10);
series.getLabels().getDefaultDataLabelFormat().getTextFormat().getPortionFormat().getFillFormat().setFillType(FillType.Solid);
series.getLabels().getDefaultDataLabelFormat().getTextFormat().getPortionFormat().getFillFormat().getSolidFillColor().setColor(Color.WHITE);
series.getLabels().getDefaultDataLabelFormat().setShowValue(true);
// Neue Serie hinzufügen
IChartSeries series2 = chart.getChartData().getSeries().add(workbook.getCell(defaultWorksheetIndex, 0, 2, "Blues"), chart.getType());
series2.getDataPoints().addDataPointForBarSeries(workbook.getCell(defaultWorksheetIndex, 1, 2, 0.70));
series2.getDataPoints().addDataPointForBarSeries(workbook.getCell(defaultWorksheetIndex, 2, 2, 0.50));
series2.getDataPoints().addDataPointForBarSeries(workbook.getCell(defaultWorksheetIndex, 3, 2, 0.20));
series2.getDataPoints().addDataPointForBarSeries(workbook.getCell(defaultWorksheetIndex, 4, 2, 0.35));
// Fülltyp und Farbe festlegen
series2.getFormat().getFill().setFillType(FillType.Solid);
series2.getFormat().getFill().getSolidFillColor().setColor(Color.BLUE);
series2.getLabels().getDefaultDataLabelFormat().setShowValue(true);
series2.getLabels().getDefaultDataLabelFormat().setNumberFormatLinkedToSource(false);
series2.getLabels().getDefaultDataLabelFormat().setNumberFormat("0.0%");
series2.getLabels().getDefaultDataLabelFormat().getTextFormat().getPortionFormat().setFontHeight(10);
series2.getLabels().getDefaultDataLabelFormat().getTextFormat().getPortionFormat().getFillFormat().setFillType(FillType.Solid);
series2.getLabels().getDefaultDataLabelFormat().getTextFormat().getPortionFormat().getFillFormat().getSolidFillColor().setColor(Color.WHITE);
// Präsentation auf Diskette schreiben
presentation.save(dataDir + "SetDataLabelsPercentageSign_out.pptx", SaveFormat.Pptx);
```

## Abschluss

Durch die Befolgung dieses Leitfadens haben Sie gelernt, wie Sie ansprechende Präsentationen mit prozentualen Datenbeschriftungen erstellen, die besonders nützlich sein können, um Informationen in Geschäftsberichten, Lehrmaterialien und mehr effektiv zu vermitteln.

## FAQs

### Wie kann ich die Farben der Diagrammreihe ändern?

 Sie können die Füllfarbe von Diagrammreihen mit ändern`setFill` Methode wie im Beispiel gezeigt.

### Kann ich die Schriftgröße der Datenbeschriftungen anpassen?

 Ja, Sie können die Schriftgröße von Datenbeschriftungen anpassen, indem Sie Folgendes festlegen`setFontHeight` Eigenschaft, wie im Code gezeigt.

### Wie kann ich dem Diagramm weitere Serien hinzufügen?

 Sie können dem Diagramm zusätzliche Reihen hinzufügen, indem Sie verwenden`add` Methode auf der`IChartSeriesCollection` Objekt.
