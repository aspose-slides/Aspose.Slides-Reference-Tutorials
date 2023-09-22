---
title: Verwalten Sie Eigenschaftsdiagramme in Java-Folien
linktitle: Verwalten Sie Eigenschaftsdiagramme in Java-Folien
second_title: Aspose.Slides Java PowerPoint-Verarbeitungs-API
description: Erfahren Sie, wie Sie mit Aspose.Slides beeindruckende Diagramme erstellen und Eigenschaften in Java-Folien verwalten. Schritt-für-Schritt-Anleitung mit Quellcode für wirkungsvolle Präsentationen.
type: docs
weight: 13
url: /de/java/data-manipulation/manage-properties-charts-java-slides/
---

## Einführung in die Verwaltung von Eigenschaften und Diagrammen in Java Slides mit Aspose.Slides

In diesem Tutorial erfahren Sie, wie Sie mit Aspose.Slides Eigenschaften verwalten und Diagramme in Java-Folien erstellen. Aspose.Slides ist eine leistungsstarke Java-API für die Arbeit mit PowerPoint-Präsentationen. Wir werden den Prozess Schritt für Schritt durchgehen, einschließlich Quellcodebeispielen.

## Voraussetzungen

 Bevor wir beginnen, stellen Sie sicher, dass die Aspose.Slides-Bibliothek für Java in Ihrem Projekt installiert und eingerichtet ist. Sie können es herunterladen unter[Hier](https://releases.aspose.com/slides/java/).

## Hinzufügen eines Diagramms zu einer Folie

Gehen Sie folgendermaßen vor, um einer Folie ein Diagramm hinzuzufügen:

1. Importieren Sie die erforderlichen Klassen und erstellen Sie eine Instanz der Presentation-Klasse.

```java
// Erstellen Sie eine Instanz der Presentation-Klasse
Presentation presentation = new Presentation();
```

2. Rufen Sie die Folie auf, auf der Sie das Diagramm hinzufügen möchten. In diesem Beispiel greifen wir auf die erste Folie zu.

```java
// Greifen Sie auf die erste Folie zu
ISlide slide = presentation.getSlides().get_Item(0);
```

3. Fügen Sie ein Diagramm mit Standarddaten hinzu. In diesem Fall fügen wir ein StackedColumn3D-Diagramm hinzu.

```java
// Diagramm mit Standarddaten hinzufügen
IChart chart = slide.getShapes().addChart(ChartType.StackedColumn3D, 0, 0, 500, 500);
```

## Festlegen von Diagrammdaten

Um die Diagrammdaten festzulegen, müssen wir eine Diagrammdaten-Arbeitsmappe erstellen und Serien und Kategorien hinzufügen. Folge diesen Schritten:

4. Legen Sie den Index des Diagrammdatenblatts fest.

```java
// Festlegen des Index des Diagrammdatenblatts
int defaultWorksheetIndex = 0;
```

5. Holen Sie sich die Diagrammdaten-Arbeitsmappe.

```java
// Abrufen des Diagrammdaten-Arbeitsblatts
IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
```

6. Fügen Sie dem Diagramm Reihen hinzu. In diesem Beispiel fügen wir zwei Serien mit den Namen „Serie 1“ und „Serie 2“ hinzu.

```java
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 1, "Series 1"), chart.getType());
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 2, "Series 2"), chart.getType());
```

7. Fügen Sie dem Diagramm Kategorien hinzu. Hier fügen wir drei Kategorien hinzu.

```java
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 1, 0, "Category 1"));
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 2, 0, "Category 2"));
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 3, 0, "Category 3"));
```

## Festlegen der 3D-Rotationseigenschaften

Legen wir nun die 3D-Rotationseigenschaften für das Diagramm fest:

8. Stellen Sie die rechten Winkelachsen ein.

```java
chart.getRotation3D().setRightAngleAxes(true);
```

9. Legen Sie die Drehwinkel für die X- und Y-Achse fest. In diesem Beispiel drehen wir X um 40 Grad und Y um 270 Grad.

```java
chart.getRotation3D().setRotationX((byte) 40);
chart.getRotation3D().setRotationY(270);
```

10. Stellen Sie den Tiefenprozentsatz auf 150 ein.

```java
chart.getRotation3D().setDepthPercents(150);
```

## Auffüllen von Seriendaten

11. Nehmen Sie die zweite Diagrammreihe und füllen Sie sie mit Datenpunkten.

```java
IChartSeries series = chart.getChartData().getSeries().get_Item(1);

// Füllen Sie Seriendaten aus
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 1, 20));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 50));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 30));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 2, 30));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 2, 10));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 2, 60));
```

## Überlappung anpassen

12. Legen Sie den Überlappungswert für Serien fest. Sie können ihn beispielsweise auf 100 einstellen, damit keine Überlappung auftritt.

```java
series.getParentSeriesGroup().setOverlap((byte) 100);
```

## Speichern der Präsentation

Speichern Sie abschließend die Präsentation auf der Festplatte.

```java
presentation.save(dataDir + "Rotation3D_out.pptx", SaveFormat.Pptx);
```

Das ist es! Sie haben mit Aspose.Slides in Java erfolgreich ein gestapeltes 3D-Säulendiagramm mit benutzerdefinierten Eigenschaften erstellt.

## Vollständiger Quellcode zum Verwalten von Eigenschaftsdiagrammen in Java-Folien

```java
// Der Pfad zum Dokumentenverzeichnis.
String dataDir = "Your Document Directory";
// Erstellen Sie eine Instanz der Presentation-Klasse
Presentation presentation = new Presentation();
// Greifen Sie auf die erste Folie zu
ISlide slide = presentation.getSlides().get_Item(0);
// Diagramm mit Standarddaten hinzufügen
IChart chart = slide.getShapes().addChart(ChartType.StackedColumn3D, 0, 0, 500, 500);
// Festlegen des Index des Diagrammdatenblatts
int defaultWorksheetIndex = 0;
// Abrufen des Diagrammdaten-Arbeitsblatts
IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
// Serie hinzufügen
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 1, "Series 1"), chart.getType());
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 2, "Series 2"), chart.getType());
// Kategorien hinzufügen
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 1, 0, "Caetegoty 1"));
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 2, 0, "Caetegoty 2"));
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 3, 0, "Caetegoty 3"));
// Legen Sie Rotation3D-Eigenschaften fest
chart.getRotation3D().setRightAngleAxes(true);
chart.getRotation3D().setRotationX((byte) 40);
chart.getRotation3D().setRotationY(270);
chart.getRotation3D().setDepthPercents(150);
// Nehmen Sie die zweite Chartserie
IChartSeries series = chart.getChartData().getSeries().get_Item(1);
// Jetzt werden Seriendaten ausgefüllt
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 1, 20));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 50));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 30));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 2, 30));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 2, 10));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 2, 60));
// Legen Sie den OverLap-Wert fest
series.getParentSeriesGroup().setOverlap((byte) 100);
// Präsentation auf Diskette schreiben
presentation.save(dataDir + "Rotation3D_out.pptx", SaveFormat.Pptx);
```

## Abschluss

In diesem Tutorial haben wir uns mit der Welt der Verwaltung von Eigenschaften und der Erstellung von Diagrammen in Java-Folien mithilfe von Aspose.Slides befasst. Aspose.Slides ist eine robuste Java-API, die es Entwicklern ermöglicht, effizient mit PowerPoint-Präsentationen zu arbeiten. Wir haben die wesentlichen Schritte erläutert und Quellcodebeispiele bereitgestellt, um Sie durch den Prozess zu führen.

## FAQs

### Wie kann ich den Diagrammtyp ändern?

 Sie können den Diagrammtyp ändern, indem Sie die ändern`ChartType`Parameter beim Hinzufügen des Diagramms. Informationen zu den verfügbaren Diagrammtypen finden Sie in der Aspose.Slides-Dokumentation.

### Kann ich die Diagrammfarben anpassen?

Ja, Sie können die Diagrammfarben anpassen, indem Sie die Fülleigenschaften von Seriendatenpunkten oder -kategorien festlegen.

### Wie füge ich einer Serie weitere Datenpunkte hinzu?

 Sie können einer Reihe weitere Datenpunkte hinzufügen, indem Sie verwenden`series.getDataPoints().addDataPointForBarSeries()` -Methode und Angabe der Zelle, die den Datenwert enthält.

### Wie kann ich einen anderen Drehwinkel einstellen?

 Um einen anderen Drehwinkel für die X- und Y-Achse festzulegen, verwenden Sie`chart.getRotation3D().setRotationX()` Und`chart.getRotation3D().setRotationY()` mit den gewünschten Winkelwerten.

### Welche anderen 3D-Eigenschaften kann ich anpassen?

Weitere 3D-Eigenschaften des Diagramms wie Tiefe, Perspektive und Beleuchtung können Sie in der Aspose.Slides-Dokumentation erkunden.