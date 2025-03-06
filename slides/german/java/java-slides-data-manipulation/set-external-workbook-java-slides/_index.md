---
title: Externes Arbeitsbuch in Java-Folien festlegen
linktitle: Externes Arbeitsbuch in Java-Folien festlegen
second_title: Aspose.Slides Java PowerPoint-Verarbeitungs-API
description: Erfahren Sie, wie Sie mit Aspose.Slides für Java externe Arbeitsmappen in Java Slides einrichten. Erstellen Sie dynamische Präsentationen mit Excel-Datenintegration.
weight: 19
url: /de/java/data-manipulation/set-external-workbook-java-slides/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Externes Arbeitsbuch in Java-Folien festlegen


## Einführung in das Festlegen externer Arbeitsmappen in Java-Folien

In diesem Tutorial erfahren Sie, wie Sie mit Aspose.Slides eine externe Arbeitsmappe in Java Slides einrichten. Sie erfahren, wie Sie eine PowerPoint-Präsentation mit einem Diagramm erstellen, das auf Daten aus einer externen Excel-Arbeitsmappe verweist. Am Ende dieses Handbuchs wissen Sie genau, wie Sie externe Daten in Ihre Java Slides-Präsentationen integrieren.

## Voraussetzungen

Bevor wir mit der Implementierung beginnen, stellen Sie sicher, dass Sie die folgenden Voraussetzungen erfüllen:

- Auf Ihrem System ist Java Development Kit (JDK) installiert.
- Aspose.Slides für die Java-Bibliothek zu Ihrem Projekt hinzugefügt.
- Eine Excel-Arbeitsmappe mit den Daten, auf die Sie in Ihrer Präsentation verweisen möchten.

## Schritt 1: Erstellen Sie eine neue Präsentation

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
```

Wir beginnen mit der Erstellung einer neuen PowerPoint-Präsentation mit Aspose.Slides.

## Schritt 2: Diagramm hinzufügen

```java
IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.Pie, 50, 50, 400, 600, false);
```

Als nächstes fügen wir ein Kreisdiagramm in die Präsentation ein. Diagrammtyp und Position können Sie nach Bedarf anpassen.

## Schritt 3: Auf externe Arbeitsmappe zugreifen

```java
IChartData chartData = chart.getChartData();
chartData.setExternalWorkbook(dataDir + "externalWorkbook.xlsx");
```

 Für den Zugriff auf die externe Arbeitsmappe verwenden wir die`setExternalWorkbook` Methode und geben Sie den Pfad zur Excel-Arbeitsmappe an, die die Daten enthält.

## Schritt 4: Diagrammdaten binden

```java
chartData.getSeries().add(chartData.getChartDataWorkbook().getCell(0, "B1"), ChartType.Pie);
chartData.getSeries().get_Item(0).getDataPoints().addDataPointForPieSeries(chartData.getChartDataWorkbook().getCell(0, "B2"));
chartData.getSeries().get_Item(0).getDataPoints().addDataPointForPieSeries(chartData.getChartDataWorkbook().getCell(0, "B3"));
chartData.getSeries().get_Item(0).getDataPoints().addDataPointForPieSeries(chartData.getChartDataWorkbook().getCell(0, "B4"));
chartData.getCategories().add(chartData.getChartDataWorkbook().getCell(0, "A2"));
chartData.getCategories().add(chartData.getChartDataWorkbook().getCell(0, "A3"));
chartData.getCategories().add(chartData.getChartDataWorkbook().getCell(0, "A4"));
```

Wir binden das Diagramm an Daten aus der externen Arbeitsmappe an, indem wir die Zellbezüge für Reihen und Kategorien angeben.

## Schritt 5: Speichern Sie die Präsentation

```java
pres.save(dataDir + "Presentation_with_externalWorkbook.pptx", SaveFormat.Pptx);
```

Abschließend speichern wir die Präsentation mit dem externen Arbeitsmappenverweis als PowerPoint-Datei ab.

## Vollständiger Quellcode zum Festlegen eines externen Arbeitsbuchs in Java-Folien

```java
// Der Pfad zum Dokumentverzeichnis.
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
try
{
	IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.Pie, 50, 50, 400, 600, false);
	IChartData chartData = chart.getChartData();
	chartData.setExternalWorkbook(dataDir + "externalWorkbook.xlsx");
	chartData.getSeries().add(chartData.getChartDataWorkbook().getCell(0, "B1"), ChartType.Pie);
	chartData.getSeries().get_Item(0).getDataPoints().addDataPointForPieSeries(chartData.getChartDataWorkbook().getCell(0, "B2"));
	chartData.getSeries().get_Item(0).getDataPoints().addDataPointForPieSeries(chartData.getChartDataWorkbook().getCell(0, "B3"));
	chartData.getSeries().get_Item(0).getDataPoints().addDataPointForPieSeries(chartData.getChartDataWorkbook().getCell(0, "B4"));
	chartData.getCategories().add(chartData.getChartDataWorkbook().getCell(0, "A2"));
	chartData.getCategories().add(chartData.getChartDataWorkbook().getCell(0, "A3"));
	chartData.getCategories().add(chartData.getChartDataWorkbook().getCell(0, "A4"));
	pres.save(dataDir + "Presentation_with_externalWorkbook.pptx", SaveFormat.Pptx);
}
finally
{
	if (pres != null) pres.dispose();
}
```

## Abschluss

In diesem Tutorial haben wir gelernt, wie man mit Aspose.Slides eine externe Arbeitsmappe in Java Slides einrichtet. Sie können jetzt Präsentationen erstellen, die dynamisch auf Daten aus Excel-Arbeitsmappen verweisen und so die Flexibilität und Interaktivität Ihrer Folien verbessern.

## Häufig gestellte Fragen

### Wie installiere ich Aspose.Slides für Java?

Aspose.Slides für Java kann installiert werden, indem Sie die Bibliothek zu Ihrem Java-Projekt hinzufügen. Sie können die Bibliothek von der Aspose-Website herunterladen und den Installationsanweisungen in der Dokumentation folgen.

### Kann ich mit externen Arbeitsmappen verschiedene Diagrammtypen verwenden?

Ja, Sie können verschiedene von Aspose.Slides unterstützte Diagrammtypen verwenden und diese an Daten aus externen Arbeitsmappen binden. Der Vorgang kann je nach gewähltem Diagrammtyp leicht variieren.

### Was passiert, wenn sich die Datenstruktur meiner externen Arbeitsmappe ändert?

Wenn sich die Struktur der Daten Ihrer externen Arbeitsmappe ändert, müssen Sie möglicherweise die Zellreferenzen in Ihrem Java-Code aktualisieren, um sicherzustellen, dass die Diagrammdaten korrekt bleiben.

### Ist Aspose.Slides mit den neuesten Java-Versionen kompatibel?

Aspose.Slides für Java wird regelmäßig aktualisiert, um die Kompatibilität mit den neuesten Java-Versionen sicherzustellen. Achten Sie darauf, nach Updates zu suchen und verwenden Sie die neueste Version der Bibliothek für optimale Leistung und Kompatibilität.

### Kann ich mehrere Diagramme hinzufügen, die auf dieselbe externe Arbeitsmappe verweisen?

Ja, Sie können Ihrer Präsentation mehrere Diagramme hinzufügen, die alle auf dieselbe externe Arbeitsmappe verweisen. Wiederholen Sie einfach die in diesem Tutorial beschriebenen Schritte für jedes Diagramm, das Sie erstellen möchten.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
