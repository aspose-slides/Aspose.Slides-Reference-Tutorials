---
title: Normale Diagramme in Java-Folien
linktitle: Normale Diagramme in Java-Folien
second_title: Aspose.Slides Java PowerPoint-Verarbeitungs-API
description: Erstellen Sie normale Diagramme in Java-Folien mit Aspose.Slides für Java. Schritt-für-Schritt-Anleitung und Quellcode zum Erstellen, Anpassen und Speichern von Diagrammen in PowerPoint-Präsentationen.
type: docs
weight: 21
url: /de/java/chart-data-manipulation/normal-charts-java-slides/
---

## Einführung in normale Diagramme in Java-Folien

In diesem Tutorial werden wir durch den Prozess der Erstellung normaler Diagramme in Java Slides mithilfe der Aspose.Slides für Java-API gehen. Wir werden Schritt-für-Schritt-Anleitungen zusammen mit dem Quellcode verwenden, um zu demonstrieren, wie man ein gruppiertes Säulendiagramm in einer PowerPoint-Präsentation erstellt.

## Voraussetzungen

Bevor Sie beginnen, stellen Sie sicher, dass die folgenden Voraussetzungen erfüllt sind:

1. Aspose.Slides für Java API installiert.
2. Einrichtung einer Java-Entwicklungsumgebung.
3. Grundkenntnisse der Java-Programmierung.

## Schritt 1: Einrichten des Projekts

Stellen Sie sicher, dass Sie über ein Verzeichnis für Ihr Projekt verfügen. Nennen wir es „Ihr Dokumentenverzeichnis“, wie im Code erwähnt. Sie können diesen durch den tatsächlichen Pfad zu Ihrem Projektverzeichnis ersetzen.

```java
// Der Pfad zum Dokumentenverzeichnis.
String dataDir = "Your Document Directory";
// Erstellen Sie ein Verzeichnis, falls es noch nicht vorhanden ist.
boolean IsExists = new File(dataDir).exists();
if (!IsExists)
    new File(dataDir).mkdirs();
```

## Schritt 2: Erstellen einer Präsentation

Jetzt erstellen wir eine PowerPoint-Präsentation und greifen auf die erste Folie zu.

```java
// Instanziieren Sie die Präsentationsklasse, die eine PPTX-Datei darstellt
Presentation pres = new Presentation();
// Greifen Sie auf die erste Folie zu
ISlide sld = pres.getSlides().get_Item(0);
```

## Schritt 3: Hinzufügen eines Diagramms

Wir fügen der Folie ein gruppiertes Säulendiagramm hinzu und legen seinen Titel fest.

```java
// Diagramm mit Standarddaten hinzufügen
IChart chart = sld.getShapes().addChart(ChartType.ClusteredColumn, 0, 0, 500, 500);
// Titel des Diagramms festlegen
chart.getChartTitle().addTextFrameForOverriding("Sample Title");
chart.getChartTitle().getTextFrameForOverriding().getTextFrameFormat().setCenterText(NullableBool.True);
chart.getChartTitle().setHeight(20);
chart.setTitle(true);
```

## Schritt 4: Diagrammdaten festlegen

Als Nächstes legen wir die Diagrammdaten fest, indem wir Serien und Kategorien definieren.

```java
// Stellen Sie die erste Reihe auf „Werte anzeigen“ ein
chart.getChartData().getSeries().get_Item(0).getLabels().getDefaultDataLabelFormat().setShowValue(true);

// Festlegen des Index des Diagrammdatenblatts
int defaultWorksheetIndex = 0;

// Abrufen des Diagrammdaten-Arbeitsblatts
IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();

// Standardmäßig generierte Serien und Kategorien löschen
chart.getChartData().getSeries().clear();
chart.getChartData().getCategories().clear();

// Neue Serie hinzufügen
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 1, "Series 1"), chart.getType());
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 2, "Series 2"), chart.getType());

// Neue Kategorien hinzufügen
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 1, 0, "Category 1"));
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 2, 0, "Category 2"));
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 3, 0, "Category 3"));
```

## Schritt 5: Auffüllen der Seriendaten

Füllen wir nun die Reihendatenpunkte für das Diagramm aus.

```java
// Nehmen Sie die erste Chartserie
IChartSeries series = chart.getChartData().getSeries().get_Item(0);

// Auffüllen von Seriendaten
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 1, 20));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 50));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 30));

// Füllfarbe für Serien festlegen
series.getFormat().getFill().setFillType(FillType.Solid);
series.getFormat().getFill().getSolidFillColor().setColor(Color.RED);

// Nehmen Sie die zweite Chartserie
series = chart.getChartData().getSeries().get_Item(1);

// Auffüllen von Seriendaten
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 2, 30));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 2, 10));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 2, 60));

// Füllfarbe für Serien festlegen
series.getFormat().getFill().setFillType(FillType.Solid);
series.getFormat().getFill().getSolidFillColor().setColor(Color.GREEN);
```

## Schritt 6: Etiketten anpassen

Lassen Sie uns die Datenbeschriftungen für die Diagrammreihe anpassen.

```java
// Auf der ersten Beschriftung wird der Kategoriename angezeigt
IDataLabel lbl = series.getDataPoints().get_Item(0).getLabel();
lbl.getDataLabelFormat().setShowCategoryName(true);

lbl = series.getDataPoints().get_Item(1).getLabel();
lbl.getDataLabelFormat().setShowSeriesName(true);

// Wert für die dritte Beschriftung mit Serienname und Trennzeichen anzeigen
lbl = series.getDataPoints().get_Item(2).getLabel();
lbl.getDataLabelFormat().setShowValue(true);
lbl.getDataLabelFormat().setShowSeriesName(true);
lbl.getDataLabelFormat().setSeparator("/");
```

## Schritt 7: Speichern der Präsentation

Speichern Sie abschließend die Präsentation mit dem Diagramm in Ihrem Projektverzeichnis.

```java
pres.save(dataDir + "AsposeChart_out.pptx", SaveFormat.Pptx);
```

Das ist es! Sie haben mit Aspose.Slides für Java erfolgreich ein gruppiertes Säulendiagramm in einer PowerPoint-Präsentation erstellt. Sie können dieses Diagramm entsprechend Ihren Anforderungen weiter anpassen.

## Vollständiger Quellcode für normale Diagramme in Java-Folien

```java
// Der Pfad zum Dokumentenverzeichnis.
String dataDir = "Your Document Directory";
// Erstellen Sie ein Verzeichnis, falls es noch nicht vorhanden ist.
boolean IsExists = new File(dataDir).exists();
if (!IsExists)
	new File(dataDir).mkdirs();
// Instanziieren Sie die Präsentationsklasse, die eine PPTX-Datei darstellt
Presentation pres = new Presentation();
// Greifen Sie auf die erste Folie zu
ISlide sld = pres.getSlides().get_Item(0);
// Diagramm mit Standarddaten hinzufügen
IChart chart = sld.getShapes().addChart(ChartType.ClusteredColumn, 0, 0, 500, 500);
// Titel des Diagramms festlegen
// Chart.getChartTitle().getTextFrameForOverriding().setText("Beispieltitel");
chart.getChartTitle().addTextFrameForOverriding("Sample Title");
chart.getChartTitle().getTextFrameForOverriding().getTextFrameFormat().setCenterText(NullableBool.True);
chart.getChartTitle().setHeight(20);
chart.setTitle(true);
// Stellen Sie die erste Reihe auf „Werte anzeigen“ ein
chart.getChartData().getSeries().get_Item(0).getLabels().getDefaultDataLabelFormat().setShowValue(true);
// Festlegen des Index des Diagrammdatenblatts
int defaultWorksheetIndex = 0;
// Abrufen des Diagrammdaten-Arbeitsblatts
IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
// Standardmäßig generierte Serien und Kategorien löschen
chart.getChartData().getSeries().clear();
chart.getChartData().getCategories().clear();
int s = chart.getChartData().getSeries().size();
s = chart.getChartData().getCategories().size();
// Neue Serie hinzufügen
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 1, "Series 1"), chart.getType());
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 2, "Series 2"), chart.getType());
// Neue Kategorien hinzufügen
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 1, 0, "Caetegoty 1"));
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 2, 0, "Caetegoty 2"));
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 3, 0, "Caetegoty 3"));
// Nehmen Sie die erste Chartserie
IChartSeries series = chart.getChartData().getSeries().get_Item(0);
// Jetzt werden Seriendaten ausgefüllt
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 1, 20));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 50));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 30));
// Füllfarbe für Serien festlegen
series.getFormat().getFill().setFillType(FillType.Solid);
series.getFormat().getFill().getSolidFillColor().setColor(Color.RED);
// Nehmen Sie die zweite Chartserie
series = chart.getChartData().getSeries().get_Item(1);
// Jetzt werden Seriendaten ausgefüllt
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 2, 30));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 2, 10));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 2, 60));
// Füllfarbe für Serien festlegen
series.getFormat().getFill().setFillType(FillType.Solid);
series.getFormat().getFill().getSolidFillColor().setColor(Color.GREEN);
//Als erstes Etikett wird der Kategoriename angezeigt
IDataLabel lbl = series.getDataPoints().get_Item(0).getLabel();
lbl.getDataLabelFormat().setShowCategoryName(true);
lbl = series.getDataPoints().get_Item(1).getLabel();
lbl.getDataLabelFormat().setShowSeriesName(true);
// Wert für drittes Etikett anzeigen
lbl = series.getDataPoints().get_Item(2).getLabel();
lbl.getDataLabelFormat().setShowValue(true);
lbl.getDataLabelFormat().setShowSeriesName(true);
lbl.getDataLabelFormat().setSeparator("/");
// Präsentation mit Diagramm speichern
pres.save(dataDir + "AsposeChart_out.pptx", SaveFormat.Pptx);
```
# Abschluss

In diesem Tutorial haben wir gelernt, wie man mithilfe der Aspose.Slides für Java-API normale Diagramme in Java Slides erstellt. Wir haben eine Schritt-für-Schritt-Anleitung mit Quellcode durchgearbeitet, um ein gruppiertes Säulendiagramm in einer PowerPoint-Präsentation zu erstellen.

## FAQs

### Wie kann ich den Diagrammtyp ändern?

 Um den Diagrammtyp zu ändern, ändern Sie die`ChartType` Parameter beim Hinzufügen des Diagramms mit`sld.getShapes().addChart()`. Sie können aus verschiedenen Diagrammtypen wählen, die in Aspose.Slides verfügbar sind.

### Kann ich die Farben der Diagrammserie ändern?

 Ja, Sie können die Farben der Diagrammreihen ändern, indem Sie mit die Füllfarbe für jede Reihe festlegen`series.getFormat().getFill().getSolidFillColor().setColor(Color.YOUR_COLOR)`.

### Wie füge ich dem Diagramm weitere Kategorien oder Serien hinzu?

 Sie können dem Diagramm weitere Kategorien oder Reihen hinzufügen, indem Sie mithilfe von neue Datenpunkte und Beschriftungen hinzufügen`chart.getChartData().getCategories().add()` Und`chart.getChartData().getSeries().add()` Methoden.

### Wie kann ich den Diagrammtitel weiter anpassen?

 Sie können den Diagrammtitel weiter anpassen, indem Sie die Eigenschaften von ändern`chart.getChartTitle()` wie Textausrichtung, Schriftgröße und Farbe.

### Wie speichere ich das Diagramm in einem anderen Dateiformat?

Um das Diagramm in einem anderen Dateiformat zu speichern, ändern Sie das`SaveFormat` Parameter in der`pres.save()` Methode in das gewünschte Format (z. B. PDF, PNG, JPEG).