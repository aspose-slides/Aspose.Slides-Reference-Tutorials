---
title: Festlegen des Datumsformats für die Kategorieachse in Java-Folien
linktitle: Festlegen des Datumsformats für die Kategorieachse in Java-Folien
second_title: Aspose.Slides Java PowerPoint-Verarbeitungs-API
description: Erfahren Sie, wie Sie mit Aspose.Slides für Java ein Datumsformat für die Kategorieachse in einem PowerPoint-Diagramm festlegen. Schritt-für-Schritt-Anleitung mit Quellcode.
weight: 26
url: /de/java/data-manipulation/setting-date-format-category-axis-java-slides/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Festlegen des Datumsformats für die Kategorieachse in Java-Folien


## Einführung in das Festlegen des Datumsformats für die Kategorieachse in Java-Folien

In diesem Tutorial erfahren Sie, wie Sie mit Aspose.Slides für Java ein Datumsformat für die Kategorieachse in einem PowerPoint-Diagramm festlegen. Aspose.Slides für Java ist eine leistungsstarke Bibliothek, mit der Sie PowerPoint-Präsentationen programmgesteuert erstellen, bearbeiten und verwalten können.

## Voraussetzungen

Bevor Sie beginnen, stellen Sie sicher, dass Sie über Folgendes verfügen:

1. Aspose.Slides für Java-Bibliothek (Sie können es herunterladen von[Hier](https://releases.aspose.com/slides/java/).
2. Java-Entwicklungsumgebung eingerichtet.

## Schritt 1: Erstellen Sie eine PowerPoint-Präsentation

Zuerst müssen wir eine PowerPoint-Präsentation erstellen, in die wir ein Diagramm einfügen. Stellen Sie sicher, dass Sie die erforderlichen Aspose.Slides-Klassen importiert haben.

```java
// Der Pfad zum Dokumentverzeichnis.
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
```

## Schritt 2: Fügen Sie der Folie ein Diagramm hinzu

Fügen wir nun der PowerPoint-Folie ein Diagramm hinzu. In diesem Beispiel verwenden wir ein Flächendiagramm.

```java
IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.Area, 50, 50, 450, 300);
```

## Schritt 3: Diagrammdaten vorbereiten

Wir richten die Diagrammdaten und -kategorien ein. In diesem Beispiel verwenden wir Datumskategorien.

```java
IChartDataWorkbook wb = chart.getChartData().getChartDataWorkbook();
wb.clear(0);

chart.getChartData().getCategories().clear();
chart.getChartData().getSeries().clear();

// Datumskategorien hinzufügen
chart.getChartData().getCategories().add(wb.getCell(0, "A2", convertToOADate(new GregorianCalendar(2015, 1, 1))));
chart.getChartData().getCategories().add(wb.getCell(0, "A3", convertToOADate(new GregorianCalendar(2016, 1, 1))));
chart.getChartData().getCategories().add(wb.getCell(0, "A4", convertToOADate(new GregorianCalendar(2017, 1, 1))));
chart.getChartData().getCategories().add(wb.getCell(0, "A5", convertToOADate(new GregorianCalendar(2018, 1, 1))));

// Datenreihen hinzufügen
IChartSeries series = chart.getChartData().getSeries().add(ChartType.Line);
series.getDataPoints().addDataPointForLineSeries(wb.getCell(0, "B2", 1));
series.getDataPoints().addDataPointForLineSeries(wb.getCell(0, "B3", 2));
series.getDataPoints().addDataPointForLineSeries(wb.getCell(0, "B4", 3));
series.getDataPoints().addDataPointForLineSeries(wb.getCell(0, "B5", 4));
```

## Schritt 4: Kategorieachse anpassen
Passen wir nun die Kategorieachse an, um Daten in einem bestimmten Format anzuzeigen (z. B. jjjj).

```java
chart.getAxes().getHorizontalAxis().setCategoryAxisType(CategoryAxisType.Date);
chart.getAxes().getHorizontalAxis().setNumberFormatLinkedToSource(false);
chart.getAxes().getHorizontalAxis().setNumberFormat("yyyy");
```

## Schritt 5: Speichern Sie die Präsentation
Speichern Sie abschließend die PowerPoint-Präsentation.

```java
pres.save(dataDir + "test.pptx", SaveFormat.Pptx);
```

Das ist es! Sie haben mit Aspose.Slides für Java erfolgreich ein Datumsformat für die Kategorieachse in einem PowerPoint-Diagramm festgelegt.

## Vollständiger Quellcode zum Festlegen des Datumsformats für die Kategorieachse in Java-Folien

```java
	// Der Pfad zum Dokumentverzeichnis.
	String dataDir = "Your Document Directory";
	Presentation pres = new Presentation();
	try
	{
		IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.Area, 50, 50, 450, 300);
		IChartDataWorkbook wb = chart.getChartData().getChartDataWorkbook();
		wb.clear(0);
		chart.getChartData().getCategories().clear();
		chart.getChartData().getSeries().clear();
		chart.getChartData().getCategories().add(wb.getCell(0, "A2", convertToOADate(new GregorianCalendar(2015, 1, 1))));
		chart.getChartData().getCategories().add(wb.getCell(0, "A3", convertToOADate(new GregorianCalendar(2016, 1, 1))));
		chart.getChartData().getCategories().add(wb.getCell(0, "A4", convertToOADate(new GregorianCalendar(2017, 1, 1))));
		chart.getChartData().getCategories().add(wb.getCell(0, "A5", convertToOADate(new GregorianCalendar(2018, 1, 1))));
		IChartSeries series = chart.getChartData().getSeries().add(ChartType.Line);
		series.getDataPoints().addDataPointForLineSeries(wb.getCell(0, "B2", 1));
		series.getDataPoints().addDataPointForLineSeries(wb.getCell(0, "B3", 2));
		series.getDataPoints().addDataPointForLineSeries(wb.getCell(0, "B4", 3));
		series.getDataPoints().addDataPointForLineSeries(wb.getCell(0, "B5", 4));
		chart.getAxes().getHorizontalAxis().setCategoryAxisType(CategoryAxisType.Date);
		chart.getAxes().getHorizontalAxis().setNumberFormatLinkedToSource(false);
		chart.getAxes().getHorizontalAxis().setNumberFormat("yyyy");
		pres.save("Your Output Directory" + "test.pptx", SaveFormat.Pptx);
	}
	finally
	{
		if (pres != null) pres.dispose();
	}
}
public static String convertToOADate(GregorianCalendar date) throws ParseException
{
	double oaDate;
	SimpleDateFormat myFormat = new SimpleDateFormat("dd MM yyyy");
	java.util.Date baseDate = myFormat.parse("30 12 1899");
	Long days = TimeUnit.DAYS.convert(date.getTimeInMillis() - baseDate.getTime(), TimeUnit.MILLISECONDS);
	oaDate = (double) days + ((double) date.get(Calendar.HOUR_OF_DAY) / 24) + ((double) date.get(Calendar.MINUTE) / (60 * 24)) + ((double) date.get(Calendar.SECOND) / (60 * 24 * 60));
	return String.valueOf(oaDate);
```

##Abschluss

Sie haben das Datumsformat für die Kategorieachse in einem Java Slides-Diagramm mithilfe von Aspose.Slides für Java erfolgreich angepasst. Auf diese Weise können Sie Datumswerte in Ihren Diagrammen im gewünschten Format darstellen. Sie können gerne weitere Anpassungsoptionen basierend auf Ihren spezifischen Anforderungen erkunden.

## Häufig gestellte Fragen

### Wie ändere ich das Datumsformat für die Kategorieachse?

 Um das Datumsformat für die Kategorieachse zu ändern, verwenden Sie die`setNumberFormat` Methode auf der Kategorieachse und geben Sie das gewünschte Datumsformatmuster an, z. B. "yyyy-MM-dd" oder "MM/yyyy". Stellen Sie sicher, dass Sie`setNumberFormatLinkedToSource(false)` um das Standardformat zu überschreiben.

### Kann ich für unterschiedliche Diagramme in derselben Präsentation unterschiedliche Datumsformate verwenden?

Ja, Sie können in verschiedenen Diagrammen innerhalb derselben Präsentation unterschiedliche Datumsformate für Kategorieachsen festlegen. Passen Sie die Kategorieachse für jedes Diagramm einfach nach Bedarf an.

### Wie füge ich dem Diagramm weitere Datenpunkte hinzu?

 Um dem Diagramm weitere Datenpunkte hinzuzufügen, verwenden Sie die`getDataPoints().addDataPointForLineSeries`Methode auf die Datenreihe anwenden und die Datenwerte bereitstellen.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
