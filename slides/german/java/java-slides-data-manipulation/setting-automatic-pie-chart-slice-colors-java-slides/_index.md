---
title: Festlegen automatischer Kreisdiagrammsegmentfarben in Java-Folien
linktitle: Festlegen automatischer Kreisdiagrammsegmentfarben in Java-Folien
second_title: Aspose.Slides Java PowerPoint-Verarbeitungs-API
description: Erfahren Sie, wie Sie mit Aspose.Slides für Java dynamische Kreisdiagramme mit automatischen Segmentfarben in Java PowerPoint-Präsentationen erstellen. Schritt-für-Schritt-Anleitung mit Quellcode.
weight: 24
url: /de/java/data-manipulation/setting-automatic-pie-chart-slice-colors-java-slides/
---

{< blocks/products/pf/main-wrap-class >}
{< blocks/products/pf/main-container >}
{< blocks/products/pf/tutorial-page-section >}


## Einführung in das Festlegen automatischer Kreisdiagrammsegmentfarben in Java-Folien

In diesem Tutorial erfahren Sie, wie Sie mit Aspose.Slides für Java ein Kreisdiagramm in einer PowerPoint-Präsentation erstellen und automatische Segmentfarben für das Diagramm festlegen. Wir stellen Ihnen eine Schritt-für-Schritt-Anleitung zusammen mit dem Quellcode zur Verfügung.

## Voraussetzungen

 Bevor Sie beginnen, stellen Sie sicher, dass Sie die Bibliothek Aspose.Slides für Java in Ihrem Java-Projekt installiert und eingerichtet haben. Sie können die Bibliothek von der Aspose-Website herunterladen:[Laden Sie Aspose.Slides für Java herunter](https://releases.aspose.com/slides/java/).

## Schritt 1: Erforderliche Pakete importieren

Zuerst müssen Sie die erforderlichen Pakete von Aspose.Slides für Java importieren:

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

 Instanziieren Sie den`Presentation` Klasse zum Erstellen einer neuen PowerPoint-Präsentation:

```java
String dataDir = "Your Document Directory";
Presentation presentation = new Presentation();
```

## Schritt 3: Eine Folie hinzufügen

Rufen Sie die erste Folie der Präsentation auf und fügen Sie ihr ein Diagramm mit Standarddaten hinzu:

```java
ISlide slide = presentation.getSlides().get_Item(0);
IChart chart = slide.getShapes().addChart(ChartType.Pie, 100, 100, 400, 400);
```

## Schritt 4: Diagrammtitel festlegen

Legen Sie einen Titel für das Diagramm fest:

```java
chart.getChartTitle().addTextFrameForOverriding("Sample Title");
chart.getChartTitle().getTextFrameForOverriding().getTextFrameFormat().setCenterText(NullableBool.True);
chart.getChartTitle().setHeight(20);
chart.setTitle(true);
```

## Schritt 5: Diagrammdaten konfigurieren

Legen Sie im Diagramm fest, ob die Werte für die erste Reihe angezeigt werden sollen, und konfigurieren Sie die Diagrammdaten:

```java
chart.getChartData().getSeries().get_Item(0).getLabels().getDefaultDataLabelFormat().setShowValue(true);

int defaultWorksheetIndex = 0;
IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
chart.getChartData().getSeries().clear();
chart.getChartData().getCategories().clear();
```

## Schritt 6: Kategorien und Serien hinzufügen

Fügen Sie dem Diagramm neue Kategorien und Reihen hinzu:

```java
chart.getChartData().getCategories().add(fact.getCell(0, 1, 0, "First Qtr"));
chart.getChartData().getCategories().add(fact.getCell(0, 2, 0, "2nd Qtr"));
chart.getChartData().getCategories().add(fact.getCell(0, 3, 0, "3rd Qtr"));

IChartSeries series = chart.getChartData().getSeries().add(fact.getCell(0, 0, 1, "Series 1"), chart.getType());
```

## Schritt 7: Datenreihe auffüllen

Füllen Sie die Reihendaten für das Kreisdiagramm auf:

```java
series.getDataPoints().addDataPointForPieSeries(fact.getCell(defaultWorksheetIndex, 1, 1, 20));
series.getDataPoints().addDataPointForPieSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 50));
series.getDataPoints().addDataPointForPieSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 30));
```

## Schritt 8: Verschiedene Slice-Farben aktivieren

Aktivieren Sie verschiedene Segmentfarben für das Kreisdiagramm:

```java
series.getParentSeriesGroup().setColorVaried(true);
```

## Schritt 9: Speichern Sie die Präsentation

Speichern Sie die Präsentation abschließend als PowerPoint-Datei:

```java
presentation.save(dataDir + "Pie.pptx", SaveFormat.Pptx);
```

## Vollständiger Quellcode zum Festlegen automatischer Kreisdiagrammsegmentfarben in Java-Folien

```java
// Der Pfad zum Dokumentverzeichnis.
String dataDir = "Your Document Directory";
// Instanziieren Sie die Präsentationsklasse, die die PPTX-Datei darstellt
Presentation presentation = new Presentation();
try
{
	// Zur ersten Folie
	ISlide slides = presentation.getSlides().get_Item(0);
	// Diagramm mit Standarddaten hinzufügen
	IChart chart = slides.getShapes().addChart(ChartType.Pie, 100, 100, 400, 400);
	// Diagrammtitel festlegen
	chart.getChartTitle().addTextFrameForOverriding("Sample Title");
	chart.getChartTitle().getTextFrameForOverriding().getTextFrameFormat().setCenterText(NullableBool.True);
	chart.getChartTitle().setHeight(20);
	chart.setTitle(true);
	// Stellen Sie die erste Serie auf „Werte anzeigen“ ein.
	chart.getChartData().getSeries().get_Item(0).getLabels().getDefaultDataLabelFormat().setShowValue(true);
	// Festlegen des Indexes des Diagrammdatenblattes
	int defaultWorksheetIndex = 0;
	// Abrufen des Arbeitsblatts mit den Diagrammdaten
	IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
	// Standardmäßig generierte Serien und Kategorien löschen
	chart.getChartData().getSeries().clear();
	chart.getChartData().getCategories().clear();
	// Neue Kategorien hinzufügen
	chart.getChartData().getCategories().add(fact.getCell(0, 1, 0, "First Qtr"));
	chart.getChartData().getCategories().add(fact.getCell(0, 2, 0, "2nd Qtr"));
	chart.getChartData().getCategories().add(fact.getCell(0, 3, 0, "3rd Qtr"));
	// Neue Serien hinzufügen
	IChartSeries series = chart.getChartData().getSeries().add(fact.getCell(0, 0, 1, "Series 1"), chart.getType());
	// Jetzt werden Seriendaten gefüllt
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

Sie haben erfolgreich ein Kreisdiagramm in einer PowerPoint-Präsentation mit Aspose.Slides für Java erstellt und es so konfiguriert, dass die Segmentfarben automatisch angezeigt werden. Diese Schritt-für-Schritt-Anleitung liefert Ihnen den dafür erforderlichen Quellcode. Sie können das Diagramm und die Präsentation nach Bedarf weiter anpassen.

## Häufig gestellte Fragen

### Wie kann ich die Farben einzelner Segmente im Kreisdiagramm anpassen?

 Um die Farben einzelner Segmente im Kreisdiagramm anzupassen, können Sie die`getAutomaticSeriesColors` Methode, um das Standardfarbschema abzurufen und die Farben dann nach Bedarf zu ändern. Hier ist ein Beispiel:

```java
//Abrufen des Standardfarbschemas
IColorFormatCollection colors = chart.getChartData().getSeries().get_Item(0).getAutomaticSeriesColors();

// Ändern Sie die Farben nach Bedarf
colors.get_Item(0).setColor(Color.RED); // Stellen Sie die Farbe des ersten Segments auf Rot ein.
colors.get_Item(1).setColor(Color.BLUE); // Stellen Sie die Farbe des zweiten Slices auf Blau ein
// Fügen Sie bei Bedarf weitere Farbänderungen hinzu
```

### Wie kann ich dem Kreisdiagramm eine Legende hinzufügen?

 Um dem Kreisdiagramm eine Legende hinzuzufügen, können Sie das`getLegend` Methode und konfigurieren Sie sie wie folgt:

```java
ILegend legend = chart.getLegend();
legend.setPosition(LegendPositionType.Right); // Festlegen der Legendenposition
legend.setOverlay(true); // Zeigen Sie die Legende über dem Diagramm an
```

### Kann ich Schriftart und Stil des Titels ändern?

Ja, Sie können die Schriftart und den Stil des Titels ändern. Verwenden Sie den folgenden Code, um die Schriftart und den Stil des Titels festzulegen:

```java
chart.getChartTitle().getTextFrameForOverriding().getParagraphs().get_Item(0).getPortions().get_Item(0).getPortionFormat().setFontHeight(20); // Schriftgröße festlegen
chart.getChartTitle().getTextFrameForOverriding().getParagraphs().get_Item(0).getPortions().get_Item(0).getPortionFormat().setFontBold(NullableBool.True); // Machen Sie den Titel fett
chart.getChartTitle().getTextFrameForOverriding().getParagraphs().get_Item(0).getPortions().get_Item(0).getPortionFormat().setFontItalic(NullableBool.True); // Den Titel kursiv machen
```

Sie können die Schriftgröße, Fettschrift und Kursivschrift nach Bedarf anpassen.
{< /blocks/products/pf/tutorial-page-section >}

{< /blocks/products/pf/main-container >}
{< /blocks/products/pf/main-wrap-class >}

{< blocks/products/products-backtop-button >}
