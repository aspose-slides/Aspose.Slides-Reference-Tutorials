---
"description": "Erfahren Sie, wie Sie mit Aspose.Slides für die Java-API Radardiagramme in Java-PowerPoint-Präsentationen erstellen."
"linktitle": "Radardiagramm erstellen in Java-Folien"
"second_title": "Aspose.Slides Java PowerPoint-Verarbeitungs-API"
"title": "Radardiagramm erstellen in Java-Folien"
"url": "/de/java/chart-creation/radar-chart-creating-java-slides/"
"weight": 10
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Radardiagramm erstellen in Java-Folien


## Einführung in das Erstellen eines Radardiagramms in Java-Folien

In diesem Tutorial führen wir Sie durch die Erstellung eines Radardiagramms mit der Aspose.Slides für Java-API. Radardiagramme eignen sich zur Visualisierung von Daten in einem kreisförmigen Muster und erleichtern so den Vergleich mehrerer Datenreihen. Wir stellen Ihnen eine Schritt-für-Schritt-Anleitung sowie Java-Quellcode zur Verfügung.

## Voraussetzungen

Bevor wir beginnen, stellen Sie sicher, dass Sie die Aspose.Slides für Java-Bibliothek in Ihr Projekt integriert haben. Sie können die Bibliothek herunterladen von [Hier](https://releases.aspose.com/slides/java/).

## Schritt 1: Einrichten der Präsentation

Beginnen wir mit dem Einrichten einer neuen PowerPoint-Präsentation und dem Hinzufügen einer Folie.

```java
String outPath = "Your Output Directory" + File.separator + "RadarChart_Out.pptx";
Presentation pres = new Presentation();
```

## Schritt 2: Hinzufügen eines Radardiagramms

Als Nächstes fügen wir der Folie ein Radardiagramm hinzu. Wir legen die Position und Abmessungen des Diagramms fest.

```java
ISlide sld = pres.getSlides().get_Item(0);
IChart ichart = sld.getShapes().addChart(ChartType.Radar, 0, 0, 400, 400);
```

## Schritt 3: Festlegen der Diagrammdaten

Wir legen nun die Diagrammdaten fest. Dazu erstellen wir eine Datenarbeitsmappe und fügen Kategorien und Reihen hinzu.

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

// Neue Serien hinzufügen
ichart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 1, "Series 1"), ichart.getType());
ichart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 2, "Series 2"), ichart.getType());
```

## Schritt 4: Auffüllen der Seriendaten

Jetzt füllen wir die Seriendaten für unser Radardiagramm aus.

```java
// Seriendaten für Serie 1 auffüllen
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

// Seriendaten für Serie 2 auffüllen
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

## Schritt 5: Achsen und Legenden anpassen

Passen wir die Achsen und Legenden für unser Radardiagramm an.

```java
// Legendenposition festlegen
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

// Festlegen der Texteigenschaften der Werteachse
IChartPortionFormat txtVal = ichart.getAxes().getVerticalAxis().getTextFormat().getPortionFormat();
txtVal.setFontBold(NullableBool.True);
txtVal.setFontHeight(10);
txtVal.getFillFormat().setFillType(FillType.Solid);
txtVal.getFillFormat().getSolidFillColor().setColor(new Color(PresetColor.DimGray));
txtVal.setLatinFont(new FontData("Calibri"));

// Festlegen des Zahlenformats der Werteachse
ichart.getAxes().getVerticalAxis().setNumberFormatLinkedToSource(false);
ichart.getAxes().getVerticalAxis().setNumberFormat("\"$\"#,##0.00");

// Einstelldiagramm Haupteinheitswert
ichart.getAxes().getVerticalAxis().setAutomaticMajorUnit(false);
ichart.getAxes().getVerticalAxis().setMajorUnit(1.25f);
```

## Schritt 6: Speichern der Präsentation

Abschließend speichern Sie die erstellte Präsentation mit dem Radardiagramm

.

```java
pres.save(outPath, SaveFormat.Pptx);
```

Fertig! Sie haben mit Aspose.Slides für Java erfolgreich ein Radardiagramm in einer PowerPoint-Präsentation erstellt. Sie können dieses Beispiel nun weiter an Ihre spezifischen Bedürfnisse anpassen.

## Vollständiger Quellcode zum Erstellen von Radardiagrammen in Java-Folien

```java
String outPath = "Your Output Directory" + File.separator + "RadarChart_Out.pptx";
Presentation pres = new Presentation();
try
{
	// Zugriff auf die erste Folie
	ISlide sld = pres.getSlides().get_Item(0);
	// Radardiagramm hinzufügen
	IChart ichart = sld.getShapes().addChart(ChartType.Radar, 0, 0, 400, 400);
	// Festlegen des Index des Diagrammdatenblatts
	int defaultWorksheetIndex = 0;
	// Abrufen der Diagrammdaten Arbeitsblatt
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
	// Neue Serien hinzufügen
	ichart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 1, "Series 1"), ichart.getType());
	ichart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 2, "Series 2"), ichart.getType());
	// Jetzt werden Seriendaten gefüllt
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
	// Jetzt werden weitere Datenreihen gefüllt
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
	// Legendenposition festlegen
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
	// Festlegen der Texteigenschaften der Werteachse
	IChartPortionFormat txtVal = ichart.getAxes().getVerticalAxis().getTextFormat().getPortionFormat();
	txtVal.setFontBold(NullableBool.True);
	txtVal.setFontHeight(10);
	txtVal.getFillFormat().setFillType(FillType.Solid);
	txtVal.getFillFormat().getSolidFillColor().setColor(new Color(PresetColor.DimGray));
	txtVal.setLatinFont(new FontData("Calibri"));
	// Festlegen des Zahlenformats der Werteachse
	ichart.getAxes().getVerticalAxis().setNumberFormatLinkedToSource(false);
	ichart.getAxes().getVerticalAxis().setNumberFormat("\"$\"#,##0.00");
	// Einstelldiagramm Haupteinheitswert
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

In diesem Tutorial haben Sie gelernt, wie Sie mit Aspose.Slides für Java ein Radardiagramm in einer PowerPoint-Präsentation erstellen. Sie können diese Konzepte anwenden, um Ihre Daten in Ihren Java-Anwendungen effektiv zu visualisieren und zu präsentieren.

## Häufig gestellte Fragen

### Wie kann ich den Diagrammtitel ändern?

Um den Diagrammtitel zu ändern, ändern Sie die folgende Zeile:
```java
ichart.getChartTitle().addTextFrameForOverriding("Radar Chart");
```

### Kann ich dem Radardiagramm weitere Datenreihen hinzufügen?

Ja, Sie können weitere Datenreihen hinzufügen, indem Sie für jede weitere Reihe, die Sie einschließen möchten, die Schritte in „Schritt 3“ und „Schritt 4“ befolgen.

### Wie passe ich die Diagrammfarben an?

Sie können die Serienfarben anpassen, indem Sie die Zeilen ändern, die die `SolidFillColor` Eigenschaft für jede Serie. Beispiel:
```java
series.getFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.RED);
```

### Wie kann ich die Achsenbeschriftungen und die Formatierung ändern?

Informationen zum Anpassen der Achsenbeschriftungen und -formatierung, einschließlich Schriftgröße und -farbe, finden Sie in „Schritt 5“.

### Wie speichere ich das Diagramm in einem anderen Dateiformat?

Sie können das Ausgabeformat ändern, indem Sie die Dateierweiterung im `outPath` Variable und unter Verwendung der entsprechenden `SaveFormat`. Um beispielsweise als PDF zu speichern, verwenden Sie `SaveFormat.Pdf`.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}