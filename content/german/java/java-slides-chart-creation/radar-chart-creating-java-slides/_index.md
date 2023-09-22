---
title: Erstellen von Radardiagrammen in Java-Folien
linktitle: Erstellen von Radardiagrammen in Java-Folien
second_title: Aspose.Slides Java PowerPoint-Verarbeitungs-API
description: Erfahren Sie, wie Sie mithilfe der Aspose.Slides für Java-API Radardiagramme in Java-PowerPoint-Präsentationen erstellen.
type: docs
weight: 10
url: /de/java/chart-creation/radar-chart-creating-java-slides/
---

## Einführung in die Erstellung eines Radardiagramms in Java-Folien

In diesem Tutorial führen wir Sie durch den Prozess der Erstellung eines Radardiagramms mithilfe der Aspose.Slides für Java-API. Netzdiagramme eignen sich zur Visualisierung von Daten in einem kreisförmigen Muster und erleichtern so den Vergleich mehrerer Datenreihen. Wir stellen Schritt-für-Schritt-Anleitungen zusammen mit dem Java-Quellcode zur Verfügung.

## Voraussetzungen

Bevor wir beginnen, stellen Sie sicher, dass die Aspose.Slides for Java-Bibliothek in Ihr Projekt integriert ist. Sie können die Bibliothek herunterladen unter[Hier](https://releases.aspose.com/slides/java/).

## Schritt 1: Einrichten der Präsentation

Beginnen wir damit, eine neue PowerPoint-Präsentation einzurichten und ihr eine Folie hinzuzufügen.

```java
String outPath = RunExamples.getOutPath() + File.separator + "RadarChart_Out.pptx";
Presentation pres = new Presentation();
```

## Schritt 2: Hinzufügen einer Radarkarte

Als Nächstes fügen wir der Folie ein Radardiagramm hinzu. Wir legen die Position und Abmessungen des Diagramms fest.

```java
ISlide sld = pres.getSlides().get_Item(0);
IChart ichart = sld.getShapes().addChart(ChartType.Radar, 0, 0, 400, 400);
```

## Schritt 3: Diagrammdaten festlegen

Wir werden nun die Diagrammdaten festlegen. Dazu gehört das Erstellen einer Datenarbeitsmappe, das Hinzufügen von Kategorien und das Hinzufügen von Serien.

```java
int defaultWorksheetIndex = 0;
IChartDataWorkbook fact = ichart.getChartData().getChartDataWorkbook();

// Diagrammtitel festlegen
ichart.getChartTitle().addTextFrameForOverriding("Radar Chart");

// Standardmäßig generierte Serien und Kategorien löschen
ichart.getChartData().getCategories().clear();
ichart.getChartData().getSeries().clear();

// Neue Kategorien hinzufügen
ichart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 1, 0, "Category 1"));
ichart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 2, 0, "Category 3"));
ichart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 3, 0, "Category 5"));
ichart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 4, 0, "Category 7"));
ichart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 5, 0, "Category 9"));
ichart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 6, 0, "Category 11"));

// Neue Serie hinzufügen
ichart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 1, "Series 1"), ichart.getType());
ichart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 2, "Series 2"), ichart.getType());
```

## Schritt 4: Auffüllen der Seriendaten

Jetzt füllen wir die Reihendaten für unser Radardiagramm aus.

```java
// Füllen Sie Seriendaten für Serie 1 aus
IChartSeries series = ichart.getChartData().getSeries().get_Item(0);
series.getDataPoints().addDataPointForRadarSeries(fact.getCell(defaultWorksheetIndex, 1, 1, 2.7));
series.getDataPoints().addDataPointForRadarSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 2.4));
series.getDataPoints().addDataPointForRadarSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 1.5));
series.getDataPoints().addDataPointForRadarSeries(fact.getCell(defaultWorksheetIndex, 4, 1, 3.5));
series.getDataPoints().addDataPointForRadarSeries(fact.getCell(defaultWorksheetIndex, 5, 1, 5));
series.getDataPoints().addDataPointForRadarSeries(fact.getCell(defaultWorksheetIndex, 6, 1, 3.5));

// Serienfarbe festlegen
series.getFormat().getLine().getFillFormat().setFillType(FillType.Solid);
series.getFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.RED);

// Füllen Sie Seriendaten für Serie 2 aus
series = ichart.getChartData().getSeries().get_Item(1);
series.getDataPoints().addDataPointForRadarSeries(fact.getCell(defaultWorksheetIndex, 1, 2, 2.5));
series.getDataPoints().addDataPointForRadarSeries(fact.getCell(defaultWorksheetIndex, 2, 2, 2.4));
series.getDataPoints().addDataPointForRadarSeries(fact.getCell(defaultWorksheetIndex, 3, 2, 1.6));
series.getDataPoints().addDataPointForRadarSeries(fact.getCell(defaultWorksheetIndex, 4, 2, 3.5));
series.getDataPoints().addDataPointForRadarSeries(fact.getCell(defaultWorksheetIndex, 5, 2, 4));
series.getDataPoints().addDataPointForRadarSeries(fact.getCell(defaultWorksheetIndex, 6, 2, 3.6));

// Serienfarbe festlegen
series.getFormat().getLine().getFillFormat().setFillType(FillType.Solid);
series.getFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.ORANGE);
```

## Schritt 5: Anpassen von Achsen und Legenden

Passen wir die Achsen und Legenden für unser Radardiagramm an.

```java
//Legendenposition festlegen
ichart.getLegend().setPosition(LegendPositionType.Bottom);

// Festlegen der Texteigenschaften der Kategorieachse
IChartPortionFormat txtCat = ichart.getAxes().getHorizontalAxis().getTextFormat().getPortionFormat();
txtCat.setFontBold(NullableBool.True);
txtCat.setFontHeight(10);
txtCat.getFillFormat().setFillType(FillType.Solid);
txtCat.getFillFormat().getSolidFillColor().setColor(new Color(PresetColor.DimGray));
txtCat.setLatinFont(new FontData("Calibri"));

// Festlegen der Texteigenschaften für Legenden
IChartPortionFormat txtleg = ichart.getLegend().getTextFormat().getPortionFormat();
txtleg.setFontBold(NullableBool.True);
txtleg.setFontHeight(10);
txtleg.getFillFormat().setFillType(FillType.Solid);
txtleg.getFillFormat().getSolidFillColor().setColor(new Color(PresetColor.DimGray));
txtleg.setLatinFont(new FontData("Calibri"));

// Festlegen der Texteigenschaften der Wertachse
IChartPortionFormat txtVal = ichart.getAxes().getVerticalAxis().getTextFormat().getPortionFormat();
txtVal.setFontBold(NullableBool.True);
txtVal.setFontHeight(10);
txtVal.getFillFormat().setFillType(FillType.Solid);
txtVal.getFillFormat().getSolidFillColor().setColor(new Color(PresetColor.DimGray));
txtVal.setLatinFont(new FontData("Calibri"));

// Einstellen des Zahlenformats der Wertachse
ichart.getAxes().getVerticalAxis().setNumberFormatLinkedToSource(false);
ichart.getAxes().getVerticalAxis().setNumberFormat("\"$\"#,##0.00");

// Festlegen des Haupteinheitenwerts des Diagramms
ichart.getAxes().getVerticalAxis().setAutomaticMajorUnit(false);
ichart.getAxes().getVerticalAxis().setMajorUnit(1.25f);
```

## Schritt 6: Speichern der Präsentation

Abschließend speichern Sie die generierte Präsentation mit dem Radardiagramm

.

```java
pres.save(outPath, SaveFormat.Pptx);
```

Das ist es! Sie haben mit Aspose.Slides für Java erfolgreich ein Radardiagramm in einer PowerPoint-Präsentation erstellt. Sie können dieses Beispiel nun weiter an Ihre spezifischen Bedürfnisse anpassen.

## Vollständiger Quellcode für die Erstellung von Radardiagrammen in Java-Folien

```java
String outPath = RunExamples.getOutPath() + File.separator + "RadarChart_Out.pptx";
Presentation pres = new Presentation();
try
{
	// Greifen Sie auf die erste Folie zu
	ISlide sld = pres.getSlides().get_Item(0);
	// Radarkarte hinzufügen
	IChart ichart = sld.getShapes().addChart(ChartType.Radar, 0, 0, 400, 400);
	// Festlegen des Index des Diagrammdatenblatts
	int defaultWorksheetIndex = 0;
	// Abrufen des Diagrammdaten-Arbeitsblatts
	IChartDataWorkbook fact = ichart.getChartData().getChartDataWorkbook();
	// Diagrammtitel festlegen
	ichart.getChartTitle().addTextFrameForOverriding("Radar Chart");
	// Standardmäßig generierte Serien und Kategorien löschen
	ichart.getChartData().getCategories().clear();
	ichart.getChartData().getSeries().clear();
	// Neue Kategorien hinzufügen
	ichart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 1, 0, "Caetegoty 1"));
	ichart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 2, 0, "Caetegoty 3"));
	ichart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 3, 0, "Caetegoty 5"));
	ichart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 4, 0, "Caetegoty 7"));
	ichart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 5, 0, "Caetegoty 9"));
	ichart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 6, 0, "Caetegoty 11"));
	// Neue Serie hinzufügen
	ichart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 1, "Series 1"), ichart.getType());
	ichart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 2, "Series 2"), ichart.getType());
	// Jetzt werden Seriendaten ausgefüllt
	IChartSeries series = ichart.getChartData().getSeries().get_Item(0);
	series.getDataPoints().addDataPointForRadarSeries(fact.getCell(defaultWorksheetIndex, 1, 1, 2.7));
	series.getDataPoints().addDataPointForRadarSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 2.4));
	series.getDataPoints().addDataPointForRadarSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 1.5));
	series.getDataPoints().addDataPointForRadarSeries(fact.getCell(defaultWorksheetIndex, 4, 1, 3.5));
	series.getDataPoints().addDataPointForRadarSeries(fact.getCell(defaultWorksheetIndex, 5, 1, 5));
	series.getDataPoints().addDataPointForRadarSeries(fact.getCell(defaultWorksheetIndex, 6, 1, 3.5));
	// Serienfarbe festlegen
	series.getFormat().getLine().getFillFormat().setFillType(FillType.Solid);
	series.getFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.RED);
	// Füllen Sie nun eine weitere Datenreihe aus
	series = ichart.getChartData().getSeries().get_Item(1);
	series.getDataPoints().addDataPointForRadarSeries(fact.getCell(defaultWorksheetIndex, 1, 2, 2.5));
	series.getDataPoints().addDataPointForRadarSeries(fact.getCell(defaultWorksheetIndex, 2, 2, 2.4));
	series.getDataPoints().addDataPointForRadarSeries(fact.getCell(defaultWorksheetIndex, 3, 2, 1.6));
	series.getDataPoints().addDataPointForRadarSeries(fact.getCell(defaultWorksheetIndex, 4, 2, 3.5));
	series.getDataPoints().addDataPointForRadarSeries(fact.getCell(defaultWorksheetIndex, 5, 2, 4));
	series.getDataPoints().addDataPointForRadarSeries(fact.getCell(defaultWorksheetIndex, 6, 2, 3.6));
	// Serienfarbe festlegen
	series.getFormat().getLine().getFillFormat().setFillType(FillType.Solid);
	series.getFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.ORANGE);
	//Legendenposition festlegen
	ichart.getLegend().setPosition(LegendPositionType.Bottom);
	// Festlegen der Texteigenschaften der Kategorieachse
	IChartPortionFormat txtCat = ichart.getAxes().getHorizontalAxis().getTextFormat().getPortionFormat();
	txtCat.setFontBold(NullableBool.True);
	txtCat.setFontHeight(10);
	txtCat.getFillFormat().setFillType(FillType.Solid);
	txtCat.getFillFormat().getSolidFillColor().setColor(new Color(PresetColor.DimGray));
	txtCat.setLatinFont(new FontData("Calibri"));
	// Festlegen der Texteigenschaften für Legenden
	IChartPortionFormat txtleg = ichart.getLegend().getTextFormat().getPortionFormat();
	txtleg.setFontBold(NullableBool.True);
	txtleg.setFontHeight(10);
	txtleg.getFillFormat().setFillType(FillType.Solid);
	txtleg.getFillFormat().getSolidFillColor().setColor(new Color(PresetColor.DimGray));
	txtCat.setLatinFont(new FontData("Calibri"));
	// Festlegen der Texteigenschaften der Wertachse
	IChartPortionFormat txtVal = ichart.getAxes().getVerticalAxis().getTextFormat().getPortionFormat();
	txtVal.setFontBold(NullableBool.True);
	txtVal.setFontHeight(10);
	txtVal.getFillFormat().setFillType(FillType.Solid);
	txtVal.getFillFormat().getSolidFillColor().setColor(new Color(PresetColor.DimGray));
	txtVal.setLatinFont(new FontData("Calibri"));
	// Einstellen des Zahlenformats der Wertachse
	ichart.getAxes().getVerticalAxis().setNumberFormatLinkedToSource(false);
	ichart.getAxes().getVerticalAxis().setNumberFormat("\"$\"#,##0.00");
	// Festlegen des Haupteinheitenwerts des Diagramms
	ichart.getAxes().getVerticalAxis().setAutomaticMajorUnit(false);
	ichart.getAxes().getVerticalAxis().setMajorUnit(1.25f);
	// Generierte Präsentation speichern
	pres.save(outPath, SaveFormat.Pptx);
}
finally
{
	if (pres != null) pres.dispose();
}
```

## Abschluss

In diesem Tutorial haben Sie gelernt, wie Sie mit Aspose.Slides für Java ein Radardiagramm in einer PowerPoint-Präsentation erstellen. Sie können diese Konzepte anwenden, um Ihre Daten effektiv in Ihren Java-Anwendungen zu visualisieren und darzustellen.

## FAQs

### Wie kann ich den Diagrammtitel ändern?

Um den Diagrammtitel zu ändern, ändern Sie die folgende Zeile:
```java
ichart.getChartTitle().addTextFrameForOverriding("Radar Chart");
```

### Kann ich dem Radardiagramm weitere Datenreihen hinzufügen?

Ja, Sie können weitere Datenreihen hinzufügen, indem Sie die Schritte in „Schritt 3“ und „Schritt 4“ für jede zusätzliche Datenreihe ausführen, die Sie einschließen möchten.

### Wie kann ich die Diagrammfarben anpassen?

 Sie können die Serienfarben anpassen, indem Sie die Linien ändern, die die festlegen`SolidFillColor` Eigenschaft für jede Serie. Zum Beispiel:
```java
series.getFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.RED);
```

### Wie kann ich die Achsenbeschriftungen und Formatierung ändern?

Beziehen Sie sich auf „Schritt 5“, um die Achsenbeschriftungen und Formatierung, einschließlich Schriftgröße und -farbe, anzupassen.

### Wie speichere ich das Diagramm in einem anderen Dateiformat?

 Sie können das Ausgabeformat ändern, indem Sie die Dateierweiterung in ändern`outPath`Variable und die entsprechende Verwendung`SaveFormat` . Um beispielsweise als PDF zu speichern, verwenden Sie`SaveFormat.Pdf`.