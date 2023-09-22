---
title: Kreisdiagramm in Java-Folien
linktitle: Kreisdiagramm in Java-Folien
second_title: Aspose.Slides Java PowerPoint-Verarbeitungs-API
description: Erfahren Sie, wie Sie mit Aspose.Slides für Java beeindruckende Kreisdiagramme in PowerPoint-Präsentationen erstellen. Schritt-für-Schritt-Anleitung mit Quellcode für Java-Entwickler.
type: docs
weight: 23
url: /de/java/chart-data-manipulation/pie-chart-java-slides/
---

## Einführung in die Erstellung eines Kreisdiagramms in Java Slides mit Aspose.Slides

In diesem Tutorial zeigen wir, wie Sie mit Aspose.Slides für Java ein Kreisdiagramm in einer PowerPoint-Präsentation erstellen. Wir stellen Ihnen Schritt-für-Schritt-Anleitungen und Java-Quellcode zur Verfügung, um Ihnen den Einstieg zu erleichtern. In diesem Handbuch wird davon ausgegangen, dass Sie Ihre Entwicklungsumgebung bereits mit Aspose.Slides für Java eingerichtet haben.

## Voraussetzungen

 Bevor Sie beginnen, stellen Sie sicher, dass die Aspose.Slides for Java-Bibliothek in Ihrem Projekt installiert und konfiguriert ist. Sie können es herunterladen unter[Hier](https://releases.aspose.com/slides/java/).

## Schritt 1: Erforderliche Bibliotheken importieren

```java
import com.aspose.slides.*;
import com.aspose.slides.charts.*;
```

Stellen Sie sicher, dass Sie die erforderlichen Klassen aus der Aspose.Slides-Bibliothek importieren.

## Schritt 2: Initialisieren Sie die Präsentation

```java
// Der Pfad zum Dokumentenverzeichnis.
String dataDir = "Your Document Directory";

// Instanziieren Sie die Präsentationsklasse, die eine PPTX-Datei darstellt
Presentation presentation = new Presentation();
```

 Erstellen Sie ein neues Präsentationsobjekt zur Darstellung Ihrer PowerPoint-Datei. Ersetzen`"Your Document Directory"` mit dem tatsächlichen Pfad, in dem Sie die Präsentation speichern möchten.

## Schritt 3: Fügen Sie eine Folie hinzu

```java
// Greifen Sie auf die erste Folie zu
ISlide slide = presentation.getSlides().get_Item(0);
```

Holen Sie sich die erste Folie der Präsentation, auf der Sie das Kreisdiagramm hinzufügen möchten.

## Schritt 4: Fügen Sie ein Kreisdiagramm hinzu

```java
// Fügen Sie ein Kreisdiagramm mit Standarddaten hinzu
IChart chart = slide.getShapes().addChart(ChartType.Pie, 100, 100, 400, 400);
```

Fügen Sie der Folie an der angegebenen Position und Größe ein Kreisdiagramm hinzu.

## Schritt 5: Legen Sie den Diagrammtitel fest

```java
// Diagrammtitel festlegen
chart.getChartTitle().addTextFrameForOverriding("Sample Title");
chart.getChartTitle().getTextFrameForOverriding().getTextFrameFormat().setCenterText(NullableBool.True);
chart.getChartTitle().setHeight(20);
chart.setTitle(true);
```

Legen Sie einen Titel für das Kreisdiagramm fest. Sie können den Titel nach Bedarf anpassen.

## Schritt 6: Diagrammdaten anpassen

```java
// Legen Sie die erste Reihe so fest, dass Werte angezeigt werden
chart.getChartData().getSeries().get_Item(0).getLabels().getDefaultDataLabelFormat().setShowValue(true);

// Festlegen des Index des Diagrammdatenblatts
int defaultWorksheetIndex = 0;

// Abrufen des Diagrammdaten-Arbeitsblatts
IChartDataWorkbook workbook = chart.getChartData().getChartDataWorkbook();

// Standardmäßig generierte Serien und Kategorien löschen
chart.getChartData().getSeries().clear();
chart.getChartData().getCategories().clear();

// Neue Kategorien hinzufügen
chart.getChartData().getCategories().add(workbook.getCell(0, 1, 0, "First Qtr"));
chart.getChartData().getCategories().add(workbook.getCell(0, 2, 0, "2nd Qtr"));
chart.getChartData().getCategories().add(workbook.getCell(0, 3, 0, "3rd Qtr"));

// Neue Serie hinzufügen
IChartSeries series = chart.getChartData().getSeries().add(workbook.getCell(0, 0, 1, "Series 1"), chart.getType());

// Auffüllen von Seriendaten
series.getDataPoints().addDataPointForPieSeries(workbook.getCell(defaultWorksheetIndex, 1, 1, 20));
series.getDataPoints().addDataPointForPieSeries(workbook.getCell(defaultWorksheetIndex, 2, 1, 50));
series.getDataPoints().addDataPointForPieSeries(workbook.getCell(defaultWorksheetIndex, 3, 1, 30));
```

Passen Sie die Diagrammdaten an, indem Sie Kategorien und Reihen hinzufügen und deren Werte festlegen. In diesem Beispiel haben wir drei Kategorien und eine Reihe mit entsprechenden Datenpunkten.

## Schritt 7: Kreisdiagrammsektoren anpassen

```java
// Sektorfarben festlegen
chart.getChartData().getSeriesGroups().get_Item(0).setColorVaried(true);

// Passen Sie das Erscheinungsbild jedes Sektors an
IChartDataPoint point1 = series.getDataPoints().get_Item(0);
point1.getFormat().getFill().setFillType(FillType.Solid);
point1.getFormat().getFill().getSolidFillColor().setColor(new Color(PresetColor.Cyan));
// Sektorgrenze anpassen
point1.getFormat().getLine().getFillFormat().setFillType(FillType.Solid);
point1.getFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.GRAY);
point1.getFormat().getLine().setWidth(3.0);
point1.getFormat().getLine().setStyle(LineStyle.ThinThick);
point1.getFormat().getLine().setDashStyle(LineDashStyle.DashDot);

//Passen Sie andere Sektoren auf ähnliche Weise an
```

Passen Sie das Erscheinungsbild jedes Sektors im Kreisdiagramm an. Sie können die Farben, Rahmenstile und andere visuelle Eigenschaften ändern.

## Schritt 8: Datenbeschriftungen anpassen

```java
// Passen Sie Datenbeschriftungen an
IDataLabel lbl1 = series.getDataPoints().get_Item(0).getLabel();
lbl1.getDataLabelFormat().setShowValue(true);

// Passen Sie Datenbeschriftungen für andere Datenpunkte auf ähnliche Weise an
```

Passen Sie Datenbeschriftungen für jeden Datenpunkt im Kreisdiagramm an. Sie können steuern, welche Werte im Diagramm angezeigt werden.

## Schritt 9: Führungslinien anzeigen

```java
// Führungslinien für das Diagramm anzeigen
series.getLabels().getDefaultDataLabelFormat().setShowLeaderLines(true);
```

Aktivieren Sie Führungslinien, um Datenbeschriftungen mit den entsprechenden Sektoren zu verbinden.

## Schritt 10: Legen Sie den Drehwinkel des Kreisdiagramms fest

```java
// Legen Sie den Drehwinkel für Kreisdiagrammsektoren fest
chart.getChartData().getSeriesGroups().get_Item(0).setFirstSliceAngle(180);
```

Legen Sie den Drehwinkel für die Kreisdiagrammsektoren fest. In diesem Beispiel stellen wir ihn auf 180 Grad ein.

## Schritt 11: Speichern Sie die Präsentation

```java
// Speichern Sie die Präsentation mit dem Kreisdiagramm
presentation.save(dataDir + "PieChart_out.pptx", SaveFormat.Pptx);
```

Speichern Sie die Präsentation mit dem Kreisdiagramm im angegebenen Verzeichnis.

## Vollständiger Quellcode für Kreisdiagramme in Java-Folien

```java
// Der Pfad zum Dokumentenverzeichnis.
String dataDir = "Your Document Directory";
// Instanziieren Sie die Präsentationsklasse, die eine PPTX-Datei darstellt
Presentation presentation = new Presentation();
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
// Abrufen des Diagrammdaten-Arbeitsblatts
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
//Funktioniert nicht in der neuen Version
// Neue Punkte hinzufügen und Sektorfarbe festlegen
// series.IsColorVaried = true;
chart.getChartData().getSeriesGroups().get_Item(0).setColorVaried(true);
IChartDataPoint point = series.getDataPoints().get_Item(0);
point.getFormat().getFill().setFillType(FillType.Solid);
point.getFormat().getFill().getSolidFillColor().setColor(new Color(PresetColor.Cyan));
// Sektorgrenze festlegen
point.getFormat().getLine().getFillFormat().setFillType(FillType.Solid);
point.getFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.GRAY);
point.getFormat().getLine().setWidth(3.0);
point.getFormat().getLine().setStyle(LineStyle.ThinThick);
point.getFormat().getLine().setDashStyle(LineDashStyle.DashDot);
IChartDataPoint point1 = series.getDataPoints().get_Item(1);
point1.getFormat().getFill().setFillType(FillType.Solid);
point1.getFormat().getFill().getSolidFillColor().setColor(new Color(PresetColor.Brown));
// Sektorgrenze festlegen
point1.getFormat().getLine().getFillFormat().setFillType(FillType.Solid);
point1.getFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.BLUE);
point1.getFormat().getLine().setWidth(3.0);
point1.getFormat().getLine().setStyle(LineStyle.Single);
point1.getFormat().getLine().setDashStyle(LineDashStyle.LargeDashDot);
IChartDataPoint point2 = series.getDataPoints().get_Item(2);
point2.getFormat().getFill().setFillType(FillType.Solid);
point2.getFormat().getFill().getSolidFillColor().setColor(new Color(PresetColor.Coral));
// Sektorgrenze festlegen
point2.getFormat().getLine().getFillFormat().setFillType(FillType.Solid);
point2.getFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.RED);
point2.getFormat().getLine().setWidth(2.0);
point2.getFormat().getLine().setStyle(LineStyle.ThinThin);
point2.getFormat().getLine().setDashStyle(LineDashStyle.LargeDashDotDot);
// Erstellen Sie benutzerdefinierte Beschriftungen für jede Kategorie für neue Serien
IDataLabel lbl1 = series.getDataPoints().get_Item(0).getLabel();
// lbl.setShowCategoryName(true);
lbl1.getDataLabelFormat().setShowValue(true);
IDataLabel lbl2 = series.getDataPoints().get_Item(1).getLabel();
lbl2.getDataLabelFormat().setShowValue(true);
lbl2.getDataLabelFormat().setShowLegendKey(true);
lbl2.getDataLabelFormat().setShowPercentage(true);
IDataLabel lbl3 = series.getDataPoints().get_Item(2).getLabel();
lbl3.getDataLabelFormat().setShowSeriesName(true);
lbl3.getDataLabelFormat().setShowPercentage(true);
// Führungslinien für das Diagramm werden angezeigt
series.getLabels().getDefaultDataLabelFormat().setShowLeaderLines(true);
// Festlegen des Rotationswinkels für Kreisdiagrammsektoren
chart.getChartData().getSeriesGroups().get_Item(0).setFirstSliceAngle(180);
// Präsentation mit Diagramm speichern
presentation.save(dataDir + "PieChart_out.pptx", SaveFormat.Pptx);
```

## Abschluss

Sie haben mit Aspose.Slides für Java erfolgreich ein Kreisdiagramm in einer PowerPoint-Präsentation erstellt. Sie können das Erscheinungsbild und die Datenbeschriftungen des Diagramms entsprechend Ihren spezifischen Anforderungen anpassen. Dieses Tutorial bietet ein einfaches Beispiel. Sie können Ihre Diagramme nach Bedarf weiter verbessern und anpassen.

## FAQs

### Wie kann ich die Farben einzelner Sektoren im Kreisdiagramm ändern?

 Um die Farben einzelner Sektoren im Kreisdiagramm zu ändern, können Sie die Füllfarbe für jeden Datenpunkt anpassen. Im bereitgestellten Codebeispiel haben wir gezeigt, wie Sie die Füllfarbe für jeden Sektor mithilfe von festlegen`getSolidFillColor().setColor()`Methode. Sie können die Farbwerte ändern, um das gewünschte Erscheinungsbild zu erzielen.

### Kann ich dem Kreisdiagramm weitere Kategorien und Datenreihen hinzufügen?

 Ja, Sie können dem Kreisdiagramm zusätzliche Kategorien und Datenreihen hinzufügen. Dazu können Sie die verwenden`getChartData().getCategories().add()` Und`getChartData().getSeries().add()` Methoden, wie im Beispiel gezeigt. Geben Sie einfach die entsprechenden Daten und Beschriftungen für die neuen Kategorien und Reihen ein, um Ihr Diagramm zu erweitern.

### Wie kann ich das Erscheinungsbild von Datenbeschriftungen anpassen?

 Sie können das Erscheinungsbild von Datenbeschriftungen mithilfe von anpassen`getDataLabelFormat()` Methode auf der Beschriftung jedes Datenpunkts. Im Beispiel haben wir gezeigt, wie der Wert auf Datenetiketten angezeigt wird`getDataLabelFormat().setShowValue(true)`. Sie können Datenbeschriftungen weiter anpassen, indem Sie steuern, welche Werte angezeigt werden, Legendenschlüssel anzeigen und andere Formatierungsoptionen anpassen.

### Kann ich den Titel des Kreisdiagramms ändern?

 Ja, Sie können den Titel des Kreisdiagramms ändern. Im bereitgestellten Code legen wir den Diagrammtitel mit fest`chart.getChartTitle().addTextFrameForOverriding("Sample Title")` . Sie können ersetzen`"Sample Title"` mit Ihrem Wunschtiteltext.

### Wie speichere ich die generierte Präsentation mit dem Kreisdiagramm?

 Um die Präsentation mit dem Kreisdiagramm zu speichern, verwenden Sie die`presentation.save()` Methode. Geben Sie den gewünschten Dateipfad und -namen sowie das Format an, in dem Sie die Präsentation speichern möchten. Zum Beispiel:
```java
presentation.save(dataDir + "PieChart_out.pptx", SaveFormat.Pptx);
```

Stellen Sie sicher, dass Sie den richtigen Dateipfad und das richtige Format angeben.

### Kann ich mit Aspose.Slides für Java andere Diagrammtypen erstellen?

 Ja, Aspose.Slides für Java unterstützt verschiedene Diagrammtypen, darunter Balkendiagramme, Liniendiagramme und mehr. Sie können verschiedene Diagrammtypen erstellen, indem Sie die ändern`ChartType` beim Hinzufügen eines Diagramms. Weitere Informationen zum Erstellen verschiedener Diagrammtypen finden Sie in der Aspose.Slides-Dokumentation.

### Wie finde ich weitere Informationen und Beispiele für die Arbeit mit Aspose.Slides für Java?

 Weitere Informationen, ausführliche Dokumentation und zusätzliche Beispiele finden Sie unter[Aspose.Slides für Java-Dokumentation](https://reference.aspose.com/slides/java/). Es bietet umfassende Ressourcen, die Ihnen bei der effektiven Nutzung der Bibliothek helfen.