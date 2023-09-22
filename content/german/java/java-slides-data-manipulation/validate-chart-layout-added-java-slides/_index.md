---
title: Diagrammlayout validieren, das in Java-Folien hinzugefügt wurde
linktitle: Diagrammlayout validieren, das in Java-Folien hinzugefügt wurde
second_title: Aspose.Slides Java PowerPoint-Verarbeitungs-API
description: Validierung des Masterdiagramm-Layouts in PowerPoint mit Aspose.Slides für Java. Erfahren Sie, wie Sie Diagramme programmgesteuert bearbeiten, um beeindruckende Präsentationen zu erzielen.
type: docs
weight: 10
url: /de/java/data-manipulation/validate-chart-layout-added-java-slides/
---

## Einführung in die Validierung des Diagrammlayouts in Aspose.Slides für Java

In diesem Tutorial erfahren Sie, wie Sie das Diagrammlayout in einer PowerPoint-Präsentation mit Aspose.Slides für Java validieren. Mit dieser Bibliothek können Sie programmgesteuert mit PowerPoint-Präsentationen arbeiten und so verschiedene Elemente, einschließlich Diagramme, einfach bearbeiten und validieren.

## Schritt 1: Initialisierung der Präsentation

 Zuerst müssen wir ein Präsentationsobjekt initialisieren und eine vorhandene PowerPoint-Präsentation laden. Ersetzen`"Your Document Directory"` mit dem tatsächlichen Pfad zu Ihrer Präsentationsdatei (`test.pptx` in diesem Beispiel).

```java
// Der Pfad zum Dokumentenverzeichnis.
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "test.pptx");
```

## Schritt 2: Hinzufügen eines Diagramms

 Als Nächstes fügen wir der Präsentation ein Diagramm hinzu. In diesem Beispiel fügen wir ein gruppiertes Säulendiagramm hinzu, aber Sie können das ändern`ChartType` wie benötigt.

```java
Chart chart = (Chart) pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 100, 100, 500, 350);
```

## Schritt 3: Validieren des Diagrammlayouts

 Jetzt validieren wir das Diagrammlayout mithilfe von`validateChartLayout()` Methode. Dadurch wird sichergestellt, dass das Diagramm innerhalb der Folie ordnungsgemäß angeordnet ist.

```java
chart.validateChartLayout();
```

## Schritt 4: Diagrammposition und -größe abrufen

Nach der Validierung des Diagrammlayouts möchten Sie möglicherweise Informationen zu seiner Position und Größe abrufen. Wir können die tatsächlichen X- und Y-Koordinaten sowie die Breite und Höhe des Diagrammbereichs ermitteln.

```java
double x = chart.getPlotArea().getActualX();
double y = chart.getPlotArea().getActualY();
double w = chart.getPlotArea().getActualWidth();
double h = chart.getPlotArea().getActualHeight();
```

## Schritt 5: Speichern der Präsentation

 Vergessen Sie abschließend nicht, die geänderte Präsentation zu speichern. In diesem Beispiel speichern wir es unter`Result.pptx`, aber Sie können bei Bedarf einen anderen Dateinamen angeben.

```java
pres.save(dataDir + "Result.pptx", SaveFormat.Pptx);
```

## Vollständiger Quellcode für Validate Chart Layout in Java Slides hinzugefügt

```java
// Der Pfad zum Dokumentenverzeichnis.
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "test.pptx");
try
{
	Chart chart = (Chart) pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 100, 100, 500, 350);
	chart.validateChartLayout();
	double x = chart.getPlotArea().getActualX();
	double y = chart.getPlotArea().getActualY();
	double w = chart.getPlotArea().getActualWidth();
	double h = chart.getPlotArea().getActualHeight();
	// Präsentation speichern
	pres.save(dataDir + "Result.pptx", SaveFormat.Pptx);
}
finally
{
	if (pres != null) pres.dispose();
}
```

## Abschluss

In diesem Tutorial sind wir in die Welt der Arbeit mit Diagrammen in PowerPoint-Präsentationen mithilfe von Aspose.Slides für Java eingetaucht. Wir haben die wesentlichen Schritte zum Validieren des Diagrammlayouts, zum Abrufen seiner Position und Größe und zum Speichern der geänderten Präsentation behandelt. Hier ist eine kurze Zusammenfassung:

## FAQs

### Wie ändere ich den Diagrammtyp?

 Um den Diagrammtyp zu ändern, ersetzen Sie ihn einfach`ChartType.ClusteredColumn` mit dem gewünschten Diagrammtyp im`addChart()` Methode.

### Kann ich die Diagrammdaten anpassen?

Ja, Sie können die Diagrammdaten anpassen, indem Sie Datenreihen, Kategorien und Werte hinzufügen und ändern. Weitere Informationen finden Sie in der Aspose.Slides-Dokumentation.

### Was passiert, wenn ich andere Diagrammeigenschaften ändern möchte?

Sie können auf verschiedene Diagrammeigenschaften zugreifen und diese entsprechend Ihren Anforderungen anpassen. Umfassende Informationen zur Diagrammmanipulation finden Sie in der Aspose.Slides-Dokumentation.
