---
title: Trendlinien in Java-Foliendiagrammen
linktitle: Trendlinien in Java-Foliendiagrammen
second_title: Aspose.Slides Java PowerPoint-Verarbeitungs-API
description: Erfahren Sie, wie Sie mit Aspose.Slides für Java verschiedene Trendlinien zu Java-Folien hinzufügen. Schritt-für-Schritt-Anleitung mit Codebeispielen für eine effektive Datenvisualisierung.
weight: 15
url: /de/java/data-manipulation/chart-trend-lines-java-slides/
---

{< blocks/products/pf/main-wrap-class >}
{< blocks/products/pf/main-container >}
{< blocks/products/pf/tutorial-page-section >}


## Einführung in Diagrammtrendlinien in Java-Folien: Eine Schritt-für-Schritt-Anleitung

In dieser umfassenden Anleitung erfahren Sie, wie Sie mit Aspose.Slides für Java Diagrammtrendlinien in Java Slides erstellen. Diagrammtrendlinien können eine wertvolle Ergänzung Ihrer Präsentationen sein und dabei helfen, Datentrends effektiv zu visualisieren und zu analysieren. Wir führen Sie mit klaren Erklärungen und Codebeispielen durch den Prozess.

## Voraussetzungen

Bevor wir mit der Erstellung von Trendlinien in Diagrammen beginnen, stellen Sie sicher, dass die folgenden Voraussetzungen erfüllt sind:

- Java-Entwicklungsumgebung
- Aspose.Slides für die Java-Bibliothek
- Ein Code-Editor Ihrer Wahl

## Schritt 1: Erste Schritte

Beginnen wir mit der Einrichtung der erforderlichen Umgebung und der Erstellung einer neuen Präsentation:

```java
// Der Pfad zum Dokumentverzeichnis.
String dataDir = "Your Document Directory";
// Erstellen Sie ein Verzeichnis, falls es noch nicht vorhanden ist.
boolean IsExists = new File(dataDir).exists();
if (!IsExists)
    new File(dataDir).mkdirs();
// Leere Präsentation erstellen
Presentation pres = new Presentation();
```

Wir haben unsere Präsentation initialisiert und sind nun bereit, ein gruppiertes Säulendiagramm hinzuzufügen:

```java
// Erstellen eines gruppierten Säulendiagramms
IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 20, 20, 500, 400);
```

## Schritt 2: Hinzufügen einer exponentiellen Trendlinie

Beginnen wir damit, unserer Diagrammreihe eine exponentielle Trendlinie hinzuzufügen:

```java
// Hinzufügen einer exponentiellen Trendlinie für Diagrammserie 1
ITrendline trendLineExp = chart.getChartData().getSeries().get_Item(0).getTrendLines().add(TrendlineType.Exponential);
trendLineExp.setDisplayEquation(false);
trendLineExp.setDisplayRSquaredValue(false);
```

## Schritt 3: Lineare Trendlinie hinzufügen

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

## Schritt 5: Hinzufügen einer gleitenden Durchschnittstrendlinie

Wir können auch eine gleitende Durchschnittstrendlinie hinzufügen:

```java
// Hinzufügen einer gleitenden Durchschnittstrendlinie für Diagrammserie 2
ITrendline trendLineMovAvg = chart.getChartData().getSeries().get_Item(1).getTrendLines().add(TrendlineType.MovingAverage);
trendLineMovAvg.setTrendlineType(TrendlineType.MovingAverage);
trendLineMovAvg.setPeriod((byte) 3);
trendLineMovAvg.setTrendlineName("New TrendLine Name");
```

## Schritt 6: Polynomische Trendlinie hinzufügen

Hinzufügen einer polynomischen Trendlinie:

```java
// Hinzufügen einer polynomischen Trendlinie für Diagrammserie 3
ITrendline trendLinePolynomial = chart.getChartData().getSeries().get_Item(2).getTrendLines().add(TrendlineType.Polynomial);
trendLinePolynomial.setTrendlineType(TrendlineType.Polynomial);
trendLinePolynomial.setForward(1);
trendLinePolynomial.setOrder((byte) 3);
```

## Schritt 7: Power-Trendlinie hinzufügen

Zum Schluss fügen wir noch eine Power-Trendlinie hinzu:

```java
// Hinzufügen einer Power-Trendlinie für Diagrammserie 3
ITrendline trendLinePower = chart.getChartData().getSeries().get_Item(1).getTrendLines().add(TrendlineType.Power);
trendLinePower.setTrendlineType(TrendlineType.Power);
trendLinePower.setBackward(1);
```

## Schritt 8: Speichern der Präsentation

Nachdem wir nun unserem Diagramm verschiedene Trendlinien hinzugefügt haben, speichern wir die Präsentation:

```java
pres.save(dataDir + "ChartTrendLines_out.pptx", SaveFormat.Pptx);
```

Herzlichen Glückwunsch! Sie haben mit Aspose.Slides für Java erfolgreich eine Präsentation mit verschiedenen Arten von Trendlinien in Java Slides erstellt.

## Vollständiger Quellcode für Diagramm-Trendlinien in Java-Folien

```java
// Der Pfad zum Dokumentverzeichnis.
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
// Hinzufügen einer polynomischen Trendlinie für Diagrammserie 3
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

In diesem Tutorial haben wir gelernt, wie man mithilfe der Bibliothek Aspose.Slides für Java verschiedene Arten von Trendlinien zu Diagrammen in Java Slides hinzufügt. Egal, ob Sie an der Datenanalyse arbeiten oder informative Präsentationen erstellen, die Möglichkeit, Trends zu visualisieren, kann ein leistungsstarkes Werkzeug sein.

## Häufig gestellte Fragen

### Wie ändere ich die Farbe einer Trendlinie in Aspose.Slides für Java?

 Um die Farbe einer Trendlinie zu ändern, können Sie das`getSolidFillColor().setColor(Color)` Methode, wie im Beispiel zum Hinzufügen einer linearen Trendlinie gezeigt.

### Kann ich einer einzelnen Diagrammreihe mehrere Trendlinien hinzufügen?

Ja, Sie können mehrere Trendlinien zu einer einzigen Chartserie hinzufügen. Rufen Sie einfach die`getTrendLines().add()` Methode für jede Trendlinie, die Sie hinzufügen möchten.

### Wie entferne ich eine Trendlinie aus einem Diagramm in Aspose.Slides für Java?

 Um eine Trendlinie aus einem Diagramm zu entfernen, können Sie das`removeAt(int index)` Methode und geben Sie den Index der Trendlinie an, die Sie entfernen möchten.

### Ist es möglich, die Anzeige der Trendliniengleichung anzupassen?

 Ja, Sie können die Anzeige der Trendliniengleichung anpassen, indem Sie`setDisplayEquation(boolean)` Methode, wie im Beispiel gezeigt.

### Wie kann ich auf weitere Ressourcen und Beispiele für Aspose.Slides für Java zugreifen?

 Sie können auf zusätzliche Ressourcen, Dokumentation und Beispiele für Aspose.Slides für Java zugreifen auf der[Aspose-Website](https://reference.aspose.com/slides/java/).
{< /blocks/products/pf/tutorial-page-section >}

{< /blocks/products/pf/main-container >}
{< /blocks/products/pf/main-wrap-class >}

{< blocks/products/products-backtop-button >}
