---
title: Zweite Plotoptionen für Diagramme in Java-Folien
linktitle: Zweite Plotoptionen für Diagramme in Java-Folien
second_title: Aspose.Slides Java PowerPoint-Verarbeitungs-API
description: Erfahren Sie, wie Sie Diagramme in Java Slides mit Aspose.Slides für Java anpassen. Entdecken Sie Optionen für die zweite Handlung und verbessern Sie Ihre Präsentationen.
type: docs
weight: 12
url: /de/java/chart-creation/second-plot-options-charts-java-slides/
---

## Einführung in die zweiten Plotoptionen für Diagramme in Java-Folien

In diesem Tutorial erfahren Sie, wie Sie mit Aspose.Slides für Java zweite Diagrammoptionen zu Diagrammen hinzufügen. Mit den zweiten Diagrammoptionen können Sie das Erscheinungsbild und Verhalten von Diagrammen anpassen, insbesondere in Szenarios wie Kreisdiagrammen. Um dies zu erreichen, stellen wir Ihnen Schritt-für-Schritt-Anleitungen und Quellcode-Beispiele zur Verfügung. 

## Voraussetzungen
Bevor wir beginnen, stellen Sie sicher, dass Aspose.Slides für Java in Ihrem Java-Projekt installiert und eingerichtet ist.

## Schritt 1: Erstellen Sie eine Präsentation
Beginnen wir mit der Erstellung einer neuen Präsentation:

```java
// Der Pfad zum Dokumentenverzeichnis.
String dataDir = "Your Document Directory";
// Erstellen Sie eine Instanz der Presentation-Klasse
Presentation presentation = new Presentation();
```

## Schritt 2: Fügen Sie einer Folie ein Diagramm hinzu
Als Nächstes fügen wir einer Folie ein Diagramm hinzu. In diesem Beispiel erstellen wir ein Kreisdiagramm:

```java
// Diagramm auf Folie hinzufügen
IChart chart = presentation.getSlides().get_Item(0).getShapes().addChart(ChartType.PieOfPie, 50, 50, 500, 400);
```

## Schritt 3: Diagrammeigenschaften anpassen
Legen wir nun verschiedene Eigenschaften für das Diagramm fest, einschließlich der Optionen für die zweite Darstellung:

```java
// Datenbeschriftungen für die erste Serie anzeigen
chart.getChartData().getSeries().get_Item(0).getLabels().getDefaultDataLabelFormat().setShowValue(true);

// Legen Sie die Größe des zweiten Kuchens fest (in Prozent).
chart.getChartData().getSeries().get_Item(0).getParentSeriesGroup().setSecondPieSize(149);

// Teilen Sie den Kuchen prozentual auf
chart.getChartData().getSeries().get_Item(0).getParentSeriesGroup().setPieSplitBy(PieSplitType.ByPercentage);

// Legen Sie die Position der Teilung fest
chart.getChartData().getSeries().get_Item(0).getParentSeriesGroup().setPieSplitPosition(53);
```

## Schritt 4: Speichern Sie die Präsentation
Speichern Sie abschließend die Präsentation mit den Diagramm- und zweiten Plotoptionen:

```java
// Präsentation auf Diskette schreiben
presentation.save(dataDir + "SecondPlotOptionsforCharts_out.pptx", SaveFormat.Pptx);
```

## Vollständiger Quellcode für Optionen für die zweite Handlung

```java
// Der Pfad zum Dokumentenverzeichnis.
String dataDir = "Your Document Directory";
// Erstellen Sie eine Instanz der Presentation-Klasse
Presentation presentation = new Presentation();
// Diagramm auf Folie hinzufügen
IChart chart = presentation.getSlides().get_Item(0).getShapes().addChart(ChartType.PieOfPie, 50, 50, 500, 400);
// Legen Sie verschiedene Eigenschaften fest
chart.getChartData().getSeries().get_Item(0).getLabels().getDefaultDataLabelFormat().setShowValue(true);
chart.getChartData().getSeries().get_Item(0).getParentSeriesGroup().setSecondPieSize(149);
chart.getChartData().getSeries().get_Item(0).getParentSeriesGroup().setPieSplitBy(PieSplitType.ByPercentage);
chart.getChartData().getSeries().get_Item(0).getParentSeriesGroup().setPieSplitPosition(53);
// Präsentation auf Diskette schreiben
presentation.save(dataDir + "SecondPlotOptionsforCharts_out.pptx", SaveFormat.Pptx);
```

## Abschluss

In diesem Tutorial haben wir gelernt, wie man mit Aspose.Slides für Java zweite Diagrammoptionen zu Diagrammen in Java Slides hinzufügt. Sie können verschiedene Eigenschaften anpassen, um das Erscheinungsbild und die Funktionalität Ihrer Diagramme zu verbessern und Ihre Präsentationen informativer und optisch ansprechender zu gestalten.

## FAQs

### Wie kann ich die Größe des zweiten Kreises in einem Kreisdiagramm ändern?

 Um die Größe des zweiten Kreises in einem Kreisdiagramm zu ändern, verwenden Sie die`setSecondPieSize` Methode wie im obigen Codebeispiel gezeigt. Passen Sie den Wert an, um die Größe in Prozent anzugeben.

###  Was macht`PieSplitBy` control in a Pie of Pie chart?

 Der`PieSplitBy`Die Eigenschaft steuert, wie das Kreisdiagramm aufgeteilt wird. Sie können es auf beides einstellen`PieSplitType.ByPercentage` oder`PieSplitType.ByValue` um das Diagramm prozentual bzw. nach einem bestimmten Wert aufzuteilen.

### Wie lege ich die Position der Teilung in einem Kreisdiagramm fest?

 Sie können die Position der Aufteilung in einem Kreisdiagramm mithilfe von festlegen`setPieSplitPosition` Methode. Passen Sie den Wert an, um die gewünschte Position festzulegen.