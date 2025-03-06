---
title: Verwalten von Eigenschaftsdiagrammen in Java-Folien
linktitle: Verwalten von Eigenschaftsdiagrammen in Java-Folien
second_title: Aspose.Slides Java PowerPoint-Verarbeitungs-API
description: Erfahren Sie, wie Sie mit Aspose.Slides beeindruckende Diagramme erstellen und Eigenschaften in Java-Folien verwalten. Schritt-für-Schritt-Anleitung mit Quellcode für wirkungsvolle Präsentationen.
weight: 13
url: /de/java/data-manipulation/manage-properties-charts-java-slides/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Verwalten von Eigenschaftsdiagrammen in Java-Folien


## Einführung in die Verwaltung von Eigenschaften und Diagrammen in Java-Folien mit Aspose.Slides

In diesem Tutorial erfahren Sie, wie Sie mit Aspose.Slides Eigenschaften verwalten und Diagramme in Java-Folien erstellen. Aspose.Slides ist eine leistungsstarke Java-API für die Arbeit mit PowerPoint-Präsentationen. Wir werden den Prozess Schritt für Schritt durchgehen, einschließlich Quellcodebeispielen.

## Voraussetzungen

Bevor wir beginnen, stellen Sie sicher, dass Sie die Aspose.Slides-Bibliothek für Java installiert und in Ihrem Projekt eingerichtet haben. Sie können sie hier herunterladen:[Hier](https://releases.aspose.com/slides/java/).

## Hinzufügen eines Diagramms zu einer Folie

Um einer Folie ein Diagramm hinzuzufügen, gehen Sie folgendermaßen vor:

1. Importieren Sie die erforderlichen Klassen und erstellen Sie eine Instanz der Präsentationsklasse.

```java
// Erstellen Sie eine Instanz der Präsentationsklasse
Presentation presentation = new Presentation();
```

2. Greifen Sie auf die Folie zu, auf der Sie das Diagramm hinzufügen möchten. In diesem Beispiel greifen wir auf die erste Folie zu.

```java
// Zur ersten Folie
ISlide slide = presentation.getSlides().get_Item(0);
```

3. Fügen Sie ein Diagramm mit Standarddaten hinzu. In diesem Fall fügen wir ein StackedColumn3D-Diagramm hinzu.

```java
// Diagramm mit Standarddaten hinzufügen
IChart chart = slide.getShapes().addChart(ChartType.StackedColumn3D, 0, 0, 500, 500);
```

## Festlegen der Diagrammdaten

Um die Diagrammdaten festzulegen, müssen wir eine Diagrammdaten-Arbeitsmappe erstellen und Reihen und Kategorien hinzufügen. Folgen Sie diesen Schritten:

4. Legt den Index des Diagrammdatenblatts fest.

```java
// Festlegen des Indexes des Diagrammdatenblattes
int defaultWorksheetIndex = 0;
```

5. Holen Sie sich die Arbeitsmappe mit den Diagrammdaten.

```java
// Abrufen des Arbeitsblatts mit den Diagrammdaten
IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
```

6. Fügen Sie dem Diagramm Reihen hinzu. In diesem Beispiel fügen wir zwei Reihen mit den Namen „Reihe 1“ und „Reihe 2“ hinzu.

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

Lassen Sie uns nun die 3D-Rotationseigenschaften für das Diagramm festlegen:

8. Stellen Sie die Achsen mit dem rechten Winkel ein.

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

// Auffüllen von Reihendaten
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 1, 20));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 50));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 30));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 2, 30));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 2, 10));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 2, 60));
```

## Überlappung anpassen

12. Legen Sie den Überlappungswert für Reihen fest. Sie können ihn beispielsweise auf 100 setzen, um keine Überlappung zu erreichen.

```java
series.getParentSeriesGroup().setOverlap((byte) 100);
```

## Speichern der Präsentation

Speichern Sie die Präsentation abschließend auf der Festplatte.

```java
presentation.save(dataDir + "Rotation3D_out.pptx", SaveFormat.Pptx);
```

Das ist es! Sie haben erfolgreich ein gestapeltes 3D-Säulendiagramm mit benutzerdefinierten Eigenschaften mit Aspose.Slides in Java erstellt.

## Vollständiger Quellcode zum Verwalten von Eigenschaftendiagrammen in Java-Folien

```java
// Der Pfad zum Dokumentverzeichnis.
String dataDir = "Your Document Directory";
// Erstellen Sie eine Instanz der Präsentationsklasse
Presentation presentation = new Presentation();
// Zur ersten Folie
ISlide slide = presentation.getSlides().get_Item(0);
// Diagramm mit Standarddaten hinzufügen
IChart chart = slide.getShapes().addChart(ChartType.StackedColumn3D, 0, 0, 500, 500);
// Festlegen des Indexes des Diagrammdatenblattes
int defaultWorksheetIndex = 0;
// Abrufen des Arbeitsblatts mit den Diagrammdaten
IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
// Serie hinzufügen
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 1, "Series 1"), chart.getType());
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 2, "Series 2"), chart.getType());
// Kategorien hinzufügen
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 1, 0, "Caetegoty 1"));
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 2, 0, "Caetegoty 2"));
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 3, 0, "Caetegoty 3"));
// Rotation3D-Eigenschaften festlegen
chart.getRotation3D().setRightAngleAxes(true);
chart.getRotation3D().setRotationX((byte) 40);
chart.getRotation3D().setRotationY(270);
chart.getRotation3D().setDepthPercents(150);
// Nehmen Sie die zweite Diagrammreihe
IChartSeries series = chart.getChartData().getSeries().get_Item(1);
// Jetzt werden Seriendaten gefüllt
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 1, 20));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 50));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 30));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 2, 30));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 2, 10));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 2, 60));
// OverLap-Wert festlegen
series.getParentSeriesGroup().setOverlap((byte) 100);
// Präsentation auf Festplatte schreiben
presentation.save(dataDir + "Rotation3D_out.pptx", SaveFormat.Pptx);
```

## Abschluss

In diesem Tutorial haben wir uns mit der Verwaltung von Eigenschaften und der Erstellung von Diagrammen in Java-Folien mithilfe von Aspose.Slides befasst. Aspose.Slides ist eine robuste Java-API, die Entwicklern die effiziente Arbeit mit PowerPoint-Präsentationen ermöglicht. Wir haben die wesentlichen Schritte erläutert und Quellcodebeispiele bereitgestellt, um Sie durch den Prozess zu führen.

## Häufig gestellte Fragen

### Wie kann ich den Diagrammtyp ändern?

 Sie können den Diagrammtyp ändern, indem Sie die`ChartType` Parameter beim Hinzufügen des Diagramms. Informationen zu verfügbaren Diagrammtypen finden Sie in der Aspose.Slides-Dokumentation.

### Kann ich die Diagrammfarben anpassen?

Ja, Sie können die Diagrammfarben anpassen, indem Sie die Fülleigenschaften von Seriendatenpunkten oder Kategorien festlegen.

### Wie füge ich einer Reihe weitere Datenpunkte hinzu?

 Sie können einer Reihe weitere Datenpunkte hinzufügen, indem Sie das`series.getDataPoints().addDataPointForBarSeries()` -Methode und Angabe der Zelle, die den Datenwert enthält.

### Wie kann ich einen anderen Drehwinkel einstellen?

 Um einen anderen Drehwinkel für die X- und Y-Achse einzustellen, verwenden Sie`chart.getRotation3D().setRotationX()` Und`chart.getRotation3D().setRotationY()` mit den gewünschten Winkelwerten.

### Welche anderen 3D-Eigenschaften kann ich anpassen?

Sie können andere 3D-Eigenschaften des Diagramms, wie Tiefe, Perspektive und Beleuchtung, erkunden, indem Sie die Aspose.Slides-Dokumentation zu Rate ziehen.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
