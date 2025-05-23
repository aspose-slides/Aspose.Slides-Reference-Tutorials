---
"description": "Erstellen Sie normale Diagramme in Java-Folien mit Aspose.Slides für Java. Schritt-für-Schritt-Anleitung und Quellcode zum Erstellen, Anpassen und Speichern von Diagrammen in PowerPoint-Präsentationen."
"linktitle": "Normale Diagramme in Java-Folien"
"second_title": "Aspose.Slides Java PowerPoint-Verarbeitungs-API"
"title": "Normale Diagramme in Java-Folien"
"url": "/de/java/chart-data-manipulation/normal-charts-java-slides/"
"weight": 21
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Normale Diagramme in Java-Folien


## Einführung in normale Diagramme in Java-Folien

In diesem Tutorial zeigen wir Ihnen, wie Sie mithilfe der Aspose.Slides für Java-API normale Diagramme in Java Slides erstellen. Anhand einer Schritt-für-Schritt-Anleitung und des Quellcodes zeigen wir Ihnen, wie Sie ein gruppiertes Säulendiagramm in einer PowerPoint-Präsentation erstellen.

## Voraussetzungen

Bevor Sie beginnen, stellen Sie sicher, dass die folgenden Voraussetzungen erfüllt sind:

1. Aspose.Slides für Java-API installiert.
2. Eine Java-Entwicklungsumgebung ist eingerichtet.
3. Grundkenntnisse der Java-Programmierung.

## Schritt 1: Einrichten des Projekts

Stellen Sie sicher, dass Sie ein Verzeichnis für Ihr Projekt haben. Nennen wir es „Ihr Dokumentverzeichnis“, wie im Code erwähnt. Sie können dies durch den tatsächlichen Pfad zu Ihrem Projektverzeichnis ersetzen.

```java
// Der Pfad zum Dokumentenverzeichnis.
String dataDir = "Your Document Directory";
// Erstellen Sie ein Verzeichnis, falls es noch nicht vorhanden ist.
boolean IsExists = new File(dataDir).exists();
if (!IsExists)
    new File(dataDir).mkdirs();
```

## Schritt 2: Erstellen einer Präsentation

Lassen Sie uns nun eine PowerPoint-Präsentation erstellen und auf die erste Folie zugreifen.

```java
// Instanziieren Sie die Präsentationsklasse, die die PPTX-Datei darstellt
Presentation pres = new Presentation();
// Zugriff auf die erste Folie
ISlide sld = pres.getSlides().get_Item(0);
```

## Schritt 3: Hinzufügen eines Diagramms

Wir fügen der Folie ein gruppiertes Säulendiagramm hinzu und legen seinen Titel fest.

```java
// Diagramm mit Standarddaten hinzufügen
IChart chart = sld.getShapes().addChart(ChartType.ClusteredColumn, 0, 0, 500, 500);
// Einstellungsdiagrammtitel
chart.getChartTitle().addTextFrameForOverriding("Sample Title");
chart.getChartTitle().getTextFrameForOverriding().getTextFrameFormat().setCenterText(NullableBool.True);
chart.getChartTitle().setHeight(20);
chart.setTitle(true);
```

## Schritt 4: Festlegen der Diagrammdaten

Als Nächstes legen wir die Diagrammdaten fest, indem wir Reihen und Kategorien definieren.

```java
// Stellen Sie die erste Serie auf „Werte anzeigen“ ein
chart.getChartData().getSeries().get_Item(0).getLabels().getDefaultDataLabelFormat().setShowValue(true);

// Festlegen des Index des Diagrammdatenblatts
int defaultWorksheetIndex = 0;

// Abrufen des Arbeitsblatts mit den Diagrammdaten
IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();

// Standardmäßig generierte Serien und Kategorien löschen
chart.getChartData().getSeries().clear();
chart.getChartData().getCategories().clear();

// Neue Serien hinzufügen
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 1, "Series 1"), chart.getType());
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 2, "Series 2"), chart.getType());

// Neue Kategorien hinzufügen
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 1, 0, "Category 1"));
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 2, 0, "Category 2"));
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 3, 0, "Category 3"));
```

## Schritt 5: Auffüllen der Seriendaten

Füllen wir nun die Datenpunkte der Reihe für das Diagramm aus.

```java
// Nehmen Sie die erste Chartreihe
IChartSeries series = chart.getChartData().getSeries().get_Item(0);

// Auffüllen von Seriendaten
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 1, 20));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 50));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 30));

// Füllfarbe für Serien festlegen
series.getFormat().getFill().setFillType(FillType.Solid);
series.getFormat().getFill().getSolidFillColor().setColor(Color.RED);

// Nehmen Sie die zweite Diagrammreihe
series = chart.getChartData().getSeries().get_Item(1);

// Auffüllen von Seriendaten
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 2, 30));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 2, 10));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 2, 60));

// Füllfarbe für Serien festlegen
series.getFormat().getFill().setFillType(FillType.Solid);
series.getFormat().getFill().getSolidFillColor().setColor(Color.GREEN);
```

## Schritt 6: Beschriftungen anpassen

Passen wir die Datenbeschriftungen für die Diagrammreihe an.

```java
// Das erste Etikett zeigt den Kategorienamen
IDataLabel lbl = series.getDataPoints().get_Item(0).getLabel();
lbl.getDataLabelFormat().setShowCategoryName(true);

lbl = series.getDataPoints().get_Item(1).getLabel();
lbl.getDataLabelFormat().setShowSeriesName(true);

// Wert für drittes Label mit Serienname und Trennzeichen anzeigen
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

Fertig! Sie haben mit Aspose.Slides für Java erfolgreich ein gruppiertes Säulendiagramm in einer PowerPoint-Präsentation erstellt. Sie können dieses Diagramm weiter an Ihre Anforderungen anpassen.

## Vollständiger Quellcode für normale Diagramme in Java-Folien

```java
// Der Pfad zum Dokumentenverzeichnis.
String dataDir = "Your Document Directory";
// Erstellen Sie ein Verzeichnis, falls es noch nicht vorhanden ist.
boolean IsExists = new File(dataDir).exists();
if (!IsExists)
	new File(dataDir).mkdirs();
// Instanziieren Sie die Präsentationsklasse, die die PPTX-Datei darstellt
Presentation pres = new Presentation();
// Zugriff auf die erste Folie
ISlide sld = pres.getSlides().get_Item(0);
// Diagramm mit Standarddaten hinzufügen
IChart chart = sld.getShapes().addChart(ChartType.ClusteredColumn, 0, 0, 500, 500);
// Einstellungsdiagrammtitel
// Chart.getChartTitle().getTextFrameForOverriding().setText("Beispieltitel");
chart.getChartTitle().addTextFrameForOverriding("Sample Title");
chart.getChartTitle().getTextFrameForOverriding().getTextFrameFormat().setCenterText(NullableBool.True);
chart.getChartTitle().setHeight(20);
chart.setTitle(true);
// Stellen Sie die erste Serie auf „Werte anzeigen“ ein
chart.getChartData().getSeries().get_Item(0).getLabels().getDefaultDataLabelFormat().setShowValue(true);
// Festlegen des Index des Diagrammdatenblatts
int defaultWorksheetIndex = 0;
// Abrufen des Arbeitsblatts mit den Diagrammdaten
IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
// Standardmäßig generierte Serien und Kategorien löschen
chart.getChartData().getSeries().clear();
chart.getChartData().getCategories().clear();
int s = chart.getChartData().getSeries().size();
s = chart.getChartData().getCategories().size();
// Neue Serien hinzufügen
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 1, "Series 1"), chart.getType());
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 2, "Series 2"), chart.getType());
// Neue Kategorien hinzufügen
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 1, 0, "Caetegoty 1"));
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 2, 0, "Caetegoty 2"));
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 3, 0, "Caetegoty 3"));
// Nehmen Sie die erste Chartreihe
IChartSeries series = chart.getChartData().getSeries().get_Item(0);
// Jetzt werden Seriendaten gefüllt
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 1, 20));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 50));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 30));
// Füllfarbe für Serien festlegen
series.getFormat().getFill().setFillType(FillType.Solid);
series.getFormat().getFill().getSolidFillColor().setColor(Color.RED);
// Nehmen Sie die zweite Diagrammreihe
series = chart.getChartData().getSeries().get_Item(1);
// Jetzt werden Seriendaten gefüllt
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 2, 30));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 2, 10));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 2, 60));
// Füllfarbe für Serien festlegen
series.getFormat().getFill().setFillType(FillType.Solid);
series.getFormat().getFill().getSolidFillColor().setColor(Color.GREEN);
// Das erste Etikett zeigt den Kategorienamen
IDataLabel lbl = series.getDataPoints().get_Item(0).getLabel();
lbl.getDataLabelFormat().setShowCategoryName(true);
lbl = series.getDataPoints().get_Item(1).getLabel();
lbl.getDataLabelFormat().setShowSeriesName(true);
// Wert für drittes Label anzeigen
lbl = series.getDataPoints().get_Item(2).getLabel();
lbl.getDataLabelFormat().setShowValue(true);
lbl.getDataLabelFormat().setShowSeriesName(true);
lbl.getDataLabelFormat().setSeparator("/");
// Präsentation mit Diagramm speichern
pres.save(dataDir + "AsposeChart_out.pptx", SaveFormat.Pptx);
```
# Abschluss

In diesem Tutorial haben wir gelernt, wie man mit der Aspose.Slides für Java-API normale Diagramme in Java Slides erstellt. Wir haben eine Schritt-für-Schritt-Anleitung mit Quellcode durchgearbeitet, um ein gruppiertes Säulendiagramm in einer PowerPoint-Präsentation zu erstellen.

## Häufig gestellte Fragen

### Wie kann ich den Diagrammtyp ändern?

Um den Diagrammtyp zu ändern, ändern Sie die `ChartType` Parameter beim Hinzufügen des Diagramms mit `sld.getShapes().addChart()`. Sie können aus verschiedenen in Aspose.Slides verfügbaren Diagrammtypen wählen.

### Kann ich die Farben der Diagrammreihen ändern?

Ja, Sie können die Farben der Diagrammreihen ändern, indem Sie die Füllfarbe für jede Reihe festlegen mit `series.getFormat().getFill().getSolidFillColor().setColor(Color.YOUR_COLOR)`.

### Wie füge ich dem Diagramm weitere Kategorien oder Reihen hinzu?

Sie können dem Diagramm weitere Kategorien oder Reihen hinzufügen, indem Sie mithilfe der Schaltfläche neue Datenpunkte und Beschriftungen hinzufügen. `chart.getChartData().getCategories().add()` Und `chart.getChartData().getSeries().add()` Methoden.

### Wie kann ich den Diagrammtitel weiter anpassen?

Sie können den Diagrammtitel weiter anpassen, indem Sie die Eigenschaften von `chart.getChartTitle()` wie Textausrichtung, Schriftgröße und Farbe.

### Wie speichere ich das Diagramm in einem anderen Dateiformat?

Um das Diagramm in einem anderen Dateiformat zu speichern, ändern Sie das `SaveFormat` Parameter im `pres.save()` Methode in das gewünschte Format (z. B. PDF, PNG, JPEG).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}