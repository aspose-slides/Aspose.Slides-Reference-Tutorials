---
title: Schriftarteigenschaften für Diagramme in Java-Folien
linktitle: Schriftarteigenschaften für Diagramme in Java-Folien
second_title: Aspose.Slides Java PowerPoint-Verarbeitungs-API
description: Verbessern Sie die Eigenschaften von Diagrammschriftarten in Java-Folien mit Aspose.Slides für Java. Passen Sie Schriftgröße, Stil und Farbe für wirkungsvolle Präsentationen an.
type: docs
weight: 11
url: /de/java/customization-and-formatting/font-properties-for-chart-java-slides/
---

## Einführung in die Schriftarteigenschaften für Diagramme in Java-Folien

Diese Anleitung führt Sie durch das Festlegen von Schriftarteigenschaften für ein Diagramm in Java Slides mithilfe von Aspose.Slides. Sie können die Schriftgröße und das Erscheinungsbild des Diagrammtexts anpassen, um die visuelle Attraktivität Ihrer Präsentationen zu verbessern.

## Voraussetzungen

 Bevor Sie beginnen, stellen Sie sicher, dass die Aspose.Slides für Java-API in Ihr Projekt integriert ist. Wenn Sie es noch nicht getan haben, können Sie es hier herunterladen[Aspose.Slides für Java-Dokumentation](https://reference.aspose.com/slides/java/).

## Schritt 1: Erstellen Sie eine Präsentation

Erstellen Sie zunächst eine neue Präsentation mit dem folgenden Code:

```java
// Der Pfad zum Dokumentenverzeichnis.
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
```

## Schritt 2: Fügen Sie ein Diagramm hinzu

Fügen wir Ihrer Präsentation nun ein gruppiertes Säulendiagramm hinzu:

```java
IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 100, 100, 500, 400);
```

Hier fügen wir der ersten Folie bei den Koordinaten (100, 100) ein gruppiertes Säulendiagramm mit einer Breite von 500 Einheiten und einer Höhe von 400 Einheiten hinzu.

## Schritt 3: Schriftarteigenschaften anpassen

Als Nächstes passen wir die Schriftarteigenschaften des Diagramms an. In diesem Beispiel stellen wir die Schriftgröße für den gesamten Diagrammtext auf 20 ein:

```java
chart.getTextFormat().getPortionFormat().setFontHeight(20);
```

Dieser Code legt die Schriftgröße für den gesamten Text im Diagramm auf 20 Punkt fest.

## Schritt 4: Datenbeschriftungen anzeigen

Sie können Datenbeschriftungen auch mit dem folgenden Code im Diagramm anzeigen:

```java
chart.getChartData().getSeries().get_Item(0).getLabels().getDefaultDataLabelFormat().setShowValue(true);
```

Diese Codezeile aktiviert Datenbeschriftungen für die erste Reihe im Diagramm und zeigt die Werte in den Diagrammspalten an.

## Schritt 5: Speichern Sie die Präsentation

Speichern Sie abschließend die Präsentation mit Ihren benutzerdefinierten Diagrammschriftarteigenschaften:

```java
pres.save(dataDir + "FontPropertiesForChart.pptx", SaveFormat.Pptx);
```

Dieser Code speichert die Präsentation im angegebenen Verzeichnis mit dem Dateinamen „FontPropertiesForChart.pptx“.

## Vollständiger Quellcode für Schriftarteigenschaften für Diagramme in Java-Folien

```java
// Der Pfad zum Dokumentenverzeichnis.
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
try
{
	IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 100, 100, 500, 400);
	chart.getTextFormat().getPortionFormat().setFontHeight(20);
	chart.getChartData().getSeries().get_Item(0).getLabels().getDefaultDataLabelFormat().setShowValue(true);
	pres.save(dataDir + "FontPropertiesForChart.pptx", SaveFormat.Pptx);
}
finally
{
	if (pres != null) pres.dispose();
}
```

## Abschluss

In diesem Tutorial haben Sie gelernt, wie Sie mit Aspose.Slides für Java die Schriftarteigenschaften für ein Diagramm in Java Slides anpassen. Sie können diese Techniken anwenden, um das Erscheinungsbild Ihrer Diagramme und Präsentationen zu verbessern. Entdecken Sie weitere Optionen im[Aspose.Slides für Java-Dokumentation](https://reference.aspose.com/slides/java/).

## FAQs

### Wie kann ich die Schriftfarbe ändern?

 Um die Schriftfarbe für Diagrammtext zu ändern, verwenden Sie`chart.getTextFormat().getPortionFormat().setFontColor(Color.RED);` , ersetzen`Color.RED` mit der gewünschten Farbe.

### Kann ich den Schriftstil ändern (fett, kursiv usw.)?

 Ja, Sie können den Schriftstil ändern. Verwenden`chart.getTextFormat().getPortionFormat().setFontBold(true);` um die Schriftart fett zu machen. Ebenso können Sie verwenden`setFontItalic(true)` um es kursiv zu machen.

### Wie passe ich die Schrifteigenschaften für bestimmte Diagrammelemente an?

Um die Schriftarteigenschaften für bestimmte Diagrammelemente wie Achsenbeschriftungen oder Legendentext anzupassen, können Sie auf diese Elemente zugreifen und ihre Schriftarteigenschaften mithilfe ähnlicher Methoden wie oben gezeigt festlegen.