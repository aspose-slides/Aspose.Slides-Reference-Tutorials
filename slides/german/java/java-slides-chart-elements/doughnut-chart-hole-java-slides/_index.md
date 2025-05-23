---
"description": "Erstellen Sie Ringdiagramme mit benutzerdefinierten Lochgrößen in Java Slides mit Aspose.Slides für Java. Schritt-für-Schritt-Anleitung mit Quellcode zur Diagrammanpassung."
"linktitle": "Donut-Diagrammloch in Java-Folien"
"second_title": "Aspose.Slides Java PowerPoint-Verarbeitungs-API"
"title": "Donut-Diagrammloch in Java-Folien"
"url": "/de/java/chart-elements/doughnut-chart-hole-java-slides/"
"weight": 11
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Donut-Diagrammloch in Java-Folien


## Einführung in das Donut-Diagramm mit einem Loch in Java-Folien

In diesem Tutorial führen wir Sie durch die Erstellung eines Ringdiagramms mit einem Loch mit Aspose.Slides für Java. Diese Schritt-für-Schritt-Anleitung führt Sie mit Quellcodebeispielen durch den Prozess.

## Voraussetzungen

Bevor Sie beginnen, stellen Sie sicher, dass die Bibliothek Aspose.Slides für Java in Ihrem Java-Projekt installiert und eingerichtet ist. Sie können sie von der [Aspose.Slides für Java-Dokumentation](https://reference.aspose.com/slides/java/).

## Schritt 1: Importieren Sie die erforderlichen Bibliotheken

```java
import com.aspose.slides.ChartType;
import com.aspose.slides.IChart;
import com.aspose.slides.Presentation;
import com.aspose.slides.SaveFormat;
```

## Schritt 2: Initialisieren der Präsentation

```java
// Der Pfad zum Dokumentenverzeichnis.
String dataDir = "Your Document Directory";

// Erstellen Sie eine Instanz der Präsentationsklasse
Presentation presentation = new Presentation();
```

## Schritt 3: Erstellen Sie das Ringdiagramm

```java
try {
    // Erstellen Sie auf der ersten Folie ein Ringdiagramm
    IChart chart = presentation.getSlides().get_Item(0).getShapes().addChart(ChartType.Doughnut, 50, 50, 400, 400);
    
    // Legen Sie die Größe des Lochs im Ringdiagramm fest (in Prozent).
    chart.getChartData().getSeriesGroups().get_Item(0).setDoughnutHoleSize((byte) 90);
    
    // Speichern Sie die Präsentation auf der Festplatte
    presentation.save(dataDir + "DoughnutHoleSize_out.pptx", SaveFormat.Pptx);
} finally {
    // Entsorgen Sie das Präsentationsobjekt
    if (presentation != null) presentation.dispose();
}
```

## Schritt 4: Führen Sie den Code aus

Führen Sie den Java-Code in Ihrer IDE oder Ihrem Texteditor aus, um ein Ringdiagramm mit einer bestimmten Lochgröße zu erstellen. Ersetzen Sie `"Your Document Directory"` durch den tatsächlichen Pfad, in dem Sie die Präsentation speichern möchten.

## Vollständiger Quellcode für Donut-Diagrammloch in Java-Folien

```java
// Der Pfad zum Dokumentenverzeichnis.
String dataDir = "Your Document Directory";
// Erstellen Sie eine Instanz der Präsentationsklasse
Presentation presentation = new Presentation();
try
{
	IChart chart = presentation.getSlides().get_Item(0).getShapes().addChart(ChartType.Doughnut, 50, 50, 400, 400);
	chart.getChartData().getSeriesGroups().get_Item(0).setDoughnutHoleSize((byte) 90);
	// Präsentation auf Festplatte schreiben
	presentation.save(dataDir + "DoughnutHoleSize_out.pptx", SaveFormat.Pptx);
}
finally
{
	if (presentation != null) presentation.dispose();
}
```

## Abschluss

In diesem Tutorial haben Sie gelernt, wie Sie mit Aspose.Slides für Java ein Ringdiagramm mit einem Loch erstellen. Sie können die Größe des Lochs anpassen, indem Sie die `setDoughnutHoleSize` Methodenparameter.

## Häufig gestellte Fragen

### Wie kann ich die Farbe der Diagrammsegmente ändern?

Um die Farbe der Diagrammsegmente zu ändern, können Sie die `setDataPointsInLegend` Methode auf der `IChart` Objekt und legen Sie für jeden Datenpunkt die gewünschte Farbe fest.

### Kann ich den Ringdiagrammsegmenten Beschriftungen hinzufügen?

Ja, Sie können den Ringdiagrammsegmenten Beschriftungen hinzufügen, indem Sie `setDataPointsLabelValue` Methode auf der `IChart` Objekt.

### Ist es möglich, dem Diagramm einen Titel hinzuzufügen?

Natürlich! Sie können dem Diagramm einen Titel hinzufügen, indem Sie `setTitle` Methode auf der `IChart` Objekt und Angabe des gewünschten Titeltextes.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}