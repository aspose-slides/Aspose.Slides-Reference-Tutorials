---
title: Festlegen der Positionsachse in Java-Folien
linktitle: Festlegen der Positionsachse in Java-Folien
second_title: Aspose.Slides Java PowerPoint-Verarbeitungs-API
description: Erweitern Sie Ihre Diagramme mit Aspose.Slides für Java. Erfahren Sie, wie Sie die Positionsachse in Java-Folien festlegen, beeindruckende Präsentationen erstellen und Diagrammlayouts ganz einfach anpassen.
type: docs
weight: 16
url: /de/java/customization-and-formatting/setting-position-axis-java-slides/
---

## Einführung in das Festlegen der Positionsachse in Aspose.Slides für Java

In diesem Tutorial erfahren Sie, wie Sie mit Aspose.Slides für Java die Positionsachse in einem Diagramm festlegen. Die Positionierung der Achse kann hilfreich sein, wenn Sie das Erscheinungsbild und Layout Ihres Diagramms anpassen möchten. Wir erstellen ein gruppiertes Säulendiagramm und passen die Position der horizontalen Achse zwischen den Kategorien an.

## Voraussetzungen

 Bevor wir beginnen, stellen Sie sicher, dass die Aspose.Slides for Java-Bibliothek in Ihrem Java-Projekt installiert und eingerichtet ist. Sie können die Bibliothek herunterladen unter[Hier](https://releases.aspose.com/slides/java/).

## Schritt 1: Erstellen einer Präsentation

Erstellen wir zunächst eine neue Präsentation, mit der wir arbeiten können:

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
```

 Unbedingt austauschen`"Your Document Directory"` mit dem tatsächlichen Pfad zu Ihrem Dokumentverzeichnis.

## Schritt 2: Hinzufügen eines Diagramms

Als Nächstes fügen wir der Folie ein gruppiertes Säulendiagramm hinzu. Wir geben den Diagrammtyp, die Position (X-, Y-Koordinaten) und die Abmessungen (Breite und Höhe) des Diagramms an:

```java
IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 50, 50, 450, 300);
```

Hier haben wir an Position (50, 50) ein gruppiertes Säulendiagramm mit einer Breite von 450 und einer Höhe von 300 hinzugefügt. Sie können diese Werte nach Bedarf anpassen.

## Schritt 3: Positionsachse einstellen

Um die Positionsachse zwischen Kategorien festzulegen, können Sie den folgenden Code verwenden:

```java
chart.getAxes().getHorizontalAxis().setAxisBetweenCategories(true);
```

Dieser Code legt die horizontale Achse so fest, dass sie zwischen Kategorien angezeigt wird, was für bestimmte Diagrammlayouts nützlich sein kann.

## Schritt 4: Speichern der Präsentation

Abschließend speichern wir die Präsentation mit dem Diagramm:

```java
pres.save(dataDir + "AsposeClusteredColumnChart.pptx", SaveFormat.Pptx);
```

 Ersetzen`"AsposeClusteredColumnChart.pptx"` mit Ihrem gewünschten Dateinamen.

Das ist es! Sie haben mit Aspose.Slides für Java erfolgreich ein gruppiertes Säulendiagramm erstellt und die Positionsachse zwischen Kategorien festgelegt.

## Vollständiger Quellcode
```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
try
{
	IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 50, 50, 450, 300);
	chart.getAxes().getHorizontalAxis().setAxisBetweenCategories(true);
	pres.save(dataDir + "AsposeScatterChart.pptx", SaveFormat.Pptx);
}
finally
{
	if (pres != null) pres.dispose();
}
```

## Abschluss

In diesem Tutorial haben wir untersucht, wie Sie mit Aspose.Slides für Java die Positionsachse in einem Diagramm festlegen. Durch Befolgen der in dieser Anleitung beschriebenen Schritte haben Sie gelernt, wie Sie ein gruppiertes Säulendiagramm erstellen und dessen Erscheinungsbild anpassen, indem Sie die horizontale Achse zwischen den Kategorien positionieren. Aspose.Slides für Java bietet leistungsstarke Funktionen für die Arbeit mit Diagrammen und Präsentationen und ist damit ein wertvolles Werkzeug für Java-Entwickler.

## FAQs

### Wie kann ich das Diagramm weiter anpassen?

Sie können verschiedene Aspekte des Diagramms anpassen, einschließlich Datenreihen, Diagrammtitel, Legenden und mehr. Siehe die[Aspose.Slides für Java-Dokumentation](https://reference.aspose.com/slides/java/) Ausführliche Anleitungen und Beispiele finden Sie hier.

### Kann ich den Diagrammtyp ändern?

 Ja, Sie können den Diagrammtyp ändern, indem Sie die ändern`ChartType` Parameter beim Hinzufügen des Diagramms. Aspose.Slides für Java unterstützt verschiedene Diagrammtypen wie Balkendiagramme, Liniendiagramme und mehr.

### Wo finde ich weitere Beispiele und Dokumentation?

 Eine umfassende Dokumentation und weitere Beispiele finden Sie auf der[Aspose.Slides für Java-Dokumentation](https://reference.aspose.com/slides/java/) Seite.

Denken Sie daran, das Präsentationsobjekt zu entsorgen, wenn Sie damit fertig sind, um Systemressourcen freizugeben:

```java
if (pres != null) pres.dispose();
```

Das war’s für dieses Tutorial. Sie haben gelernt, wie Sie mit Aspose.Slides für Java die Positionsachse in einem Diagramm festlegen.