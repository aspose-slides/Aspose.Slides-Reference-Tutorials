---
"description": "Erfahren Sie, wie Sie mit Aspose.Slides für Java die aktuelle Position von Diagrammdatenbeschriftungen in Java Slides ermitteln. Schritt-für-Schritt-Anleitung mit Quellcode."
"linktitle": "Aktuelle Position der Diagrammdatenbeschriftung in Java-Folien abrufen"
"second_title": "Aspose.Slides Java PowerPoint-Verarbeitungs-API"
"title": "Aktuelle Position der Diagrammdatenbeschriftung in Java-Folien abrufen"
"url": "/de/java/data-manipulation/actual-position-chart-data-label-java-slides/"
"weight": 18
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Aktuelle Position der Diagrammdatenbeschriftung in Java-Folien abrufen


## Einführung zum Abrufen der tatsächlichen Position der Diagrammdatenbeschriftung in Java-Folien

In diesem Tutorial erfahren Sie, wie Sie die aktuelle Position von Diagrammbeschriftungen mit Aspose.Slides für Java abrufen. Wir erstellen ein Java-Programm, das eine PowerPoint-Präsentation mit einem Diagramm generiert, die Beschriftungen anpasst und anschließend Formen hinzufügt, die die Positionen dieser Beschriftungen darstellen.

## Voraussetzungen

Stellen Sie vor dem Beginn sicher, dass Sie die Bibliothek Aspose.Slides für Java in Ihrem Java-Projekt eingerichtet haben.

## Schritt 1: Erstellen Sie eine PowerPoint-Präsentation

Erstellen wir zunächst eine neue PowerPoint-Präsentation und fügen ein Diagramm hinzu. Die Datenbeschriftungen des Diagramms werden wir später im Tutorial anpassen.

```java
// Der Pfad zum Dokumentenverzeichnis.
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
In diesem Schritt durchlaufen wir die Datenpunkte der Diagrammreihe und ermitteln die tatsächliche Position der Datenbeschriftungen mit einem Wert größer als 4. Anschließend fügen wir Ellipsen hinzu, um diese Positionen darzustellen.

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
// Der Pfad zum Dokumentenverzeichnis.
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
				shape.getFillFormat().getSolidFillColor().setColor(com.aspose.cells.Color.fromArgb(100, 0, 255, 0).d());//ZU TUN
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

In diesem Tutorial haben Sie gelernt, wie Sie die aktuelle Position von Diagrammdatenbeschriftungen in Java-Folien mit Aspose.Slides für Java abrufen. Dieses Wissen können Sie nun nutzen, um Ihre PowerPoint-Präsentationen mit benutzerdefinierten Datenbeschriftungen und visuellen Darstellungen ihrer Positionen zu verbessern.

## Häufig gestellte Fragen

### Wie kann ich Datenbeschriftungen in einem Diagramm anpassen?

Um Datenbeschriftungen in einem Diagramm anzupassen, können Sie die `setDefaultDataLabelFormat` Methode für die Diagrammreihe und legen Sie Eigenschaften wie Position und Sichtbarkeit fest. Beispiel:
```java
for (IChartSeries series : chart.getChartData().getSeries()) {
    series.getLabels().getDefaultDataLabelFormat().setPosition(LegendDataLabelPosition.OutsideEnd);
    series.getLabels().getDefaultDataLabelFormat().setShowValue(true);
}
```

### Wie kann ich Formen hinzufügen, um Datenbeschriftungspositionen darzustellen?

Sie können die Datenpunkte einer Diagrammreihe durchlaufen und die `getActualX`, `getActualY`, `getActualWidth`, Und `getActualHeight` Methoden der Datenbeschriftung, um ihre Position zu erhalten. Anschließend können Sie Formen hinzufügen, indem Sie `addAutoShape` Methode. Hier ist ein Beispiel:
```java
float x = point.getLabel().getActualX();
float y = point.getLabel().getActualY();
float w = point.getLabel().getActualWidth();
float h = point.getLabel().getActualHeight();
IAutoShape shape = chart.getUserShapes().getShapes().addAutoShape(ShapeType.Ellipse, x, y, w, h);
```

### Wie kann ich die erstellte Präsentation speichern?

Sie können die erstellte Präsentation speichern, indem Sie `save` Methode. Geben Sie den gewünschten Dateipfad und die `SaveFormat` als Parameter. Beispiel:
```java
pres.save(dataDir + "GetActualPositionOFChartDatalabel.pptx", SaveFormat.Pptx);
```

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}