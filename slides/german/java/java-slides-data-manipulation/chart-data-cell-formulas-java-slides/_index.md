---
title: Diagrammdatenzellenformeln in Java-Folien
linktitle: Diagrammdatenzellenformeln in Java-Folien
second_title: Aspose.Slides Java PowerPoint-Verarbeitungs-API
description: Erfahren Sie, wie Sie mit Aspose.Slides für Java Diagrammdatenzellenformeln in Java PowerPoint-Präsentationen festlegen. Erstellen Sie dynamische Diagramme mit Formeln.
weight: 11
url: /de/java/data-manipulation/chart-data-cell-formulas-java-slides/
---

{< blocks/products/pf/main-wrap-class >}
{< blocks/products/pf/main-container >}
{< blocks/products/pf/tutorial-page-section >}


## Einführung in Diagrammdatenzellenformeln in Aspose.Slides für Java

In diesem Tutorial erfahren Sie, wie Sie mit Aspose.Slides für Java mit Diagrammdatenzellenformeln arbeiten. Mit Aspose.Slides können Sie Diagramme in PowerPoint-Präsentationen erstellen und bearbeiten, einschließlich der Festlegung von Formeln für Datenzellen.

## Voraussetzungen

 Bevor Sie beginnen, stellen Sie sicher, dass Sie die Aspose.Slides für Java-Bibliothek installiert haben. Sie können sie hier herunterladen:[Hier](https://releases.aspose.com/slides/java/).

## Schritt 1: Erstellen Sie eine PowerPoint-Präsentation

Lassen Sie uns zunächst eine neue PowerPoint-Präsentation erstellen und ihr ein Diagramm hinzufügen.

```java
String outpptxFile = "Your Output Directory" + File.separator + "ChartDataCell_Formulas_out.pptx";
Presentation presentation = new Presentation();
try
{
    // Fügen Sie der ersten Folie ein Diagramm hinzu
    IChart chart = presentation.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 150, 150, 500, 300);
    
    // Abrufen der Arbeitsmappe für Diagrammdaten
    IChartDataWorkbook workbook = chart.getChartData().getChartDataWorkbook();
    
    // Fahren Sie mit den Datenzellenvorgängen fort
    // ...
    
    // Speichern der Präsentation
    presentation.save(outpptxFile, SaveFormat.Pptx);
}
finally
{
    if (presentation != null) presentation.dispose();
}
```

## Schritt 2: Formeln für Datenzellen festlegen

Jetzt legen wir Formeln für bestimmte Datenzellen im Diagramm fest. In diesem Beispiel legen wir Formeln für zwei verschiedene Zellen fest.

### Zelle 1: Verwenden der A1-Notation

```java
IChartDataCell cell1 = workbook.getCell(0, "B2");
cell1.setFormula("1 + SUM(F2:H5)");
```

Im obigen Code legen wir eine Formel für Zelle B2 mit der Notation A1 fest. Die Formel berechnet die Summe der Zellen F2 bis H5 und addiert 1 zum Ergebnis.

### Zelle 2: Verwenden der R1C1-Notation

```java
IChartDataCell cell2 = workbook.getCell(0, "C2");
cell2.setR1C1Formula("MAX(R2C6:R5C8) / 3");
```

Hier legen wir eine Formel für Zelle C2 mit der Notation R1C1 fest. Die Formel berechnet den Maximalwert im Bereich R2C6 bis R5C8 und dividiert ihn dann durch 3.

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

## Vollständiger Quellcode für Diagrammdatenzellenformeln in Java-Folien

```java
String outpptxFile = "Your Output Directory" + File.pathSeparator + "ChartDataCell_Formulas_out.pptx";
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

In diesem Tutorial haben wir untersucht, wie man mit Diagrammdatenzellenformeln in Aspose.Slides für Java arbeitet. Wir haben das Erstellen einer PowerPoint-Präsentation, das Hinzufügen eines Diagramms, das Festlegen von Formeln für Datenzellen, das Berechnen der Formeln und das Speichern der Präsentation behandelt. Sie können diese Funktionen jetzt nutzen, um dynamische und datengesteuerte Diagramme in Ihren Präsentationen zu erstellen.

## FAQs

### Wie füge ich einer bestimmten Folie ein Diagramm hinzu?

 Um ein Diagramm zu einer bestimmten Folie hinzuzufügen, können Sie das`getSlides().get_Item(slideIndex)` , um zur gewünschten Folie zu gelangen, und verwenden Sie dann die`addChart` Methode zum Hinzufügen des Diagramms.

### Kann ich in Datenzellen unterschiedliche Arten von Formeln verwenden?

Ja, Sie können in Datenzellenformeln verschiedene Arten von Formeln verwenden, darunter mathematische Operationen, Funktionen und Verweise auf andere Zellen.

### Wie ändere ich den Diagrammtyp?

 Sie können den Diagrammtyp ändern, indem Sie das`setChartType` Methode auf der`IChart` Objekt und Angabe der gewünschten`ChartType`.
{< /blocks/products/pf/tutorial-page-section >}

{< /blocks/products/pf/main-container >}
{< /blocks/products/pf/main-wrap-class >}

{< blocks/products/products-backtop-button >}
