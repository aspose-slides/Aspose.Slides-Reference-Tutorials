---
title: Benutzerdefinierten Fehler in Java-Folien hinzufügen
linktitle: Benutzerdefinierten Fehler in Java-Folien hinzufügen
second_title: Aspose.Slides Java PowerPoint-Verarbeitungs-API
description: Erfahren Sie, wie Sie mit Aspose.Slides benutzerdefinierte Fehlerbalken zu PowerPoint-Diagrammen in Java Slides hinzufügen. Schritt-für-Schritt-Anleitung mit Quellcode zur präzisen Datenvisualisierung.
weight: 11
url: /de/java/chart-data-manipulation/add-custom-error-java-slides/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Benutzerdefinierten Fehler in Java-Folien hinzufügen


## Einführung in das Hinzufügen benutzerdefinierter Fehlerbalken in Java-Folien mit Aspose.Slides

In diesem Tutorial erfahren Sie, wie Sie mit Aspose.Slides für Java benutzerdefinierte Fehlerbalken zu einem Diagramm in einer PowerPoint-Präsentation hinzufügen. Fehlerbalken sind nützlich, um Variabilität oder Unsicherheit in Datenpunkten in einem Diagramm anzuzeigen.

## Voraussetzungen

Bevor Sie beginnen, stellen Sie sicher, dass Sie über Folgendes verfügen:

- Aspose.Slides für die Java-Bibliothek, die in Ihrem Projekt installiert und konfiguriert ist.
- Eine Java-Entwicklungsumgebung wurde eingerichtet.

## Schritt 1: Erstellen Sie eine leere Präsentation

Erstellen Sie zunächst eine leere PowerPoint-Präsentation.

```java
// Der Pfad zum Dokumentverzeichnis.
String dataDir = "Your Document Directory";
// Leere Präsentation erstellen
Presentation presentation = new Presentation();
```

## Schritt 2: Ein Blasendiagramm hinzufügen

Als Nächstes fügen wir der Präsentation ein Blasendiagramm hinzu.

```java
// Erstellen eines Blasendiagramms
IChart chart = presentation.getSlides().get_Item(0).getShapes().addChart(ChartType.Bubble, 50, 50, 400, 300, true);
```

## Schritt 3: Benutzerdefinierte Fehlerbalken hinzufügen

Fügen wir nun der Diagrammreihe benutzerdefinierte Fehlerbalken hinzu.

```java
// Hinzufügen benutzerdefinierter Fehlerbalken und Festlegen ihres Formats
IChartSeries series = chart.getChartData().getSeries().get_Item(0);
IErrorBarsFormat errBarX = series.getErrorBarsXFormat();
IErrorBarsFormat errBarY = series.getErrorBarsYFormat();
errBarX.setVisible(true);
errBarY.setVisible(true);
errBarX.setValueType(ErrorBarValueType.Custom);
errBarY.setValueType(ErrorBarValueType.Custom);
```

## Schritt 4: Fehlerbalkendaten festlegen

In diesem Schritt greifen wir auf die Datenpunkte der Diagrammreihe zu und legen die benutzerdefinierten Fehlerbalkenwerte für jeden Punkt fest.

```java
// Auf Datenpunkte von Diagrammreihen zugreifen und Fehlerbalkenwerte für einzelne Punkte festlegen
IChartDataPointCollection points = series.getDataPoints();
points.getDataSourceTypeForErrorBarsCustomValues().setDataSourceTypeForXPlusValues(DataSourceType.DoubleLiterals);
points.getDataSourceTypeForErrorBarsCustomValues().setDataSourceTypeForXMinusValues(DataSourceType.DoubleLiterals);
points.getDataSourceTypeForErrorBarsCustomValues().setDataSourceTypeForYPlusValues(DataSourceType.DoubleLiterals);
points.getDataSourceTypeForErrorBarsCustomValues().setDataSourceTypeForYMinusValues(DataSourceType.DoubleLiterals);

// Festlegen von Fehlerbalken für Diagrammserienpunkte
for (int i = 0; i < points.size(); i++)
{
    points.get_Item(i).getErrorBarsCustomValues().getXMinus().setAsLiteralDouble(i + 1);
    points.get_Item(i).getErrorBarsCustomValues().getXPlus().setAsLiteralDouble(i + 1);
    points.get_Item(i).getErrorBarsCustomValues().getYMinus().setAsLiteralDouble(i + 1);
    points.get_Item(i).getErrorBarsCustomValues().getYPlus().setAsLiteralDouble(i + 1);
}
```

## Schritt 5: Speichern Sie die Präsentation

Speichern Sie abschließend die Präsentation mit den benutzerdefinierten Fehlerbalken.

```java
// Präsentation speichern
presentation.save(dataDir + "ErrorBarsCustomValues_out.pptx", SaveFormat.Pptx);
```

Das ist es! Sie haben mit Aspose.Slides für Java erfolgreich benutzerdefinierte Fehlerbalken zu einem Diagramm in einer PowerPoint-Präsentation hinzugefügt.

## Vollständiger Quellcode zum Hinzufügen benutzerdefinierter Fehler in Java-Folien

```java
// Der Pfad zum Dokumentverzeichnis.
String dataDir = "Your Document Directory";
// Leere Präsentation erstellen
Presentation presentation = new Presentation();
try
{
	// Erstellen eines Blasendiagramms
	IChart chart = presentation.getSlides().get_Item(0).getShapes().addChart(ChartType.Bubble, 50, 50, 400, 300, true);
	// Hinzufügen benutzerdefinierter Fehlerbalken und Festlegen ihres Formats
	IChartSeries series = chart.getChartData().getSeries().get_Item(0);
	IErrorBarsFormat errBarX = series.getErrorBarsXFormat();
	IErrorBarsFormat errBarY = series.getErrorBarsYFormat();
	errBarX.setVisible(true);
	errBarY.setVisible(true);
	errBarX.setValueType(ErrorBarValueType.Custom);
	errBarY.setValueType(ErrorBarValueType.Custom);
	// Auf Datenpunkte von Diagrammreihen zugreifen und Fehlerbalkenwerte für einzelne Punkte festlegen
	IChartDataPointCollection points = series.getDataPoints();
	points.getDataSourceTypeForErrorBarsCustomValues().setDataSourceTypeForXPlusValues(DataSourceType.DoubleLiterals);
	points.getDataSourceTypeForErrorBarsCustomValues().setDataSourceTypeForXMinusValues(DataSourceType.DoubleLiterals);
	points.getDataSourceTypeForErrorBarsCustomValues().setDataSourceTypeForYPlusValues(DataSourceType.DoubleLiterals);
	points.getDataSourceTypeForErrorBarsCustomValues().setDataSourceTypeForYMinusValues(DataSourceType.DoubleLiterals);
	// Festlegen von Fehlerbalken für Diagrammserienpunkte
	for (int i = 0; i < points.size(); i++)
	{
		points.get_Item(i).getErrorBarsCustomValues().getXMinus().setAsLiteralDouble(i + 1);
		points.get_Item(i).getErrorBarsCustomValues().getXPlus().setAsLiteralDouble(i + 1);
		points.get_Item(i).getErrorBarsCustomValues().getYMinus().setAsLiteralDouble(i + 1);
		points.get_Item(i).getErrorBarsCustomValues().getYPlus().setAsLiteralDouble(i + 1);
	}
	// Präsentation speichern
	presentation.save(dataDir + "ErrorBarsCustomValues_out.pptx", SaveFormat.Pptx);
}
finally
{
	if (presentation != null) presentation.dispose();
}
```

## Abschluss

In diesem umfassenden Tutorial haben Sie gelernt, wie Sie Ihre PowerPoint-Präsentationen verbessern können, indem Sie mit Aspose.Slides für Java benutzerdefinierte Fehlerbalken zu Diagrammen hinzufügen. Fehlerbalken bieten wertvolle Einblicke in die Variabilität und Unsicherheit von Daten und machen Ihre Diagramme informativer und optisch ansprechender.

## Häufig gestellte Fragen

### Wie passe ich die Darstellung von Fehlerbalken an?

 Sie können das Erscheinungsbild der Fehlerbalken anpassen, indem Sie die Eigenschaften des`IErrorBarsFormat` Objekt, wie etwa Linienstil, Linienfarbe und Fehlerbalkenbreite.

### Kann ich anderen Diagrammtypen Fehlerbalken hinzufügen?

Ja, Sie können Fehlerbalken zu verschiedenen Diagrammtypen hinzufügen, die von Aspose.Slides für Java unterstützt werden, darunter Balkendiagramme, Liniendiagramme und Streudiagramme.

### Wie lege ich für jeden Datenpunkt unterschiedliche Fehlerbalkenwerte fest?

Sie können die Datenpunkte durchlaufen und für jeden Punkt benutzerdefinierte Fehlerbalkenwerte festlegen, wie im obigen Code gezeigt.

### Ist es möglich, Fehlerbalken für bestimmte Datenpunkte auszublenden?

 Ja, Sie können die Sichtbarkeit von Fehlerbalken für einzelne Datenpunkte steuern, indem Sie die`setVisible` Eigentum der`IErrorBarsFormat` Objekt.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
