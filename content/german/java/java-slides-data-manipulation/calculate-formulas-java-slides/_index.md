---
title: Berechnen Sie Formeln in Java-Folien
linktitle: Berechnen Sie Formeln in Java-Folien
second_title: Aspose.Slides Java PowerPoint-Verarbeitungs-API
description: Erfahren Sie, wie Sie mit Aspose.Slides für Java Formeln in Java Slides berechnen. Schritt-für-Schritt-Anleitung mit Quellcode für dynamische PowerPoint-Präsentationen.
type: docs
weight: 10
url: /de/java/data-manipulation/calculate-formulas-java-slides/
---

## Einführung in die Berechnung von Formeln in Java Slides mit Aspose.Slides

In diesem Handbuch zeigen wir, wie Sie Formeln in Java Slides mithilfe der Aspose.Slides für Java-API berechnen. Aspose.Slides ist eine leistungsstarke Bibliothek für die Arbeit mit PowerPoint-Präsentationen und bietet Funktionen zum Bearbeiten von Diagrammen und zum Durchführen von Formelberechnungen in Folien.

## Voraussetzungen

Bevor Sie beginnen, stellen Sie sicher, dass Sie über Folgendes verfügen:

- Java-Entwicklungsumgebung
-  Aspose.Slides für Java-Bibliothek (Sie können sie herunterladen von[Hier](https://releases.aspose.com/slides/java/)
- Grundkenntnisse der Java-Programmierung

## Schritt 1: Erstellen Sie eine neue Präsentation

Lassen Sie uns zunächst eine neue PowerPoint-Präsentation erstellen und eine Folie hinzufügen. In diesem Beispiel arbeiten wir mit einer einzelnen Folie.

```java
String resultPath = RunExamples.getOutPath() + "CalculateFormulas_out.pptx";
Presentation presentation = new Presentation();
```

## Schritt 2: Fügen Sie der Folie ein Diagramm hinzu

Nun fügen wir der Folie ein gruppiertes Säulendiagramm hinzu. Wir werden dieses Diagramm verwenden, um Formelberechnungen zu demonstrieren.

```java
IChart s_chart = presentation.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 10, 10, 600, 300);
```

## Schritt 3: Formeln und Werte festlegen

Als Nächstes legen wir mithilfe der Aspose.Slides-API Formeln und Werte für die Diagrammdatenzellen fest. Wir berechnen die Formeln für diese Zellen.

```java
IChartDataWorkbook workbook = s_chart.getChartData().getChartDataWorkbook();

// Legen Sie die Formel für Zelle A1 fest
IChartDataCell cell = workbook.getCell(0, "A1");
cell.setFormula("ABS(A2) + MAX(B2:C2)");

// Legen Sie den Wert für Zelle A2 fest
workbook.getCell(0, "A2").setValue(-1);
workbook.calculateFormulas();

// Legen Sie die Formel für Zelle B2 fest
workbook.getCell(0, "B2").setFormula("2");
workbook.calculateFormulas();

// Legen Sie die Formel für Zelle C2 fest
workbook.getCell(0, "C2").setFormula("A2 + 4");
workbook.calculateFormulas();

// Legen Sie die Formel für Zelle A1 erneut fest
cell.setFormula("MAX(2:2)");
workbook.calculateFormulas();
```

## Schritt 4: Speichern Sie die Präsentation

Abschließend speichern wir die geänderte Darstellung mit den berechneten Formeln.

```java
presentation.save(resultPath, SaveFormat.Pptx);
```

## Vollständiger Quellcode zum Berechnen von Formeln in Java-Folien

```java
String resultPath = RunExamples.getOutPath() + "CalculateFormulas_out.pptx";
Presentation presentation = new Presentation();
try {
	IChart s_chart = presentation.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 10, 10, 600, 300);
	IChartDataWorkbook workbook = s_chart.getChartData().getChartDataWorkbook();
	IChartDataCell cell = workbook.getCell(0, "A1");
	cell.setFormula("ABS(A2) + MAX(B2:C2)");
	workbook.getCell(0, "A2").setValue(-1);
	workbook.calculateFormulas();
	workbook.getCell(0, "B2").setFormula("2");
	workbook.calculateFormulas();
	workbook.getCell(0, "C2").setFormula("A2 + 4");
	workbook.calculateFormulas();
	cell.setFormula("MAX(2:2)");
	workbook.calculateFormulas();
	presentation.save(resultPath, SaveFormat.Pptx);
} finally {
	if (presentation != null) presentation.dispose();
}
```

## Abschluss

In dieser Anleitung haben wir gelernt, wie man mit Aspose.Slides für Java Formeln in Java Slides berechnet. Wir haben eine neue Präsentation erstellt, ein Diagramm hinzugefügt, Formeln und Werte für Diagrammdatenzellen festgelegt und die Präsentation mit den berechneten Formeln gespeichert.

## FAQs

### Wie lege ich Formeln für Diagrammdatenzellen fest?

 Mit können Sie Formeln für Diagrammdatenzellen festlegen`setFormula` Methode von`IChartDataCell` in Aspose.Slides.

### Wie lege ich Werte für Diagrammdatenzellen fest?

 Mit können Sie Werte für Diagrammdatenzellen festlegen`setValue` Methode von`IChartDataCell` in Aspose.Slides.

### Wie berechne ich Formeln in einer Arbeitsmappe?

 Sie können Formeln in einer Arbeitsmappe mit berechnen`calculateFormulas` Methode von`IChartDataWorkbook` in Aspose.Slides.
