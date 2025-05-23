---
"description": "Verbessern Sie die Schrifteigenschaften von Diagrammen in Java-Folien mit Aspose.Slides für Java. Passen Sie Schriftgröße, Stil und Farbe für wirkungsvolle Präsentationen an."
"linktitle": "Schrifteigenschaften für Diagramme in Java-Folien"
"second_title": "Aspose.Slides Java PowerPoint-Verarbeitungs-API"
"title": "Schrifteigenschaften für Diagramme in Java-Folien"
"url": "/de/java/customization-and-formatting/font-properties-for-chart-java-slides/"
"weight": 11
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Schrifteigenschaften für Diagramme in Java-Folien


## Einführung in die Schrifteigenschaften für Diagramme in Java-Folien

Diese Anleitung führt Sie durch das Festlegen der Schrifteigenschaften für ein Diagramm in Java Slides mit Aspose.Slides. Sie können die Schriftgröße und das Erscheinungsbild des Diagrammtextes anpassen, um die visuelle Attraktivität Ihrer Präsentationen zu verbessern.

## Voraussetzungen

Bevor Sie beginnen, stellen Sie sicher, dass Aspose.Slides für Java API in Ihr Projekt integriert ist. Falls noch nicht geschehen, können Sie es von der [Aspose.Slides für Java-Dokumentation](https://reference.aspose.com/slides/java/).

## Schritt 1: Erstellen Sie eine Präsentation

Erstellen Sie zunächst eine neue Präsentation mit dem folgenden Code:

```java
// Der Pfad zum Dokumentenverzeichnis.
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
```

## Schritt 2: Diagramm hinzufügen

Fügen wir Ihrer Präsentation nun ein gruppiertes Säulendiagramm hinzu:

```java
IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 100, 100, 500, 400);
```

Hier fügen wir der ersten Folie bei den Koordinaten (100, 100) ein gruppiertes Säulendiagramm mit einer Breite von 500 Einheiten und einer Höhe von 400 Einheiten hinzu.

## Schritt 3: Schrifteigenschaften anpassen

Als Nächstes passen wir die Schrifteigenschaften des Diagramms an. In diesem Beispiel setzen wir die Schriftgröße für den gesamten Diagrammtext auf 20:

```java
chart.getTextFormat().getPortionFormat().setFontHeight(20);
```

Dieser Code legt die Schriftgröße für den gesamten Text im Diagramm auf 20 Punkte fest.

## Schritt 4: Datenbeschriftungen anzeigen

Mit dem folgenden Code können Sie auch Datenbeschriftungen im Diagramm anzeigen:

```java
chart.getChartData().getSeries().get_Item(0).getLabels().getDefaultDataLabelFormat().setShowValue(true);
```

Diese Codezeile aktiviert Datenbeschriftungen für die erste Reihe im Diagramm und zeigt die Werte in den Diagrammspalten an.

## Schritt 5: Speichern Sie die Präsentation

Speichern Sie abschließend die Präsentation mit Ihren angepassten Diagrammschrifteigenschaften:

```java
pres.save(dataDir + "FontPropertiesForChart.pptx", SaveFormat.Pptx);
```

Dieser Code speichert die Präsentation im angegebenen Verzeichnis unter dem Dateinamen „FontPropertiesForChart.pptx“.

## Vollständiger Quellcode für Schrifteigenschaften für Diagramme in Java-Folien

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

In diesem Tutorial haben Sie gelernt, wie Sie die Schrifteigenschaften eines Diagramms in Java Slides mit Aspose.Slides für Java anpassen. Sie können diese Techniken anwenden, um das Erscheinungsbild Ihrer Diagramme und Präsentationen zu verbessern. Weitere Optionen finden Sie im [Aspose.Slides für Java-Dokumentation](https://reference.aspose.com/slides/java/).

## Häufig gestellte Fragen

### Wie kann ich die Schriftfarbe ändern?

Um die Schriftfarbe für Diagrammtext zu ändern, verwenden Sie `chart.getTextFormat().getPortionFormat().setFontColor(Color.RED);`, ersetzt `Color.RED` mit der gewünschten Farbe.

### Kann ich den Schriftstil (fett, kursiv usw.) ändern?

Ja, Sie können den Schriftstil ändern. Verwenden Sie `chart.getTextFormat().getPortionFormat().setFontBold(true);` um die Schrift fett zu machen. Ebenso können Sie `setFontItalic(true)` um es kursiv zu machen.

### Wie passe ich die Schrifteigenschaften für bestimmte Diagrammelemente an?

Um die Schrifteigenschaften für bestimmte Diagrammelemente wie Achsenbeschriftungen oder Legendentext anzupassen, können Sie auf diese Elemente zugreifen und ihre Schrifteigenschaften mit ähnlichen Methoden wie oben gezeigt festlegen.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}