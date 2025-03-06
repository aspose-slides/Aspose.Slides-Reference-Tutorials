---
title: Festlegen der Positionsachse in Java-Folien
linktitle: Festlegen der Positionsachse in Java-Folien
second_title: Aspose.Slides Java PowerPoint-Verarbeitungs-API
description: Verbessern Sie Ihre Diagramme mit Aspose.Slides für Java. Erfahren Sie, wie Sie die Positionsachse in Java-Folien festlegen, beeindruckende Präsentationen erstellen und Diagrammlayouts mühelos anpassen.
weight: 16
url: /de/java/customization-and-formatting/setting-position-axis-java-slides/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}


## Einführung in das Einstellen der Positionsachse in Aspose.Slides für Java

In diesem Tutorial lernen wir, wie man die Positionsachse in einem Diagramm mit Aspose.Slides für Java einstellt. Das Positionieren der Achse kann nützlich sein, wenn Sie das Erscheinungsbild und Layout Ihres Diagramms anpassen möchten. Wir erstellen ein gruppiertes Säulendiagramm und passen die Position der horizontalen Achse zwischen den Kategorien an.

## Voraussetzungen

 Bevor wir beginnen, stellen Sie sicher, dass Sie die Bibliothek Aspose.Slides für Java in Ihrem Java-Projekt installiert und eingerichtet haben. Sie können die Bibliothek von herunterladen[Hier](https://releases.aspose.com/slides/java/).

## Schritt 1: Erstellen einer Präsentation

Lassen Sie uns zunächst eine neue Präsentation zum Arbeiten erstellen:

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
```

 Ersetzen Sie unbedingt`"Your Document Directory"` durch den tatsächlichen Pfad zu Ihrem Dokumentverzeichnis.

## Schritt 2: Hinzufügen eines Diagramms

Als Nächstes fügen wir der Folie ein gruppiertes Säulendiagramm hinzu. Wir geben den Diagrammtyp, die Position (x-, y-Koordinaten) und die Abmessungen (Breite und Höhe) des Diagramms an:

```java
IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 50, 50, 450, 300);
```

Hier haben wir an der Position (50, 50) ein gruppiertes Säulendiagramm mit einer Breite von 450 und einer Höhe von 300 hinzugefügt. Sie können diese Werte nach Bedarf anpassen.

## Schritt 3: Positionsachse festlegen

Um die Positionsachse zwischen Kategorien festzulegen, können Sie den folgenden Code verwenden:

```java
chart.getAxes().getHorizontalAxis().setAxisBetweenCategories(true);
```

Dieser Code legt die horizontale Achse für die Anzeige zwischen den Kategorien fest, was für bestimmte Diagrammlayouts nützlich sein kann.

## Schritt 4: Speichern der Präsentation

Zum Schluss speichern wir die Präsentation mit dem Diagramm:

```java
pres.save(dataDir + "AsposeClusteredColumnChart.pptx", SaveFormat.Pptx);
```

 Ersetzen`"AsposeClusteredColumnChart.pptx"` durch den gewünschten Dateinamen.

Das ist es! Sie haben erfolgreich ein gruppiertes Säulendiagramm erstellt und die Positionsachse zwischen den Kategorien mit Aspose.Slides für Java festgelegt.

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

In diesem Tutorial haben wir untersucht, wie man die Positionsachse in einem Diagramm mit Aspose.Slides für Java einstellt. Indem Sie die in diesem Handbuch beschriebenen Schritte befolgen, haben Sie gelernt, wie Sie ein gruppiertes Säulendiagramm erstellen und sein Erscheinungsbild anpassen, indem Sie die horizontale Achse zwischen den Kategorien positionieren. Aspose.Slides für Java bietet leistungsstarke Funktionen für die Arbeit mit Diagrammen und Präsentationen und ist damit ein wertvolles Tool für Java-Entwickler.

## Häufig gestellte Fragen

### Wie kann ich das Diagramm weiter anpassen?

Sie können verschiedene Aspekte des Diagramms anpassen, einschließlich Datenreihen, Diagrammtitel, Legenden und mehr. Weitere Informationen finden Sie im[Aspose.Slides für Java-Dokumentation](https://reference.aspose.com/slides/java/) für detaillierte Anweisungen und Beispiele.

### Kann ich den Diagrammtyp ändern?

 Ja, Sie können den Diagrammtyp ändern, indem Sie die`ChartType` Parameter beim Hinzufügen des Diagramms. Aspose.Slides für Java unterstützt verschiedene Diagrammtypen wie Balkendiagramme, Liniendiagramme und mehr.

### Wo finde ich weitere Beispiele und Dokumentation?

 Eine ausführliche Dokumentation und weitere Beispiele finden Sie auf der[Aspose.Slides für Java-Dokumentation](https://reference.aspose.com/slides/java/) Seite.

Denken Sie daran, das Präsentationsobjekt zu entsorgen, wenn Sie es nicht mehr benötigen, um Systemressourcen freizugeben:

```java
if (pres != null) pres.dispose();
```

Das war's für dieses Tutorial. Sie haben gelernt, wie Sie die Positionsachse in einem Diagramm mit Aspose.Slides für Java festlegen.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
