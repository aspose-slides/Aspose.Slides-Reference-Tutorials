---
title: Festlegen einer Legende für die Datenbeschriftung in Java-Folien
linktitle: Festlegen einer Legende für die Datenbeschriftung in Java-Folien
second_title: Aspose.Slides Java PowerPoint-Verarbeitungs-API
description: Erfahren Sie, wie Sie Callouts für Datenbeschriftungen in Aspose.Slides für Java einrichten. Schritt-für-Schritt-Anleitung mit Quellcode.
weight: 25
url: /de/java/data-manipulation/setting-callout-data-label-java-slides/
---

{< blocks/products/pf/main-wrap-class >}
{< blocks/products/pf/main-container >}
{< blocks/products/pf/tutorial-page-section >}


## Einführung in das Festlegen von Callouts für Datenbeschriftungen in Aspose.Slides für Java

In diesem Tutorial zeigen wir, wie Sie mit Aspose.Slides für Java Callouts für Datenbeschriftungen in einem Diagramm einrichten. Callouts können nützlich sein, um bestimmte Datenpunkte in Ihrem Diagramm hervorzuheben. Wir gehen den Code Schritt für Schritt durch und stellen den erforderlichen Quellcode bereit.

## Voraussetzungen

- Sie sollten Aspose.Slides für Java installiert haben.
- Erstellen Sie ein Java-Projekt und fügen Sie Ihrem Projekt die Aspose.Slides-Bibliothek hinzu.

## Schritt 1: Erstellen Sie eine Präsentation und fügen Sie ein Diagramm hinzu

 Zuerst müssen wir eine Präsentation erstellen und ein Diagramm zu einer Folie hinzufügen. Stellen Sie sicher, dass Sie`"Your Document Directory"` durch den tatsächlichen Pfad zu Ihrem Dokumentverzeichnis.

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "testc.pptx");
ISlide slide = pres.getSlides().get_Item(0);
IChart chart = slide.getShapes().addChart(ChartType.Doughnut, 10, 10, 500, 500, false);
```

## Schritt 2: Konfigurieren Sie das Diagramm

Als Nächstes konfigurieren wir das Diagramm, indem wir Eigenschaften wie Legende, Reihen und Kategorien festlegen.

```java
IChartDataWorkbook workBook = chart.getChartData().getChartDataWorkbook();
chart.getChartData().getSeries().clear();
chart.getChartData().getCategories().clear();
chart.setLegend(false);

// Serien und Kategorien konfigurieren (Anzahl der Serien und Kategorien ist anpassbar)
int seriesIndex = 0;
while (seriesIndex < 15) {
    IChartSeries series = chart.getChartData().getSeries().add(workBook.getCell(0, 0, seriesIndex + 1, "SERIES " + seriesIndex), chart.getType());
    series.setExplosion(0);
    series.getParentSeriesGroup().setDoughnutHoleSize((byte) 20);
    series.getParentSeriesGroup().setFirstSliceAngle(351);
    seriesIndex++;
}

int categoryIndex = 0;
while (categoryIndex < 15) {
    chart.getChartData().getCategories().add(workBook.getCell(0, categoryIndex + 1, 0, "CATEGORY " + categoryIndex));
    int i = 0;
    while (i < chart.getChartData().getSeries().size()) {
        // Fügen Sie hier Datenpunkte hinzu
        // ...
        i++;
    }
    categoryIndex++;
}
```

## Schritt 3: Datenbeschriftungen anpassen

Jetzt passen wir die Datenbeschriftungen an und richten dabei auch Beschriftungen für die letzte Reihe ein.

```java
int i = 0;
while (i < chart.getChartData().getSeries().size()) {
    IChartSeries iCS = chart.getChartData().getSeries().get_Item(i);
    IChartDataPoint dataPoint = iCS.getDataPoints().addDataPointForDoughnutSeries(workBook.getCell(0, categoryIndex + 1, i + 1, 1));
    dataPoint.getFormat().getFill().setFillType(FillType.Solid);
    // Passen Sie die Datenpunktformatierung an (Füllung, Linie usw.)

    if (i == chart.getChartData().getSeries().size() - 1) {
        IDataLabel lbl = dataPoint.getLabel();
        lbl.getTextFormat().getTextBlockFormat().setAutofitType(TextAutofitType.Shape);
        //Passen Sie die Etikettenformatierung an (Schriftart, Füllung usw.)
        lbl.getDataLabelFormat().setShowValue(false);
        lbl.getDataLabelFormat().setShowCategoryName(true);
        lbl.getDataLabelFormat().setShowSeriesName(false);
        // Aktivieren von Callouts
        lbl.getDataLabelFormat().setShowLabelAsDataCallout(true);
        lbl.getDataLabelFormat().setShowLeaderLines(true);
    }
    i++;
}
```

## Schritt 4: Speichern Sie die Präsentation

Abschließend speichern Sie die Präsentation mit dem konfigurierten Diagramm.

```java
pres.save("chart.pptx", SaveFormat.Pptx);
```

Jetzt haben Sie mit Aspose.Slides für Java erfolgreich Callouts für Datenbeschriftungen in einem Diagramm eingerichtet. Passen Sie den Code entsprechend Ihren spezifischen Diagramm- und Datenanforderungen an.

## Vollständiger Quellcode zum Festlegen von Callouts für Datenbeschriftungen in Java-Folien

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
pres.save("chart.pptx", SaveFormat.Pptx);
```

## Abschluss

In diesem Tutorial haben wir untersucht, wie Sie mit Aspose.Slides für Java Beschriftungen für Datenbeschriftungen in einem Diagramm einrichten. Beschriftungen sind wertvolle Tools zum Hervorheben bestimmter Datenpunkte in Ihren Diagrammen und Präsentationen. Wir haben eine Schritt-für-Schritt-Anleitung zusammen mit Quellcode bereitgestellt, um Ihnen bei dieser Anpassung zu helfen.

## Häufig gestellte Fragen

### Wie passe ich das Erscheinungsbild von Datenbeschriftungen an?

Um das Erscheinungsbild von Datenbeschriftungen anzupassen, können Sie Eigenschaften wie Schriftart, Füllung und Linienstile ändern. Beispiel:

```java
IDataLabel lbl = dataPoint.getLabel();
lbl.getTextFormat().getTextBlockFormat().setAutofitType(TextAutofitType.Shape);
lbl.getDataLabelFormat().getTextFormat().getPortionFormat().setFontBold(NullableBool.True);
lbl.getDataLabelFormat().getTextFormat().getPortionFormat().setLatinFont(new FontData("DINPro-Bold"));
lbl.getDataLabelFormat().getTextFormat().getPortionFormat().setFontHeight(12);
lbl.getDataLabelFormat().getTextFormat().getPortionFormat().getFillFormat().setFillType(FillType.Solid);
lbl.getDataLabelFormat().getTextFormat().getPortionFormat().getFillFormat().getSolidFillColor().setColor(Color.LIGHT_GRAY);
lbl.getDataLabelFormat().getFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.WHITE);
```

### Wie kann ich Callouts für Datenbeschriftungen aktivieren oder deaktivieren?

 Um Beschriftungen für Datenbeschriftungen zu aktivieren oder zu deaktivieren, verwenden Sie die`setShowLabelAsDataCallout` Methode. Stellen Sie es ein auf`true` zur Aktivierung von Callouts und`false`um sie zu deaktivieren.

```java
lbl.getDataLabelFormat().setShowLabelAsDataCallout(true); // Aktivieren von Callouts
lbl.getDataLabelFormat().setShowLabelAsDataCallout(false); // Callouts deaktivieren
```

### Kann ich die Führungslinien für Datenbeschriftungen anpassen?

Ja, Sie können die Führungslinien für Datenbeschriftungen mithilfe von Eigenschaften wie Linienstil, Farbe und Breite anpassen. Beispiel:

```java
lbl.getDataLabelFormat().setShowLeaderLines(true); // Führungslinien aktivieren
lbl.getDataLabelFormat().getLeaderLinesFormat().getFormat().getLine().setStyle(LineStyle.Single);
lbl.getDataLabelFormat().getLeaderLinesFormat().getFormat().getLine().setWidth(1);
lbl.getDataLabelFormat().getLeaderLinesFormat().getFormat().getLine().getFillFormat().setFillType(FillType.Solid);
lbl.getDataLabelFormat().getLeaderLinesFormat().getFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.BLACK);
```

Dies sind einige allgemeine Anpassungsoptionen für Datenbeschriftungen und Beschriftungen in Aspose.Slides für Java. Sie können das Erscheinungsbild weiter an Ihre spezifischen Anforderungen anpassen.
{< /blocks/products/pf/tutorial-page-section >}

{< /blocks/products/pf/main-container >}
{< /blocks/products/pf/main-wrap-class >}

{< blocks/products/products-backtop-button >}
