---
title: Diagrammdatenzellenformeln in Java-Folien
linktitle: Diagrammdatenzellenformeln in Java-Folien
second_title: Aspose.Slides Java PowerPoint-Verarbeitungs-API
description: Erfahren Sie, wie Sie mit Aspose.Slides für Java Diagrammdaten-Zellformeln in Java-PowerPoint-Präsentationen festlegen. Erstellen Sie dynamische Diagramme mit Formeln.
type: docs
weight: 11
url: /de/java/data-manipulation/chart-data-cell-formulas-java-slides/
---

## Einführung in Diagrammdaten-Zellenformeln in Aspose.Slides für Java

In diesem Tutorial erfahren Sie, wie Sie mit Aspose.Slides für Java mit Zellformeln für Diagrammdaten arbeiten. Mit Aspose.Slides können Sie Diagramme in PowerPoint-Präsentationen erstellen und bearbeiten, einschließlich der Festlegung von Formeln für Datenzellen.

## Voraussetzungen

 Bevor Sie beginnen, stellen Sie sicher, dass die Aspose.Slides for Java-Bibliothek installiert ist. Sie können es herunterladen unter[Hier](https://releases.aspose.com/slides/java/).

## Schritt 1: Erstellen Sie eine PowerPoint-Präsentation

Lassen Sie uns zunächst eine neue PowerPoint-Präsentation erstellen und ein Diagramm hinzufügen.

```java
String outpptxFile = RunExamples.getOutPath() + File.separator + "ChartDataCell_Formulas_out.pptx";
Presentation presentation = new Presentation();
try
{
    // Fügen Sie der ersten Folie ein Diagramm hinzu
    IChart chart = presentation.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 150, 150, 500, 300);
    
    // Holen Sie sich die Arbeitsmappe für Diagrammdaten
    IChartDataWorkbook workbook = chart.getChartData().getChartDataWorkbook();
    
    // Fahren Sie mit den Datenzellenoperationen fort
    // ...
    
    // Speichern Sie die Präsentation
    presentation.save(outpptxFile, SaveFormat.Pptx);
}
finally
{
    if (presentation != null) presentation.dispose();
}
```

## Schritt 2: Formeln für Datenzellen festlegen

Lassen Sie uns nun Formeln für bestimmte Datenzellen im Diagramm festlegen. In diesem Beispiel legen wir Formeln für zwei verschiedene Zellen fest.

### Zelle 1: Verwendung der A1-Notation

```java
IChartDataCell cell1 = workbook.getCell(0, "B2");
cell1.setFormula("1 + SUM(F2:H5)");
```

Im obigen Code legen wir eine Formel für Zelle B2 in der A1-Notation fest. Die Formel berechnet die Summe der Zellen F2 bis H5 und addiert 1 zum Ergebnis.

### Zelle 2: Verwendung der R1C1-Notation

```java
IChartDataCell cell2 = workbook.getCell(0, "C2");
cell2.setR1C1Formula("MAX(R2C6:R5C8) / 3");
```

Hier legen wir eine Formel für Zelle C2 unter Verwendung der R1C1-Notation fest. Die Formel berechnet den Maximalwert im Bereich R2C6 bis R5C8 und dividiert ihn dann durch 3.

## Schritt 3: Formeln berechnen

Nachdem Sie die Formeln festgelegt haben, müssen Sie diese unbedingt mit dem folgenden Code berechnen:

```java
workbook.calculateFormulas();
```

Dieser Schritt stellt sicher, dass das Diagramm die aktualisierten Werte basierend auf den Formeln widerspiegelt.

## Schritt 4: Speichern Sie die Präsentation

Speichern Sie abschließend die geänderte Präsentation in einer Datei.

```java
presentation.save(outpptxFile, SaveFormat.Pptx);
```

## Vollständiger Quellcode für Diagrammdaten-Zellenformeln in Java-Folien

```java
String outpptxFile = RunExamples.getOutPath() + File.pathSeparator + "ChartDataCell_Formulas_out.pptx";
Presentation presentation = new Presentation();
try
{
	IChart chart = presentation.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 150, 150, 500, 300);
	IChartDataWorkbook workbook = chart.getChartData().getChartDataWorkbook();
	IChartDataCell cell1 = workbook.getCell(0, "B2");
	cell1.setFormula("1 + SUM(F2:H5)");
	IChartDataCell cell2 = workbook.getCell(0, "C2");
	cell2.setR1C1Formula("MAX(R2C6:R5C8) / 3");
	workbook.calculateFormulas();
	presentation.save(outpptxFile, SaveFormat.Pptx);
}
finally
{
	if (presentation != null) presentation.dispose();
}
```

## Abschluss

In diesem Tutorial haben wir untersucht, wie man in Aspose.Slides für Java mit Zellformeln für Diagrammdaten arbeitet. Wir haben das Erstellen einer PowerPoint-Präsentation, das Hinzufügen eines Diagramms, das Festlegen von Formeln für Datenzellen, das Berechnen der Formeln und das Speichern der Präsentation behandelt. Sie können diese Funktionen jetzt nutzen, um dynamische und datengesteuerte Diagramme in Ihren Präsentationen zu erstellen.

## FAQs

### Wie füge ich einer bestimmten Folie ein Diagramm hinzu?

 Um einer bestimmten Folie ein Diagramm hinzuzufügen, können Sie die verwenden`getSlides().get_Item(slideIndex)` -Methode, um auf die gewünschte Folie zuzugreifen, und verwenden Sie dann die`addChart` Methode zum Hinzufügen des Diagramms.

### Kann ich in Datenzellen verschiedene Arten von Formeln verwenden?

Ja, Sie können in Datenzellenformeln verschiedene Arten von Formeln verwenden, einschließlich mathematischer Operationen, Funktionen und Verweise auf andere Zellen.

### Wie ändere ich den Diagrammtyp?

 Sie können den Diagrammtyp ändern, indem Sie verwenden`setChartType` Methode auf der`IChart` Objekt und Angabe des Gewünschten`ChartType`.