---
"description": "Erfahren Sie, wie Sie mit Aspose.Slides für Java dynamische Diagramme mit automatischer Serienfarbe in PowerPoint-Präsentationen erstellen. Optimieren Sie Ihre Datenvisualisierungen mühelos."
"linktitle": "Automatische Diagrammreihenfarbe in Java-Folien"
"second_title": "Aspose.Slides Java PowerPoint-Verarbeitungs-API"
"title": "Automatische Diagrammreihenfarbe in Java-Folien"
"url": "/de/java/chart-data-manipulation/automatic-chart-series-color-java-slides/"
"weight": 14
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Automatische Diagrammreihenfarbe in Java-Folien


## Einführung in die automatische Diagrammreihenfarbe in Aspose.Slides für Java

In diesem Tutorial erfahren Sie, wie Sie mit Aspose.Slides für Java eine PowerPoint-Präsentation mit einem Diagramm erstellen und automatische Füllfarben für Diagrammreihen festlegen. Automatische Füllfarben können Ihre Diagramme optisch ansprechender gestalten und Ihnen Zeit sparen, da die Bibliothek die Farben für Sie auswählt.

## Voraussetzungen

Bevor Sie beginnen, stellen Sie sicher, dass die Bibliothek Aspose.Slides für Java in Ihrem Projekt installiert ist. Sie können sie hier herunterladen: [Hier](https://releases.aspose.com/slides/java/).

## Schritt 1: Erstellen Sie eine neue Präsentation

Zuerst erstellen wir eine neue PowerPoint-Präsentation und fügen ihr eine Folie hinzu.

```java
// Der Pfad zum Dokumentenverzeichnis.
String dataDir = "Your Document Directory";
// Erstellen Sie eine Instanz der Präsentationsklasse
Presentation presentation = new Presentation();
```

## Schritt 2: Fügen Sie der Folie ein Diagramm hinzu

Als Nächstes fügen wir der Folie ein gruppiertes Säulendiagramm hinzu. Außerdem legen wir fest, dass die erste Reihe Werte anzeigt.

```java
// Zugriff auf die erste Folie
ISlide slide = presentation.getSlides().get_Item(0);
// Diagramm mit Standarddaten hinzufügen
IChart chart = slide.getShapes().addChart(ChartType.ClusteredColumn, 0, 0, 500, 500);
// Stellen Sie die erste Serie auf „Werte anzeigen“ ein
chart.getChartData().getSeries().get_Item(0).getLabels().getDefaultDataLabelFormat().setShowValue(true);
```

## Schritt 3: Diagrammdaten füllen

Nun füllen wir das Diagramm mit Daten. Wir löschen zunächst die standardmäßig generierten Reihen und Kategorien und fügen dann neue Reihen und Kategorien hinzu.

```java
// Festlegen des Index des Diagrammdatenblatts
int defaultWorksheetIndex = 0;
// Abrufen des Arbeitsblatts mit den Diagrammdaten
IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
// Standardmäßig generierte Serien und Kategorien löschen
chart.getChartData().getSeries().clear();
chart.getChartData().getCategories().clear();

// Neue Serien hinzufügen
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 1, "Series 1"), chart.getType());
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 2, "Series 2"), chart.getType());

// Neue Kategorien hinzufügen
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 1, 0, "Category 1"));
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 2, 0, "Category 2"));
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 3, 0, "Category 3"));
```

## Schritt 4: Seriendaten auffüllen

Wir werden die Seriendaten sowohl für Serie 1 als auch für Serie 2 auffüllen.

```java
// Nehmen Sie die erste Chartreihe
IChartSeries series = chart.getChartData().getSeries().get_Item(0);
// Jetzt werden Seriendaten gefüllt
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 1, 20));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 50));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 30));

// Nehmen Sie die zweite Diagrammreihe
series = chart.getChartData().getSeries().get_Item(1);
// Jetzt werden Seriendaten gefüllt
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 2, 30));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 2, 10));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 2, 60));
```

## Schritt 5: Automatische Füllfarbe für Serien festlegen

Legen wir nun die automatischen Füllfarben für die Diagrammreihe fest. Die Bibliothek wählt dann die Farben für uns aus.

```java
// Automatische Füllfarbe für Serien einstellen
series.getFormat().getFill().setFillType(FillType.NotDefined);
```

## Schritt 6: Speichern Sie die Präsentation

Abschließend speichern wir die Präsentation mit dem Diagramm in einer PowerPoint-Datei.

```java
// Präsentation mit Diagramm speichern
presentation.save(dataDir + "AutomaticColor_out.pptx", SaveFormat.Pptx);
```

## Vollständiger Quellcode für die automatische Diagrammreihenfarbe in Java-Folien

```java
// Der Pfad zum Dokumentenverzeichnis.
String dataDir = "Your Document Directory";
// Erstellen Sie eine Instanz der Präsentationsklasse
Presentation presentation = new Presentation();
try
{
	// Zugriff auf die erste Folie
	ISlide slide = presentation.getSlides().get_Item(0);
	// Diagramm mit Standarddaten hinzufügen
	IChart chart = slide.getShapes().addChart(ChartType.ClusteredColumn, 0, 0, 500, 500);
	// Stellen Sie die erste Serie auf „Werte anzeigen“ ein
	chart.getChartData().getSeries().get_Item(0).getLabels().getDefaultDataLabelFormat().setShowValue(true);
	// Festlegen des Index des Diagrammdatenblatts
	int defaultWorksheetIndex = 0;
	// Abrufen des Arbeitsblatts mit den Diagrammdaten
	IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
	// Standardmäßig generierte Serien und Kategorien löschen
	chart.getChartData().getSeries().clear();
	chart.getChartData().getCategories().clear();
	int s = chart.getChartData().getSeries().size();
	s = chart.getChartData().getCategories().size();
	// Neue Serien hinzufügen
	chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 1, "Series 1"), chart.getType());
	chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 2, "Series 2"), chart.getType());
	// Neue Kategorien hinzufügen
	chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 1, 0, "Caetegoty 1"));
	chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 2, 0, "Caetegoty 2"));
	chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 3, 0, "Caetegoty 3"));
	// Nehmen Sie die erste Chartreihe
	IChartSeries series = chart.getChartData().getSeries().get_Item(0);
	// Jetzt werden Seriendaten gefüllt
	series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 1, 20));
	series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 50));
	series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 30));
	// Automatische Füllfarbe für Serien einstellen
	series.getFormat().getFill().setFillType(FillType.NotDefined);
	// Nehmen Sie die zweite Diagrammreihe
	series = chart.getChartData().getSeries().get_Item(1);
	// Jetzt werden Seriendaten gefüllt
	series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 2, 30));
	series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 2, 10));
	series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 2, 60));
	// Füllfarbe für Serien festlegen
	series.getFormat().getFill().setFillType(FillType.Solid);
	series.getFormat().getFill().getSolidFillColor().setColor(Color.GRAY);
	// Präsentation mit Diagramm speichern
	presentation.save(dataDir + "AutomaticColor_out.pptx", SaveFormat.Pptx);
}
finally
{
	if (presentation != null) presentation.dispose();
}
```

## Abschluss

In diesem Tutorial haben wir gelernt, wie Sie mit Aspose.Slides für Java eine PowerPoint-Präsentation mit einem Diagramm erstellen und automatische Füllfarben für Diagrammreihen festlegen. Automatische Farben können die visuelle Attraktivität Ihrer Diagramme steigern und Ihre Präsentationen ansprechender gestalten. Sie können das Diagramm nach Bedarf weiter an Ihre spezifischen Anforderungen anpassen.

## Häufig gestellte Fragen

### Wie lege ich automatische Füllfarben für Diagrammreihen in Aspose.Slides für Java fest?

Um automatische Füllfarben für Diagrammreihen in Aspose.Slides für Java festzulegen, verwenden Sie den folgenden Code:

```java
// Automatische Füllfarbe für Serien einstellen
series.getFormat().getFill().setFillType(FillType.NotDefined);
```

Mit diesem Code kann die Bibliothek automatisch Farben für die Diagrammreihe auswählen.

### Kann ich die Diagrammfarben bei Bedarf anpassen?

Ja, Sie können die Diagrammfarben nach Bedarf anpassen. Im Beispiel haben wir automatische Füllfarben verwendet. Sie können jedoch auch bestimmte Farben festlegen, indem Sie Folgendes ändern: `FillType` Und `SolidFillColor` Eigenschaften des Serienformats.

### Wie kann ich dem Diagramm zusätzliche Reihen oder Kategorien hinzufügen?

Um dem Diagramm weitere Reihen oder Kategorien hinzuzufügen, verwenden Sie die `getSeries()` Und `getCategories()` Methoden des Diagramms `ChartData` Objekt. Sie können neue Serien und Kategorien hinzufügen, indem Sie deren Daten und Beschriftungen angeben.

### Ist es möglich, das Diagramm und die Beschriftungen weiter zu formatieren?

Ja, Sie können Diagramm, Reihen und Beschriftungen nach Bedarf weiter formatieren. Aspose.Slides für Java bietet umfangreiche Formatierungsoptionen für Diagramme, einschließlich Schriftarten, Farben, Stilen und mehr. Weitere Informationen zu den Formatierungsoptionen finden Sie in der Dokumentation.

### Wo finde ich weitere Informationen zur Arbeit mit Aspose.Slides für Java?

Weitere Informationen und eine ausführliche Dokumentation zu Aspose.Slides für Java finden Sie in der Referenzdokumentation [Hier](https://reference.aspose.com/slides/java/).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}