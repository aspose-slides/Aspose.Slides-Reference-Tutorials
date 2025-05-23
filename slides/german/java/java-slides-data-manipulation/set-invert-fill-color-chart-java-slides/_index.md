---
"description": "Erfahren Sie, wie Sie mit Aspose.Slides invertierte Füllfarben für Java Slides-Diagramme festlegen. Optimieren Sie Ihre Diagrammvisualisierungen mit dieser Schritt-für-Schritt-Anleitung und dem Quellcode."
"linktitle": "Invertiertes Füllfarbendiagramm in Java-Folien festlegen"
"second_title": "Aspose.Slides Java PowerPoint-Verarbeitungs-API"
"title": "Invertiertes Füllfarbendiagramm in Java-Folien festlegen"
"url": "/de/java/data-manipulation/set-invert-fill-color-chart-java-slides/"
"weight": 22
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Invertiertes Füllfarbendiagramm in Java-Folien festlegen


## Einführung in das Festlegen des invertierten Füllfarbendiagramms in Java-Folien

In diesem Tutorial zeigen wir, wie Sie die Füllfarbe für ein Diagramm in Java Slides mit Aspose.Slides für Java invertieren. Das Invertieren der Füllfarbe ist eine nützliche Funktion, wenn Sie negative Werte in einem Diagramm mit einer bestimmten Farbe hervorheben möchten. Wir stellen Ihnen dazu eine Schritt-für-Schritt-Anleitung und den Quellcode zur Verfügung.

## Voraussetzungen

Bevor Sie beginnen, stellen Sie sicher, dass die folgenden Voraussetzungen erfüllt sind:

1. Aspose.Slides für Java-Bibliothek installiert.
2. Java-Entwicklungsumgebung eingerichtet.

## Schritt 1: Erstellen Sie eine Präsentation

Zuerst müssen wir eine Präsentation erstellen, der wir unser Diagramm hinzufügen. Sie können den folgenden Code verwenden, um eine Präsentation zu erstellen:

```java
// Der Pfad zum Dokumentenverzeichnis.
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
```

## Schritt 2: Diagramm hinzufügen

Als Nächstes fügen wir der Präsentation ein gruppiertes Säulendiagramm hinzu. So geht's:

```java
IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 100, 100, 400, 300);
```

## Schritt 3: Diagrammdaten einrichten

Lassen Sie uns nun die Diagrammdaten einschließlich Serien und Kategorien einrichten:

```java
IChartDataWorkbook workBook = chart.getChartData().getChartDataWorkbook();
chart.getChartData().getSeries().clear();
chart.getChartData().getCategories().clear();

// Hinzufügen neuer Serien und Kategorien
chart.getChartData().getSeries().add(workBook.getCell(0, 0, 1, "Series 1"), chart.getType());
chart.getChartData().getCategories().add(workBook.getCell(0, 1, 0, "Category 1"));
chart.getChartData().getCategories().add(workBook.getCell(0, 2, 0, "Category 2"));
chart.getChartData().getCategories().add(workBook.getCell(0, 3, 0, "Category 3"));
```

## Schritt 4: Seriendaten auffüllen

Füllen wir nun die Reihendaten für das Diagramm aus:

```java
IChartSeries series = chart.getChartData().getSeries().get_Item(0);
series.getDataPoints().addDataPointForBarSeries(workBook.getCell(0, 1, 1, -20));
series.getDataPoints().addDataPointForBarSeries(workBook.getCell(0, 2, 1, 50));
series.getDataPoints().addDataPointForBarSeries(workBook.getCell(0, 3, 1, -30));
```

## Schritt 5: Füllfarbe umkehren

Um die invertierte Füllfarbe für die Diagrammreihe festzulegen, können Sie den folgenden Code verwenden:

```java
Color seriesColor = series.getAutomaticSeriesColor();
series.setInvertIfNegative(true);
series.getFormat().getFill().setFillType(FillType.Solid);
series.getFormat().getFill().getSolidFillColor().setColor(seriesColor);
series.getInvertedSolidFillColor().setColor(Color.RED);
```

Im obigen Code legen wir für die Reihe fest, dass die Füllfarbe für negative Werte invertiert wird, und geben die Farbe für die invertierte Füllung an.

## Schritt 6: Speichern Sie die Präsentation

Speichern Sie abschließend die Präsentation mit dem Diagramm:

```java
pres.save(dataDir + "SetInvertFillColorChart_out.pptx", SaveFormat.Pptx);
```

## Vollständiger Quellcode zum Festlegen des invertierten Füllfarbendiagramms in Java-Folien

```java
// Der Pfad zum Dokumentenverzeichnis.
String dataDir = "Your Document Directory";
Color inverColor = Color.RED;
Presentation pres = new Presentation();
try
{
IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 100, 100, 400, 300);
IChartDataWorkbook workBook = chart.getChartData().getChartDataWorkbook();
chart.getChartData().getSeries().clear();
chart.getChartData().getCategories().clear();
// Hinzufügen neuer Serien und Kategorien
chart.getChartData().getSeries().add(workBook.getCell(0, 0, 1, "Series 1"), chart.getType());
chart.getChartData().getCategories().add(workBook.getCell(0, 1, 0, "Category 1"));
chart.getChartData().getCategories().add(workBook.getCell(0, 2, 0, "Category 2"));
chart.getChartData().getCategories().add(workBook.getCell(0, 3, 0, "Category 3"));
// Nehmen Sie die erste Diagrammreihe und füllen Sie die Reihendaten aus.
IChartSeries series = chart.getChartData().getSeries().get_Item(0);
series.getDataPoints().addDataPointForBarSeries(workBook.getCell(0, 1, 1, -20));
series.getDataPoints().addDataPointForBarSeries(workBook.getCell(0, 2, 1, 50));
series.getDataPoints().addDataPointForBarSeries(workBook.getCell(0, 3, 1, -30));
Color seriesColor = series.getAutomaticSeriesColor();
series.setInvertIfNegative(true);
series.getFormat().getFill().setFillType(FillType.Solid);
series.getFormat().getFill().getSolidFillColor().setColor(seriesColor);
series.getInvertedSolidFillColor().setColor(Color.RED);
pres.save(dataDir + "SetInvertFillColorChart_out.pptx", SaveFormat.Pptx);
}
finally
{
if (pres != null) pres.dispose();
}
```

## Abschluss

In diesem Tutorial haben wir Ihnen gezeigt, wie Sie die invertierte Füllfarbe für ein Diagramm in Java Slides mit Aspose.Slides für Java festlegen. Mit dieser Funktion können Sie negative Werte in Ihren Diagrammen mit einer bestimmten Farbe hervorheben und so Ihre Daten optisch ansprechender gestalten.

## Häufig gestellte Fragen

In diesem Abschnitt beantworten wir einige häufig gestellte Fragen zum Festlegen der invertierten Füllfarbe für ein Diagramm in Java Slides mithilfe von Aspose.Slides für Java.

### Wie installiere ich Aspose.Slides für Java?

Sie können Aspose.Slides für Java installieren, indem Sie die Aspose.Slides JAR-Dateien in Ihr Java-Projekt einbinden. Sie können die Bibliothek von der [Aspose.Slides für Java-Downloadseite](https://releases.aspose.com/slides/java/). Befolgen Sie die Installationsanweisungen in der Dokumentation für Ihre spezifische Entwicklungsumgebung.

### Kann ich die Farbe für die invertierte Füllung in der Diagrammreihe anpassen?

Ja, Sie können die Farbe für die invertierte Füllung in der Diagrammreihe anpassen. Im bereitgestellten Codebeispiel wird die `series.getInvertedSolidFillColor().setColor(Color.RED)` Linie setzt die Farbe für die invertierte Füllung auf Rot. Sie können ersetzen `Color.RED` mit jeder anderen Farbe Ihrer Wahl.

### Wie kann ich den Diagrammtyp in Aspose.Slides für Java ändern?

Sie können den Diagrammtyp ändern, indem Sie die `ChartType` Parameter beim Hinzufügen eines Diagramms zur Präsentation. Im Codebeispiel haben wir `ChartType.ClusteredColumn`Sie können andere Diagrammtypen wie Liniendiagramme, Balkendiagramme, Kreisdiagramme usw. erkunden, indem Sie die entsprechenden `ChartType` Enumerationswert.

### Wie füge ich einem Diagramm mehrere Datenreihen hinzu?

Um mehrere Datenreihen zu einem Diagramm hinzuzufügen, können Sie das `chart.getChartData().getSeries().add(...)` Methode für jede hinzuzufügende Reihe. Stellen Sie sicher, dass Sie für jede Reihe die entsprechenden Datenpunkte und Beschriftungen angeben, um Ihr Diagramm mit mehreren Reihen zu füllen.

### Gibt es eine Möglichkeit, andere Aspekte des Diagramm-Erscheinungsbilds anzupassen?

Ja, Sie können verschiedene Aspekte des Diagramm-Erscheinungsbilds, einschließlich Achsenbeschriftungen, Titel, Legenden und mehr, mit Aspose.Slides für Java anpassen. Detaillierte Anleitungen zum Anpassen von Diagrammelementen und -darstellung finden Sie in der Dokumentation.

### Kann ich das Diagramm in verschiedenen Formaten speichern?

Ja, Sie können das Diagramm mit Aspose.Slides für Java in verschiedenen Formaten speichern. Im bereitgestellten Codebeispiel haben wir die Präsentation als PPTX-Datei gespeichert. Sie können verschiedene `SaveFormat` Optionen zum Speichern in anderen Formaten wie PDF, PNG oder SVG, je nach Ihren Anforderungen.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}