---
title: Fehlerbalken in Java-Folien hinzufügen
linktitle: Fehlerbalken in Java-Folien hinzufügen
second_title: Aspose.Slides Java PowerPoint-Verarbeitungs-API
description: Erfahren Sie, wie Sie mit Aspose.Slides in Java Fehlerbalken zu PowerPoint-Diagrammen hinzufügen. Schritt-für-Schritt-Anleitung mit Quellcode zum Anpassen von Fehlerbalken.
weight: 13
url: /de/java/chart-data-manipulation/add-error-bars-java-slides/
---

{< blocks/products/pf/main-wrap-class >}
{< blocks/products/pf/main-container >}
{< blocks/products/pf/tutorial-page-section >}


## Einführung in das Hinzufügen von Fehlerbalken in Java-Folien mit Aspose.Slides

In diesem Tutorial zeigen wir, wie Sie mit Aspose.Slides für Java Fehlerbalken zu einem Diagramm in einer PowerPoint-Folie hinzufügen. Fehlerbalken liefern wertvolle Informationen über die Variabilität oder Unsicherheit von Datenpunkten in einem Diagramm. Wir erstellen ein Blasendiagramm und fügen ihm Fehlerbalken hinzu. Fangen wir an!

## Voraussetzungen

Bevor Sie beginnen, stellen Sie sicher, dass Sie die Bibliothek Aspose.Slides für Java in Ihrem Java-Projekt installiert und eingerichtet haben. Sie können die Bibliothek von der[Aspose-Website](https://downloads.aspose.com/slides/java).

## Schritt 1: Erstellen Sie eine leere Präsentation

```java
// Der Pfad zum Dokumentverzeichnis.
String dataDir = "Your Document Directory";
// Leere Präsentation erstellen
Presentation presentation = new Presentation();
```

In diesem Schritt erstellen wir eine leere Präsentation, in die wir unser Diagramm mit Fehlerbalken einfügen.

## Schritt 2: Erstellen Sie ein Blasendiagramm

```java
// Erstellen eines Blasendiagramms
IChart chart = presentation.getSlides().get_Item(0).getShapes().addChart(ChartType.Bubble, 50, 50, 400, 300, true);
```

Hier erstellen wir ein Blasendiagramm und geben seine Position und Abmessungen auf der Folie an.

## Schritt 3: Fehlerbalken hinzufügen und Format festlegen

```java
// Fehlerbalken hinzufügen und ihr Format festlegen
IErrorBarsFormat errBarX = chart.getChartData().getSeries().get_Item(0).getErrorBarsXFormat();
IErrorBarsFormat errBarY = chart.getChartData().getSeries().get_Item(0).getErrorBarsYFormat();
errBarX.setVisible(true);
errBarY.setVisible(true);
errBarX.setValueType(ErrorBarValueType.Fixed);
errBarX.setValue(0.1f);
errBarY.setValueType(ErrorBarValueType.Percentage);
errBarY.setValue(5);
errBarX.setType(ErrorBarType.Plus);
errBarY.getFormat().getLine().setWidth(2);
errBarX.setEndCap(true);
```

In diesem Schritt fügen wir dem Diagramm Fehlerbalken hinzu und legen ihr Format fest. Sie können Fehlerbalken anpassen, indem Sie Werte, Typen und andere Eigenschaften ändern.

- `errBarX` stellt Fehlerbalken entlang der X-Achse dar.
- `errBarY` stellt Fehlerbalken entlang der Y-Achse dar.
- Wir machen sowohl X- als auch Y-Fehlerbalken sichtbar.
- `setValueType` Gibt den Wertetyp für Fehlerbalken an (z. B. „Fest“ oder „Prozentsatz“).
- `setValue` legt den Wert für Fehlerbalken fest.
- `setType` definiert die Art der Fehlerbalken (z. B. Plus oder Minus).
-  Wir setzen die Breite der Fehlerbalkenlinien mit`getFormat().getLine().setWidth(2)`.
- `setEndCap`Gibt an, ob die Fehlerbalken mit Endkappen versehen werden sollen.

## Schritt 4: Speichern Sie die Präsentation

```java
// Präsentation speichern
presentation.save(dataDir + "ErrorBars_out.pptx", SaveFormat.Pptx);
```

Abschließend speichern wir die Präsentation mit den hinzugefügten Fehlerbalken an einem angegebenen Ort.

Das ist es! Sie haben mit Aspose.Slides für Java erfolgreich Fehlerbalken zu einem Diagramm in einer PowerPoint-Folie hinzugefügt.

## Vollständiger Quellcode zum Hinzufügen von Fehlerbalken in Java-Folien

```java
// Der Pfad zum Dokumentverzeichnis.
String dataDir = "Your Document Directory";
// Leere Präsentation erstellen
Presentation presentation = new Presentation();
try
{
	// Erstellen eines Blasendiagramms
	IChart chart = presentation.getSlides().get_Item(0).getShapes().addChart(ChartType.Bubble, 50, 50, 400, 300, true);
	// Fehlerbalken hinzufügen und ihr Format festlegen
	IErrorBarsFormat errBarX = chart.getChartData().getSeries().get_Item(0).getErrorBarsXFormat();
	IErrorBarsFormat errBarY = chart.getChartData().getSeries().get_Item(0).getErrorBarsYFormat();
	errBarX.setVisible(true);
	errBarY.setVisible(true);
	errBarX.setValueType(ErrorBarValueType.Fixed);
	errBarX.setValue(0.1f);
	errBarY.setValueType(ErrorBarValueType.Percentage);
	errBarY.setValue(5);
	errBarX.setType(ErrorBarType.Plus);
	errBarY.getFormat().getLine().setWidth(2);
	errBarX.setEndCap(true);
	// Präsentation speichern
	presentation.save(dataDir + "ErrorBars_out.pptx", SaveFormat.Pptx);
}
finally
{
	if (presentation != null) presentation.dispose();
}
```

## Abschluss

In diesem Tutorial haben wir untersucht, wie Sie Ihre PowerPoint-Präsentationen verbessern können, indem Sie mit Aspose.Slides für Java Fehlerbalken zu Diagrammen hinzufügen. Fehlerbalken bieten wertvolle Einblicke in Datenvariabilität und -unsicherheiten und machen Ihre Präsentationen informativer und optisch ansprechender.

## Häufig gestellte Fragen

### Wie kann ich die Darstellung von Fehlerbalken weiter anpassen?

Sie können Fehlerbalken anpassen, indem Sie ihre Eigenschaften wie Linienstil, Farbe und Breite ändern, wie in Schritt 3 gezeigt.

### Kann ich verschiedenen Diagrammtypen Fehlerbalken hinzufügen?

Ja, Sie können Fehlerbalken zu verschiedenen Diagrammtypen hinzufügen, die von Aspose.Slides für Java unterstützt werden. Erstellen Sie einfach den gewünschten Diagrammtyp und befolgen Sie die gleichen Schritte zur Anpassung der Fehlerbalken.

### Wie kann ich die Position und Größe des Diagramms auf der Folie anpassen?

 Sie können die Position und die Abmessungen des Diagramms steuern, indem Sie die Parameter im`addChart` Methode, wie in Schritt 2 gezeigt.

### Wo finde ich weitere Informationen zu Aspose.Slides für Java?

 Weitere Informationen finden Sie im[Aspose.Slides für Java-Dokumentation](https://reference.aspose.com/slides/java/) für detaillierte Informationen zur Benutzung der Bibliothek.
{< /blocks/products/pf/tutorial-page-section >}

{< /blocks/products/pf/main-container >}
{< /blocks/products/pf/main-wrap-class >}

{< blocks/products/products-backtop-button >}
