---
title: Festlegen automatischer Kreisdiagramm-Slice-Farben in Java-Folien
linktitle: Festlegen automatischer Kreisdiagramm-Slice-Farben in Java-Folien
second_title: Aspose.Slides Java PowerPoint-Verarbeitungs-API
description: Erfahren Sie, wie Sie mit Aspose.Slides für Java dynamische Kreisdiagramme mit automatischen Segmentfarben in Java-PowerPoint-Präsentationen erstellen. Schritt-für-Schritt-Anleitung mit Quellcode.
type: docs
weight: 24
url: /de/java/data-manipulation/setting-automatic-pie-chart-slice-colors-java-slides/
---

## Einführung in das Festlegen automatischer Kreisdiagramm-Slice-Farben in Java-Folien

In diesem Tutorial erfahren Sie, wie Sie mit Aspose.Slides für Java ein Kreisdiagramm in einer PowerPoint-Präsentation erstellen und automatische Segmentfarben für das Diagramm festlegen. Wir stellen Ihnen eine Schritt-für-Schritt-Anleitung zusammen mit dem Quellcode zur Verfügung.

## Voraussetzungen

 Bevor Sie beginnen, stellen Sie sicher, dass die Aspose.Slides for Java-Bibliothek in Ihrem Java-Projekt installiert und eingerichtet ist. Sie können die Bibliothek von der Aspose-Website herunterladen:[Laden Sie Aspose.Slides für Java herunter](https://releases.aspose.com/slides/java/).

## Schritt 1: Erforderliche Pakete importieren

Zunächst müssen Sie die erforderlichen Pakete von Aspose.Slides für Java importieren:

```java
import com.aspose.slides.ChartType;
import com.aspose.slides.IChart;
import com.aspose.slides.IChartSeries;
import com.aspose.slides.ISlide;
import com.aspose.slides.Presentation;
import com.aspose.slides.SaveFormat;
import com.aspose.slides.NullableBool;
import com.aspose.slides.charts.IChartDataWorkbook;
```

## Schritt 2: Erstellen Sie eine PowerPoint-Präsentation

 Instanziieren Sie die`Presentation` Klasse zum Erstellen einer neuen PowerPoint-Präsentation:

```java
String dataDir = "Your Document Directory";
Presentation presentation = new Presentation();
```

## Schritt 3: Fügen Sie eine Folie hinzu

Greifen Sie auf die erste Folie der Präsentation zu und fügen Sie ein Diagramm mit Standarddaten hinzu:

```java
ISlide slide = presentation.getSlides().get_Item(0);
IChart chart = slide.getShapes().addChart(ChartType.Pie, 100, 100, 400, 400);
```

## Schritt 4: Legen Sie den Diagrammtitel fest

Legen Sie einen Titel für das Diagramm fest:

```java
chart.getChartTitle().addTextFrameForOverriding("Sample Title");
chart.getChartTitle().getTextFrameForOverriding().getTextFrameFormat().setCenterText(NullableBool.True);
chart.getChartTitle().setHeight(20);
chart.setTitle(true);
```

## Schritt 5: Diagrammdaten konfigurieren

Stellen Sie das Diagramm so ein, dass es Werte für die erste Serie anzeigt, und konfigurieren Sie die Diagrammdaten:

```java
chart.getChartData().getSeries().get_Item(0).getLabels().getDefaultDataLabelFormat().setShowValue(true);

int defaultWorksheetIndex = 0;
IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
chart.getChartData().getSeries().clear();
chart.getChartData().getCategories().clear();
```

## Schritt 6: Kategorien und Serien hinzufügen

Fügen Sie dem Diagramm neue Kategorien und Serien hinzu:

```java
chart.getChartData().getCategories().add(fact.getCell(0, 1, 0, "First Qtr"));
chart.getChartData().getCategories().add(fact.getCell(0, 2, 0, "2nd Qtr"));
chart.getChartData().getCategories().add(fact.getCell(0, 3, 0, "3rd Qtr"));

IChartSeries series = chart.getChartData().getSeries().add(fact.getCell(0, 0, 1, "Series 1"), chart.getType());
```

## Schritt 7: Füllen Sie die Seriendaten aus

Füllen Sie die Reihendaten für das Kreisdiagramm aus:

```java
series.getDataPoints().addDataPointForPieSeries(fact.getCell(defaultWorksheetIndex, 1, 1, 20));
series.getDataPoints().addDataPointForPieSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 50));
series.getDataPoints().addDataPointForPieSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 30));
```

## Schritt 8: Aktivieren Sie verschiedene Schnittfarben

Aktivieren Sie verschiedene Segmentfarben für das Kreisdiagramm:

```java
series.getParentSeriesGroup().setColorVaried(true);
```

## Schritt 9: Speichern Sie die Präsentation

Speichern Sie abschließend die Präsentation in einer PowerPoint-Datei:

```java
presentation.save(dataDir + "Pie.pptx", SaveFormat.Pptx);
```

## Vollständiger Quellcode zum Festlegen automatischer Kreisdiagramm-Slice-Farben in Java-Folien

```java
// Der Pfad zum Dokumentenverzeichnis.
String dataDir = "Your Document Directory";
// Instanziieren Sie die Präsentationsklasse, die eine PPTX-Datei darstellt
Presentation presentation = new Presentation();
try
{
	// Greifen Sie auf die erste Folie zu
	ISlide slides = presentation.getSlides().get_Item(0);
	// Diagramm mit Standarddaten hinzufügen
	IChart chart = slides.getShapes().addChart(ChartType.Pie, 100, 100, 400, 400);
	// Titel des Diagramms festlegen
	chart.getChartTitle().addTextFrameForOverriding("Sample Title");
	chart.getChartTitle().getTextFrameForOverriding().getTextFrameFormat().setCenterText(NullableBool.True);
	chart.getChartTitle().setHeight(20);
	chart.setTitle(true);
	// Stellen Sie die erste Reihe auf „Werte anzeigen“ ein
	chart.getChartData().getSeries().get_Item(0).getLabels().getDefaultDataLabelFormat().setShowValue(true);
	// Festlegen des Index des Diagrammdatenblatts
	int defaultWorksheetIndex = 0;
	//Abrufen des Diagrammdaten-Arbeitsblatts
	IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
	// Standardmäßig generierte Serien und Kategorien löschen
	chart.getChartData().getSeries().clear();
	chart.getChartData().getCategories().clear();
	// Neue Kategorien hinzufügen
	chart.getChartData().getCategories().add(fact.getCell(0, 1, 0, "First Qtr"));
	chart.getChartData().getCategories().add(fact.getCell(0, 2, 0, "2nd Qtr"));
	chart.getChartData().getCategories().add(fact.getCell(0, 3, 0, "3rd Qtr"));
	// Neue Serie hinzufügen
	IChartSeries series = chart.getChartData().getSeries().add(fact.getCell(0, 0, 1, "Series 1"), chart.getType());
	// Jetzt werden Seriendaten ausgefüllt
	series.getDataPoints().addDataPointForPieSeries(fact.getCell(defaultWorksheetIndex, 1, 1, 20));
	series.getDataPoints().addDataPointForPieSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 50));
	series.getDataPoints().addDataPointForPieSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 30));
	series.getParentSeriesGroup().setColorVaried(true);
	presentation.save(dataDir + "Pie.pptx", SaveFormat.Pptx);
}
finally
{
	if (presentation != null) presentation.dispose();
}
```

## Abschluss

Sie haben mit Aspose.Slides für Java erfolgreich ein Kreisdiagramm in einer PowerPoint-Präsentation erstellt und es so konfiguriert, dass es automatische Segmentfarben hat. Diese Schritt-für-Schritt-Anleitung stellt Ihnen den notwendigen Quellcode zur Verfügung, um dies zu erreichen. Sie können das Diagramm und die Präsentation nach Bedarf weiter anpassen.

## FAQs

### Wie kann ich die Farben einzelner Segmente im Kreisdiagramm anpassen?

 Um die Farben einzelner Abschnitte im Kreisdiagramm anzupassen, können Sie die verwenden`getAutomaticSeriesColors`-Methode, um das Standardfarbschema abzurufen und dann die Farben nach Bedarf zu ändern. Hier ist ein Beispiel:

```java
// Rufen Sie das Standardfarbschema ab
IColorFormatCollection colors = chart.getChartData().getSeries().get_Item(0).getAutomaticSeriesColors();

// Ändern Sie die Farben nach Bedarf
colors.get_Item(0).setColor(Color.RED); // Stellen Sie die Farbe des ersten Slice auf Rot ein
colors.get_Item(1).setColor(Color.BLUE); // Stellen Sie die Farbe des zweiten Segments auf Blau ein
// Fügen Sie nach Bedarf weitere Farbmodifikationen hinzu
```

### Wie kann ich dem Kreisdiagramm eine Legende hinzufügen?

 Um dem Kreisdiagramm eine Legende hinzuzufügen, können Sie die verwenden`getLegend` Methode und konfigurieren Sie sie wie folgt:

```java
ILegend legend = chart.getLegend();
legend.setPosition(LegendPositionType.Right); // Legen Sie die Position der Legende fest
legend.setOverlay(true); // Zeigen Sie die Legende über dem Diagramm an
```

### Kann ich die Schriftart und den Stil des Titels ändern?

Ja, Sie können die Schriftart und den Stil des Titels ändern. Verwenden Sie den folgenden Code, um die Schriftart und den Stil des Titels festzulegen:

```java
chart.getChartTitle().getTextFrameForOverriding().getParagraphs().get_Item(0).getPortions().get_Item(0).getPortionFormat().setFontHeight(20); // Schriftgröße festlegen
chart.getChartTitle().getTextFrameForOverriding().getParagraphs().get_Item(0).getPortions().get_Item(0).getPortionFormat().setFontBold(NullableBool.True); // Machen Sie den Titel fett
chart.getChartTitle().getTextFrameForOverriding().getParagraphs().get_Item(0).getPortions().get_Item(0).getPortionFormat().setFontItalic(NullableBool.True); // Machen Sie den Titel kursiv
```

Sie können die Schriftgröße, Fettschrift und Kursivschrift nach Bedarf anpassen.