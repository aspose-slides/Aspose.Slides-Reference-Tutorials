---
title: Donut-Diagrammloch in Java-Folien
linktitle: Donut-Diagrammloch in Java-Folien
second_title: Aspose.Slides Java PowerPoint-Verarbeitungs-API
description: Erstellen Sie Donut-Diagramme mit benutzerdefinierten Lochgrößen in Java Slides mit Aspose.Slides für Java. Schritt-für-Schritt-Anleitung mit Quellcode zur Diagrammanpassung.
type: docs
weight: 11
url: /de/java/chart-elements/doughnut-chart-hole-java-slides/
---

## Einführung in das Donut-Diagramm mit Loch in Java-Folien

In diesem Tutorial führen wir Sie durch die Erstellung eines Donut-Diagramms mit einem Loch mit Aspose.Slides für Java. Diese Schritt-für-Schritt-Anleitung führt Sie anhand von Quellcode-Beispielen durch den Prozess.

## Voraussetzungen

 Bevor Sie beginnen, stellen Sie sicher, dass die Aspose.Slides for Java-Bibliothek in Ihrem Java-Projekt installiert und eingerichtet ist. Sie können es hier herunterladen[Aspose.Slides für Java-Dokumentation](https://reference.aspose.com/slides/java/).

## Schritt 1: Importieren Sie die erforderlichen Bibliotheken

```java
import com.aspose.slides.ChartType;
import com.aspose.slides.IChart;
import com.aspose.slides.Presentation;
import com.aspose.slides.SaveFormat;
```

## Schritt 2: Initialisieren Sie die Präsentation

```java
// Der Pfad zum Dokumentenverzeichnis.
String dataDir = "Your Document Directory";

// Erstellen Sie eine Instanz der Presentation-Klasse
Presentation presentation = new Presentation();
```

## Schritt 3: Erstellen Sie das Donut-Diagramm

```java
try {
    // Erstellen Sie auf der ersten Folie ein Donut-Diagramm
    IChart chart = presentation.getSlides().get_Item(0).getShapes().addChart(ChartType.Doughnut, 50, 50, 400, 400);
    
    // Legen Sie die Größe des Lochs im Donut-Diagramm fest (in Prozent).
    chart.getChartData().getSeriesGroups().get_Item(0).setDoughnutHoleSize((byte) 90);
    
    // Speichern Sie die Präsentation auf der Festplatte
    presentation.save(dataDir + "DoughnutHoleSize_out.pptx", SaveFormat.Pptx);
} finally {
    // Entsorgen Sie das Präsentationsobjekt
    if (presentation != null) presentation.dispose();
}
```

## Schritt 4: Führen Sie den Code aus

 Führen Sie den Java-Code in Ihrer IDE oder Ihrem Texteditor aus, um ein Donut-Diagramm mit einer bestimmten Lochgröße zu erstellen. Unbedingt austauschen`"Your Document Directory"` mit dem tatsächlichen Pfad, in dem Sie die Präsentation speichern möchten.

## Vollständiger Quellcode für Donut Chart Hole in Java Slides

```java
// Der Pfad zum Dokumentenverzeichnis.
String dataDir = "Your Document Directory";
// Erstellen Sie eine Instanz der Presentation-Klasse
Presentation presentation = new Presentation();
try
{
	IChart chart = presentation.getSlides().get_Item(0).getShapes().addChart(ChartType.Doughnut, 50, 50, 400, 400);
	chart.getChartData().getSeriesGroups().get_Item(0).setDoughnutHoleSize((byte) 90);
	// Präsentation auf Diskette schreiben
	presentation.save(dataDir + "DoughnutHoleSize_out.pptx", SaveFormat.Pptx);
}
finally
{
	if (presentation != null) presentation.dispose();
}
```

## Abschluss

 In diesem Tutorial haben Sie gelernt, wie Sie mit Aspose.Slides für Java ein Donut-Diagramm mit einem Loch erstellen. Sie können die Größe des Lochs anpassen, indem Sie anpassen`setDoughnutHoleSize` Methodenparameter.

## FAQs

### Wie kann ich die Farbe der Diagrammsegmente ändern?

 Um die Farbe der Diagrammsegmente zu ändern, können Sie die verwenden`setDataPointsInLegend` Methode auf der`IChart` Objekt und stellen Sie für jeden Datenpunkt die gewünschte Farbe ein.

### Kann ich den Ringdiagrammsegmenten Beschriftungen hinzufügen?

 Ja, Sie können Beschriftungen zu den Donut-Diagrammsegmenten hinzufügen, indem Sie die verwenden`setDataPointsLabelValue` Methode auf der`IChart` Objekt.

### Ist es möglich, dem Diagramm einen Titel hinzuzufügen?

 Sicherlich! Mit können Sie dem Diagramm einen Titel hinzufügen`setTitle` Methode auf der`IChart` Objekt und Bereitstellung des gewünschten Titeltextes.