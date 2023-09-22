---
title: Streudiagramm in Java-Folien
linktitle: Streudiagramm in Java-Folien
second_title: Aspose.Slides Java PowerPoint-Verarbeitungs-API
description: Erfahren Sie, wie Sie mit Aspose.Slides Streudiagramme in Java erstellen. Schritt-für-Schritt-Anleitung mit Java-Quellcode zur Datenvisualisierung in Präsentationen.
type: docs
weight: 11
url: /de/java/chart-creation/scattered-chart-java-slides/
---

## Einführung in das Streudiagramm in Aspose.Slides für Java

In diesem Tutorial führen wir Sie durch den Prozess der Erstellung eines Streudiagramms mit Aspose.Slides für Java. Streudiagramme eignen sich zur Visualisierung von Datenpunkten auf einer zweidimensionalen Ebene. Wir stellen Ihnen Schritt-für-Schritt-Anleitungen zur Verfügung und fügen zu Ihrer Bequemlichkeit Java-Quellcode hinzu.

## Voraussetzungen

Bevor Sie beginnen, stellen Sie sicher, dass die folgenden Voraussetzungen erfüllt sind:

1. [Aspose.Slides für Java](https://products.aspose.com/slides/java) Eingerichtet.
2. Einrichtung einer Java-Entwicklungsumgebung.

## Schritt 1: Initialisieren Sie die Präsentation

Importieren Sie zunächst die erforderlichen Bibliotheken und erstellen Sie eine neue Präsentation.

```java
// Der Pfad zum Dokumentenverzeichnis.
String dataDir = "Your Document Directory";

// Erstellen Sie ein Verzeichnis, falls es noch nicht vorhanden ist.
boolean IsExists = new File(dataDir).exists();
if (!IsExists)
    new File(dataDir).mkdirs();

// Erstellen Sie eine neue Präsentation
Presentation pres = new Presentation();
```

## Schritt 2: Fügen Sie eine Folie hinzu und erstellen Sie das Streudiagramm

 Fügen Sie als Nächstes eine Folie hinzu und erstellen Sie darauf das Streudiagramm. Wir werden das verwenden`ScatterWithSmoothLines` Diagrammtyp in diesem Beispiel.

```java
// Holen Sie sich die erste Folie
ISlide slide = pres.getSlides().get_Item(0);

// Erstellen des Streudiagramms
IChart chart = slide.getShapes().addChart(ChartType.ScatterWithSmoothLines, 0, 0, 400, 400);
```

## Schritt 3: Diagrammdaten vorbereiten

Bereiten wir nun die Daten für unser Streudiagramm vor. Wir fügen zwei Serien mit jeweils mehreren Datenpunkten hinzu.

```java
// Abrufen des Standard-Arbeitsblattindex für Diagrammdaten
int defaultWorksheetIndex = 0;

// Abrufen des Diagrammdaten-Arbeitsblatts
IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();

// Demoserie löschen
chart.getChartData().getSeries().clear();

// Fügen Sie die erste Serie hinzu
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 1, 1, "Series 1"), chart.getType());
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 1, 3, "Series 2"), chart.getType());

// Nehmen Sie die erste Chartserie
IChartSeries series = chart.getChartData().getSeries().get_Item(0);

// Fügen Sie Datenpunkte zur ersten Serie hinzu
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 1), fact.getCell(defaultWorksheetIndex, 2, 2, 3));
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 2), fact.getCell(defaultWorksheetIndex, 3, 2, 10));

// Bearbeiten Sie den Serientyp
series.setType(ChartType.ScatterWithStraightLinesAndMarkers);
series.getMarker().setSize(10); // Markierungsgröße ändern
series.getMarker().setSymbol(MarkerStyleType.Star); // Markierungssymbol ändern

// Nehmen Sie die zweite Chartserie
series = chart.getChartData().getSeries().get_Item(1);

// Fügen Sie Datenpunkte zur zweiten Reihe hinzu
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 2, 3, 5), fact.getCell(defaultWorksheetIndex, 2, 4, 2));
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 3, 3, 3), fact.getCell(defaultWorksheetIndex, 3, 4, 1));
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 4, 3, 2), fact.getCell(defaultWorksheetIndex, 4, 4, 2));
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 5, 3, 5), fact.getCell(defaultWorksheetIndex, 5, 4, 1));

// Ändern Sie den Markierungsstil für die zweite Serie
series.getMarker().setSize(10);
series.getMarker().setSymbol(MarkerStyleType.Circle);
```

## Schritt 4: Speichern Sie die Präsentation

Speichern Sie abschließend die Präsentation mit dem Streudiagramm in einer PPTX-Datei.

```java
pres.save(dataDir + "AsposeChart_out.pptx", SaveFormat.Pptx);
```

Das ist es! Sie haben mit Aspose.Slides für Java erfolgreich ein Streudiagramm erstellt. Sie können dieses Beispiel nun weiter an Ihre spezifischen Daten- und Designanforderungen anpassen.

## Vollständiger Quellcode für Streudiagramme in Java-Folien
```java
// Der Pfad zum Dokumentenverzeichnis.
String dataDir = "Your Document Directory";
// Erstellen Sie ein Verzeichnis, falls es noch nicht vorhanden ist.
boolean IsExists = new File(dataDir).exists();
if (!IsExists)
	new File(dataDir).mkdirs();
Presentation pres = new Presentation();
ISlide slide = pres.getSlides().get_Item(0);
// Erstellen des Standarddiagramms
IChart chart = slide.getShapes().addChart(ChartType.ScatterWithSmoothLines, 0, 0, 400, 400);
// Abrufen des Standard-Arbeitsblattindex für Diagrammdaten
int defaultWorksheetIndex = 0;
// Abrufen des Diagrammdaten-Arbeitsblatts
IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
// Demoserie löschen
chart.getChartData().getSeries().clear();
// Neue Serie hinzufügen
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 1, 1, "Series 1"), chart.getType());
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 1, 3, "Series 2"), chart.getType());
// Nehmen Sie die erste Chartserie
IChartSeries series = chart.getChartData().getSeries().get_Item(0);
// Fügen Sie dort einen neuen Punkt (1:3) hinzu.
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 1), fact.getCell(defaultWorksheetIndex, 2, 2, 3));
// Neuen Punkt hinzufügen (2:10)
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 2), fact.getCell(defaultWorksheetIndex, 3, 2, 10));
// Bearbeiten Sie den Serientyp
series.setType(ChartType.ScatterWithStraightLinesAndMarkers);
// Ändern der Diagrammreihenmarkierung
series.getMarker().setSize(10);
series.getMarker().setSymbol(MarkerStyleType.Star);
// Nehmen Sie die zweite Chartserie
series = chart.getChartData().getSeries().get_Item(1);
// Fügen Sie dort einen neuen Punkt (5:2) hinzu.
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 2, 3, 5), fact.getCell(defaultWorksheetIndex, 2, 4, 2));
// Neuen Punkt hinzufügen (3:1)
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 3, 3, 3), fact.getCell(defaultWorksheetIndex, 3, 4, 1));
// Neuen Punkt hinzufügen (2:2)
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 4, 3, 2), fact.getCell(defaultWorksheetIndex, 4, 4, 2));
// Neuen Punkt hinzufügen (5:1)
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 5, 3, 5), fact.getCell(defaultWorksheetIndex, 5, 4, 1));
// Ändern der Diagrammreihenmarkierung
series.getMarker().setSize(10);
series.getMarker().setSymbol(MarkerStyleType.Circle);
pres.save(dataDir + "AsposeChart_out.pptx", SaveFormat.Pptx);
```

## Abschluss

In diesem Tutorial haben wir Sie durch den Prozess der Erstellung eines Streudiagramms mit Aspose.Slides für Java geführt. Streudiagramme sind leistungsstarke Werkzeuge zur Visualisierung von Datenpunkten in einem zweidimensionalen Raum und erleichtern die Analyse und das Verständnis komplexer Datenbeziehungen.

## FAQs

### Wie kann ich den Diagrammtyp ändern?

 Um den Diagrammtyp zu ändern, verwenden Sie die`setType`Methode für die Diagrammreihe und geben Sie den gewünschten Diagrammtyp an. Zum Beispiel,`series.setType(ChartType.Line)` würde die Reihe in ein Liniendiagramm ändern.

### Wie kann ich die Größe und den Stil der Markierung anpassen?

 Sie können die Größe und den Stil der Markierung mit ändern`getMarker` Methode für die Serie und legen Sie dann die Größen- und Symboleigenschaften fest. Zum Beispiel:

```java
series.getMarker().setSize(10);
series.getMarker().setSymbol(MarkerStyleType.Circle);
```

Weitere Anpassungsoptionen finden Sie in der Dokumentation zu Aspose.Slides für Java.

 Denken Sie daran, es auszutauschen`"Your Document Directory"` mit dem tatsächlichen Pfad, in dem Sie die Präsentation speichern möchten.