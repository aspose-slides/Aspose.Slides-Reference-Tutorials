---
title: Streudiagramm in Java-Folien
linktitle: Streudiagramm in Java-Folien
second_title: Aspose.Slides Java PowerPoint-Verarbeitungs-API
description: Erfahren Sie, wie Sie mit Aspose.Slides Streudiagramme in Java erstellen. Schritt-für-Schritt-Anleitung mit Java-Quellcode zur Datenvisualisierung in Präsentationen.
type: docs
weight: 11
url: /de/java/chart-creation/scattered-chart-java-slides/
---

## Einführung in Streudiagramme in Aspose.Slides für Java

In diesem Tutorial führen wir Sie durch den Prozess der Erstellung eines Streudiagramms mit Aspose.Slides für Java. Streudiagramme sind nützlich, um Datenpunkte auf einer zweidimensionalen Ebene zu visualisieren. Wir geben Ihnen Schritt-für-Schritt-Anleitungen und fügen zu Ihrer Bequemlichkeit Java-Quellcode hinzu.

## Voraussetzungen

Stellen Sie zunächst sicher, dass die folgenden Voraussetzungen erfüllt sind:

1. [Aspose.Slides für Java](https://products.aspose.com/slides/java) Eingerichtet.
2. Eine Java-Entwicklungsumgebung wurde eingerichtet.

## Schritt 1: Initialisieren der Präsentation

Importieren Sie zunächst die benötigten Bibliotheken und erstellen Sie eine neue Präsentation.

```java
// Der Pfad zum Dokumentverzeichnis.
String dataDir = "Your Document Directory";

// Erstellen Sie ein Verzeichnis, falls es noch nicht vorhanden ist.
boolean IsExists = new File(dataDir).exists();
if (!IsExists)
    new File(dataDir).mkdirs();

// Erstellen einer neuen Präsentation
Presentation pres = new Presentation();
```

## Schritt 2: Folie hinzufügen und Streudiagramm erstellen

 Als nächstes fügen wir eine Folie hinzu und erstellen darauf das Streudiagramm. Wir verwenden die`ScatterWithSmoothLines` Diagrammtyp in diesem Beispiel.

```java
// Holen Sie sich die erste Folie
ISlide slide = pres.getSlides().get_Item(0);

// Erstellen des Streudiagramms
IChart chart = slide.getShapes().addChart(ChartType.ScatterWithSmoothLines, 0, 0, 400, 400);
```

## Schritt 3: Diagrammdaten vorbereiten

Bereiten wir nun die Daten für unser Streudiagramm vor. Wir fügen zwei Reihen hinzu, jede mit mehreren Datenpunkten.

```java
// Abrufen des Standardarbeitsblattindexes für Diagrammdaten
int defaultWorksheetIndex = 0;

// Abrufen des Arbeitsblatts mit den Diagrammdaten
IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();

// Demoserie löschen
chart.getChartData().getSeries().clear();

// Fügen Sie die erste Serie hinzu
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 1, 1, "Series 1"), chart.getType());
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 1, 3, "Series 2"), chart.getType());

// Nehmen Sie die erste Chartserie
IChartSeries series = chart.getChartData().getSeries().get_Item(0);

// Fügen Sie der ersten Reihe Datenpunkte hinzu
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 1), fact.getCell(defaultWorksheetIndex, 2, 2, 3));
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 2), fact.getCell(defaultWorksheetIndex, 3, 2, 10));

// Bearbeiten Sie den Serientyp
series.setType(ChartType.ScatterWithStraightLinesAndMarkers);
series.getMarker().setSize(10); // Markergröße ändern
series.getMarker().setSymbol(MarkerStyleType.Star); // Markersymbol ändern

// Nehmen Sie die zweite Chartserie
series = chart.getChartData().getSeries().get_Item(1);

// Datenpunkte zur zweiten Reihe hinzufügen
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 2, 3, 5), fact.getCell(defaultWorksheetIndex, 2, 4, 2));
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 3, 3, 3), fact.getCell(defaultWorksheetIndex, 3, 4, 1));
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 4, 3, 2), fact.getCell(defaultWorksheetIndex, 4, 4, 2));
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 5, 3, 5), fact.getCell(defaultWorksheetIndex, 5, 4, 1));

// Ändern des Markierungsstils für die zweite Serie
series.getMarker().setSize(10);
series.getMarker().setSymbol(MarkerStyleType.Circle);
```

## Schritt 4: Speichern Sie die Präsentation

Speichern Sie abschließend die Präsentation mit dem Streudiagramm als PPTX-Datei.

```java
pres.save(dataDir + "AsposeChart_out.pptx", SaveFormat.Pptx);
```

Das ist es! Sie haben erfolgreich ein Streudiagramm mit Aspose.Slides für Java erstellt. Sie können dieses Beispiel jetzt weiter anpassen, um es an Ihre spezifischen Daten- und Designanforderungen anzupassen.

## Vollständiger Quellcode für Streudiagramme in Java-Folien
```java
// Der Pfad zum Dokumentverzeichnis.
String dataDir = "Your Document Directory";
// Erstellen Sie ein Verzeichnis, falls es noch nicht vorhanden ist.
boolean IsExists = new File(dataDir).exists();
if (!IsExists)
	new File(dataDir).mkdirs();
Presentation pres = new Presentation();
ISlide slide = pres.getSlides().get_Item(0);
// Erstellen des Standarddiagramms
IChart chart = slide.getShapes().addChart(ChartType.ScatterWithSmoothLines, 0, 0, 400, 400);
// Abrufen des Standardarbeitsblattindexes für Diagrammdaten
int defaultWorksheetIndex = 0;
// Abrufen des Arbeitsblatts mit den Diagrammdaten
IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
// Demoserie löschen
chart.getChartData().getSeries().clear();
// Neue Serie hinzufügen
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 1, 1, "Series 1"), chart.getType());
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 1, 3, "Series 2"), chart.getType());
// Erste Chartserie erstellen
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
// Nehmen Sie die zweite Diagrammreihe
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

In diesem Tutorial haben wir Sie durch den Prozess der Erstellung eines Streudiagramms mit Aspose.Slides für Java geführt. Streudiagramme sind leistungsstarke Tools zur Visualisierung von Datenpunkten in einem zweidimensionalen Raum und erleichtern die Analyse und das Verständnis komplexer Datenbeziehungen.

## Häufig gestellte Fragen

### Wie kann ich den Diagrammtyp ändern?

 Um den Diagrammtyp zu ändern, verwenden Sie die`setType`Methode auf der Diagrammreihe und geben Sie den gewünschten Diagrammtyp an. Beispiel:`series.setType(ChartType.Line)` würde die Reihe in ein Liniendiagramm ändern.

### Wie passe ich Größe und Stil der Markierung an?

 Sie können die Größe und den Stil der Markierung ändern, indem Sie auf`getMarker` Methode für die Serie und legen Sie dann die Größe und die Symboleigenschaften fest. Beispiel:

```java
series.getMarker().setSize(10);
series.getMarker().setSymbol(MarkerStyleType.Circle);
```

Weitere Anpassungsoptionen finden Sie in der Dokumentation zu Aspose.Slides für Java.

 Denken Sie daran, zu ersetzen`"Your Document Directory"` durch den tatsächlichen Pfad, in dem Sie die Präsentation speichern möchten.