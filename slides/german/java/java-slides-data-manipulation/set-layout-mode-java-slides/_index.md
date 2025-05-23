---
"description": "Erfahren Sie, wie Sie mit Aspose.Slides Layoutmodi für Java-Folien festlegen. Passen Sie die Positionierung und Größe von Diagrammen in dieser Schritt-für-Schritt-Anleitung mit Quellcode an."
"linktitle": "Layoutmodus in Java-Folien festlegen"
"second_title": "Aspose.Slides Java PowerPoint-Verarbeitungs-API"
"title": "Layoutmodus in Java-Folien festlegen"
"url": "/de/java/data-manipulation/set-layout-mode-java-slides/"
"weight": 23
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Layoutmodus in Java-Folien festlegen


## Einführung in den Set-Layout-Modus in Java Slides

In diesem Tutorial lernen wir, wie man den Layoutmodus für ein Diagramm in Java-Folien mit Aspose.Slides für Java einstellt. Der Layoutmodus bestimmt die Positionierung und Größe des Diagramms innerhalb der Folie.

## Voraussetzungen

Bevor wir beginnen, stellen Sie sicher, dass die Bibliothek Aspose.Slides für Java in Ihrem Java-Projekt installiert und eingerichtet ist. Sie können die Bibliothek herunterladen von [Hier](https://releases.aspose.com/slides/java/).

## Schritt 1: Erstellen Sie eine Präsentation

Zuerst müssen wir eine neue Präsentation erstellen.

```java
String dataDir = "Your Document Directory";
Presentation presentation = new Presentation();
```

## Schritt 2: Folie und Diagramm hinzufügen

Als Nächstes fügen wir eine Folie und ein Diagramm hinzu. In diesem Beispiel erstellen wir ein gruppiertes Säulendiagramm.

```java
ISlide slide = presentation.getSlides().get_Item(0);
IChart chart = slide.getShapes().addChart(ChartType.ClusteredColumn, 20, 100, 600, 400);
```

## Schritt 3: Diagrammlayout festlegen

Nun legen wir das Layout für das Diagramm fest. Wir passen die Position und Größe des Diagramms innerhalb der Folie mithilfe der `setX`, `setY`, `setWidth`, `setHeight` Methoden. Zusätzlich werden wir die `LayoutTargetType` um den Layoutmodus zu bestimmen.

```java
chart.getPlotArea().setX(0.2f);
chart.getPlotArea().setY(0.2f);
chart.getPlotArea().setWidth(0.7f);
chart.getPlotArea().setHeight(0.7f);
chart.getPlotArea().setLayoutTargetType(LayoutTargetType.Inner);
```

In diesem Beispiel haben wir den Layoutzieltyp des Diagramms auf „Inner“ eingestellt, was bedeutet, dass es relativ zum inneren Bereich der Folie positioniert und skaliert wird.

## Schritt 4: Speichern Sie die Präsentation

Abschließend speichern wir die Präsentation mit den Diagrammlayouteinstellungen.

```java
presentation.save(dataDir + "SetLayoutMode_outer.pptx", SaveFormat.Pptx);
```

## Vollständiger Quellcode zum Festlegen des Layoutmodus in Java-Folien

```java
String dataDir = "Your Document Directory";
Presentation presentation = new Presentation();
try
{
	ISlide slide = presentation.getSlides().get_Item(0);
	IChart chart = slide.getShapes().addChart(ChartType.ClusteredColumn, 20, 100, 600, 400);
	chart.getPlotArea().setX(0.2f);
	chart.getPlotArea().setY(0.2f);
	chart.getPlotArea().setWidth(0.7f);
	chart.getPlotArea().setHeight(0.7f);
	chart.getPlotArea().setLayoutTargetType(LayoutTargetType.Inner);
	presentation.save(dataDir + "SetLayoutMode_outer.pptx", SaveFormat.Pptx);
}
finally
{
	if (presentation != null) presentation.dispose();
}
```

## Abschluss

In diesem Tutorial haben wir gelernt, wie man den Layoutmodus für ein Diagramm in Java-Folien mit Aspose.Slides für Java einstellt. Sie können die Position und Größe des Diagramms Ihren spezifischen Anforderungen entsprechend anpassen, indem Sie die Werte in der `setX`, `setY`, `setWidth`, `setHeight`, Und `setLayoutTargetType` Methoden. Dadurch haben Sie Kontrolle über die Platzierung der Diagramme auf Ihren Folien.

## Häufig gestellte Fragen

### Wie ändere ich den Layoutmodus für ein Diagramm in Aspose.Slides für Java?

Um den Layoutmodus für ein Diagramm in Aspose.Slides für Java zu ändern, können Sie die `setLayoutTargetType` Methode auf dem Diagrammbereich. Sie können es entweder auf `LayoutTargetType.Inner` oder `LayoutTargetType.Outer` abhängig von Ihrem gewünschten Layout.

### Kann ich die Position und Größe des Diagramms innerhalb der Folie anpassen?

Ja, Sie können die Position und Größe des Diagramms innerhalb der Folie anpassen, indem Sie die `setX`, `setY`, `setWidth`, Und `setHeight` Methoden im Diagrammbereich. Passen Sie diese Werte an, um das Diagramm entsprechend Ihren Anforderungen zu positionieren und zu skalieren.

### Wo finde ich weitere Informationen zu Aspose.Slides für Java?

Weitere Informationen zu Aspose.Slides für Java finden Sie in der [Dokumentation](https://reference.aspose.com/slides/java/). Es enthält detaillierte API-Referenzen und Beispiele, die Ihnen helfen, effektiv mit Folien und Diagrammen in Java zu arbeiten.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}