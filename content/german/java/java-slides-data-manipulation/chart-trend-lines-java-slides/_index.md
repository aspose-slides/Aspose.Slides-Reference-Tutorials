---
title: Diagrammtrendlinien in Java-Folien
linktitle: Diagrammtrendlinien in Java-Folien
second_title: Aspose.Slides Java PowerPoint-Verarbeitungs-API
description: Erfahren Sie, wie Sie mit Aspose.Slides für Java verschiedene Trendlinien zu Java-Folien hinzufügen. Schritt-für-Schritt-Anleitung mit Codebeispielen für eine effektive Datenvisualisierung.
type: docs
weight: 15
url: /de/java/data-manipulation/chart-trend-lines-java-slides/
---

## Einführung in Diagrammtrendlinien in Java-Folien: Eine Schritt-für-Schritt-Anleitung

In dieser umfassenden Anleitung erfahren Sie, wie Sie mit Aspose.Slides für Java Diagrammtrendlinien in Java Slides erstellen. Diagrammtrendlinien können eine wertvolle Ergänzung zu Ihren Präsentationen sein und dabei helfen, Datentrends effektiv zu visualisieren und zu analysieren. Wir führen Sie mit klaren Erklärungen und Codebeispielen durch den Prozess.

## Voraussetzungen

Bevor wir uns mit der Erstellung von Diagrammtrendlinien befassen, stellen Sie sicher, dass die folgenden Voraussetzungen erfüllt sind:

- Java-Entwicklungsumgebung
- Aspose.Slides für Java-Bibliothek
- Ein Code-Editor Ihrer Wahl

## Schritt 1: Erste Schritte

Beginnen wir damit, die erforderliche Umgebung einzurichten und eine neue Präsentation zu erstellen:

```java
// Der Pfad zum Dokumentenverzeichnis.
String dataDir = "Your Document Directory";
// Erstellen Sie ein Verzeichnis, falls es noch nicht vorhanden ist.
boolean IsExists = new File(dataDir).exists();
if (!IsExists)
    new File(dataDir).mkdirs();
// Leere Präsentation erstellen
Presentation pres = new Presentation();
```

Wir haben unsere Präsentation initialisiert und können nun ein gruppiertes Säulendiagramm hinzufügen:

```java
// Erstellen eines gruppierten Säulendiagramms
IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 20, 20, 500, 400);
```

## Schritt 2: Hinzufügen einer exponentiellen Trendlinie

Beginnen wir damit, unserer Diagrammserie eine exponentielle Trendlinie hinzuzufügen:

```java
// Hinzufügen einer exponentiellen Trendlinie für Diagrammserie 1
ITrendline trendLineExp = chart.getChartData().getSeries().get_Item(0).getTrendLines().add(TrendlineType.Exponential);
trendLineExp.setDisplayEquation(false);
trendLineExp.setDisplayRSquaredValue(false);
```

## Schritt 3: Hinzufügen einer linearen Trendlinie

Als Nächstes fügen wir unserer Diagrammreihe eine lineare Trendlinie hinzu:

```java
// Hinzufügen einer linearen Trendlinie für Diagrammserie 1
ITrendline trendLineLinear = chart.getChartData().getSeries().get_Item(0).getTrendLines().add(TrendlineType.Linear);
trendLineLinear.setTrendlineType(TrendlineType.Linear);
trendLineLinear.getFormat().getLine().getFillFormat().setFillType(FillType.Solid);
trendLineLinear.getFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.RED);
```

## Schritt 4: Logarithmische Trendlinie hinzufügen

Fügen wir nun einer anderen Diagrammreihe eine logarithmische Trendlinie hinzu:

```java
// Hinzufügen einer logarithmischen Trendlinie für Diagrammserie 2
ITrendline trendLineLog = chart.getChartData().getSeries().get_Item(1).getTrendLines().add(TrendlineType.Logarithmic);
trendLineLog.setTrendlineType(TrendlineType.Logarithmic);
trendLineLog.addTextFrameForOverriding("New log trend line");
```

## Schritt 5: Hinzufügen einer Trendlinie für den gleitenden Durchschnitt

Wir können auch eine Trendlinie des gleitenden Durchschnitts hinzufügen:

```java
// Hinzufügen einer Trendlinie des gleitenden Durchschnitts für Diagrammserie 2
ITrendline trendLineMovAvg = chart.getChartData().getSeries().get_Item(1).getTrendLines().add(TrendlineType.MovingAverage);
trendLineMovAvg.setTrendlineType(TrendlineType.MovingAverage);
trendLineMovAvg.setPeriod((byte) 3);
trendLineMovAvg.setTrendlineName("New TrendLine Name");
```

## Schritt 6: Polynom-Trendlinie hinzufügen

Hinzufügen einer polynomialen Trendlinie:

```java
// Hinzufügen einer polynomialen Trendlinie für Diagrammserie 3
ITrendline trendLinePolynomial = chart.getChartData().getSeries().get_Item(2).getTrendLines().add(TrendlineType.Polynomial);
trendLinePolynomial.setTrendlineType(TrendlineType.Polynomial);
trendLinePolynomial.setForward(1);
trendLinePolynomial.setOrder((byte) 3);
```

## Schritt 7: Leistungstrendlinie hinzufügen

Zum Schluss fügen wir noch eine Leistungstrendlinie hinzu:

```java
// Leistungstrendlinie für Diagrammserie 3 hinzugefügt
ITrendline trendLinePower = chart.getChartData().getSeries().get_Item(1).getTrendLines().add(TrendlineType.Power);
trendLinePower.setTrendlineType(TrendlineType.Power);
trendLinePower.setBackward(1);
```

## Schritt 8: Speichern der Präsentation

Nachdem wir unserem Diagramm nun verschiedene Trendlinien hinzugefügt haben, speichern wir die Präsentation:

```java
pres.save(dataDir + "ChartTrendLines_out.pptx", SaveFormat.Pptx);
```

Glückwunsch! Sie haben mit Aspose.Slides für Java erfolgreich eine Präsentation mit verschiedenen Arten von Trendlinien in Java Slides erstellt.

## Vollständiger Quellcode für Diagrammtrendlinien in Java-Folien

```java
// Der Pfad zum Dokumentenverzeichnis.
String dataDir = "Your Document Directory";
// Erstellen Sie ein Verzeichnis, falls es noch nicht vorhanden ist.
boolean IsExists = new File(dataDir).exists();
if (!IsExists)
	new File(dataDir).mkdirs();
// Leere Präsentation erstellen
Presentation pres = new Presentation();
// Erstellen eines gruppierten Säulendiagramms
IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 20, 20, 500, 400);
// Hinzufügen einer ponentiellen Trendlinie für Diagrammserie 1
ITrendline tredLinep = chart.getChartData().getSeries().get_Item(0).getTrendLines().add(TrendlineType.Exponential);
tredLinep.setDisplayEquation(false);
tredLinep.setDisplayRSquaredValue(false);
// Hinzufügen einer linearen Trendlinie für Diagrammserie 1
ITrendline tredLineLin = chart.getChartData().getSeries().get_Item(0).getTrendLines().add(TrendlineType.Linear);
tredLineLin.setTrendlineType(TrendlineType.Linear);
tredLineLin.getFormat().getLine().getFillFormat().setFillType(FillType.Solid);
tredLineLin.getFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.RED);
// Hinzufügen einer logarithmischen Trendlinie für Diagrammserie 2
ITrendline tredLineLog = chart.getChartData().getSeries().get_Item(1).getTrendLines().add(TrendlineType.Logarithmic);
tredLineLog.setTrendlineType(TrendlineType.Logarithmic);
tredLineLog.addTextFrameForOverriding("New log trend line");
// Hinzufügen einer MovingAverage-Trendlinie für Diagrammserie 2
ITrendline tredLineMovAvg = chart.getChartData().getSeries().get_Item(1).getTrendLines().add(TrendlineType.MovingAverage);
tredLineMovAvg.setTrendlineType(TrendlineType.MovingAverage);
tredLineMovAvg.setPeriod((byte) 3);
tredLineMovAvg.setTrendlineName("New TrendLine Name");
// Hinzufügen einer polynomialen Trendlinie für Diagrammserie 3
ITrendline tredLinePol = chart.getChartData().getSeries().get_Item(2).getTrendLines().add(TrendlineType.Polynomial);
tredLinePol.setTrendlineType(TrendlineType.Polynomial);
tredLinePol.setForward(1);
tredLinePol.setOrder((byte) 3);
// Hinzufügen einer Power-Trendlinie für Diagrammserie 3
ITrendline tredLinePower = chart.getChartData().getSeries().get_Item(1).getTrendLines().add(TrendlineType.Power);
tredLinePower.setTrendlineType(TrendlineType.Power);
tredLinePower.setBackward(1);
// Präsentation speichern
pres.save(dataDir + "ChartTrendLines_out.pptx", SaveFormat.Pptx);
```

## Abschluss

In diesem Tutorial haben wir gelernt, wie man mithilfe der Aspose.Slides for Java-Bibliothek verschiedene Arten von Trendlinien zu Diagrammen in Java Slides hinzufügt. Ganz gleich, ob Sie an Datenanalysen arbeiten oder informative Präsentationen erstellen, die Möglichkeit, Trends zu visualisieren, kann ein leistungsstarkes Werkzeug sein.

## FAQs

### Wie ändere ich die Farbe einer Trendlinie in Aspose.Slides für Java?

Um die Farbe einer Trendlinie zu ändern, können Sie die verwenden`getSolidFillColor().setColor(Color)` Methode, wie im Beispiel zum Hinzufügen einer linearen Trendlinie gezeigt.

### Kann ich einer einzelnen Diagrammserie mehrere Trendlinien hinzufügen?

 Ja, Sie können einer einzelnen Diagrammserie mehrere Trendlinien hinzufügen. Rufen Sie einfach an`getTrendLines().add()` Methode für jede Trendlinie, die Sie hinzufügen möchten.

### Wie entferne ich eine Trendlinie aus einem Diagramm in Aspose.Slides für Java?

 Um eine Trendlinie aus einem Diagramm zu entfernen, können Sie die verwenden`removeAt(int index)` -Methode und geben Sie den Index der Trendlinie an, die Sie entfernen möchten.

### Ist es möglich, die Anzeige der Trendliniengleichung anzupassen?

 Ja, Sie können die Anzeige der Trendliniengleichung mithilfe von anpassen`setDisplayEquation(boolean)` Methode, wie im Beispiel gezeigt.

### Wie kann ich auf weitere Ressourcen und Beispiele für Aspose.Slides für Java zugreifen?

 Sie können auf zusätzliche Ressourcen, Dokumentation und Beispiele für Aspose.Slides für Java zugreifen[Aspose-Website](https://reference.aspose.com/slides/java/).