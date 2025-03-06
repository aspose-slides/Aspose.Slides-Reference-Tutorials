---
title: Schriftgrößenlegende in Java-Folien
linktitle: Schriftgrößenlegende in Java-Folien
second_title: Aspose.Slides Java PowerPoint-Verarbeitungs-API
description: Verbessern Sie PowerPoint-Präsentationen mit Aspose.Slides für Java. Erfahren Sie in unserer Schritt-für-Schritt-Anleitung, wie Sie die Schriftgrößen von Legenden und mehr anpassen.
weight: 13
url: /de/java/chart-elements/font-size-legend-java-slides/
---

{< blocks/products/pf/main-wrap-class >}
{< blocks/products/pf/main-container >}
{< blocks/products/pf/tutorial-page-section >}


## Einführung in die Schriftgrößenlegende in Java Slides

In diesem Tutorial erfahren Sie, wie Sie die Schriftgröße der Legende in einer PowerPoint-Folie mit Aspose.Slides für Java anpassen. Wir stellen Ihnen Schritt-für-Schritt-Anleitungen und Quellcode zur Verfügung, um diese Aufgabe zu erfüllen.

## Voraussetzungen

 Bevor Sie beginnen, stellen Sie sicher, dass Sie die Bibliothek Aspose.Slides für Java in Ihrem Java-Projekt installiert und eingerichtet haben. Sie können die Bibliothek von herunterladen[Hier](https://releases.aspose.com/slides/java/).

## Schritt 1: Initialisieren der Präsentation

Importieren Sie zunächst die erforderlichen Klassen und initialisieren Sie Ihre PowerPoint-Präsentation.

```java
// Der Pfad zum Dokumentverzeichnis.
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "test.pptx");
```

 Ersetzen`"Your Document Directory"` durch den tatsächlichen Pfad zu Ihrer PowerPoint-Datei.

## Schritt 2: Diagramm hinzufügen

Als Nächstes fügen wir der Folie ein Diagramm hinzu und legen die Schriftgröße der Legende fest.

```java
try
{
    IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 50, 50, 600, 400);
    chart.getLegend().getTextFormat().getPortionFormat().setFontHeight(20);
}
```

 In diesem Code erstellen wir ein gruppiertes Säulendiagramm auf der ersten Folie und setzen die Schriftgröße des Legendentextes auf 20 Punkte. Sie können die`setFontHeight`Wert, um die Schriftgröße nach Bedarf zu ändern.

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

Speichern Sie abschließend die geänderte Präsentation in einer neuen Datei.

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
// Der Pfad zum Dokumentverzeichnis.
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

Sie haben die Schriftgröße der Legende in einer Java PowerPoint-Folie mithilfe von Aspose.Slides für Java erfolgreich angepasst. Sie können die Funktionen von Aspose.Slides weiter erkunden, um interaktive und optisch ansprechende Präsentationen zu erstellen.

## Häufig gestellte Fragen

### Wie ändere ich die Schriftgröße des Legendentextes in einem Diagramm?

Um die Schriftgröße des Legendentextes in einem Diagramm zu ändern, können Sie den folgenden Code verwenden:

```java
IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 50, 50, 600, 400);
chart.getLegend().getTextFormat().getPortionFormat().setFontHeight(20);
```

 In diesem Code erstellen wir ein Diagramm und setzen die Schriftgröße des Legendentextes auf 20 Punkte. Sie können die`setFontHeight` Wert, um die Schriftgröße zu ändern.

### Kann ich andere Eigenschaften der Legende in einem Diagramm anpassen?

Ja, Sie können mit Aspose.Slides verschiedene Eigenschaften der Legende in einem Diagramm anpassen. Einige der allgemeinen Eigenschaften, die Sie anpassen können, sind Textformatierung, Position, Sichtbarkeit und mehr. Um beispielsweise die Position der Legende zu ändern, können Sie Folgendes verwenden:

```java
chart.getLegend().setPosition(LegendPosition.Bottom);
```

Dieser Code legt fest, dass die Legende unten im Diagramm angezeigt wird. Weitere Anpassungsoptionen finden Sie in der Aspose.Slides-Dokumentation.

### Wie lege ich Minimal- und Maximalwerte für die vertikale Achse in einem Diagramm fest?

Um Minimal- und Maximalwerte für die vertikale Achse in einem Diagramm festzulegen, können Sie den folgenden Code verwenden:

```java
chart.getAxes().getVerticalAxis().setAutomaticMinValue(false);
chart.getAxes().getVerticalAxis().setMinValue(-5);
chart.getAxes().getVerticalAxis().setAutomaticMaxValue(false);
chart.getAxes().getVerticalAxis().setMaxValue(10);
```

Hier deaktivieren wir die automatische Achsenskalierung und geben die Mindest- und Höchstwerte für die vertikale Achse an. Passen Sie die Werte nach Bedarf für Ihre Diagrammdaten an.

### Wo finde ich weitere Informationen und Dokumentation zu Aspose.Slides?

 Ausführliche Dokumentation und API-Referenzen für Aspose.Slides für Java finden Sie auf der Aspose-Dokumentationswebsite. Besuchen Sie[Hier](https://reference.aspose.com/slides/java/) für detaillierte Informationen zur Benutzung der Bibliothek.
{< /blocks/products/pf/tutorial-page-section >}

{< /blocks/products/pf/main-container >}
{< /blocks/products/pf/main-wrap-class >}

{< blocks/products/products-backtop-button >}
