---
title: Fügen Sie Datenpunkten in Java-Folien Farbe hinzu
linktitle: Fügen Sie Datenpunkten in Java-Folien Farbe hinzu
second_title: Aspose.Slides Java PowerPoint-Verarbeitungs-API
description: Erfahren Sie, wie Sie mit Aspose.Slides für Java Datenpunkten in Java-Folien Farbe hinzufügen.
weight: 10
url: /de/java/chart-data-manipulation/add-color-data-points-java-slides/
---

{< blocks/products/pf/main-wrap-class >}
{< blocks/products/pf/main-container >}
{< blocks/products/pf/tutorial-page-section >}


## Einführung in das Hinzufügen von Farbe zu Datenpunkten in Java-Folien

In diesem Tutorial zeigen wir, wie Sie mit Aspose.Slides für Java Datenpunkten in Java-Folien Farbe hinzufügen. Diese Schritt-für-Schritt-Anleitung enthält Quellcodebeispiele, die Ihnen bei dieser Aufgabe helfen.

## Voraussetzungen

Stellen Sie zunächst sicher, dass die folgenden Voraussetzungen erfüllt sind:

- Java-Entwicklungsumgebung
- Aspose.Slides für Java-Bibliothek

## Schritt 1: Erstellen Sie eine neue Präsentation

Zuerst erstellen wir eine neue Präsentation mit Aspose.Slides für Java. Diese Präsentation dient als Container für unser Diagramm.

```java
Presentation pres = new Presentation();
```

## Schritt 2: Fügen Sie ein Sunburst-Diagramm hinzu

Fügen wir nun der Präsentation ein Sunburst-Diagramm hinzu. Wir geben den Diagrammtyp, die Position und die Größe an.

```java
// Der Pfad zum Dokumentverzeichnis.
String dataDir = "Your Document Directory";
IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.Sunburst, 100, 100, 450, 400);
```

## Schritt 3: Auf Datenpunkte zugreifen

 Um Datenpunkte im Diagramm zu ändern, müssen wir auf die`IChartDataPointCollection` Objekt.

```java
IChartDataPointCollection dataPoints = chart.getChartData().getSeries().get_Item(0).getDataPoints();
```

## Schritt 4: Datenpunkte anpassen

In diesem Schritt passen wir bestimmte Datenpunkte an. Hier ändern wir die Farbe der Datenpunkte und konfigurieren die Beschriftungseinstellungen.

```java
// Datenpunkt 0 anpassen
IDataLabel branch1Label = dataPoints.get_Item(0).getDataPointLevels().get_Item(2).getLabel();
branch1Label.getDataLabelFormat().setShowCategoryName(false);
branch1Label.getDataLabelFormat().setShowSeriesName(true);
branch1Label.getDataLabelFormat().getTextFormat().getPortionFormat().getFillFormat().setFillType(FillType.Solid);
branch1Label.getDataLabelFormat().getTextFormat().getPortionFormat().getFillFormat().getSolidFillColor().setColor(java.awt.Color.YELLOW);

// Datenpunkt 9 anpassen
IFormat steam4Format = dataPoints.get_Item(9).getFormat();
steam4Format.getFill().setFillType(FillType.Solid);
steam4Format.getFill().getSolidFillColor().setColor(com.aspose.cells.Color.fromArgb(0, 176, 240, 255).d());
```

## Schritt 5: Speichern Sie die Präsentation

Speichern Sie abschließend die Präsentation mit dem angepassten Diagramm.

```java
pres.save("Your Output Directory/AddColorToDataPoints.pptx", SaveFormat.Pptx);
```

Das ist es! Sie haben mit Aspose.Slides für Java erfolgreich bestimmten Datenpunkten in einer Java-Folie Farbe hinzugefügt.

## Vollständiger Quellcode zum Hinzufügen von Farbe zu Datenpunkten in Java-Folien

```java
Presentation pres = new Presentation();
try
{
	// Der Pfad zum Dokumentverzeichnis.
	String dataDir = "Your Document Directory";
	IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.Sunburst, 100, 100, 450, 400);
	IChartDataPointCollection dataPoints = chart.getChartData().getSeries().get_Item(0).getDataPoints();
	dataPoints.get_Item(3).getDataPointLevels().get_Item(0).getLabel().getDataLabelFormat().setShowValue(true);
	IDataLabel branch1Label = dataPoints.get_Item(0).getDataPointLevels().get_Item(2).getLabel();
	branch1Label.getDataLabelFormat().setShowCategoryName(false);
	branch1Label.getDataLabelFormat().setShowSeriesName(true);
	branch1Label.getDataLabelFormat().getTextFormat().getPortionFormat().getFillFormat().setFillType(FillType.Solid);
	branch1Label.getDataLabelFormat().getTextFormat().getPortionFormat().getFillFormat().getSolidFillColor().setColor(java.awt.Color.YELLOW);
	IFormat steam4Format = dataPoints.get_Item(9).getFormat();
	steam4Format.getFill().setFillType(FillType.Solid);
	steam4Format.getFill().getSolidFillColor().setColor(com.aspose.cells.Color.fromArgb(0, 176, 240, 255).d());//MACHEN
	pres.save(dataDir + "AddColorToDataPoints.pptx", SaveFormat.Pptx);
}
finally
{
	if (pres != null) pres.dispose();
}
```

## Abschluss

In diesem Tutorial haben Sie gelernt, wie Sie mit Aspose.Slides für Java Datenpunkten in Java-Folien Farbe hinzufügen. Sie können Ihre Diagramme und Präsentationen weiter an Ihre spezifischen Anforderungen anpassen.

## Häufig gestellte Fragen

### Wie kann ich die Farbe anderer Datenpunkte ändern?

Um die Farbe anderer Datenpunkte zu ändern, können Sie einen ähnlichen Ansatz wie in Schritt 4 gezeigt verfolgen. Greifen Sie auf den Datenpunkt zu, den Sie anpassen möchten, und ändern Sie seine Farb- und Beschriftungseinstellungen.

### Kann ich andere Aspekte des Diagramms anpassen?

 Ja, Sie können verschiedene Aspekte des Diagramms anpassen, einschließlich Schriftarten, Beschriftungen, Titel und mehr. Weitere Informationen finden Sie im[Aspose.Slides für Java-Dokumentation](https://reference.aspose.com/slides/java/) für detaillierte Anpassungsoptionen.

### Wo finde ich weitere Beispiele und Dokumentation?

 Weitere Beispiele und eine ausführliche Dokumentation zur Verwendung von Aspose.Slides für Java finden Sie auf der[Aspose.Slides-Dokumentation](https://reference.aspose.com/slides/java/) Webseite.
{< /blocks/products/pf/tutorial-page-section >}

{< /blocks/products/pf/main-container >}
{< /blocks/products/pf/main-wrap-class >}

{< blocks/products/products-backtop-button >}
