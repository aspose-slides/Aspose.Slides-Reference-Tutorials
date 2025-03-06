---
title: Animieren von Serien in Java-Folien
linktitle: Animieren von Serien in Java-Folien
second_title: Aspose.Slides Java PowerPoint-Verarbeitungs-API
description: Optimieren Sie Ihre Präsentationen mit Serienanimationen in Aspose.Slides für Java. Folgen Sie unserer Schritt-für-Schritt-Anleitung mit Quellcodebeispielen, um ansprechende PowerPoint-Animationen zu erstellen.
weight: 11
url: /de/java/animation-and-layout/animating-series-java-slides/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}


## Einführung in die Animation von Serien in Aspose.Slides für Java

In dieser Anleitung führen wir Sie durch den Prozess der Animation von Serien in Java-Folien mithilfe der Aspose.Slides für Java API. Mit dieser Bibliothek können Sie programmgesteuert mit PowerPoint-Präsentationen arbeiten.

## Voraussetzungen

Bevor wir beginnen, stellen Sie sicher, dass die folgenden Voraussetzungen erfüllt sind:

- Aspose.Slides für die Java-Bibliothek.
- Java-Entwicklungsumgebung eingerichtet.

## Schritt 1: Laden Sie die Präsentation

 Zuerst müssen wir eine vorhandene PowerPoint-Präsentation laden, die ein Diagramm enthält. Ersetzen Sie`"Your Document Directory"` durch den tatsächlichen Pfad zu Ihrer Präsentationsdatei.

```java
// Der Pfad zum Dokumentverzeichnis.
String dataDir = "Your Document Directory";
// Instanziieren Sie die Präsentationsklasse, die eine Präsentationsdatei darstellt
Presentation presentation = new Presentation(dataDir + "ExistingChart.pptx");
```

## Schritt 2: Zugriff auf das Diagramm

Als Nächstes greifen wir auf das Diagramm innerhalb der Präsentation zu. In diesem Beispiel gehen wir davon aus, dass sich das Diagramm auf der ersten Folie befindet und die erste Form auf dieser Folie darstellt.

```java
// Referenz zum Chart-Objekt abrufen
ISlide slide = presentation.getSlides().get_Item(0);
IShapeCollection shapes = slide.getShapes();
IChart chart = (IChart) shapes.get_Item(0);
```

## Schritt 3: Animationen hinzufügen

Fügen wir nun den Reihen im Diagramm Animationen hinzu. Wir verwenden einen Einblendeffekt und lassen jede Reihe nacheinander erscheinen.

```java
// Animieren Sie das gesamte Diagramm
slide.getTimeline().getMainSequence().addEffect(chart, EffectType.Fade, EffectSubtype.None, EffectTriggerType.AfterPrevious);

// Fügen Sie jeder Serie Animationen hinzu (vorausgesetzt, es gibt 4 Serien)
for (int i = 0; i < 4; i++) {
    ((Sequence) slide.getTimeline().getMainSequence()).addEffect(chart,
            EffectChartMajorGroupingType.BySeries, i,
            EffectType.Appear, EffectSubtype.None, EffectTriggerType.AfterPrevious);
}
```

Im obigen Code verwenden wir einen Einblendeffekt für das gesamte Diagramm und fügen anschließend in einer Schleife nacheinander jeder Reihe einen „Erscheinen“-Effekt hinzu.

## Schritt 4: Speichern Sie die Präsentation

Speichern Sie abschließend die geänderte Präsentation auf der Festplatte.

```java
presentation.save(dataDir + "AnimatingSeries_out.pptx", SaveFormat.Pptx);
```

## Vollständiger Quellcode zum Animieren von Serien in Aspose.Slides für Java

```java
// Der Pfad zum Dokumentverzeichnis.
String dataDir = "Your Document Directory";
// Instanziieren Sie die Präsentationsklasse, die eine Präsentationsdatei darstellt
Presentation presentation = new Presentation(dataDir + "ExistingChart.pptx");
try
{
	// Referenz des Diagrammobjekts abrufen
	ISlide slide = presentation.getSlides().get_Item(0);
	IShapeCollection shapes = slide.getShapes();
	IChart chart = (IChart) shapes.get_Item(0);
	// Animieren Sie die Serie
	slide.getTimeline().getMainSequence().addEffect(chart, EffectType.Fade, EffectSubtype.None,
			EffectTriggerType.AfterPrevious);
	((Sequence) slide.getTimeline().getMainSequence()).addEffect(chart,
			EffectChartMajorGroupingType.BySeries, 0,
			EffectType.Appear, EffectSubtype.None, EffectTriggerType.AfterPrevious);
	((Sequence) slide.getTimeline().getMainSequence()).addEffect(chart,
			EffectChartMajorGroupingType.BySeries, 1,
			EffectType.Appear, EffectSubtype.None, EffectTriggerType.AfterPrevious);
	((Sequence) slide.getTimeline().getMainSequence()).addEffect(chart,
			EffectChartMajorGroupingType.BySeries, 2,
			EffectType.Appear, EffectSubtype.None, EffectTriggerType.AfterPrevious);
	((Sequence) slide.getTimeline().getMainSequence()).addEffect(chart,
			EffectChartMajorGroupingType.BySeries, 3,
			EffectType.Appear, EffectSubtype.None, EffectTriggerType.AfterPrevious);
	// Schreiben Sie die geänderte Präsentation auf die Festplatte
	presentation.save(dataDir + "AnimatingSeries_out.pptx", SaveFormat.Pptx);
}
finally
{
	if (presentation != null) presentation.dispose();
}
```

## Abschluss

Sie haben mit Aspose.Slides für Java erfolgreich Serien in einem PowerPoint-Diagramm animiert. Dadurch können Sie Ihre Präsentationen ansprechender und optisch ansprechender gestalten. Entdecken Sie weitere Animationsoptionen und optimieren Sie Ihre Präsentationen nach Bedarf.

## Häufig gestellte Fragen

### Wie steuere ich die Reihenfolge von Serienanimationen?

 Um die Reihenfolge der Serienanimationen zu steuern, verwenden Sie die`EffectTriggerType.AfterPrevious` Parameter beim Hinzufügen der Effekte. Dadurch wird jede Serienanimation gestartet, nachdem die vorherige beendet ist.

### Kann ich für jede Serie unterschiedliche Animationen verwenden?

 Ja, Sie können für jede Serie unterschiedliche Animationen verwenden, indem Sie unterschiedliche`EffectType` Und`EffectSubtype` Werte beim Hinzufügen von Effekten.

### Was ist, wenn meine Präsentation mehr als vier Serien umfasst?

Sie können die Schleife in Schritt 3 erweitern, um Animationen für alle Reihen in Ihrem Diagramm hinzuzufügen. Passen Sie einfach die Bedingung der Schleife entsprechend an.

### Wie kann ich die Dauer und Verzögerung der Animation anpassen?

Sie können die Dauer und Verzögerung der Animation anpassen, indem Sie Eigenschaften für die Animationseffekte festlegen. Weitere Informationen zu den verfügbaren Anpassungsoptionen finden Sie in der Dokumentation zu Aspose.Slides für Java.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
