---
title: Ermitteln Sie Breite und Höhe aus dem Diagrammbereich in Java-Folien
linktitle: Ermitteln Sie Breite und Höhe aus dem Diagrammbereich in Java-Folien
second_title: Aspose.Slides Java PowerPoint-Verarbeitungs-API
description: Erfahren Sie, wie Sie mit Aspose.Slides für Java Diagrammflächendimensionen in Java Slides abrufen. Verbessern Sie Ihre PowerPoint-Automatisierungsfähigkeiten.
type: docs
weight: 21
url: /de/java/data-manipulation/get-width-height-chart-plot-area-java-slides/
---

## Einführung

Diagramme sind eine leistungsstarke Möglichkeit, Daten in PowerPoint-Präsentationen zu visualisieren. Manchmal müssen Sie aus verschiedenen Gründen die Abmessungen des Plotbereichs eines Diagramms kennen, z. B. um die Größe zu ändern oder Elemente innerhalb des Diagramms neu zu positionieren. In dieser Anleitung wird gezeigt, wie Sie mit Java und Aspose.Slides für Java die Breite und Höhe des Plotbereichs ermitteln.

## Voraussetzungen

 Bevor wir uns mit dem Code befassen, stellen Sie sicher, dass die Aspose.Slides for Java-Bibliothek in Ihrem Java-Projekt installiert und eingerichtet ist. Sie können die Bibliothek von der Aspose-Website herunterladen[Hier](https://releases.aspose.com/slides/java/).

## Schritt 1: Einrichten der Umgebung

Stellen Sie sicher, dass Sie die Aspose.Slides for Java-Bibliothek zu Ihrem Java-Projekt hinzugefügt haben. Sie können dies tun, indem Sie die Bibliothek in die Abhängigkeiten Ihres Projekts einbinden oder die JAR-Datei manuell hinzufügen.

## Schritt 2: Erstellen einer PowerPoint-Präsentation

Beginnen wir mit der Erstellung einer PowerPoint-Präsentation und dem Hinzufügen einer Folie. Dies dient als Container für unser Diagramm.

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "test.Pptx");
```

 Ersetzen`"Your Document Directory"` mit dem Pfad zu Ihrem Dokumentenverzeichnis.

## Schritt 3: Hinzufügen eines Diagramms

Nun fügen wir der Folie ein gruppiertes Säulendiagramm hinzu. Wir werden auch das Diagrammlayout validieren.

```java
Chart chart = (Chart) pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 100, 100, 500, 350);
chart.validateChartLayout();
```

Dieser Code erstellt ein gruppiertes Säulendiagramm an der Position (100, 100) mit den Dimensionen (500, 350).

## Schritt 4: Ermitteln der Abmessungen der Grundstücksfläche

Um die Breite und Höhe des Diagrammbereichs abzurufen, können wir den folgenden Code verwenden:

```java
double x = chart.getPlotArea().getActualX();
double y = chart.getPlotArea().getActualY();
double w = chart.getPlotArea().getActualWidth();
double h = chart.getPlotArea().getActualHeight();
```

 Nun zu den Variablen`x`, `y`, `w` , Und`h` enthalten die jeweiligen Werte für die X-Koordinate, Y-Koordinate, Breite und Höhe des Plotbereichs.

## Schritt 5: Speichern der Präsentation

Speichern Sie abschließend die Präsentation mit dem Diagramm.

```java
pres.save(dataDir + "Chart_out.pptx", SaveFormat.Pptx);
```

 Unbedingt austauschen`"Chart_out.pptx"` mit dem gewünschten Namen der Ausgabedatei.

## Vollständiger Quellcode zum Abrufen von Breite und Höhe aus dem Diagrammbereich in Java-Folien

```java
// Der Pfad zum Dokumentenverzeichnis.
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "test.Pptx");
try
{
	Chart chart = (Chart) pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 100, 100, 500, 350);
	chart.validateChartLayout();
	double x = chart.getPlotArea().getActualX();
	double y = chart.getPlotArea().getActualY();
	double w = chart.getPlotArea().getActualWidth();
	double h = chart.getPlotArea().getActualHeight();
	// Präsentation mit Diagramm speichern
	pres.save(dataDir + "Chart_out.pptx", SaveFormat.Pptx);
}
finally
{
	if (pres != null) pres.dispose();
}
```

## Abschluss

In diesem Artikel haben wir behandelt, wie Sie die Breite und Höhe des Plotbereichs eines Diagramms in Java Slides mithilfe der Aspose.Slides für Java-API ermitteln. Diese Informationen können hilfreich sein, wenn Sie das Layout Ihrer Diagramme in PowerPoint-Präsentationen dynamisch anpassen müssen.

## FAQs

### Wie kann ich den Diagrammtyp auf etwas anderes als gruppierte Spalten ändern?

 Sie können den Diagrammtyp durch Ersetzen ändern`ChartType.ClusteredColumn` mit der gewünschten Diagrammtyp-Aufzählung, z`ChartType.Line` oder`ChartType.Pie`.

### Kann ich andere Eigenschaften des Diagramms ändern?

Ja, Sie können mithilfe der Aspose.Slides für Java-API verschiedene Eigenschaften des Diagramms ändern, z. B. Daten, Beschriftungen und Formatierung. Weitere Einzelheiten finden Sie in der Dokumentation.

### Ist Aspose.Slides für Java für die professionelle PowerPoint-Automatisierung geeignet?

Ja, Aspose.Slides für Java ist eine leistungsstarke Bibliothek zur Automatisierung von PowerPoint-Aufgaben in Java-Anwendungen. Es bietet umfassende Funktionen für die Arbeit mit Präsentationen, Folien, Formen, Diagrammen und mehr.

### Wie kann ich mehr über Aspose.Slides für Java erfahren?

 Eine ausführliche Dokumentation und Beispiele finden Sie auf der Dokumentationsseite von Aspose.Slides für Java[Hier](https://reference.aspose.com/slides/java/).
