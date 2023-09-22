---
title: Legen Sie Diagrammdaten aus der Arbeitsmappe in Java-Folien fest
linktitle: Legen Sie Diagrammdaten aus der Arbeitsmappe in Java-Folien fest
second_title: Aspose.Slides Java PowerPoint-Verarbeitungs-API
description: Erfahren Sie, wie Sie mithilfe von Aspose.Slides Diagrammdaten aus einer Excel-Arbeitsmappe in Java Slides festlegen. Schritt-für-Schritt-Anleitung mit Codebeispielen für dynamische Präsentationen.
type: docs
weight: 15
url: /de/java/data-manipulation/set-chart-data-from-workbook-java-slides/
---

## Einführung in das Festlegen von Diagrammdaten aus einer Arbeitsmappe in Java-Folien

Aspose.Slides für Java ist eine leistungsstarke Bibliothek, die es Entwicklern ermöglicht, programmgesteuert mit PowerPoint-Präsentationen zu arbeiten. Es bietet umfangreiche Funktionen zum Erstellen, Bearbeiten und Verwalten von PowerPoint-Folien. Eine häufige Anforderung bei der Arbeit mit Präsentationen besteht darin, Diagrammdaten dynamisch aus einer externen Datenquelle, beispielsweise einer Excel-Arbeitsmappe, festzulegen. In diesem Tutorial zeigen wir Ihnen, wie Sie dies mit Java erreichen.

## Voraussetzungen

Bevor wir uns mit der Implementierung befassen, stellen Sie sicher, dass Sie die folgenden Voraussetzungen erfüllen:

- Java Development Kit (JDK) auf Ihrem System installiert.
- Aspose.Slides für Java-Bibliothek zu Ihrem Projekt hinzugefügt.
- Eine Excel-Arbeitsmappe mit den Daten, die Sie für das Diagramm verwenden möchten.

## Schritt 1: Erstellen Sie eine Präsentation

```java
String outPath = RunExamples.getOutPath() + "response2.pptx";
Presentation pres = new Presentation();
```

Wir beginnen mit der Erstellung einer neuen PowerPoint-Präsentation mit Aspose.Slides für Java.

## Schritt 2: Fügen Sie ein Diagramm hinzu

```java
IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.Pie, 50, 50, 500, 400);
```

Als Nächstes fügen wir einer der Folien der Präsentation ein Diagramm hinzu. In diesem Beispiel fügen wir ein Kreisdiagramm hinzu, Sie können jedoch den Diagrammtyp auswählen, der Ihren Anforderungen entspricht.

## Schritt 3: Diagrammdaten löschen

```java
chart.getChartData().getChartDataWorkbook().clear(0);
```

Wir löschen alle vorhandenen Daten aus dem Diagramm, um es für neue Daten aus der Excel-Arbeitsmappe vorzubereiten.

## Schritt 4: Excel-Arbeitsmappe laden

```java
Workbook workbook = new Workbook(RunExamples.getDataDir_Charts() + "book1.xlsx");
```

 Wir laden die Excel-Arbeitsmappe, die die Daten enthält, die wir für das Diagramm verwenden möchten. Ersetzen`"book1.xlsx"` mit dem Pfad zu Ihrer Excel-Datei.

## Schritt 5: Arbeitsmappen-Stream in Diagrammdaten schreiben

```java
ByteArrayOutputStream mem = new ByteArrayOutputStream();
workbook.save(mem, com.aspose.cells.SaveFormat.XLSX);
mem.flush();
chart.getChartData().writeWorkbookStream(mem.toByteArray());
```

Wir konvertieren die Excel-Arbeitsmappendaten in einen Stream und schreiben ihn in die Diagrammdaten.

## Schritt 6: Legen Sie den Datenbereich des Diagramms fest

```java
chart.getChartData().setRange("Sheet2!$A$1:$B$3");
```

Wir geben den Zellbereich aus der Excel-Arbeitsmappe an, der als Daten für das Diagramm verwendet werden soll. Passen Sie den Bereich nach Bedarf für Ihre Daten an.

## Schritt 7: Diagrammreihen anpassen

```java
IChartSeries series = chart.getChartData().getSeries().get_Item(0);
series.getParentSeriesGroup().setColorVaried(true);
```

Sie können verschiedene Eigenschaften der Diagrammreihe an Ihre Anforderungen anpassen. In diesem Beispiel aktivieren wir verschiedene Farben für die Diagrammreihe.

## Schritt 8: Speichern Sie die Präsentation

```java
pres.save(outPath, SaveFormat.Pptx);
```

Abschließend speichern wir die Präsentation mit den aktualisierten Diagrammdaten im angegebenen Ausgabepfad.

## Vollständiger Quellcode zum Festlegen von Diagrammdaten aus der Arbeitsmappe in Java-Folien

```java
String outPath = RunExamples.getOutPath() + "response2.pptx";
Presentation pres = new Presentation();
try {
	IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.Pie, 50, 50, 500, 400);
	chart.getChartData().getChartDataWorkbook().clear(0);
	Workbook workbook = null;
	try {
		workbook = new Workbook(RunExamples.getDataDir_Charts() + "book1.xlsx");
	} catch (Exception ex) {
		System.out.println(ex);
	}
	ByteArrayOutputStream mem = new ByteArrayOutputStream();
	workbook.save(mem, com.aspose.cells.SaveFormat.XLSX);
	mem.flush();
	chart.getChartData().writeWorkbookStream(mem.toByteArray());
	chart.getChartData().setRange("Sheet2!$A$1:$B$3");
	IChartSeries series = chart.getChartData().getSeries().get_Item(0);
	series.getParentSeriesGroup().setColorVaried(true);
	pres.save(outPath, SaveFormat.Pptx);
} catch(Exception e) {
} finally {
	if (pres != null) pres.dispose();
}
```

## Abschluss

In diesem Tutorial haben wir gelernt, wie man mithilfe der Aspose.Slides for Java-Bibliothek Diagrammdaten aus einer Excel-Arbeitsmappe in Java Slides festlegt. Indem Sie der Schritt-für-Schritt-Anleitung folgen und die bereitgestellten Quellcode-Beispiele verwenden, können Sie dynamische Diagrammdaten problemlos in Ihre PowerPoint-Präsentationen integrieren.

## FAQs

### Wie kann ich das Erscheinungsbild des Diagramms in meiner Präsentation anpassen?

Sie können das Erscheinungsbild des Diagramms anpassen, indem Sie Eigenschaften wie Farben, Schriftarten, Beschriftungen usw. ändern. Ausführliche Informationen zu Diagrammanpassungsoptionen finden Sie in der Dokumentation zu Aspose.Slides für Java.

### Kann ich Daten aus einer anderen Excel-Datei für das Diagramm verwenden?

Ja, Sie können Daten aus jeder Excel-Datei verwenden, indem Sie beim Laden der Arbeitsmappe im Code den richtigen Dateipfad angeben.

### Welche anderen Arten von Diagrammen kann ich mit Aspose.Slides für Java erstellen?

Aspose.Slides für Java unterstützt verschiedene Diagrammtypen, darunter Balkendiagramme, Liniendiagramme, Streudiagramme und mehr. Sie können den Diagrammtyp auswählen, der Ihren Datendarstellungsanforderungen am besten entspricht.

### Ist es möglich, die Diagrammdaten in einer laufenden Präsentation dynamisch zu aktualisieren?

Ja, Sie können Diagrammdaten in einer Präsentation dynamisch aktualisieren, indem Sie die zugrunde liegende Arbeitsmappe ändern und dann die Diagrammdaten aktualisieren.

### Wo finde ich weitere Beispiele und Ressourcen für die Arbeit mit Aspose.Slides für Java?

 Weitere Beispiele und Ressourcen finden Sie unter[Aspose-Website](https://www.aspose.com/). Darüber hinaus bietet die Dokumentation zu Aspose.Slides für Java umfassende Anleitungen zum Arbeiten mit der Bibliothek.