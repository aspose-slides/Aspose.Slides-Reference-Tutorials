---
title: Diagrammentitäten in Java-Folien
linktitle: Diagrammentitäten in Java-Folien
second_title: Aspose.Slides Java PowerPoint-Verarbeitungs-API
description: Erfahren Sie, wie Sie mit Aspose.Slides Java Slides-Diagramme erstellen und anpassen. Verbessern Sie Ihre Präsentationen mit leistungsstarken Diagrammelementen.
weight: 13
url: /de/java/data-manipulation/chart-entities-java-slides/
---

{< blocks/products/pf/main-wrap-class >}
{< blocks/products/pf/main-container >}
{< blocks/products/pf/tutorial-page-section >}


## Einführung in Diagrammentitäten in Java-Folien

Diagramme sind leistungsstarke Tools zur Visualisierung von Daten in Präsentationen. Egal, ob Sie Geschäftsberichte, akademische Präsentationen oder andere Inhalte erstellen, Diagramme helfen dabei, Informationen effektiv zu vermitteln. Aspose.Slides für Java bietet robuste Funktionen für die Arbeit mit Diagrammen und ist damit die erste Wahl für Java-Entwickler.

## Voraussetzungen

Bevor wir in die Welt der Diagrammentitäten eintauchen, stellen Sie sicher, dass die folgenden Voraussetzungen erfüllt sind:

- Java Development Kit (JDK) installiert
- Aspose.Slides für Java-Bibliothek heruntergeladen und zu Ihrem Projekt hinzugefügt
- Grundkenntnisse der Java-Programmierung

Beginnen wir nun mit dem Erstellen und Anpassen von Diagrammen mit Aspose.Slides für Java.

## Schritt 1: Erstellen einer Präsentation

Der erste Schritt besteht darin, eine neue Präsentation zu erstellen, in die Sie Ihr Diagramm einfügen. Hier ist ein Codeausschnitt zum Erstellen einer Präsentation:

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
```

## Schritt 2: Hinzufügen eines Diagramms

Sobald Ihre Präsentation fertig ist, können Sie ein Diagramm hinzufügen. In diesem Beispiel fügen wir ein einfaches Liniendiagramm mit Markierungen hinzu. So können Sie es machen:

```java
// Zugriff auf die erste Folie
ISlide slide = pres.getSlides().get_Item(0);

// Hinzufügen des Beispieldiagramms
IChart chart = slide.getShapes().addChart(ChartType.LineWithMarkers, 50, 50, 500, 400);
```

## Schritt 3: Diagrammtitel anpassen

Ein gut definiertes Diagramm sollte einen Titel haben. Lassen Sie uns einen Titel für unser Diagramm festlegen:

```java
// Festlegen des Diagrammtitels
chart.setTitle(true);
chart.getChartTitle().addTextFrameForOverriding("");
IPortion chartTitle = chart.getChartTitle().getTextFrameForOverriding().getParagraphs().get_Item(0).getPortions().get_Item(0);
chartTitle.setText("Sample Chart");
```

## Schritt 4: Gitternetzlinien formatieren

Sie können die Haupt- und Nebenrasterlinien Ihres Diagramms formatieren. Lassen Sie uns einige Formatierungen für die Rasterlinien der vertikalen Achse festlegen:

```java
// Festlegen des Formats der Hauptrasterlinien für die Werteachse
chart.getAxes().getVerticalAxis().getMajorGridLinesFormat().getLine().getFillFormat().setFillType(FillType.Solid);
chart.getAxes().getVerticalAxis().getMajorGridLinesFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.BLUE);
chart.getAxes().getVerticalAxis().getMajorGridLinesFormat().getLine().setWidth(5);
chart.getAxes().getVerticalAxis().getMajorGridLinesFormat().getLine().setDashStyle(LineDashStyle.DashDot);

// Festlegen des Formats für Nebenrasterlinien für die Werteachse
chart.getAxes().getVerticalAxis().getMinorGridLinesFormat().getLine().getFillFormat().setFillType(FillType.Solid);
chart.getAxes().getVerticalAxis().getMinorGridLinesFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.RED);
chart.getAxes().getVerticalAxis().getMinorGridLinesFormat().getLine().setWidth(3);
```

## Schritt 5: Werteachse anpassen

Sie haben Kontrolle über das Zahlenformat sowie die Maximal- und Minimalwerte der Werteachse. So passen Sie sie an:

```java
// Zahlenformat der Werteachse festlegen
chart.getAxes().getVerticalAxis().setNumberFormatLinkedToSource(false);
chart.getAxes().getVerticalAxis().setDisplayUnit(DisplayUnitType.Thousands);
chart.getAxes().getVerticalAxis().setNumberFormat("0.0%");

// Einstelldiagramm Maximal-, Minimalwerte
chart.getAxes().getVerticalAxis().setAutomaticMajorUnit(false);
chart.getAxes().getVerticalAxis().setAutomaticMaxValue(false);
chart.getAxes().getVerticalAxis().setAutomaticMinorUnit(false);
chart.getAxes().getVerticalAxis().setAutomaticMinValue(false);
chart.getAxes().getVerticalAxis().setMaxValue(15f);
chart.getAxes().getVerticalAxis().setMinValue(-2f);
chart.getAxes().getVerticalAxis().setMinorUnit(0.5f);
chart.getAxes().getVerticalAxis().setMajorUnit(2.0f);
```

## Schritt 6: Titel der Werteachse hinzufügen

Um Ihr Diagramm informativer zu gestalten, können Sie der Werteachse einen Titel hinzufügen:

```java
// Festlegen des Titels der Werteachse
chart.getAxes().getVerticalAxis().setTitle(true);
chart.getAxes().getVerticalAxis().getTitle().addTextFrameForOverriding("");
IPortion valtitle = chart.getAxes().getVerticalAxis().getTitle().getTextFrameForOverriding().getParagraphs().get_Item(0).getPortions().get_Item(0);
valtitle.setText("Primary Axis");
```

## Schritt 7: Kategorieachse formatieren

Die Kategorieachse, die normalerweise Datenkategorien darstellt, kann auch angepasst werden:

```java
// Festlegen des Formats der Hauptrasterlinien für die Kategorieachse
chart.getAxes().getHorizontalAxis().getMajorGridLinesFormat().getLine().getFillFormat().setFillType(FillType.Solid);
chart.getAxes().getHorizontalAxis().getMajorGridLinesFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.GREEN);
chart.getAxes().getHorizontalAxis().getMajorGridLinesFormat().getLine().setWidth(5);

// Festlegen des Formats für Nebengitterlinien für die Kategorieachse
chart.getAxes().getHorizontalAxis().getMinorGridLinesFormat().getLine().getFillFormat().setFillType(FillType.Solid);
chart.getAxes().getHorizontalAxis().getMinorGridLinesFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.YELLOW);
chart.getAxes().getHorizontalAxis().getMinorGridLinesFormat().getLine().setWidth(3);
```

## Schritt 8: Legenden hinzufügen

Legenden helfen dabei, die Datenreihen in Ihrem Diagramm zu erklären. Lassen Sie uns die Legenden anpassen:

```java
// Festlegen der Texteigenschaften für Legenden
IChartPortionFormat txtleg = chart.getLegend().getTextFormat().getPortionFormat();
txtleg.setFontBold(NullableBool.True);
txtleg.setFontHeight(16);
txtleg.setFontItalic(NullableBool.True);
txtleg.getFillFormat().setFillType(FillType.Solid);
txtleg.getFillFormat().getSolidFillColor().setColor(Color.RED);

// Legen Sie fest, ob Diagrammlegenden ohne überlappende Diagramme angezeigt werden sollen.
chart.getLegend().setOverlay(true);
```

## Schritt 9: Speichern der Präsentation

Speichern Sie abschließend Ihre Präsentation mit dem Diagramm:

```java
pres.save(dataDir + "FormattedChart_out.pptx", SaveFormat.Pptx);
```

## Vollständiger Quellcode für Diagrammentitäten in Java-Folien

```java
// Der Pfad zum Dokumentverzeichnis.
String dataDir = "Your Document Directory";
// Erstellen Sie ein Verzeichnis, falls es noch nicht vorhanden ist.
boolean IsExists = new File(dataDir).exists();
if (!IsExists)
	new File(dataDir).mkdirs();
// Präsentation instanziieren// Präsentation instanziieren
Presentation pres = new Presentation();
try
{
	// Zugriff auf die erste Folie
	ISlide slide = pres.getSlides().get_Item(0);
	// Hinzufügen des Beispieldiagramms
	IChart chart = slide.getShapes().addChart(ChartType.LineWithMarkers, 50, 50, 500, 400);
	// Festlegen des Diagrammtitels
	chart.setTitle(true);
	chart.getChartTitle().addTextFrameForOverriding("");
	IPortion chartTitle = chart.getChartTitle().getTextFrameForOverriding().getParagraphs().get_Item(0).getPortions().get_Item(0);
	chartTitle.setText("Sample Chart");
	chartTitle.getPortionFormat().getFillFormat().setFillType(FillType.Solid);
	chartTitle.getPortionFormat().getFillFormat().getSolidFillColor().setColor(Color.GRAY);
	chartTitle.getPortionFormat().setFontHeight(20);
	chartTitle.getPortionFormat().setFontBold(NullableBool.True);
	chartTitle.getPortionFormat().setFontItalic(NullableBool.True);
	// Festlegen des Formats der Hauptrasterlinien für die Werteachse
	chart.getAxes().getVerticalAxis().getMajorGridLinesFormat().getLine().getFillFormat().setFillType(FillType.Solid);
	chart.getAxes().getVerticalAxis().getMajorGridLinesFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.BLUE);
	chart.getAxes().getVerticalAxis().getMajorGridLinesFormat().getLine().setWidth(5);
	chart.getAxes().getVerticalAxis().getMajorGridLinesFormat().getLine().setDashStyle(LineDashStyle.DashDot);
	// Festlegen des Formats für Nebenrasterlinien für die Werteachse
	chart.getAxes().getVerticalAxis().getMinorGridLinesFormat().getLine().getFillFormat().setFillType(FillType.Solid);
	chart.getAxes().getVerticalAxis().getMinorGridLinesFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.RED);
	chart.getAxes().getVerticalAxis().getMinorGridLinesFormat().getLine().setWidth(3);
	// Zahlenformat der Werteachse festlegen
	chart.getAxes().getVerticalAxis().setNumberFormatLinkedToSource(false);
	chart.getAxes().getVerticalAxis().setDisplayUnit(DisplayUnitType.Thousands);
	chart.getAxes().getVerticalAxis().setNumberFormat("0.0%");
	// Einstelldiagramm Maximal-, Minimalwerte
	chart.getAxes().getVerticalAxis().setAutomaticMajorUnit(false);
	chart.getAxes().getVerticalAxis().setAutomaticMaxValue(false);
	chart.getAxes().getVerticalAxis().setAutomaticMinorUnit(false);
	chart.getAxes().getVerticalAxis().setAutomaticMinValue(false);
	chart.getAxes().getVerticalAxis().setMaxValue(15f);
	chart.getAxes().getVerticalAxis().setMinValue(-2f);
	chart.getAxes().getVerticalAxis().setMinorUnit(0.5f);
	chart.getAxes().getVerticalAxis().setMajorUnit(2.0f);
	// Festlegen der Texteigenschaften der Werteachse
	IChartPortionFormat txtVal = chart.getAxes().getVerticalAxis().getTextFormat().getPortionFormat();
	txtVal.setFontBold(NullableBool.True);
	txtVal.setFontHeight(16);
	txtVal.setFontItalic(NullableBool.True);
	txtVal.getFillFormat().setFillType(FillType.Solid);
	txtVal.getFillFormat().getSolidFillColor().setColor(Color.GREEN);
	txtVal.setLatinFont(new FontData("Times New Roman"));
	// Festlegen des Titels der Werteachse
	chart.getAxes().getVerticalAxis().setTitle(true);
	chart.getAxes().getVerticalAxis().getTitle().addTextFrameForOverriding("");
	IPortion valtitle = chart.getAxes().getVerticalAxis().getTitle().getTextFrameForOverriding().getParagraphs().get_Item(0).getPortions().get_Item(0);
	valtitle.setText("Primary Axis");
	valtitle.getPortionFormat().getFillFormat().setFillType(FillType.Solid);
	valtitle.getPortionFormat().getFillFormat().getSolidFillColor().setColor(Color.GRAY);
	valtitle.getPortionFormat().setFontHeight(20);
	valtitle.getPortionFormat().setFontBold(NullableBool.True);
	valtitle.getPortionFormat().setFontItalic(NullableBool.True);
	// Format der Wertachsenlinie festlegen: Jetzt veraltet
	// chart.getAxes().getVerticalAxis().aVerticalAxis.l.AxisLine.setWidth(10);
	// chart.getAxes().getVerticalAxis().AxisLine.getFillFormat().setFillType(FillType.Solid);
	// Chart.getAxes().getVerticalAxis().AxisLine.getFillFormat().getSolidFillColor().Color = Farbe.Rot;
	// Festlegen des Formats der Hauptrasterlinien für die Kategorieachse
	chart.getAxes().getHorizontalAxis().getMajorGridLinesFormat().getLine().getFillFormat().setFillType(FillType.Solid);
	chart.getAxes().getHorizontalAxis().getMajorGridLinesFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.GREEN);
	chart.getAxes().getHorizontalAxis().getMajorGridLinesFormat().getLine().setWidth(5);
	// Festlegen des Formats für Nebengitterlinien für die Kategorieachse
	chart.getAxes().getHorizontalAxis().getMinorGridLinesFormat().getLine().getFillFormat().setFillType(FillType.Solid);
	chart.getAxes().getHorizontalAxis().getMinorGridLinesFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.YELLOW);
	chart.getAxes().getHorizontalAxis().getMinorGridLinesFormat().getLine().setWidth(3);
	// Festlegen der Texteigenschaften der Kategorieachse
	IChartPortionFormat txtCat = chart.getAxes().getHorizontalAxis().getTextFormat().getPortionFormat();
	txtCat.setFontBold(NullableBool.True);
	txtCat.setFontHeight(16);
	txtCat.setFontItalic(NullableBool.True);
	txtCat.getFillFormat().setFillType(FillType.Solid);
	txtCat.getFillFormat().getSolidFillColor().setColor(Color.BLUE);
	txtCat.setLatinFont(new FontData("Arial"));
	// Kategorietitel festlegen
	chart.getAxes().getHorizontalAxis().setTitle(true);
	chart.getAxes().getHorizontalAxis().getTitle().addTextFrameForOverriding("");
	IPortion catTitle = chart.getAxes().getHorizontalAxis().getTitle().getTextFrameForOverriding().getParagraphs().get_Item(0).getPortions().get_Item(0);
	catTitle.setText("Sample Category");
	catTitle.getPortionFormat().getFillFormat().setFillType(FillType.Solid);
	catTitle.getPortionFormat().getFillFormat().getSolidFillColor().setColor(Color.GRAY);
	catTitle.getPortionFormat().setFontHeight(20);
	catTitle.getPortionFormat().setFontBold(NullableBool.True);
	catTitle.getPortionFormat().setFontItalic(NullableBool.True);
	// Festlegen der Beschriftungsposition der Kategorieachse
	chart.getAxes().getHorizontalAxis().setTickLabelPosition(TickLabelPositionType.Low);
	// Einstellen des Drehwinkels der Kategorieachsenbeschriftung
	chart.getAxes().getHorizontalAxis().setTickLabelRotationAngle(45);
	// Festlegen der Texteigenschaften für Legenden
	IChartPortionFormat txtleg = chart.getLegend().getTextFormat().getPortionFormat();
	txtleg.setFontBold(NullableBool.True);
	txtleg.setFontHeight(16);
	txtleg.setFontItalic(NullableBool.True);
	txtleg.getFillFormat().setFillType(FillType.Solid);
	txtleg.getFillFormat().getSolidFillColor().setColor(Color.RED);
	// Legen Sie fest, ob Diagrammlegenden ohne überlappende Diagramme angezeigt werden sollen.
	chart.getLegend().setOverlay(true);
	// Aufzeichnen der ersten Reihe auf der sekundären Werteachse
	// Chart.getChartData().getSeries().get_Item(0).PlotOnSecondAxis = true;
	// Farbschema für die Rückwand festlegen
	chart.getBackWall().setThickness(1);
	chart.getBackWall().getFormat().getFill().setFillType(FillType.Solid);
	chart.getBackWall().getFormat().getFill().getSolidFillColor().setColor(Color.ORANGE);
	chart.getFloor().getFormat().getFill().setFillType(FillType.Solid);
	chart.getFloor().getFormat().getFill().getSolidFillColor().getColor();
	//Festlegen der Farbe des Plotbereichs
	chart.getPlotArea().getFormat().getFill().setFillType(FillType.Solid);
	chart.getPlotArea().getFormat().getFill().getSolidFillColor().setColor(new Color(PresetColor.LightCyan));
	// Präsentation speichern
	pres.save(dataDir + "FormattedChart_out.pptx", SaveFormat.Pptx);
}
finally
{
	if (pres != null) pres.dispose();
}
```

## Abschluss

In diesem Artikel haben wir die Welt der Diagrammentitäten in Java Slides mit Aspose.Slides für Java erkundet. Sie haben gelernt, wie Sie Diagramme erstellen, anpassen und bearbeiten, um Ihre Präsentationen zu verbessern. Diagramme machen Ihre Daten nicht nur optisch ansprechend, sondern helfen Ihrem Publikum auch, komplexe Informationen leichter zu verstehen.

## Häufig gestellte Fragen

### Wie ändere ich den Diagrammtyp?

 Um den Diagrammtyp zu ändern, verwenden Sie die`chart.setType()` und geben Sie den gewünschten Diagrammtyp an.

### Kann ich einem Diagramm mehrere Datenreihen hinzufügen?

 Ja, Sie können mehrere Datenreihen zu einem Diagramm hinzufügen, indem Sie`chart.getChartData().getSeries().addSeries()` Methode.

### Wie passe ich die Diagrammfarben an?

Sie können die Diagrammfarben anpassen, indem Sie das Füllformat für verschiedene Diagrammelemente wie Gitternetzlinien, Titel und Legenden festlegen.

### Kann ich 3D-Diagramme erstellen?

 Ja, Aspose.Slides für Java unterstützt die Erstellung von 3D-Diagrammen. Sie können die`ChartType` zu einem 3D-Diagrammtyp, um eines zu erstellen.

### Ist Aspose.Slides für Java mit den neuesten Java-Versionen kompatibel?

Ja, Aspose.Slides für Java wird regelmäßig aktualisiert, um die neuesten Java-Versionen zu unterstützen und Kompatibilität mit einer Vielzahl von Java-Umgebungen zu bieten.
{< /blocks/products/pf/tutorial-page-section >}

{< /blocks/products/pf/main-container >}
{< /blocks/products/pf/main-wrap-class >}

{< blocks/products/products-backtop-button >}
