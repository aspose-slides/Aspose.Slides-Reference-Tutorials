---
"description": "Optimieren Sie Ihre PowerPoint-Präsentationen mit Aspose.Slides für Java. Lernen Sie, bestehende Diagramme programmgesteuert zu bearbeiten. Schritt-für-Schritt-Anleitung mit Quellcode zur Diagrammanpassung."
"linktitle": "Vorhandenes Diagramm in Java-Folien"
"second_title": "Aspose.Slides Java PowerPoint-Verarbeitungs-API"
"title": "Vorhandenes Diagramm in Java-Folien"
"url": "/de/java/chart-elements/existing-chart-java-slides/"
"weight": 12
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Vorhandenes Diagramm in Java-Folien


## Einführung in vorhandene Diagramme in Java-Folien mit Aspose.Slides für Java

In diesem Tutorial zeigen wir, wie Sie ein vorhandenes Diagramm in einer PowerPoint-Präsentation mit Aspose.Slides für Java ändern. Wir führen Sie durch die Schritte zum Ändern von Diagrammdaten, Kategorienamen und Reihennamen sowie zum Hinzufügen einer neuen Reihe zum Diagramm. Stellen Sie sicher, dass Aspose.Slides für Java in Ihrem Projekt eingerichtet ist.

## Voraussetzungen

Bevor wir beginnen, stellen Sie sicher, dass die folgenden Voraussetzungen erfüllt sind:

1. Aspose.Slides für die Java-Bibliothek, die in Ihrem Projekt enthalten ist.
2. Eine vorhandene PowerPoint-Präsentation mit einem Diagramm, das Sie ändern möchten.
3. Java-Entwicklungsumgebung eingerichtet.

## Schritt 1: Laden Sie die Präsentation

```java
// Der Pfad zum Dokumentenverzeichnis.
String dataDir = "Your Document Directory";

// Instanziieren Sie die Präsentationsklasse, die die PPTX-Datei darstellt
Presentation pres = new Presentation(dataDir + "ExistingChart.pptx");
```

## Schritt 2: Zugriff auf Folie und Diagramm

```java
// Greifen Sie auf die erste Folie zu
ISlide sld = pres.getSlides().get_Item(0);

// Greifen Sie auf das Diagramm auf der Folie zu
IChart chart = (IChart) sld.getShapes().get_Item(0);
```

## Schritt 3: Diagrammdaten und Kategorienamen ändern

```java
// Festlegen des Index des Diagrammdatenblatts
int defaultWorksheetIndex = 0;

// Abrufen des Arbeitsblatts mit den Diagrammdaten
IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();

// Ändern der Diagrammkategorienamen
fact.getCell(defaultWorksheetIndex, 1, 0, "Modified Category 1");
fact.getCell(defaultWorksheetIndex, 2, 0, "Modified Category 2");
```

## Schritt 4: Aktualisieren der ersten Diagrammreihe

```java
// Nehmen Sie die erste Chartserie
IChartSeries series = chart.getChartData().getSeries().get_Item(0);

// Seriennamen aktualisieren
fact.getCell(defaultWorksheetIndex, 0, 1, "New_Series1");

// Seriendaten aktualisieren
series.getDataPoints().get_Item(0).getValue().setData(90);
series.getDataPoints().get_Item(1).getValue().setData(123);
series.getDataPoints().get_Item(2).getValue().setData(44);
```

## Schritt 5: Aktualisieren der zweiten Diagrammreihe

```java
// Nehmen Sie die zweite Chartreihe
series = chart.getChartData().getSeries().get_Item(1);

// Seriennamen aktualisieren
fact.getCell(defaultWorksheetIndex, 0, 2, "New_Series2");

// Seriendaten aktualisieren
series.getDataPoints().get_Item(0).getValue().setData(23);
series.getDataPoints().get_Item(1).getValue().setData(67);
series.getDataPoints().get_Item(2).getValue().setData(99);
```

## Schritt 6: Dem Diagramm eine neue Serie hinzufügen

```java
// Hinzufügen einer neuen Serie
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 3, "Series 3"), chart.getType());

// Nehmen Sie die dritte Chartserie
series = chart.getChartData().getSeries().get_Item(2);

// Auffüllen von Reihendaten
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 3, 20));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 3, 50));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 3, 30));
```

## Schritt 7: Diagrammtyp ändern

```java
// Ändern Sie den Diagrammtyp in „Gruppierter Zylinder“
chart.setType(ChartType.ClusteredCylinder);
```

## Schritt 8: Speichern der geänderten Präsentation

```java
// Speichern Sie die Präsentation mit dem geänderten Diagramm
pres.save(dataDir + "AsposeChartModified_out.pptx", SaveFormat.Pptx);
```

Herzlichen Glückwunsch! Sie haben ein vorhandenes Diagramm in einer PowerPoint-Präsentation mit Aspose.Slides für Java erfolgreich geändert. Mit diesem Code können Sie nun Diagramme in Ihren PowerPoint-Präsentationen programmgesteuert anpassen.

## Vollständiger Quellcode für vorhandene Diagramme in Java-Folien

```java
// Der Pfad zum Dokumentenverzeichnis.
String dataDir = "Your Document Directory";
// Instanziieren Sie die Präsentationsklasse, die die PPTX-Datei darstellt. // Instanziieren Sie die Präsentationsklasse, die die PPTX-Datei darstellt.
Presentation pres = new Presentation(dataDir + "ExistingChart.pptx");
// Zugriff auf den ersten SlideMarker
ISlide sld = pres.getSlides().get_Item(0);
// Diagramm mit Standarddaten hinzufügen
IChart chart = (IChart) sld.getShapes().get_Item(0);
// Festlegen des Index des Diagrammdatenblatts
int defaultWorksheetIndex = 0;
// Abrufen des Arbeitsblatts mit den Diagrammdaten
IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
// Ändern des Diagrammkategorienamens
fact.getCell(defaultWorksheetIndex, 1, 0, "Modified Category 1");
fact.getCell(defaultWorksheetIndex, 2, 0, "Modified Category 2");
// Nehmen Sie die erste Chartreihe
IChartSeries series = chart.getChartData().getSeries().get_Item(0);
// Aktualisierung der Seriendaten
fact.getCell(defaultWorksheetIndex, 0, 1, "New_Series1");// Ändern des Seriennamens
series.getDataPoints().get_Item(0).getValue().setData(90);
series.getDataPoints().get_Item(1).getValue().setData(123);
series.getDataPoints().get_Item(2).getValue().setData(44);
// Nehmen Sie die zweite Chartserie
series = chart.getChartData().getSeries().get_Item(1);
// Aktualisierung der Seriendaten
fact.getCell(defaultWorksheetIndex, 0, 2, "New_Series2");// Ändern des Seriennamens
series.getDataPoints().get_Item(0).getValue().setData(23);
series.getDataPoints().get_Item(1).getValue().setData(67);
series.getDataPoints().get_Item(2).getValue().setData(99);
// Jetzt eine neue Serie hinzufügen
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 3, "Series 3"), chart.getType());
// Nehmen Sie die 3. Chartserie
series = chart.getChartData().getSeries().get_Item(2);
// Jetzt werden Seriendaten gefüllt
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 3, 20));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 3, 50));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 3, 30));
chart.setType(ChartType.ClusteredCylinder);
// Präsentation mit Diagramm speichern
pres.save(dataDir + "AsposeChartModified_out.pptx", SaveFormat.Pptx);
```
## Abschluss

In diesem umfassenden Tutorial haben wir gelernt, wie Sie ein vorhandenes Diagramm in einer PowerPoint-Präsentation mit Aspose.Slides für Java anpassen. Indem Sie der Schritt-für-Schritt-Anleitung folgen und Quellcodebeispiele verwenden, können Sie Diagramme ganz einfach an Ihre spezifischen Anforderungen anpassen und aktualisieren. Hier ist eine Zusammenfassung der behandelten Themen:

## Häufig gestellte Fragen

### Wie kann ich den Diagrammtyp ändern?

Sie können den Diagrammtyp ändern, indem Sie das `chart.setType(ChartType.ChartTypeHere)` Methode. Ersetzen `ChartTypeHere` mit dem gewünschten Diagrammtyp, wie zum Beispiel `ChartType.ClusteredCylinder` in unserem Beispiel.

### Kann ich einer Reihe weitere Datenpunkte hinzufügen?

Ja, Sie können einer Reihe weitere Datenpunkte hinzufügen, indem Sie `series.getDataPoints().addDataPointForBarSeries(cell)` Methode. Stellen Sie sicher, dass Sie die entsprechenden Zellendaten angeben.

### Wie aktualisiere ich die Kategorienamen?

Sie können Kategorienamen aktualisieren, indem Sie `fact.getCell(worksheetIndex, columnIndex, rowIndex, newValue)` um die neuen Kategorienamen festzulegen.

### Wie ändere ich Seriennamen?

Um Seriennamen zu ändern, verwenden Sie `fact.getCell(worksheetIndex, columnIndex, rowIndex, newValue)` um die neuen Seriennamen festzulegen.

### Gibt es eine Möglichkeit, eine Reihe aus dem Diagramm zu entfernen?

Ja, Sie können eine Serie aus dem Diagramm entfernen, indem Sie das `chart.getChartData().getSeries().removeAt(index)` Methode, wobei `index` ist der Index der Serie, die Sie entfernen möchten.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}