---
title: Invertieren, wenn negativ für einzelne Serien in Java-Folien
linktitle: Invertieren, wenn negativ für einzelne Serien in Java-Folien
second_title: Aspose.Slides Java PowerPoint-Verarbeitungs-API
description: Erfahren Sie, wie Sie die Funktion „Invert If Negative“ in Aspose.Slides für Java verwenden, um die Diagrammdarstellung in PowerPoint-Präsentationen zu verbessern.
weight: 11
url: /de/java/data-manipulation/invert-if-negative-individual-series-java-slides/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Invertieren, wenn negativ für einzelne Serien in Java-Folien


## Einführung in „Invert If Negative“ für einzelne Serien in Java-Folien

Aspose.Slides für Java bietet leistungsstarke Tools zum Arbeiten mit Präsentationen. Eine interessante Funktion ist die Möglichkeit, zu steuern, wie Datenreihen in Diagrammen angezeigt werden. In diesem Artikel erfahren Sie, wie Sie die Funktion „Invertieren, wenn negativ“ für einzelne Reihen in Java Slides verwenden. Mit dieser Funktion können Sie negative Datenpunkte in einem Diagramm optisch hervorheben und Ihre Präsentationen informativer und ansprechender gestalten.

## Voraussetzungen

Bevor wir uns in den Code vertiefen, stellen Sie sicher, dass die folgenden Voraussetzungen erfüllt sind:

- Auf Ihrem System ist Java Development Kit (JDK) installiert.
-  Aspose.Slides für Java-Bibliothek. Sie können es herunterladen von[Hier](https://releases.aspose.com/slides/java/).

## Einrichten Ihres Projekts

Erstellen Sie zunächst ein neues Java-Projekt in Ihrer bevorzugten integrierten Entwicklungsumgebung (IDE). Sobald Ihr Projekt eingerichtet ist, befolgen Sie diese Schritte, um die Funktion „Invertieren, wenn negativ“ für einzelne Serien in Java-Folien zu implementieren.

## Schritt 1: Integrieren Sie die Aspose.Slides-Bibliothek

Zuerst müssen Sie die Aspose.Slides-Bibliothek in Ihr Projekt einbinden. Sie können dies tun, indem Sie die JAR-Datei der Bibliothek zum Klassenpfad Ihres Projekts hinzufügen. Dieser Schritt stellt sicher, dass Sie auf alle erforderlichen Klassen und Methoden für die Arbeit mit PowerPoint-Präsentationen zugreifen können.

```java
import com.aspose.slides.*;
```

## Schritt 2: Erstellen Sie eine Präsentation

 Lassen Sie uns nun eine neue PowerPoint-Präsentation mit Aspose.Slides erstellen. Sie können das Verzeichnis, in dem Sie die Präsentation speichern möchten, mit dem`dataDir` Variable.

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
```

## Schritt 3: Ein Diagramm hinzufügen

In diesem Schritt fügen wir der Präsentation ein Diagramm hinzu. Als Beispiel verwenden wir ein gruppiertes Säulendiagramm. Sie können je nach Bedarf verschiedene Diagrammtypen auswählen.

```java
IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 50, 50, 600, 400, true);
```

## Schritt 4: Konfigurieren der Diagrammdatenreihe

Als Nächstes konfigurieren wir die Datenreihe des Diagramms. Um die Funktion „Invertieren, wenn negativ“ zu demonstrieren, erstellen wir einen Beispieldatensatz mit positiven und negativen Werten.

```java
IChartSeriesCollection series = chart.getChartData().getSeries();
chart.getChartData().getSeries().clear();

// Hinzufügen von Datenpunkten zur Reihe
series.add(chart.getChartData().getChartDataWorkbook().getCell(0, "B1"), chart.getType());
series.get_Item(0).getDataPoints().addDataPointForBarSeries(chart.getChartData().getChartDataWorkbook().getCell(0, "B2", -5));
series.get_Item(0).getDataPoints().addDataPointForBarSeries(chart.getChartData().getChartDataWorkbook().getCell(0, "B3", 3));
series.get_Item(0).getDataPoints().addDataPointForBarSeries(chart.getChartData().getChartDataWorkbook().getCell(0, "B4", -2));
series.get_Item(0).getDataPoints().addDataPointForBarSeries(chart.getChartData().getChartDataWorkbook().getCell(0, "B5", 1));
```

## Schritt 5: „Invertieren, wenn negativ“ anwenden

Nun wenden wir die Funktion „Invertieren, wenn negativ“ auf einen der Datenpunkte an. Dadurch wird die Farbe dieses bestimmten Datenpunkts optisch invertiert, wenn er negativ ist.

```java
series.get_Item(0).setInvertIfNegative(false); // Standardmäßig nicht invertieren
series.get_Item(0).getDataPoints().get_Item(2).setInvertIfNegative(true); // Invertieren Sie die Farbe für den dritten Datenpunkt
```

## Schritt 6: Speichern Sie die Präsentation

Speichern Sie die Präsentation abschließend im angegebenen Verzeichnis.

```java
pres.save(dataDir + "InvertIfNegativeForIndividualSeries.pptx", SaveFormat.Pptx);
```

## Vollständiger Quellcode zum Invertieren, wenn negativ für einzelne Serien in Java-Folien

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
try
{
	IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 50, 50, 600, 400, true);
	IChartSeriesCollection series = chart.getChartData().getSeries();
	chart.getChartData().getSeries().clear();
	series.add(chart.getChartData().getChartDataWorkbook().getCell(0, "B1"), chart.getType());
	series.get_Item(0).getDataPoints().addDataPointForBarSeries(chart.getChartData().getChartDataWorkbook().getCell(0, "B2", -5));
	series.get_Item(0).getDataPoints().addDataPointForBarSeries(chart.getChartData().getChartDataWorkbook().getCell(0, "B3", 3));
	series.get_Item(0).getDataPoints().addDataPointForBarSeries(chart.getChartData().getChartDataWorkbook().getCell(0, "B4", -2));
	series.get_Item(0).getDataPoints().addDataPointForBarSeries(chart.getChartData().getChartDataWorkbook().getCell(0, "B5", 1));
	series.get_Item(0).setInvertIfNegative(false);
	series.get_Item(0).getDataPoints().get_Item(2).setInvertIfNegative(true);
	pres.save(dataDir + "InvertIfNegativeForIndividualSeries.pptx", SaveFormat.Pptx);
}
finally
{
	if (pres != null) pres.dispose();
}
```

## Abschluss

In diesem Tutorial haben wir gelernt, wie man die Funktion „Invertieren, wenn negativ“ für einzelne Reihen in Java-Folien mit Aspose.Slides für Java verwendet. Mit dieser Funktion können Sie negative Datenpunkte in Ihren Diagrammen hervorheben und so Ihre Präsentationen optisch ansprechender und informativer gestalten.

## Häufig gestellte Fragen

### Was ist der Zweck der Funktion „Invertieren, wenn negativ“ in Aspose.Slides für Java?

Mit der Funktion „Invertieren, wenn negativ“ in Aspose.Slides für Java können Sie negative Datenpunkte in Diagrammen optisch hervorheben. Durch die Hervorhebung bestimmter Datenpunkte können Sie Ihre Präsentationen informativer und ansprechender gestalten.

### Wie kann ich die Aspose.Slides-Bibliothek in mein Java-Projekt einbinden?

Um die Aspose.Slides-Bibliothek in Ihr Java-Projekt einzubinden, müssen Sie die JAR-Datei der Bibliothek zum Klassenpfad Ihres Projekts hinzufügen. Dadurch können Sie auf alle erforderlichen Klassen und Methoden für die Arbeit mit PowerPoint-Präsentationen zugreifen.

### Kann ich mit der Funktion „Invertieren, wenn negativ“ verschiedene Diagrammtypen verwenden?

Ja, Sie können mit der Funktion „Invertieren, wenn negativ“ verschiedene Diagrammtypen verwenden. In diesem Tutorial haben wir als Beispiel ein gruppiertes Säulendiagramm verwendet, aber Sie können die Funktion je nach Ihren Anforderungen auf verschiedene Diagrammtypen anwenden.

### Ist es möglich, das Erscheinungsbild der invertierten Datenpunkte anzupassen?

Ja, Sie können das Erscheinungsbild der invertierten Datenpunkte anpassen. Aspose.Slides für Java bietet Optionen zur Steuerung der Farbe und des Stils von Datenpunkten, wenn diese aufgrund der Einstellung „Invertieren, wenn negativ“ invertiert werden.

### Wo kann ich auf die Aspose.Slides-Dokumentation für Java zugreifen?

Sie können auf die Dokumentation für Aspose.Slides für Java unter zugreifen.[Hier](https://reference.aspose.com/slides/java/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
