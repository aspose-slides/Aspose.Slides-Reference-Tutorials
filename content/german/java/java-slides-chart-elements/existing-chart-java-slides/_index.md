---
title: Vorhandenes Diagramm in Java-Folien
linktitle: Vorhandenes Diagramm in Java-Folien
second_title: Aspose.Slides Java PowerPoint-Verarbeitungs-API
description: Verbessern Sie Ihre PowerPoint-Präsentationen mit Aspose.Slides für Java. Erfahren Sie, wie Sie vorhandene Diagramme programmgesteuert ändern. Schritt-für-Schritt-Anleitung mit Quellcode zur Diagrammanpassung.
type: docs
weight: 12
url: /de/java/chart-elements/existing-chart-java-slides/
---

## Einführung in vorhandene Diagramme in Java-Folien mit Aspose.Slides für Java

In diesem Tutorial zeigen wir, wie Sie mit Aspose.Slides für Java ein vorhandenes Diagramm in einer PowerPoint-Präsentation ändern. Wir gehen die Schritte durch, um Diagrammdaten, Kategorienamen und Reihennamen zu ändern und dem Diagramm eine neue Reihe hinzuzufügen. Stellen Sie sicher, dass Aspose.Slides für Java in Ihrem Projekt eingerichtet ist.

## Voraussetzungen

Bevor wir beginnen, stellen Sie sicher, dass die folgenden Voraussetzungen erfüllt sind:

1. Aspose.Slides für Java-Bibliothek in Ihrem Projekt enthalten.
2. Eine vorhandene PowerPoint-Präsentation mit einem Diagramm, das Sie ändern möchten.
3. Einrichtung einer Java-Entwicklungsumgebung.

## Schritt 1: Laden Sie die Präsentation

```java
// Der Pfad zum Dokumentenverzeichnis.
String dataDir = "Your Document Directory";

// Instanziieren Sie die Präsentationsklasse, die eine PPTX-Datei darstellt
Presentation pres = new Presentation(dataDir + "ExistingChart.pptx");
```

## Schritt 2: Greifen Sie auf die Folie und das Diagramm zu

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

//Abrufen des Diagrammdaten-Arbeitsblatts
IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();

// Ändern Sie die Namen der Diagrammkategorien
fact.getCell(defaultWorksheetIndex, 1, 0, "Modified Category 1");
fact.getCell(defaultWorksheetIndex, 2, 0, "Modified Category 2");
```

## Schritt 4: Aktualisieren Sie die erste Diagrammreihe

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

## Schritt 5: Zweite Diagrammreihe aktualisieren

```java
// Nehmen Sie die zweite Chartserie
series = chart.getChartData().getSeries().get_Item(1);

// Seriennamen aktualisieren
fact.getCell(defaultWorksheetIndex, 0, 2, "New_Series2");

// Seriendaten aktualisieren
series.getDataPoints().get_Item(0).getValue().setData(23);
series.getDataPoints().get_Item(1).getValue().setData(67);
series.getDataPoints().get_Item(2).getValue().setData(99);
```

## Schritt 6: Fügen Sie dem Diagramm eine neue Serie hinzu

```java
// Hinzufügen einer neuen Serie
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 3, "Series 3"), chart.getType());

// Nehmen Sie die dritte Chartserie
series = chart.getChartData().getSeries().get_Item(2);

// Füllen Sie Seriendaten aus
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 3, 20));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 3, 50));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 3, 30));
```

## Schritt 7: Diagrammtyp ändern

```java
//Ändern Sie den Diagrammtyp in „Gruppierter Zylinder“.
chart.setType(ChartType.ClusteredCylinder);
```

## Schritt 8: Speichern Sie die geänderte Präsentation

```java
// Speichern Sie die Präsentation mit dem geänderten Diagramm
pres.save(dataDir + "AsposeChartModified_out.pptx", SaveFormat.Pptx);
```

Glückwunsch! Sie haben mit Aspose.Slides für Java erfolgreich ein vorhandenes Diagramm in einer PowerPoint-Präsentation geändert. Mit diesem Code können Sie nun Diagramme in Ihren PowerPoint-Präsentationen programmgesteuert anpassen.

## Vollständiger Quellcode für vorhandene Diagramme in Java-Folien

```java
// Der Pfad zum Dokumentenverzeichnis.
String dataDir = "Your Document Directory";
// Instanziieren Sie die Präsentationsklasse, die die PPTX-Datei darstellt. // Instanziieren Sie die Präsentationsklasse, die die PPTX-Datei darstellt
Presentation pres = new Presentation(dataDir + "ExistingChart.pptx");
// Greifen Sie auf den ersten Folienmarker zu
ISlide sld = pres.getSlides().get_Item(0);
// Diagramm mit Standarddaten hinzufügen
IChart chart = (IChart) sld.getShapes().get_Item(0);
// Festlegen des Index des Diagrammdatenblatts
int defaultWorksheetIndex = 0;
//Abrufen des Diagrammdaten-Arbeitsblatts
IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
// Ändern des Namens der Diagrammkategorie
fact.getCell(defaultWorksheetIndex, 1, 0, "Modified Category 1");
fact.getCell(defaultWorksheetIndex, 2, 0, "Modified Category 2");
// Nehmen Sie die erste Chartserie
IChartSeries series = chart.getChartData().getSeries().get_Item(0);
// Aktualisiert jetzt die Seriendaten
fact.getCell(defaultWorksheetIndex, 0, 1, "New_Series1");// Serienname ändern
series.getDataPoints().get_Item(0).getValue().setData(90);
series.getDataPoints().get_Item(1).getValue().setData(123);
series.getDataPoints().get_Item(2).getValue().setData(44);
// Nehmen Sie die zweite Chartserie
series = chart.getChartData().getSeries().get_Item(1);
// Aktualisiert jetzt die Seriendaten
fact.getCell(defaultWorksheetIndex, 0, 2, "New_Series2");// Serienname ändern
series.getDataPoints().get_Item(0).getValue().setData(23);
series.getDataPoints().get_Item(1).getValue().setData(67);
series.getDataPoints().get_Item(2).getValue().setData(99);
// Nun wird eine neue Serie hinzugefügt
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 3, "Series 3"), chart.getType());
// Nehmen Sie die 3. Chartserie
series = chart.getChartData().getSeries().get_Item(2);
// Jetzt werden Seriendaten ausgefüllt
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 3, 20));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 3, 50));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 3, 30));
chart.setType(ChartType.ClusteredCylinder);
// Präsentation mit Diagramm speichern
pres.save(dataDir + "AsposeChartModified_out.pptx", SaveFormat.Pptx);
```
## Abschluss

In diesem umfassenden Tutorial haben wir gelernt, wie man mit Aspose.Slides für Java ein vorhandenes Diagramm in einer PowerPoint-Präsentation ändert. Indem Sie der Schritt-für-Schritt-Anleitung folgen und Quellcodebeispiele verwenden, können Sie Diagramme ganz einfach an Ihre spezifischen Anforderungen anpassen und aktualisieren. Hier ist eine Zusammenfassung dessen, was wir behandelt haben:

## FAQs

### Wie kann ich den Diagrammtyp ändern?

 Sie können den Diagrammtyp ändern, indem Sie verwenden`chart.setType(ChartType.ChartTypeHere)` Methode. Ersetzen`ChartTypeHere` mit dem gewünschten Diagrammtyp, z`ChartType.ClusteredCylinder` in unserem Beispiel.

### Kann ich einer Serie weitere Datenpunkte hinzufügen?

 Ja, Sie können einer Reihe weitere Datenpunkte hinzufügen`series.getDataPoints().addDataPointForBarSeries(cell)` Methode. Stellen Sie sicher, dass Sie die entsprechenden Zelldaten angeben.

### Wie aktualisiere ich die Kategorienamen?

 Sie können Kategorienamen aktualisieren, indem Sie verwenden`fact.getCell(worksheetIndex, columnIndex, rowIndex, newValue)` um die neuen Kategorienamen festzulegen.

### Wie ändere ich Seriennamen?

 Um Seriennamen zu ändern, verwenden Sie`fact.getCell(worksheetIndex, columnIndex, rowIndex, newValue)` um die neuen Seriennamen festzulegen.

### Gibt es eine Möglichkeit, eine Reihe aus dem Diagramm zu entfernen?

 Ja, Sie können eine Reihe mithilfe von aus dem Diagramm entfernen`chart.getChartData().getSeries().removeAt(index)` Methode, wo`index`ist der Index der Serie, die Sie entfernen möchten.