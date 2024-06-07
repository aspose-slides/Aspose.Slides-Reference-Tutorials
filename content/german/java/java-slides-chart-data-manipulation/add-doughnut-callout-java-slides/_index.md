---
title: Donut-Callout in Java-Folien hinzufügen
linktitle: Donut-Callout in Java-Folien hinzufügen
second_title: Aspose.Slides Java PowerPoint-Verarbeitungs-API
description: Erfahren Sie, wie Sie mit Aspose.Slides für Java Donut-Callouts in Java-Folien einfügen. Schritt-für-Schritt-Anleitung mit Quellcode für erweiterte Präsentationen.
type: docs
weight: 12
url: /de/java/chart-data-manipulation/add-doughnut-callout-java-slides/
---

## Einführung zum Hinzufügen eines Donut-Callouts in Java-Folien mit Aspose.Slides für Java

In diesem Tutorial führen wir Sie durch den Prozess des Hinzufügens eines Donut-Callouts zu einer Folie in Java mithilfe von Aspose.Slides für Java. Ein Donut-Callout ist ein Diagrammelement, mit dem bestimmte Datenpunkte in einem Donut-Diagramm hervorgehoben werden können. Wir stellen Ihnen zu Ihrer Bequemlichkeit schrittweise Anweisungen und den vollständigen Quellcode zur Verfügung.

## Voraussetzungen

Stellen Sie zunächst sicher, dass die folgenden Voraussetzungen erfüllt sind:

1. Java-Entwicklungsumgebung
2. Aspose.Slides für Java-Bibliothek
3. Integrierte Entwicklungsumgebung (IDE) wie Eclipse oder IntelliJ IDEA
4. Eine PowerPoint-Präsentation, in der Sie den Donut-Callout einfügen möchten

## Schritt 1: Richten Sie Ihr Java-Projekt ein

1. Erstellen Sie ein neues Java-Projekt in der von Ihnen gewählten IDE.
2. Fügen Sie Ihrem Projekt die Bibliothek Aspose.Slides für Java als Abhängigkeit hinzu.

## Schritt 2: Initialisieren der Präsentation

Um zu beginnen, müssen Sie eine PowerPoint-Präsentation initialisieren und eine Folie erstellen, auf der Sie den Donut-Callout hinzufügen möchten. Hier ist der Code, um dies zu erreichen:

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "testc.pptx");
ISlide slide = pres.getSlides().get_Item(0);
```

 Ersetzen Sie unbedingt`"Your Document Directory"` durch den tatsächlichen Pfad zu Ihrer PowerPoint-Präsentationsdatei.

## Schritt 3: Erstellen Sie ein Ringdiagramm

Als Nächstes erstellen Sie ein Ringdiagramm auf der Folie. Sie können die Position und Größe des Diagramms nach Ihren Anforderungen anpassen. Hier ist der Code zum Hinzufügen eines Ringdiagramms:

```java
IChart chart = slide.getShapes().addChart(ChartType.Doughnut, 10, 10, 500, 500, false);
```

## Schritt 4: Passen Sie das Donut-Diagramm an

Jetzt ist es an der Zeit, das Donut-Diagramm anzupassen. Wir legen verschiedene Eigenschaften fest, z. B. das Entfernen der Legende, das Konfigurieren der Lochgröße und das Anpassen des ersten Schnittwinkels. Hier ist der Code:

```java
IChartDataWorkbook workBook = chart.getChartData().getChartDataWorkbook();
chart.getChartData().getSeries().clear();
chart.getChartData().getCategories().clear();
chart.setLegend(false);
int seriesIndex = 0;
while (seriesIndex < 15) {
    IChartSeries series = chart.getChartData().getSeries().add(workBook.getCell(0, 0, seriesIndex + 1, "SERIES " + seriesIndex), chart.getType());
    series.setExplosion(0);
    series.getParentSeriesGroup().setDoughnutHoleSize((byte) 20);
    series.getParentSeriesGroup().setFirstSliceAngle(351);
    seriesIndex++;
}
```

Dieser Codeausschnitt legt die Eigenschaften für das Ringdiagramm fest. Sie können die Werte an Ihre spezifischen Anforderungen anpassen.

## Schritt 5: Daten zum Ringdiagramm hinzufügen

Fügen wir nun Daten zum Ringdiagramm hinzu. Wir werden auch das Erscheinungsbild der Datenpunkte anpassen. Hier ist der Code, um dies zu erreichen:

```java
int categoryIndex = 0;
while (categoryIndex < 15) {
    chart.getChartData().getCategories().add(workBook.getCell(0, categoryIndex + 1, 0, "CATEGORY " + categoryIndex));
    int i = 0;
    while (i < chart.getChartData().getSeries().size()) {
        IChartSeries iCS = chart.getChartData().getSeries().get_Item(i);
        IChartDataPoint dataPoint = iCS.getDataPoints().addDataPointForDoughnutSeries(workBook.getCell(0, categoryIndex + 1, i + 1, 1));
        dataPoint.getFormat().getFill().setFillType(FillType.Solid);
        // Passen Sie hier das Erscheinungsbild des Datenpunkts an
        i++;
    }
    categoryIndex++;
}
```

In diesem Code fügen wir dem Ringdiagramm Kategorien und Datenpunkte hinzu. Sie können das Erscheinungsbild der Datenpunkte nach Bedarf weiter anpassen.

## Schritt 6: Speichern Sie die Präsentation

Vergessen Sie nicht, Ihre Präsentation zu speichern, nachdem Sie den Donut-Callout hinzugefügt haben. Hier ist der Code zum Speichern der Präsentation:

```java
pres.save(dataDir + "chart.pptx", SaveFormat.Pptx);
```

 Ersetzen Sie unbedingt`"chart.pptx"` durch den gewünschten Dateinamen.

Herzlichen Glückwunsch! Sie haben mithilfe von Aspose.Slides für Java erfolgreich einen Donut-Callout zu einer Java-Folie hinzugefügt. Sie können jetzt Ihre Java-Anwendung ausführen, um die PowerPoint-Präsentation mit dem Donut-Diagramm und dem Callout zu generieren.

## Vollständiger Quellcode zum Hinzufügen eines Donut-Callouts in Java-Folien

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "testc.pptx");
ISlide slide = pres.getSlides().get_Item(0);
IChart chart = slide.getShapes().addChart(ChartType.Doughnut, 10, 10, 500, 500, false);
IChartDataWorkbook workBook = chart.getChartData().getChartDataWorkbook();
chart.getChartData().getSeries().clear();
chart.getChartData().getCategories().clear();
chart.setLegend(false);
int seriesIndex = 0;
while (seriesIndex < 15)
{
	IChartSeries series = chart.getChartData().getSeries().add(workBook.getCell(0, 0, seriesIndex + 1, "SERIES " + seriesIndex), chart.getType());
	series.setExplosion(0);
	series.getParentSeriesGroup().setDoughnutHoleSize((byte) 20);
	series.getParentSeriesGroup().setFirstSliceAngle(351);
	seriesIndex++;
}
int categoryIndex = 0;
while (categoryIndex < 15)
{
	chart.getChartData().getCategories().add(workBook.getCell(0, categoryIndex + 1, 0, "CATEGORY " + categoryIndex));
	int i = 0;
	while (i < chart.getChartData().getSeries().size())
	{
		IChartSeries iCS = chart.getChartData().getSeries().get_Item(i);
		IChartDataPoint dataPoint = iCS.getDataPoints().addDataPointForDoughnutSeries(workBook.getCell(0, categoryIndex + 1, i + 1, 1));
		dataPoint.getFormat().getFill().setFillType(FillType.Solid);
		dataPoint.getFormat().getLine().getFillFormat().setFillType(FillType.Solid);
		dataPoint.getFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.WHITE);
		dataPoint.getFormat().getLine().setWidth(1);
		dataPoint.getFormat().getLine().setStyle(LineStyle.Single);
		dataPoint.getFormat().getLine().setDashStyle(LineDashStyle.Solid);
		if (i == chart.getChartData().getSeries().size() - 1)
		{
			IDataLabel lbl = dataPoint.getLabel();
			lbl.getTextFormat().getTextBlockFormat().setAutofitType(TextAutofitType.Shape);
			lbl.getDataLabelFormat().getTextFormat().getPortionFormat().setFontBold(NullableBool.True);
			lbl.getDataLabelFormat().getTextFormat().getPortionFormat().setLatinFont(new FontData("DINPro-Bold"));
			lbl.getDataLabelFormat().getTextFormat().getPortionFormat().setFontHeight(12);
			lbl.getDataLabelFormat().getTextFormat().getPortionFormat().getFillFormat().setFillType(FillType.Solid);
			lbl.getDataLabelFormat().getTextFormat().getPortionFormat().getFillFormat().getSolidFillColor().setColor(Color.LIGHT_GRAY);
			lbl.getDataLabelFormat().getFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.WHITE);
			lbl.getDataLabelFormat().setShowValue(false);
			lbl.getDataLabelFormat().setShowCategoryName(true);
			lbl.getDataLabelFormat().setShowSeriesName(false);
			//lbl.getDataLabelFormat().setShowLabelAsDataCallout(true);
			lbl.getDataLabelFormat().setShowLeaderLines(true);
			lbl.getDataLabelFormat().setShowLabelAsDataCallout(false);
			chart.validateChartLayout();
			lbl.setX(lbl.getX() + (float) 0.5);
			lbl.setY(lbl.getY() + (float) 0.5);
		}
		i++;
	}
	categoryIndex++;
}
pres.save(dataDir + "chart.pptx", SaveFormat.Pptx);
```

## Abschluss

In diesem Tutorial haben wir den Vorgang des Hinzufügens eines Donut-Callouts zu einer Java-Folie mithilfe von Aspose.Slides für Java behandelt. Sie haben gelernt, wie Sie ein Donut-Diagramm erstellen, sein Erscheinungsbild anpassen und Datenpunkte hinzufügen. Sie können Ihre Präsentationen mit dieser leistungsstarken Bibliothek weiter verbessern und weitere Diagrammoptionen erkunden.

## Häufig gestellte Fragen

### Wie kann ich das Erscheinungsbild des Donut-Callouts ändern?

Sie können das Erscheinungsbild des Donut-Callouts anpassen, indem Sie die Eigenschaften der Datenpunkte im Diagramm ändern. Im bereitgestellten Code können Sie sehen, wie Sie die Füllfarbe, Linienfarbe, den Schriftstil und andere Attribute von Datenpunkten festlegen.

### Kann ich dem Ringdiagramm weitere Datenpunkte hinzufügen?

Ja, Sie können dem Ringdiagramm beliebig viele Datenpunkte hinzufügen. Erweitern Sie einfach die Schleifen im Code, in denen Kategorien und Datenpunkte hinzugefügt werden, und geben Sie die entsprechenden Daten und Formatierungen an.

### Wie kann ich die Position und Größe des Ringdiagramms auf der Folie anpassen?

Sie können die Position und Größe des Ringdiagramms ändern, indem Sie die Parameter im`addChart` Methode. Die vier Zahlen in dieser Methode entsprechen den X- und Y-Koordinaten der oberen linken Ecke des Diagramms bzw. seiner Breite und Höhe.