---
title: Invertieren, wenn negativ für einzelne Reihen in Java-Folien
linktitle: Invertieren, wenn negativ für einzelne Reihen in Java-Folien
second_title: Aspose.Slides Java PowerPoint-Verarbeitungs-API
description: Erfahren Sie, wie Sie die Funktion „Invert If Negative“ in Aspose.Slides für Java verwenden, um Diagrammvisualisierungen in PowerPoint-Präsentationen zu verbessern.
type: docs
weight: 11
url: /de/java/data-manipulation/invert-if-negative-individual-series-java-slides/
---

## Einführung in „Umkehren, wenn negativ“ für einzelne Reihen in Java-Folien

Aspose.Slides für Java bietet leistungsstarke Tools für die Arbeit mit Präsentationen. Eine interessante Funktion ist die Möglichkeit, zu steuern, wie Datenreihen in Diagrammen angezeigt werden. In diesem Artikel erfahren Sie, wie Sie die Funktion „Umkehren bei Negativ“ für einzelne Serien in Java-Folien verwenden. Mit dieser Funktion können Sie negative Datenpunkte in einem Diagramm visuell unterscheiden und so Ihre Präsentationen informativer und ansprechender gestalten.

## Voraussetzungen

Bevor wir uns mit dem Code befassen, stellen Sie sicher, dass die folgenden Voraussetzungen erfüllt sind:

- Java Development Kit (JDK) auf Ihrem System installiert.
-  Aspose.Slides für Java-Bibliothek. Sie können es herunterladen unter[Hier](https://releases.aspose.com/slides/java/).

## Einrichten Ihres Projekts

Erstellen Sie zunächst ein neues Java-Projekt in Ihrer bevorzugten integrierten Entwicklungsumgebung (IDE). Sobald Ihr Projekt eingerichtet ist, befolgen Sie diese Schritte, um die Funktion „Umkehren bei Negativ“ für einzelne Serien in Java Slides zu implementieren.

## Schritt 1: Binden Sie die Aspose.Slides-Bibliothek ein

Zunächst müssen Sie die Aspose.Slides-Bibliothek in Ihr Projekt einbinden. Sie können dies tun, indem Sie die JAR-Bibliotheksdatei zum Klassenpfad Ihres Projekts hinzufügen. Dieser Schritt stellt sicher, dass Sie auf alle notwendigen Klassen und Methoden für die Arbeit mit PowerPoint-Präsentationen zugreifen können.

```java
import com.aspose.slides.*;
```

## Schritt 2: Erstellen Sie eine Präsentation

 Lassen Sie uns nun eine neue PowerPoint-Präsentation mit Aspose.Slides erstellen. Mit können Sie das Verzeichnis festlegen, in dem Sie die Präsentation speichern möchten`dataDir` Variable.

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
```

## Schritt 3: Fügen Sie ein Diagramm hinzu

In diesem Schritt fügen wir der Präsentation ein Diagramm hinzu. Als Beispiel verwenden wir ein gruppiertes Säulendiagramm. Je nach Ihren Anforderungen können Sie verschiedene Diagrammtypen auswählen.

```java
IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 50, 50, 600, 400, true);
```

## Schritt 4: Konfigurieren Sie die Diagrammdatenreihe

Als Nächstes konfigurieren wir die Datenreihe des Diagramms. Um die Funktion „Umkehren bei Negativ“ zu demonstrieren, erstellen wir einen Beispieldatensatz mit positiven und negativen Werten.

```java
IChartSeriesCollection series = chart.getChartData().getSeries();
chart.getChartData().getSeries().clear();

// Datenpunkte zur Serie hinzufügen
series.add(chart.getChartData().getChartDataWorkbook().getCell(0, "B1"), chart.getType());
series.get_Item(0).getDataPoints().addDataPointForBarSeries(chart.getChartData().getChartDataWorkbook().getCell(0, "B2", -5));
series.get_Item(0).getDataPoints().addDataPointForBarSeries(chart.getChartData().getChartDataWorkbook().getCell(0, "B3", 3));
series.get_Item(0).getDataPoints().addDataPointForBarSeries(chart.getChartData().getChartDataWorkbook().getCell(0, "B4", -2));
series.get_Item(0).getDataPoints().addDataPointForBarSeries(chart.getChartData().getChartDataWorkbook().getCell(0, "B5", 1));
```

## Schritt 5: „Umkehren, wenn negativ“ anwenden

Jetzt wenden wir die Funktion „Invert If Negative“ auf einen der Datenpunkte an. Dadurch wird die Farbe dieses bestimmten Datenpunkts visuell umgekehrt, wenn er negativ ist.

```java
series.get_Item(0).setInvertIfNegative(false); // Standardmäßig nicht invertieren
series.get_Item(0).getDataPoints().get_Item(2).setInvertIfNegative(true); // Kehren Sie die Farbe für den dritten Datenpunkt um
```

## Schritt 6: Speichern Sie die Präsentation

Speichern Sie abschließend die Präsentation in Ihrem angegebenen Verzeichnis.

```java
pres.save(dataDir + "InvertIfNegativeForIndividualSeries.pptx", SaveFormat.Pptx);
```

## Vollständiger Quellcode für „Umkehren, wenn negativ“ für einzelne Reihen in Java-Folien

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

In diesem Tutorial haben wir gelernt, wie man die Funktion „Invert If Negative“ für einzelne Serien in Java Slides mit Aspose.Slides für Java verwendet. Mit dieser Funktion können Sie negative Datenpunkte in Ihren Diagrammen hervorheben und so Ihre Präsentationen optisch ansprechender und informativer gestalten.

## FAQs

### Was ist der Zweck der Funktion „Invert If Negative“ in Aspose.Slides für Java?

Mit der Funktion „Invert If Negative“ in Aspose.Slides für Java können Sie negative Datenpunkte in Diagrammen visuell unterscheiden. Es trägt dazu bei, Ihre Präsentationen informativer und ansprechender zu gestalten, indem es bestimmte Datenpunkte hervorhebt.

### Wie kann ich die Aspose.Slides-Bibliothek in mein Java-Projekt einbinden?

Um die Aspose.Slides-Bibliothek in Ihr Java-Projekt einzubinden, müssen Sie die JAR-Bibliotheksdatei zum Klassenpfad Ihres Projekts hinzufügen. Dadurch erhalten Sie Zugriff auf alle notwendigen Klassen und Methoden für die Arbeit mit PowerPoint-Präsentationen.

### Kann ich mit der Funktion „Umkehren bei Negativ“ verschiedene Diagrammtypen verwenden?

Ja, Sie können mit der Funktion „Bei Negativ umkehren“ verschiedene Diagrammtypen verwenden. In diesem Tutorial haben wir als Beispiel ein gruppiertes Säulendiagramm verwendet, Sie können die Funktion jedoch je nach Ihren Anforderungen auf verschiedene Diagrammtypen anwenden.

### Ist es möglich, das Erscheinungsbild der invertierten Datenpunkte anzupassen?

Ja, Sie können das Erscheinungsbild der invertierten Datenpunkte anpassen. Aspose.Slides für Java bietet Optionen zum Steuern der Farbe und des Stils von Datenpunkten, wenn diese aufgrund der Einstellung „Invertieren, wenn negativ“ invertiert werden.

### Wo kann ich auf die Dokumentation zu Aspose.Slides für Java zugreifen?

 Sie können auf die Dokumentation für Aspose.Slides für Java unter zugreifen[Hier](https://reference.aspose.com/slides/java/).