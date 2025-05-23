---
"description": "Erfahren Sie, wie Sie mit Aspose.Slides für Java die Dimensionen von Diagrammflächen in Java-Folien abrufen. Verbessern Sie Ihre PowerPoint-Automatisierungsfähigkeiten."
"linktitle": "Ermitteln Sie Breite und Höhe aus dem Diagramm-Plotbereich in Java-Folien"
"second_title": "Aspose.Slides Java PowerPoint-Verarbeitungs-API"
"title": "Ermitteln Sie Breite und Höhe aus dem Diagramm-Plotbereich in Java-Folien"
"url": "/de/java/data-manipulation/get-width-height-chart-plot-area-java-slides/"
"weight": 21
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Ermitteln Sie Breite und Höhe aus dem Diagramm-Plotbereich in Java-Folien


## Einführung

Diagramme bieten eine leistungsstarke Möglichkeit, Daten in PowerPoint-Präsentationen zu visualisieren. Manchmal benötigen Sie die Abmessungen des Diagrammbereichs aus verschiedenen Gründen, z. B. um die Größe oder Position von Elementen im Diagramm zu ändern. Diese Anleitung zeigt, wie Sie die Breite und Höhe des Diagrammbereichs mit Java und Aspose.Slides für Java ermitteln.

## Voraussetzungen

Bevor wir uns mit dem Code befassen, stellen Sie sicher, dass die Bibliothek Aspose.Slides für Java in Ihrem Java-Projekt installiert und eingerichtet ist. Sie können die Bibliothek von der Aspose-Website herunterladen. [Hier](https://releases.aspose.com/slides/java/).

## Schritt 1: Einrichten der Umgebung

Stellen Sie sicher, dass die Bibliothek Aspose.Slides für Java zu Ihrem Java-Projekt hinzugefügt wurde. Sie können dies tun, indem Sie die Bibliothek in die Abhängigkeiten Ihres Projekts aufnehmen oder die JAR-Datei manuell hinzufügen.

## Schritt 2: Erstellen einer PowerPoint-Präsentation

Beginnen wir mit der Erstellung einer PowerPoint-Präsentation und dem Hinzufügen einer Folie. Diese dient als Container für unser Diagramm.

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "test.Pptx");
```

Ersetzen `"Your Document Directory"` mit dem Pfad zu Ihrem Dokumentverzeichnis.

## Schritt 3: Hinzufügen eines Diagramms

Fügen wir der Folie nun ein gruppiertes Säulendiagramm hinzu. Wir validieren außerdem das Diagrammlayout.

```java
Chart chart = (Chart) pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 100, 100, 500, 350);
chart.validateChartLayout();
```

Dieser Code erstellt ein gruppiertes Säulendiagramm an Position (100, 100) mit den Dimensionen (500, 350).

## Schritt 4: Ermitteln der Abmessungen der Grundstücksfläche

Um die Breite und Höhe des Diagrammbereichs abzurufen, können wir den folgenden Code verwenden:

```java
double x = chart.getPlotArea().getActualX();
double y = chart.getPlotArea().getActualY();
double w = chart.getPlotArea().getActualWidth();
double h = chart.getPlotArea().getActualHeight();
```

Nun die Variablen `x`, `y`, `w`, Und `h` enthalten die jeweiligen Werte für die X-Koordinate, Y-Koordinate, Breite und Höhe des Plotbereichs.

## Schritt 5: Speichern der Präsentation

Speichern Sie abschließend die Präsentation mit dem Diagramm.

```java
pres.save(dataDir + "Chart_out.pptx", SaveFormat.Pptx);
```

Stellen Sie sicher, dass Sie `"Chart_out.pptx"` durch den gewünschten Ausgabedateinamen.

## Vollständiger Quellcode zum Abrufen von Breite und Höhe aus dem Diagramm-Plotbereich in Java-Folien

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

In diesem Artikel haben wir erläutert, wie Sie die Breite und Höhe des Diagrammbereichs in Java Slides mithilfe der Aspose.Slides für Java-API ermitteln. Diese Informationen können hilfreich sein, wenn Sie das Layout Ihrer Diagramme in PowerPoint-Präsentationen dynamisch anpassen müssen.

## Häufig gestellte Fragen

### Wie kann ich den Diagrammtyp in etwas anderes als gruppierte Spalten ändern?

Sie können den Diagrammtyp ändern, indem Sie `ChartType.ClusteredColumn` mit der gewünschten Diagrammtyp-Aufzählung, wie zum Beispiel `ChartType.Line` oder `ChartType.Pie`.

### Kann ich andere Eigenschaften des Diagramms ändern?

Ja, Sie können verschiedene Eigenschaften des Diagramms, wie Daten, Beschriftungen und Formatierung, mithilfe der Aspose.Slides für Java-API ändern. Weitere Informationen finden Sie in der Dokumentation.

### Ist Aspose.Slides für Java für die professionelle PowerPoint-Automatisierung geeignet?

Ja, Aspose.Slides für Java ist eine leistungsstarke Bibliothek zur Automatisierung von PowerPoint-Aufgaben in Java-Anwendungen. Sie bietet umfassende Funktionen für die Arbeit mit Präsentationen, Folien, Formen, Diagrammen und mehr.

### Wie kann ich mehr über Aspose.Slides für Java erfahren?

Ausführliche Dokumentation und Beispiele finden Sie auf der Dokumentationsseite von Aspose.Slides für Java [Hier](https://reference.aspose.com/slides/java/).


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}