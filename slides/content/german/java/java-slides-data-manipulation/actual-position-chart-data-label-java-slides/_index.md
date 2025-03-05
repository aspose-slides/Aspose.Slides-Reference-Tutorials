---
title: Aktuelle Position der Diagrammdatenbeschriftung in Java-Folien abrufen
linktitle: Aktuelle Position der Diagrammdatenbeschriftung in Java-Folien abrufen
second_title: Aspose.Slides Java PowerPoint-Verarbeitungs-API
description: Erfahren Sie, wie Sie mit Aspose.Slides für Java die tatsächliche Position von Diagrammdatenbeschriftungen in Java Slides ermitteln. Schritt-für-Schritt-Anleitung mit Quellcode.
type: docs
weight: 18
url: /de/java/data-manipulation/actual-position-chart-data-label-java-slides/
---

## Einführung zum Abrufen der tatsächlichen Position der Diagrammdatenbeschriftung in Java-Folien

In diesem Tutorial erfahren Sie, wie Sie die tatsächliche Position von Diagrammdatenbeschriftungen mit Aspose.Slides für Java abrufen. Wir erstellen ein Java-Programm, das eine PowerPoint-Präsentation mit einem Diagramm generiert, die Datenbeschriftungen anpasst und dann Formen hinzufügt, die die Positionen dieser Datenbeschriftungen darstellen.

## Voraussetzungen

Stellen Sie vor dem Beginn sicher, dass Sie die Bibliothek Aspose.Slides für Java in Ihrem Java-Projekt eingerichtet haben.

## Schritt 1: Erstellen Sie eine PowerPoint-Präsentation

Lassen Sie uns zunächst eine neue PowerPoint-Präsentation erstellen und ihr ein Diagramm hinzufügen. Wir werden die Datenbeschriftungen des Diagramms später im Tutorial anpassen.

```java
// Der Pfad zum Dokumentverzeichnis.
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
try {
    IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 50, 50, 500, 400);
    chart.validateChartLayout();
} finally {
    if (pres != null) pres.dispose();
}
```

## Schritt 2: Datenbeschriftungen anpassen
Passen wir nun die Datenbeschriftungen für die Diagrammreihe an. Wir legen ihre Position fest und zeigen die Werte an.

```java
try {
    // ... (vorheriger Code)
    for (IChartSeries series : chart.getChartData().getSeries()) {
        series.getLabels().getDefaultDataLabelFormat().setPosition(LegendDataLabelPosition.OutsideEnd);
        series.getLabels().getDefaultDataLabelFormat().setShowValue(true);
    }
    // ... (restlicher Code)
} finally {
    if (pres != null) pres.dispose();
}
```

## Schritt 3: Tatsächliche Position der Datenbeschriftungen ermitteln
In diesem Schritt durchlaufen wir die Datenpunkte der Diagrammreihe und rufen die tatsächliche Position der Datenbeschriftungen ab, die einen Wert größer als 4 haben. Anschließend fügen wir Ellipsen hinzu, um diese Positionen darzustellen.

```java
try {
    // ... (vorheriger Code)
    for (IChartSeries series : chart.getChartData().getSeries()) {
        for (IChartDataPoint point : series.getDataPoints()) {
            if (point.getValue().toDouble() > 4) {
                float x = point.getLabel().getActualX();
                float y = point.getLabel().getActualY();
                float w = point.getLabel().getActualWidth();
                float h = point.getLabel().getActualHeight();
                IAutoShape shape = chart.getUserShapes().getShapes().addAutoShape(ShapeType.Ellipse, x, y, w, h);
                shape.getFillFormat().setFillType(FillType.Solid);
                shape.getFillFormat().getSolidFillColor().setColor(com.aspose.cells.Color.fromArgb(100, 0, 255, 0).d());
            }
        }
    }
    // ... (restlicher Code)
} finally {
    if (pres != null) pres.dispose();
}
```

## Schritt 4: Speichern Sie die Präsentation
Speichern Sie abschließend die erstellte Präsentation in einer Datei.

```java
try {
    // ... (vorheriger Code)
    pres.save(dataDir + "GetActualPositionOFChartDatalabel.pptx", SaveFormat.Pptx);
} finally {
    if (pres != null) pres.dispose();
}
```

## Vollständiger Quellcode zum Abrufen der tatsächlichen Position der Diagrammdatenbeschriftung in Java-Folien

```java
// Der Pfad zum Dokumentverzeichnis.
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
try
{
	IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 50, 50, 500, 400);
	for (IChartSeries series : chart.getChartData().getSeries())
	{
		series.getLabels().getDefaultDataLabelFormat().setPosition(LegendDataLabelPosition.OutsideEnd);
		series.getLabels().getDefaultDataLabelFormat().setShowValue(true);
	}
	chart.validateChartLayout();
	for (IChartSeries series : chart.getChartData().getSeries())
	{
		for (IChartDataPoint point : series.getDataPoints())
		{
			if (point.getValue().toDouble() > 4)
			{
				float x = point.getLabel().getActualX();
				float y = point.getLabel().getActualY();
				float w = point.getLabel().getActualWidth();
				float h = point.getLabel().getActualHeight();
				IAutoShape shape = chart.getUserShapes().getShapes().addAutoShape(ShapeType.Ellipse, x, y, w, h);
				shape.getFillFormat().setFillType(FillType.Solid);
				shape.getFillFormat().getSolidFillColor().setColor(com.aspose.cells.Color.fromArgb(100, 0, 255, 0).d());//MACHEN
			}
		}
	}
	pres.save(dataDir + "GetActualPositionOFChartDatalabel", SaveFormat.Pptx);
}
finally
{
	if (pres != null) pres.dispose();
}
```

## Abschluss

In diesem Tutorial haben Sie gelernt, wie Sie mit Aspose.Slides für Java die tatsächliche Position von Diagrammdatenbeschriftungen in Java-Folien abrufen. Dieses Wissen können Sie nun nutzen, um Ihre PowerPoint-Präsentationen mit benutzerdefinierten Datenbeschriftungen und visuellen Darstellungen ihrer Positionen zu verbessern.

## Häufig gestellte Fragen

### Wie kann ich Datenbeschriftungen in einem Diagramm anpassen?

 Um Datenbeschriftungen in einem Diagramm anzupassen, können Sie das`setDefaultDataLabelFormat` Methode für die Diagrammreihe und legen Sie Eigenschaften wie Position und Sichtbarkeit fest. Beispiel:
```java
for (IChartSeries series : chart.getChartData().getSeries()) {
    series.getLabels().getDefaultDataLabelFormat().setPosition(LegendDataLabelPosition.OutsideEnd);
    series.getLabels().getDefaultDataLabelFormat().setShowValue(true);
}
```

### Wie kann ich Formen hinzufügen, um Datenbeschriftungspositionen darzustellen?

 Sie können die Datenpunkte einer Diagrammreihe durchlaufen und die`getActualX`, `getActualY`, `getActualWidth` , Und`getActualHeight`Methoden der Datenbeschriftung, um ihre Position zu erhalten. Anschließend können Sie Formen hinzufügen, indem Sie`addAutoShape` Methode. Hier ist ein Beispiel:
```java
float x = point.getLabel().getActualX();
float y = point.getLabel().getActualY();
float w = point.getLabel().getActualWidth();
float h = point.getLabel().getActualHeight();
IAutoShape shape = chart.getUserShapes().getShapes().addAutoShape(ShapeType.Ellipse, x, y, w, h);
```

### Wie kann ich die erstellte Präsentation speichern?

 Sie können die erstellte Präsentation speichern mit dem`save` Methode. Geben Sie den gewünschten Dateipfad und die`SaveFormat` als Parameter. Beispiel:
```java
pres.save(dataDir + "GetActualPositionOFChartDatalabel.pptx", SaveFormat.Pptx);
```