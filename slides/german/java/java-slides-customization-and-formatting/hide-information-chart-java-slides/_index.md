---
title: Informationen aus Diagrammen in Java-Folien ausblenden
linktitle: Informationen aus Diagrammen in Java-Folien ausblenden
second_title: Aspose.Slides Java PowerPoint-Verarbeitungs-API
description: Erfahren Sie, wie Sie mit Aspose.Slides für Java Diagrammelemente in Java-Folien ausblenden. Passen Sie Präsentationen mit Schritt-für-Schritt-Anleitung und Quellcode für mehr Übersichtlichkeit und Ästhetik an.
weight: 13
url: /de/java/customization-and-formatting/hide-information-chart-java-slides/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}


## Einführung zum Ausblenden von Informationen aus Diagrammen in Java-Folien

In diesem Tutorial erfahren Sie, wie Sie mithilfe der Aspose.Slides für Java-API verschiedene Elemente aus einem Diagramm in Java Slides ausblenden. Mit diesem Code können Sie Ihre Diagramme nach Bedarf für Ihre Präsentationen anpassen.

## Schritt 1: Einrichten der Umgebung

 Bevor wir beginnen, stellen Sie sicher, dass Sie die Aspose.Slides für Java-Bibliothek zu Ihrem Projekt hinzugefügt haben. Sie können sie hier herunterladen:[Hier](https://releases.aspose.com/slides/java/).

## Schritt 2: Erstellen Sie eine neue Präsentation

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
```

## Schritt 3: Hinzufügen eines Diagramms zur Folie

Wir fügen einer Folie ein Liniendiagramm mit Markierungen hinzu und blenden dann verschiedene Elemente des Diagramms aus.

```java
ISlide slide = pres.getSlides().get_Item(0);
IChart chart = slide.getShapes().addChart(ChartType.LineWithMarkers, 140, 118, 320, 370);
```

## Schritt 4: Diagrammtitel ausblenden

Sie können den Diagrammtitel wie folgt ausblenden:

```java
chart.setTitle(false);
```

## Schritt 5: Werteachse ausblenden

Um die Werteachse (vertikale Achse) auszublenden, verwenden Sie den folgenden Code:

```java
chart.getAxes().getVerticalAxis().setVisible(false);
```

## Schritt 6: Kategorieachse ausblenden

Um die Kategorieachse (horizontale Achse) auszublenden, verwenden Sie diesen Code:

```java
chart.getAxes().getHorizontalAxis().setVisible(false);
```

## Schritt 7: Legende ausblenden

Sie können die Legende des Diagramms wie folgt ausblenden:

```java
chart.setLegend(false);
```

## Schritt 8: Hauptgitterlinien ausblenden

Um die Hauptgitterlinien der horizontalen Achse auszublenden, können Sie den folgenden Code verwenden:

```java
chart.getAxes().getHorizontalAxis().getMajorGridLinesFormat().getLine().getFillFormat().setFillType(FillType.NoFill);
```

## Schritt 9: Serie entfernen

Wenn Sie alle Reihen aus dem Diagramm entfernen möchten, können Sie eine Schleife wie diese verwenden:

```java
for (int i = 0; i < chart.getChartData().getSeries().size(); i++) {
    chart.getChartData().getSeries().removeAt(i);
}
```

## Schritt 10: Diagrammserien anpassen

Sie können die Diagrammreihe nach Bedarf anpassen. In diesem Beispiel ändern wir den Markierungsstil, die Position der Datenbeschriftung, die Markierungsgröße, die Linienfarbe und den Strichstil:

```java
IChartSeries series = chart.getChartData().getSeries().get_Item(0);
series.getMarker().setSymbol(MarkerStyleType.Circle);
series.getLabels().getDefaultDataLabelFormat().setShowValue(true);
series.getLabels().getDefaultDataLabelFormat().setPosition(LegendDataLabelPosition.Top);
series.getMarker().setSize(15);
series.getFormat().getLine().getFillFormat().setFillType(FillType.Solid);
series.getFormat().getLine().getFillFormat().getSolidFillColor().setColor(new Color(PresetColor.Purple));
series.getFormat().getLine().setDashStyle(LineDashStyle.Solid);
```

## Schritt 11: Speichern Sie die Präsentation

Speichern Sie die Präsentation abschließend in einer Datei:

```java
pres.save(dataDir + "HideInformationFromChart.pptx", SaveFormat.Pptx);
```

Das ist es! Sie haben erfolgreich verschiedene Elemente aus einem Diagramm in Java Slides mithilfe von Aspose.Slides für Java ausgeblendet. Sie können Ihre Diagramme und Präsentationen nach Bedarf weiter an Ihre spezifischen Anforderungen anpassen.

## Vollständiger Quellcode zum Ausblenden von Informationen aus Diagrammen in Java-Folien

```java
// Der Pfad zum Dokumentverzeichnis.
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
try
{
	ISlide slide = pres.getSlides().get_Item(0);
	IChart chart = slide.getShapes().addChart(ChartType.LineWithMarkers, 140, 118, 320, 370);
	//Diagrammtitel ausblenden
	chart.setTitle(false);
	///Werteachse ausblenden
	chart.getAxes().getVerticalAxis().setVisible(false);
	//Sichtbarkeit der Kategorieachse
	chart.getAxes().getHorizontalAxis().setVisible(false);
	//Legende ausblenden
	chart.setLegend(false);
	//Ausblenden von Hauptgitterlinien
	chart.getAxes().getHorizontalAxis().getMajorGridLinesFormat().getLine().getFillFormat().setFillType(FillType.NoFill);
	for (int i = 0; i < chart.getChartData().getSeries().size(); i++)
	{
		chart.getChartData().getSeries().removeAt(i);
	}
	IChartSeries series = chart.getChartData().getSeries().get_Item(0);
	series.getMarker().setSymbol(MarkerStyleType.Circle);
	series.getLabels().getDefaultDataLabelFormat().setShowValue(true);
	series.getLabels().getDefaultDataLabelFormat().setPosition(LegendDataLabelPosition.Top);
	series.getMarker().setSize(15);
	//Festlegen der Linienfarbe der Serie
	series.getFormat().getLine().getFillFormat().setFillType(FillType.Solid);
	series.getFormat().getLine().getFillFormat().getSolidFillColor().setColor(new Color(PresetColor.Purple));
	series.getFormat().getLine().setDashStyle(LineDashStyle.Solid);
	pres.save(dataDir + "HideInformationFromChart.pptx", SaveFormat.Pptx);
}
finally
{
	if (pres != null) pres.dispose();
}
```
## Abschluss

In dieser Schritt-für-Schritt-Anleitung haben wir untersucht, wie Sie mithilfe der Aspose.Slides für Java-API verschiedene Elemente aus einem Diagramm in Java Slides ausblenden können. Dies kann unglaublich nützlich sein, wenn Sie Ihre Diagramme für Präsentationen anpassen und sie optisch ansprechender gestalten oder an Ihre spezifischen Anforderungen anpassen müssen.

## Häufig gestellte Fragen

### Wie kann ich das Erscheinungsbild von Diagrammelementen weiter anpassen?

Sie können verschiedene Eigenschaften von Diagrammelementen wie Linienfarbe, Füllfarbe, Markierungsstil und mehr anpassen, indem Sie auf die entsprechenden Eigenschaften der Diagrammreihen, Markierungen, Beschriftungen und des Formats zugreifen.

### Kann ich bestimmte Datenpunkte im Diagramm ausblenden?

Ja, Sie können bestimmte Datenpunkte ausblenden, indem Sie die Daten in der Diagrammreihe bearbeiten. Sie können Datenpunkte entfernen oder ihre Werte auf Null setzen, um sie auszublenden.

### Wie kann ich dem Diagramm weitere Reihen hinzufügen?

 Sie können dem Diagramm weitere Reihen hinzufügen, indem Sie das`IChartData.getSeries().add` Methode und Angabe der Datenpunkte für die neue Reihe.

### Ist es möglich, den Diagrammtyp dynamisch zu ändern?

Ja, Sie können den Diagrammtyp dynamisch ändern, indem Sie ein neues Diagramm des gewünschten Typs erstellen und Daten aus dem alten Diagramm in das neue kopieren.

### Wie kann ich den Titel und die Achsenbeschriftungen des Diagramms programmgesteuert ändern?

Sie können den Titel und die Beschriftungen des Diagramms und der Achsen festlegen, indem Sie auf die jeweiligen Eigenschaften zugreifen und den gewünschten Text und die gewünschte Formatierung festlegen.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
