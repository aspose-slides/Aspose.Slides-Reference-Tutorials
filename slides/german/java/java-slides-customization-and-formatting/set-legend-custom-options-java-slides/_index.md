---
title: Festlegen benutzerdefinierter Legendenoptionen in Java-Folien
linktitle: Festlegen benutzerdefinierter Legendenoptionen in Java-Folien
second_title: Aspose.Slides Java PowerPoint-Verarbeitungs-API
description: Erfahren Sie, wie Sie mit Aspose.Slides für Java benutzerdefinierte Legendenoptionen in Java Slides festlegen. Passen Sie die Position und Größe der Legende in Ihren PowerPoint-Diagrammen an.
weight: 14
url: /de/java/customization-and-formatting/set-legend-custom-options-java-slides/
---

{< blocks/products/pf/main-wrap-class >}
{< blocks/products/pf/main-container >}
{< blocks/products/pf/tutorial-page-section >}


## Einführung in das Festlegen benutzerdefinierter Legendenoptionen in Java-Folien

In diesem Tutorial zeigen wir, wie Sie die Legendeneigenschaften eines Diagramms in einer PowerPoint-Präsentation mit Aspose.Slides für Java anpassen. Sie können die Position, Größe und andere Attribute der Legende an Ihre Präsentationsanforderungen anpassen.

## Voraussetzungen

Bevor Sie beginnen, stellen Sie sicher, dass Sie über Folgendes verfügen:

- Aspose.Slides für Java API installiert.
- Java-Entwicklungsumgebung eingerichtet.

## Schritt 1: Benötigte Klassen importieren:

```java
// Aspose.Slides für Java-Klassen importieren
import com.aspose.slides.*;
```

## Schritt 2: Geben Sie den Pfad zu Ihrem Dokumentverzeichnis an:

```java
String dataDir = "Your Document Directory";
```

##  Schritt 3: Erstellen Sie eine Instanz des`Presentation` class:

```java
Presentation presentation = new Presentation();
```

## Schritt 4: Fügen Sie der Präsentation eine Folie hinzu:

```java
try {
    ISlide slide = presentation.getSlides().get_Item(0);
```

## Schritt 5: Fügen Sie der Folie ein gruppiertes Säulendiagramm hinzu:

```java
    IChart chart = slide.getShapes().addChart(ChartType.ClusteredColumn, 50, 50, 500, 500);
```

## Schritt 6. Legendeneigenschaften festlegen:

- Legen Sie die X-Position der Legende fest (relativ zur Diagrammbreite):

```java
chart.getLegend().setX(50 / chart.getWidth());
```

- Legen Sie die Y-Position der Legende fest (relativ zur Diagrammhöhe):

```java
chart.getLegend().setY(50 / chart.getHeight());
```

- Legen Sie die Breite der Legende fest (relativ zur Diagrammbreite):

```java
chart.getLegend().setWidth(100 / chart.getWidth());
```

- Legen Sie die Höhe der Legende fest (relativ zur Diagrammhöhe):

```java
chart.getLegend().setHeight(100 / chart.getHeight());
```

## Schritt 7: Speichern Sie die Präsentation auf der Festplatte:

```java
    presentation.save(dataDir + "Legend_out.pptx", SaveFormat.Pptx);
} finally {
    if (presentation != null) presentation.dispose();
}
```

Das ist es! Sie haben die Legendeneigenschaften eines Diagramms in einer PowerPoint-Präsentation mit Aspose.Slides für Java erfolgreich angepasst.

## Vollständiger Quellcode für benutzerdefinierte Legendenoptionen in Java-Folien

```java
// Der Pfad zum Dokumentverzeichnis.
String dataDir = "Your Document Directory";
// Erstellen Sie eine Instanz der Präsentationsklasse
Presentation presentation = new Presentation();
try
{
	// Referenz der Folie erhalten
	ISlide slide = presentation.getSlides().get_Item(0);
	// Fügen Sie auf der Folie ein gruppiertes Säulendiagramm hinzu
	IChart chart = slide.getShapes().addChart(ChartType.ClusteredColumn, 50, 50, 500, 500);
	// Festlegen der Legendeneigenschaften
	chart.getLegend().setX(50 / chart.getWidth());
	chart.getLegend().setY(50 / chart.getHeight());
	chart.getLegend().setWidth(100 / chart.getWidth());
	chart.getLegend().setHeight(100 / chart.getHeight());
	// Präsentation auf Festplatte schreiben
	presentation.save(dataDir + "Legend_out.pptx", SaveFormat.Pptx);
}
finally
{
	if (presentation != null) presentation.dispose();
}
```
## Abschluss

In diesem Tutorial haben wir gelernt, wie man die Legendeneigenschaften eines Diagramms in einer PowerPoint-Präsentation mit Aspose.Slides für Java anpasst. Sie können die Position, Größe und andere Attribute der Legende ändern, um optisch ansprechende und informative Präsentationen zu erstellen.

## Häufig gestellte Fragen

## Wie kann ich die Position der Legende ändern?

 Um die Position der Legende zu ändern, verwenden Sie die`setX` Und`setY` Methoden des Legendenobjekts. Die Werte werden relativ zur Breite und Höhe des Diagramms angegeben.

## Wie kann ich die Größe der Legende anpassen?

 Sie können die Größe der Legende anpassen, indem Sie`setWidth` Und`setHeight` Methoden des Legendenobjekts. Diese Werte sind ebenfalls relativ zur Breite und Höhe des Diagramms.

## Kann ich andere Legendenattribute anpassen?

Ja, Sie können verschiedene Attribute der Legende anpassen, z. B. Schriftstil, Rahmen, Hintergrundfarbe und mehr. Detaillierte Informationen zum weiteren Anpassen von Legenden finden Sie in der Aspose.Slides-Dokumentation.
{< /blocks/products/pf/tutorial-page-section >}

{< /blocks/products/pf/main-container >}
{< /blocks/products/pf/main-wrap-class >}

{< blocks/products/products-backtop-button >}
