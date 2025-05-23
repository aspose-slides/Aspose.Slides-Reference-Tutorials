---
"description": "Optimieren Sie PowerPoint-Präsentationen mit Aspose.Slides für Java. Erfahren Sie in unserer Schritt-für-Schritt-Anleitung, wie Sie die Schriftgröße der Legende und mehr anpassen."
"linktitle": "Schriftgrößenlegende in Java-Folien"
"second_title": "Aspose.Slides Java PowerPoint-Verarbeitungs-API"
"title": "Schriftgrößenlegende in Java-Folien"
"url": "/de/java/chart-elements/font-size-legend-java-slides/"
"weight": 13
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Schriftgrößenlegende in Java-Folien


## Einführung in die Schriftgrößenlegende in Java Slides

In diesem Tutorial erfahren Sie, wie Sie die Schriftgröße der Legende einer PowerPoint-Folie mit Aspose.Slides für Java anpassen. Wir stellen Ihnen Schritt-für-Schritt-Anleitungen und Quellcode zur Verfügung.

## Voraussetzungen

Bevor Sie beginnen, stellen Sie sicher, dass die Bibliothek Aspose.Slides für Java in Ihrem Java-Projekt installiert und eingerichtet ist. Sie können die Bibliothek hier herunterladen: [Hier](https://releases.aspose.com/slides/java/).

## Schritt 1: Initialisieren der Präsentation

Importieren Sie zunächst die erforderlichen Klassen und initialisieren Sie Ihre PowerPoint-Präsentation.

```java
// Der Pfad zum Dokumentenverzeichnis.
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "test.pptx");
```

Ersetzen `"Your Document Directory"` durch den tatsächlichen Pfad zu Ihrer PowerPoint-Datei.

## Schritt 2: Diagramm hinzufügen

Als Nächstes fügen wir der Folie ein Diagramm hinzu und legen die Schriftgröße der Legende fest.

```java
try
{
    IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 50, 50, 600, 400);
    chart.getLegend().getTextFormat().getPortionFormat().setFontHeight(20);
}
```

In diesem Code erstellen wir ein gruppiertes Säulendiagramm auf der ersten Folie und setzen die Schriftgröße des Legendentextes auf 20 Punkte. Sie können die `setFontHeight` Wert, um die Schriftgröße nach Bedarf zu ändern.

## Schritt 3: Achsenwerte anpassen

Passen wir nun die Werte der vertikalen Achse des Diagramms an.

```java
    chart.getAxes().getVerticalAxis().setAutomaticMinValue(false);
    chart.getAxes().getVerticalAxis().setMinValue(-5);
    chart.getAxes().getVerticalAxis().setAutomaticMaxValue(false);
    chart.getAxes().getVerticalAxis().setMaxValue(10);
```

Hier legen wir die Minimal- und Maximalwerte für die vertikale Achse fest. Sie können die Werte entsprechend Ihren Datenanforderungen ändern.

## Schritt 4: Speichern Sie die Präsentation

Speichern Sie die geänderte Präsentation abschließend in einer neuen Datei.

```java
    pres.save(dataDir + "output.pptx", SaveFormat.Pptx);
}
finally
{
    if (pres != null) pres.dispose();
}
```

Dieser Code speichert die geänderte Präsentation als „output.pptx“ im angegebenen Verzeichnis.

## Vollständiger Quellcode für die Schriftgrößenlegende in Java-Folien

```java
// Der Pfad zum Dokumentenverzeichnis.
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "test.pptx");
try
{
	IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 50, 50, 600, 400);
	chart.getLegend().getTextFormat().getPortionFormat().setFontHeight(20);
	chart.getAxes().getVerticalAxis().setAutomaticMinValue(false);
	chart.getAxes().getVerticalAxis().setMinValue(-5);
	chart.getAxes().getVerticalAxis().setAutomaticMaxValue(false);
	chart.getAxes().getVerticalAxis().setMaxValue(10);
	pres.save(dataDir + "output.pptx", SaveFormat.Pptx);
}
finally
{
	if (pres != null) pres.dispose();
}
```

## Abschluss

Sie haben die Schriftgröße der Legende in einer Java PowerPoint-Folie mit Aspose.Slides für Java erfolgreich angepasst. Sie können die Funktionen von Aspose.Slides weiter erkunden, um interaktive und optisch ansprechende Präsentationen zu erstellen.

## Häufig gestellte Fragen

### Wie ändere ich die Schriftgröße des Legendentextes in einem Diagramm?

Um die Schriftgröße des Legendentextes in einem Diagramm zu ändern, können Sie den folgenden Code verwenden:

```java
IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 50, 50, 600, 400);
chart.getLegend().getTextFormat().getPortionFormat().setFontHeight(20);
```

In diesem Code erstellen wir ein Diagramm und setzen die Schriftgröße des Legendentextes auf 20 Punkte. Sie können die `setFontHeight` Wert, um die Schriftgröße zu ändern.

### Kann ich andere Eigenschaften der Legende in einem Diagramm anpassen?

Ja, Sie können verschiedene Eigenschaften der Legende in einem Diagramm mit Aspose.Slides anpassen. Zu den gängigen Eigenschaften, die Sie anpassen können, gehören Textformatierung, Position, Sichtbarkeit und mehr. Um beispielsweise die Position der Legende zu ändern, können Sie Folgendes verwenden:

```java
chart.getLegend().setPosition(LegendPosition.Bottom);
```

Dieser Code legt fest, dass die Legende unten im Diagramm angezeigt wird. Weitere Anpassungsmöglichkeiten finden Sie in der Aspose.Slides-Dokumentation.

### Wie lege ich Minimal- und Maximalwerte für die vertikale Achse in einem Diagramm fest?

Um Minimal- und Maximalwerte für die vertikale Achse in einem Diagramm festzulegen, können Sie den folgenden Code verwenden:

```java
chart.getAxes().getVerticalAxis().setAutomaticMinValue(false);
chart.getAxes().getVerticalAxis().setMinValue(-5);
chart.getAxes().getVerticalAxis().setAutomaticMaxValue(false);
chart.getAxes().getVerticalAxis().setMaxValue(10);
```

Hier deaktivieren wir die automatische Achsenskalierung und legen die Minimal- und Maximalwerte für die vertikale Achse fest. Passen Sie die Werte nach Bedarf an Ihre Diagrammdaten an.

### Wo finde ich weitere Informationen und Dokumentation zu Aspose.Slides?

Ausführliche Dokumentation und API-Referenzen zu Aspose.Slides für Java finden Sie auf der Aspose-Dokumentationswebsite. Besuchen Sie [Hier](https://reference.aspose.com/slides/java/) für detaillierte Informationen zur Bibliotheksnutzung.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}