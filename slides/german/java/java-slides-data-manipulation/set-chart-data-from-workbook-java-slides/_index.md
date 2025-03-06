---
title: Festlegen von Diagrammdaten aus der Arbeitsmappe in Java-Folien
linktitle: Festlegen von Diagrammdaten aus der Arbeitsmappe in Java-Folien
second_title: Aspose.Slides Java PowerPoint-Verarbeitungs-API
description: Erfahren Sie, wie Sie mit Aspose.Slides Diagrammdaten aus einer Excel-Arbeitsmappe in Java Slides festlegen. Schritt-für-Schritt-Anleitung mit Codebeispielen für dynamische Präsentationen.
weight: 15
url: /de/java/data-manipulation/set-chart-data-from-workbook-java-slides/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}


## Einführung in das Festlegen von Diagrammdaten aus einer Arbeitsmappe in Java-Folien

Aspose.Slides für Java ist eine leistungsstarke Bibliothek, die es Entwicklern ermöglicht, programmgesteuert mit PowerPoint-Präsentationen zu arbeiten. Sie bietet umfangreiche Funktionen zum Erstellen, Bearbeiten und Verwalten von PowerPoint-Folien. Eine häufige Anforderung bei der Arbeit mit Präsentationen besteht darin, Diagrammdaten dynamisch aus einer externen Datenquelle, beispielsweise einer Excel-Arbeitsmappe, festzulegen. In diesem Tutorial zeigen wir, wie dies mit Java erreicht werden kann.

## Voraussetzungen

Bevor wir mit der Implementierung beginnen, stellen Sie sicher, dass Sie die folgenden Voraussetzungen erfüllen:

- Auf Ihrem System ist Java Development Kit (JDK) installiert.
- Aspose.Slides für die Java-Bibliothek zu Ihrem Projekt hinzugefügt.
- Eine Excel-Arbeitsmappe mit den Daten, die Sie für das Diagramm verwenden möchten.

## Schritt 1: Erstellen Sie eine Präsentation

```java
String outPath = "Your Output Directory" + "response2.pptx";
Presentation pres = new Presentation();
```

Wir beginnen mit der Erstellung einer neuen PowerPoint-Präsentation mit Aspose.Slides für Java.

## Schritt 2: Diagramm hinzufügen

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
Workbook workbook = new Workbook("Your Document Directory";
```

 Wir laden die Excel-Arbeitsmappe, die die Daten enthält, die wir für das Diagramm verwenden möchten. Ersetzen Sie`"book1.xlsx"` durch den Pfad zu Ihrer Excel-Datei.

## Schritt 5: Arbeitsmappen-Stream in Diagrammdaten schreiben

```java
ByteArrayOutputStream mem = new ByteArrayOutputStream();
workbook.save(mem, com.aspose.cells.SaveFormat.XLSX);
mem.flush();
chart.getChartData().writeWorkbookStream(mem.toByteArray());
```

Wir konvertieren die Daten der Excel-Arbeitsmappe in einen Stream und schreiben sie in die Diagrammdaten.

## Schritt 6: Datenbereich des Diagramms festlegen

```java
chart.getChartData().setRange("Sheet2!$A$1:$B$3");
```

Wir geben den Zellbereich aus der Excel-Arbeitsmappe an, der als Daten für das Diagramm verwendet werden soll. Passen Sie den Bereich nach Bedarf an Ihre Daten an.

## Schritt 7: Diagrammserien anpassen

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

## Vollständiger Quellcode zum Festlegen von Diagrammdaten aus einer Arbeitsmappe in Java-Folien

```java
String outPath = "Your Output Directory" + "response2.pptx";
Presentation pres = new Presentation();
try {
	IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.Pie, 50, 50, 500, 400);
	chart.getChartData().getChartDataWorkbook().clear(0);
	Workbook workbook = null;
	try {
		workbook = new Workbook("Your Document Directory";
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

In diesem Tutorial haben wir gelernt, wie Sie mithilfe der Bibliothek Aspose.Slides für Java Diagrammdaten aus einer Excel-Arbeitsmappe in Java Slides festlegen. Indem Sie der Schritt-für-Schritt-Anleitung folgen und die bereitgestellten Quellcodebeispiele verwenden, können Sie dynamische Diagrammdaten problemlos in Ihre PowerPoint-Präsentationen integrieren.

## Häufig gestellte Fragen

### Wie kann ich das Erscheinungsbild des Diagramms in meiner Präsentation anpassen?

Sie können das Erscheinungsbild des Diagramms anpassen, indem Sie Eigenschaften wie Farben, Schriftarten, Beschriftungen usw. ändern. Detaillierte Informationen zu den Anpassungsoptionen für Diagramme finden Sie in der Dokumentation zu Aspose.Slides für Java.

### Kann ich für das Diagramm Daten aus einer anderen Excel-Datei verwenden?

Ja, Sie können Daten aus jeder beliebigen Excel-Datei verwenden, indem Sie beim Laden der Arbeitsmappe im Code den richtigen Dateipfad angeben.

### Welche anderen Diagrammtypen kann ich mit Aspose.Slides für Java erstellen?

Aspose.Slides für Java unterstützt verschiedene Diagrammtypen, darunter Balkendiagramme, Liniendiagramme, Streudiagramme und mehr. Sie können den Diagrammtyp auswählen, der Ihren Anforderungen an die Datendarstellung am besten entspricht.

### Ist es möglich, die Diagrammdaten während einer laufenden Präsentation dynamisch zu aktualisieren?

Ja, Sie können Diagrammdaten in einer Präsentation dynamisch aktualisieren, indem Sie die zugrunde liegende Arbeitsmappe ändern und dann die Diagrammdaten aktualisieren.

### Wo finde ich weitere Beispiele und Ressourcen zur Arbeit mit Aspose.Slides für Java?

 Weitere Beispiele und Ressourcen finden Sie auf der[Aspose-Website](https://www.aspose.com/). Darüber hinaus bietet die Aspose.Slides für Java-Dokumentation umfassende Anleitungen zur Arbeit mit der Bibliothek.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
