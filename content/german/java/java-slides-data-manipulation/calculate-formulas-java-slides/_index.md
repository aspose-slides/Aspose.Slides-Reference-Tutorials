---
title: Formeln in Java-Folien berechnen
linktitle: Formeln in Java-Folien berechnen
second_title: Aspose.Slides Java PowerPoint-Verarbeitungs-API
description: Erfahren Sie, wie Sie mit Aspose.Slides für Java Formeln in Java Slides berechnen. Schritt-für-Schritt-Anleitung mit Quellcode für dynamische PowerPoint-Präsentationen.
type: docs
weight: 10
url: /de/java/data-manipulation/calculate-formulas-java-slides/
---

## Einführung in die Berechnung von Formeln in Java-Folien mit Aspose.Slides

In dieser Anleitung zeigen wir, wie man Formeln in Java Slides mithilfe der Aspose.Slides für Java-API berechnet. Aspose.Slides ist eine leistungsstarke Bibliothek für die Arbeit mit PowerPoint-Präsentationen und bietet Funktionen zum Bearbeiten von Diagrammen und Durchführen von Formelberechnungen innerhalb von Folien.

## Voraussetzungen

Bevor Sie beginnen, stellen Sie sicher, dass Sie über Folgendes verfügen:

- Java-Entwicklungsumgebung
-  Aspose.Slides für Java-Bibliothek (Sie können es herunterladen von[Hier](https://releases.aspose.com/slides/java/)
- Grundkenntnisse der Java-Programmierung

## Schritt 1: Erstellen Sie eine neue Präsentation

Lassen Sie uns zunächst eine neue PowerPoint-Präsentation erstellen und ihr eine Folie hinzufügen. In diesem Beispiel arbeiten wir mit einer einzelnen Folie.

```java
String resultPath = RunExamples.getOutPath() + "CalculateFormulas_out.pptx";
Presentation presentation = new Presentation();
```

## Schritt 2: Fügen Sie der Folie ein Diagramm hinzu

Fügen wir der Folie nun ein gruppiertes Säulendiagramm hinzu. Wir verwenden dieses Diagramm, um Formelberechnungen zu demonstrieren.

```java
IChart s_chart = presentation.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 10, 10, 600, 300);
```

## Schritt 3: Formeln und Werte festlegen

Als Nächstes legen wir mithilfe der Aspose.Slides-API Formeln und Werte für die Diagrammdatenzellen fest. Wir berechnen die Formeln für diese Zellen.

```java
IChartDataWorkbook workbook = s_chart.getChartData().getChartDataWorkbook();

// Formel für Zelle A1 festlegen
IChartDataCell cell = workbook.getCell(0, "A1");
cell.setFormula("ABS(A2) + MAX(B2:C2)");

// Wert für Zelle A2 festlegen
workbook.getCell(0, "A2").setValue(-1);
workbook.calculateFormulas();

// Formel für Zelle B2 festlegen
workbook.getCell(0, "B2").setFormula("2");
workbook.calculateFormulas();

// Formel für Zelle C2 festlegen
workbook.getCell(0, "C2").setFormula("A2 + 4");
workbook.calculateFormulas();

// Formel für Zelle A1 erneut festlegen
cell.setFormula("MAX(2:2)");
workbook.calculateFormulas();
```

## Schritt 4: Speichern Sie die Präsentation

Abschließend speichern wir die geänderte Darstellung mit den berechneten Formeln ab.

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

In dieser Anleitung haben wir gelernt, wie man Formeln in Java Slides mit Aspose.Slides für Java berechnet. Wir haben eine neue Präsentation erstellt, ihr ein Diagramm hinzugefügt, Formeln und Werte für Diagrammdatenzellen festgelegt und die Präsentation mit den berechneten Formeln gespeichert.

## Häufig gestellte Fragen

### Wie lege ich Formeln für Diagrammdatenzellen fest?

 Sie können Formeln für Diagrammdatenzellen festlegen mit dem`setFormula` Methode von`IChartDataCell` in Aspose.Slides.

### Wie lege ich Werte für Diagrammdatenzellen fest?

 Sie können Werte für Diagrammdatenzellen festlegen mit dem`setValue` Methode von`IChartDataCell` in Aspose.Slides.

### Wie berechne ich Formeln in einer Arbeitsmappe?

 Sie können Formeln in einer Arbeitsmappe berechnen mit dem`calculateFormulas` Methode von`IChartDataWorkbook` in Aspose.Slides.
