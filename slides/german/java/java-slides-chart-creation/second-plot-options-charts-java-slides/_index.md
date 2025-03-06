---
title: Zweite Plotoptionen für Diagramme in Java-Folien
linktitle: Zweite Plotoptionen für Diagramme in Java-Folien
second_title: Aspose.Slides Java PowerPoint-Verarbeitungs-API
description: Erfahren Sie, wie Sie Diagramme in Java Slides mit Aspose.Slides für Java anpassen. Entdecken Sie zweite Plotoptionen und verbessern Sie Ihre Präsentationen.
weight: 12
url: /de/java/chart-creation/second-plot-options-charts-java-slides/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}


## Einführung in zweite Plotoptionen für Diagramme in Java-Folien

In diesem Tutorial erfahren Sie, wie Sie mit Aspose.Slides für Java zweite Plotoptionen zu Diagrammen hinzufügen. Mit zweiten Plotoptionen können Sie das Erscheinungsbild und Verhalten von Diagrammen anpassen, insbesondere in Szenarien wie Kreisdiagrammen. Wir stellen Ihnen dazu Schritt-für-Schritt-Anleitungen und Quellcodebeispiele zur Verfügung. 

## Voraussetzungen
Bevor wir beginnen, stellen Sie sicher, dass Sie Aspose.Slides für Java in Ihrem Java-Projekt installiert und eingerichtet haben.

## Schritt 1: Erstellen Sie eine Präsentation
Beginnen wir mit der Erstellung einer neuen Präsentation:

```java
// Der Pfad zum Dokumentverzeichnis.
String dataDir = "Your Document Directory";
// Erstellen Sie eine Instanz der Präsentationsklasse
Presentation presentation = new Presentation();
```

## Schritt 2: Einer Folie ein Diagramm hinzufügen
Als Nächstes fügen wir einer Folie ein Diagramm hinzu. In diesem Beispiel erstellen wir ein Kreisdiagramm:

```java
// Diagramm zur Folie hinzufügen
IChart chart = presentation.getSlides().get_Item(0).getShapes().addChart(ChartType.PieOfPie, 50, 50, 500, 400);
```

## Schritt 3: Diagrammeigenschaften anpassen
Lassen Sie uns nun verschiedene Eigenschaften für das Diagramm festlegen, einschließlich zweiter Plotoptionen:

```java
// Datenbeschriftungen für die erste Reihe anzeigen
chart.getChartData().getSeries().get_Item(0).getLabels().getDefaultDataLabelFormat().setShowValue(true);

// Legen Sie die Größe des zweiten Kreises fest (in Prozent).
chart.getChartData().getSeries().get_Item(0).getParentSeriesGroup().setSecondPieSize(149);

// Den Kuchen prozentual aufteilen
chart.getChartData().getSeries().get_Item(0).getParentSeriesGroup().setPieSplitBy(PieSplitType.ByPercentage);

// Legen Sie die Position der Teilung fest
chart.getChartData().getSeries().get_Item(0).getParentSeriesGroup().setPieSplitPosition(53);
```

## Schritt 4: Speichern Sie die Präsentation
Speichern Sie abschließend die Präsentation mit dem Diagramm und den zweiten Plotoptionen:

```java
// Präsentation auf Festplatte schreiben
presentation.save(dataDir + "SecondPlotOptionsforCharts_out.pptx", SaveFormat.Pptx);
```

## Vollständiger Quellcode für zweite Plotoptionen

```java
// Der Pfad zum Dokumentverzeichnis.
String dataDir = "Your Document Directory";
// Erstellen Sie eine Instanz der Präsentationsklasse
Presentation presentation = new Presentation();
// Diagramm zur Folie hinzufügen
IChart chart = presentation.getSlides().get_Item(0).getShapes().addChart(ChartType.PieOfPie, 50, 50, 500, 400);
// Festlegen unterschiedlicher Eigenschaften
chart.getChartData().getSeries().get_Item(0).getLabels().getDefaultDataLabelFormat().setShowValue(true);
chart.getChartData().getSeries().get_Item(0).getParentSeriesGroup().setSecondPieSize(149);
chart.getChartData().getSeries().get_Item(0).getParentSeriesGroup().setPieSplitBy(PieSplitType.ByPercentage);
chart.getChartData().getSeries().get_Item(0).getParentSeriesGroup().setPieSplitPosition(53);
// Präsentation auf Festplatte schreiben
presentation.save(dataDir + "SecondPlotOptionsforCharts_out.pptx", SaveFormat.Pptx);
```

## Abschluss

In diesem Tutorial haben wir gelernt, wie man mit Aspose.Slides für Java zweite Plotoptionen zu Diagrammen in Java Slides hinzufügt. Sie können verschiedene Eigenschaften anpassen, um das Erscheinungsbild und die Funktionalität Ihrer Diagramme zu verbessern und Ihre Präsentationen informativer und optisch ansprechender zu gestalten.

## Häufig gestellte Fragen

### Wie kann ich die Größe des zweiten Kreises in einem Kreis-aus-Kreis-Diagramm ändern?

Um die Größe des zweiten Kreises in einem Kreis-aus-Kreis-Diagramm zu ändern, verwenden Sie die`setSecondPieSize` Methode wie im obigen Codebeispiel gezeigt. Passen Sie den Wert an, um die Größe in Prozent anzugeben.

###  Was macht`PieSplitBy` control in a Pie of Pie chart?

 Der`PieSplitBy` Eigenschaft steuert, wie das Kreisdiagramm aufgeteilt wird. Sie können es auf entweder`PieSplitType.ByPercentage` oder`PieSplitType.ByValue` um das Diagramm prozentual bzw. nach einem bestimmten Wert aufzuteilen.

### Wie lege ich die Position der Teilung in einem Kreis-von-Kreis-Diagramm fest?

 Sie können die Position der Teilung in einem Kreisdiagramm mit dem`setPieSplitPosition` Methode. Passen Sie den Wert an, um die gewünschte Position anzugeben.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
