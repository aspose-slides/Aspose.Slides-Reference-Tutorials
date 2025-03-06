---
title: Kartendiagramm in Java-Folien
linktitle: Kartendiagramm in Java-Folien
second_title: Aspose.Slides Java PowerPoint-Verarbeitungs-API
description: Erstellen Sie mit Aspose.Slides für Java beeindruckende Kartendiagramme in PowerPoint-Präsentationen. Schritt-für-Schritt-Anleitung und Quellcode für Java-Entwickler.
weight: 15
url: /de/java/chart-elements/map-chart-java-slides/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Kartendiagramm in Java-Folien


## Einführung in Kartendiagramme in Java-Folien mit Aspose.Slides für Java

In diesem Tutorial führen wir Sie durch den Prozess der Erstellung eines Kartendiagramms in einer PowerPoint-Präsentation mit Aspose.Slides für Java. Kartendiagramme sind eine großartige Möglichkeit, geografische Daten in Ihren Präsentationen zu visualisieren.

## Voraussetzungen

 Bevor Sie beginnen, stellen Sie sicher, dass Sie die Aspose.Slides für Java-Bibliothek in Ihr Java-Projekt integriert haben. Sie können sie hier herunterladen:[Hier](https://releases.aspose.com/slides/java/).

## Schritt 1: Richten Sie Ihr Projekt ein

Stellen Sie sicher, dass Sie Ihr Java-Projekt eingerichtet und die Bibliothek Aspose.Slides für Java zum Klassenpfad Ihres Projekts hinzugefügt haben.

## Schritt 2: Erstellen Sie eine PowerPoint-Präsentation

Lassen Sie uns zunächst eine neue PowerPoint-Präsentation erstellen.

```java
String resultPath = "MapChart_out.pptx";
Presentation presentation = new Presentation();
```

## Schritt 3: Ein Kartendiagramm hinzufügen

Jetzt fügen wir der Präsentation ein Kartendiagramm hinzu.

```java
IChart chart = presentation.getSlides().get_Item(0).getShapes().addChart(ChartType.Map, 50, 50, 500, 400, false);
IChartDataWorkbook wb = chart.getChartData().getChartDataWorkbook();
```

## Schritt 4: Daten zum Kartendiagramm hinzufügen

Fügen wir dem Kartendiagramm einige Daten hinzu. Wir erstellen eine Reihe und fügen ihr Datenpunkte hinzu.

```java
IChartSeries series = chart.getChartData().getSeries().add(ChartType.Map);
series.getDataPoints().addDataPointForMapSeries(wb.getCell(0, "B2", 5));
series.getDataPoints().addDataPointForMapSeries(wb.getCell(0, "B3", 1));
series.getDataPoints().addDataPointForMapSeries(wb.getCell(0, "B4", 10));
```

## Schritt 5: Kategorien hinzufügen

Wir müssen dem Kartendiagramm Kategorien hinzufügen, die verschiedene geografische Regionen darstellen.

```java
chart.getChartData().getCategories().add(wb.getCell(0, "A2", "United States"));
chart.getChartData().getCategories().add(wb.getCell(0, "A3", "Mexico"));
chart.getChartData().getCategories().add(wb.getCell(0, "A4", "Brazil"));
```

## Schritt 6: Datenpunkte anpassen

Sie können einzelne Datenpunkte anpassen. In diesem Beispiel ändern wir die Farbe und den Wert eines bestimmten Datenpunkts.

```java
IChartDataPoint dataPoint = series.getDataPoints().get_Item(1);
dataPoint.getColorValue().getAsCell().setValue("15");
dataPoint.getFormat().getFill().setFillType(FillType.Solid);
dataPoint.getFormat().getFill().getSolidFillColor().setColor(Color.GREEN);
```

## Schritt 7: Speichern Sie die Präsentation

Speichern Sie abschließend die Präsentation mit dem Kartendiagramm.

```java
presentation.save(resultPath, SaveFormat.Pptx);
```

Das ist es! Sie haben mit Aspose.Slides für Java ein Kartendiagramm in einer PowerPoint-Präsentation erstellt. Sie können das Diagramm weiter anpassen und andere von Aspose.Slides angebotene Funktionen erkunden, um Ihre Präsentationen zu verbessern.

## Vollständiger Quellcode für Kartendiagramme in Java-Folien

```java
String resultPath = "Your Output Directory" +  "MapChart_out.pptx";
Presentation presentation = new Presentation();
try {
	//leeres Diagramm erstellen
	IChart chart = presentation.getSlides().get_Item(0).getShapes().addChart(ChartType.Map, 50, 50, 500, 400, false);
	IChartDataWorkbook wb = chart.getChartData().getChartDataWorkbook();
	//Fügen Sie Serien und einige Datenpunkte hinzu
	IChartSeries series = chart.getChartData().getSeries().add(ChartType.Map);
	series.getDataPoints().addDataPointForMapSeries(wb.getCell(0, "B2", 5));
	series.getDataPoints().addDataPointForMapSeries(wb.getCell(0, "B3", 1));
	series.getDataPoints().addDataPointForMapSeries(wb.getCell(0, "B4", 10));
	//Kategorien hinzufügen
	chart.getChartData().getCategories().add(wb.getCell(0, "A2", "United States"));
	chart.getChartData().getCategories().add(wb.getCell(0, "A3", "Mexico"));
	chart.getChartData().getCategories().add(wb.getCell(0, "A4", "Brazil"));
	//Datenpunktwert ändern
	IChartDataPoint dataPoint = series.getDataPoints().get_Item(1);
	dataPoint.getColorValue().getAsCell().setValue("15");
	//Festlegen des Erscheinungsbilds von Datenpunkten
	dataPoint.getFormat().getFill().setFillType(FillType.Solid);
	dataPoint.getFormat().getFill().getSolidFillColor().setColor(Color.GREEN);
	presentation.save(resultPath, SaveFormat.Pptx);
} finally {
	if (presentation != null) presentation.dispose();
}
```

## Abschluss

In diesem Tutorial haben wir den Prozess der Erstellung eines Kartendiagramms in einer PowerPoint-Präsentation mit Aspose.Slides für Java durchgegangen. Kartendiagramme sind eine effektive Möglichkeit, geografische Daten zu visualisieren und Ihre Präsentationen ansprechender und informativer zu gestalten. Lassen Sie uns die wichtigsten Schritte zusammenfassen:

## Häufig gestellte Fragen

### Wie kann ich den Kartendiagrammtyp ändern?

 Sie können den Diagrammtyp ändern, indem Sie`ChartType.Map` mit dem gewünschten Diagrammtyp, wenn Sie das Diagramm in Schritt 3 erstellen.

### Wie kann ich das Erscheinungsbild des Kartendiagramms anpassen?

 Sie können das Erscheinungsbild des Diagramms anpassen, indem Sie die Eigenschaften des`dataPoint` Objekt in Schritt 6. Sie können Farben, Werte und mehr ändern.

### Kann ich weitere Datenpunkte und Kategorien hinzufügen?

 Ja, Sie können so viele Datenpunkte und Kategorien hinzufügen, wie Sie benötigen. Verwenden Sie einfach die`series.getDataPoints().addDataPointForMapSeries()` Und`chart.getChartData().getCategories().add()` Methoden, um sie hinzuzufügen.

### Wie integriere ich Aspose.Slides für Java in mein Projekt?

 Laden Sie die Bibliothek herunter von[Hier](https://releases.aspose.com/slides/java/) und fügen Sie es dem Klassenpfad Ihres Projekts hinzu.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
