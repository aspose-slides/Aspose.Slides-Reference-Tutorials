---
title: Legen Sie eine externe Arbeitsmappe in Java-Folien fest
linktitle: Legen Sie eine externe Arbeitsmappe in Java-Folien fest
second_title: Aspose.Slides Java PowerPoint-Verarbeitungs-API
description: Erfahren Sie, wie Sie mit Aspose.Slides für Java externe Arbeitsmappen in Java Slides festlegen. Erstellen Sie dynamische Präsentationen mit Excel-Datenintegration.
type: docs
weight: 19
url: /de/java/data-manipulation/set-external-workbook-java-slides/
---

## Einführung in das Festlegen externer Arbeitsmappen in Java-Folien

In diesem Tutorial erfahren Sie, wie Sie mit Aspose.Slides eine externe Arbeitsmappe in Java Slides einrichten. Sie erfahren, wie Sie eine PowerPoint-Präsentation mit einem Diagramm erstellen, das auf Daten aus einer externen Excel-Arbeitsmappe verweist. Am Ende dieses Leitfadens werden Sie ein klares Verständnis dafür haben, wie Sie externe Daten in Ihre Java Slides-Präsentationen integrieren.

## Voraussetzungen

Bevor wir uns mit der Implementierung befassen, stellen Sie sicher, dass Sie die folgenden Voraussetzungen erfüllen:

- Java Development Kit (JDK) auf Ihrem System installiert.
- Aspose.Slides für Java-Bibliothek zu Ihrem Projekt hinzugefügt.
- Eine Excel-Arbeitsmappe mit den Daten, auf die Sie in Ihrer Präsentation verweisen möchten.

## Schritt 1: Erstellen Sie eine neue Präsentation

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
```

Wir beginnen mit der Erstellung einer neuen PowerPoint-Präsentation mit Aspose.Slides.

## Schritt 2: Fügen Sie ein Diagramm hinzu

```java
IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.Pie, 50, 50, 400, 600, false);
```

Als nächstes fügen wir ein Kreisdiagramm in die Präsentation ein. Sie können den Diagrammtyp und die Position nach Bedarf anpassen.

## Schritt 3: Greifen Sie auf die externe Arbeitsmappe zu

```java
IChartData chartData = chart.getChartData();
chartData.setExternalWorkbook(dataDir + "externalWorkbook.xlsx");
```

 Um auf die externe Arbeitsmappe zuzugreifen, verwenden wir die`setExternalWorkbook` -Methode und geben Sie den Pfad zur Excel-Arbeitsmappe an, die die Daten enthält.

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

Wir binden das Diagramm an Daten aus der externen Arbeitsmappe, indem wir die Zellbezüge für Reihen und Kategorien angeben.

## Schritt 5: Speichern Sie die Präsentation

```java
pres.save(dataDir + "Presentation_with_externalWorkbook.pptx", SaveFormat.Pptx);
```

Abschließend speichern wir die Präsentation mit der externen Arbeitsmappenreferenz als PowerPoint-Datei.

## Vollständiger Quellcode für Set External Workbook in Java Slides

```java
// Der Pfad zum Dokumentenverzeichnis.
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

## FAQs

### Wie installiere ich Aspose.Slides für Java?

Aspose.Slides für Java kann installiert werden, indem Sie die Bibliothek zu Ihrem Java-Projekt hinzufügen. Sie können die Bibliothek von der Aspose-Website herunterladen und den Installationsanweisungen in der Dokumentation folgen.

### Kann ich mit externen Arbeitsmappen unterschiedliche Diagrammtypen verwenden?

Ja, Sie können verschiedene von Aspose.Slides unterstützte Diagrammtypen verwenden und diese an Daten aus externen Arbeitsmappen binden. Der Vorgang kann je nach gewähltem Diagrammtyp geringfügig variieren.

### Was passiert, wenn sich die Datenstruktur meiner externen Arbeitsmappe ändert?

Wenn sich die Struktur der Daten Ihrer externen Arbeitsmappe ändert, müssen Sie möglicherweise die Zellverweise in Ihrem Java-Code aktualisieren, um sicherzustellen, dass die Diagrammdaten korrekt bleiben.

### Ist Aspose.Slides mit den neuesten Java-Versionen kompatibel?

Aspose.Slides für Java wird regelmäßig aktualisiert, um die Kompatibilität mit den neuesten Java-Versionen sicherzustellen. Achten Sie darauf, nach Updates zu suchen und die neueste Version der Bibliothek zu verwenden, um optimale Leistung und Kompatibilität zu gewährleisten.

### Kann ich mehrere Diagramme hinzufügen, die auf dieselbe externe Arbeitsmappe verweisen?

Ja, Sie können Ihrer Präsentation mehrere Diagramme hinzufügen, die alle auf dieselbe externe Arbeitsmappe verweisen. Wiederholen Sie einfach die in diesem Tutorial beschriebenen Schritte für jedes Diagramm, das Sie erstellen möchten.