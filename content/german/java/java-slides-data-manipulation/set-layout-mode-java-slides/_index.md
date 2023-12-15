---
title: Legen Sie den Layoutmodus in Java-Folien fest
linktitle: Legen Sie den Layoutmodus in Java-Folien fest
second_title: Aspose.Slides Java PowerPoint-Verarbeitungs-API
description: Erfahren Sie, wie Sie mit Aspose.Slides Layoutmodi für Java-Folien festlegen. Passen Sie die Diagrammpositionierung und -größe in dieser Schritt-für-Schritt-Anleitung mit Quellcode an.
type: docs
weight: 23
url: /de/java/data-manipulation/set-layout-mode-java-slides/
---

## Einführung in das Festlegen des Layoutmodus in Java-Folien

In diesem Tutorial erfahren Sie, wie Sie mit Aspose.Slides für Java den Layoutmodus für ein Diagramm in Java-Folien festlegen. Der Layoutmodus bestimmt die Positionierung und Größe des Diagramms innerhalb der Folie.

## Voraussetzungen

 Bevor wir beginnen, stellen Sie sicher, dass die Aspose.Slides for Java-Bibliothek in Ihrem Java-Projekt installiert und eingerichtet ist. Sie können die Bibliothek herunterladen unter[Hier](https://releases.aspose.com/slides/java/).

## Schritt 1: Erstellen Sie eine Präsentation

Zuerst müssen wir eine neue Präsentation erstellen.

```java
String dataDir = "Your Document Directory";
Presentation presentation = new Presentation();
```

## Schritt 2: Fügen Sie eine Folie und ein Diagramm hinzu

Als nächstes fügen wir eine Folie und ein Diagramm hinzu. In diesem Beispiel erstellen wir ein gruppiertes Säulendiagramm.

```java
ISlide slide = presentation.getSlides().get_Item(0);
IChart chart = slide.getShapes().addChart(ChartType.ClusteredColumn, 20, 100, 600, 400);
```

## Schritt 3: Legen Sie das Diagrammlayout fest

 Legen wir nun das Layout für das Diagramm fest. Wir passen die Position und Größe des Diagramms innerhalb der Folie mithilfe von an`setX`, `setY`, `setWidth`, `setHeight` Methoden. Zusätzlich werden wir die festlegen`LayoutTargetType` um den Layoutmodus zu bestimmen.

```java
chart.getPlotArea().setX(0.2f);
chart.getPlotArea().setY(0.2f);
chart.getPlotArea().setWidth(0.7f);
chart.getPlotArea().setHeight(0.7f);
chart.getPlotArea().setLayoutTargetType(LayoutTargetType.Inner);
```

In diesem Beispiel haben wir den Layout-Zieltyp des Diagramms auf „Inner“ festgelegt, was bedeutet, dass es relativ zum inneren Bereich der Folie positioniert und in seiner Größe positioniert wird.

## Schritt 4: Speichern Sie die Präsentation

Abschließend speichern wir die Präsentation mit den Diagrammlayouteinstellungen.

```java
presentation.save(dataDir + "SetLayoutMode_outer.pptx", SaveFormat.Pptx);
```

## Vollständiger Quellcode für den Set-Layout-Modus in Java-Folien

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

 In diesem Tutorial haben wir gelernt, wie man mit Aspose.Slides für Java den Layoutmodus für ein Diagramm in Java-Folien festlegt. Sie können die Position und Größe des Diagramms entsprechend Ihren spezifischen Anforderungen anpassen, indem Sie die Werte im anpassen`setX`, `setY`, `setWidth`, `setHeight` , Und`setLayoutTargetType`Methoden. Dadurch haben Sie die Kontrolle über die Platzierung von Diagrammen in Ihren Folien.

## FAQs

### Wie ändere ich den Layoutmodus für ein Diagramm in Aspose.Slides für Java?

 Um den Layoutmodus für ein Diagramm in Aspose.Slides für Java zu ändern, können Sie Folgendes verwenden`setLayoutTargetType` Methode auf dem Plotbereich des Diagramms. Sie können es auf beides einstellen`LayoutTargetType.Inner` oder`LayoutTargetType.Outer` je nach gewünschtem Layout.

### Kann ich die Position und Größe des Diagramms innerhalb der Folie anpassen?

 Ja, Sie können die Position und Größe des Diagramms innerhalb der Folie mithilfe von anpassen`setX`, `setY`, `setWidth` , Und`setHeight` Methoden im Plotbereich des Diagramms. Passen Sie diese Werte an, um das Diagramm entsprechend Ihren Anforderungen zu positionieren und zu vergrößern.

### Wo finde ich weitere Informationen zu Aspose.Slides für Java?

 Weitere Informationen zu Aspose.Slides für Java finden Sie im[Dokumentation](https://reference.aspose.com/slides/java/). Es enthält detaillierte API-Referenzen und Beispiele, die Ihnen helfen, effektiv mit Folien und Diagrammen in Java zu arbeiten.