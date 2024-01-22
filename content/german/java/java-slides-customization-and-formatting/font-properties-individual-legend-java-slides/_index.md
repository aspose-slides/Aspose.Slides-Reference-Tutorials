---
title: Schriftarteigenschaften für einzelne Legenden in Java-Folien
linktitle: Schriftarteigenschaften für einzelne Legenden in Java-Folien
second_title: Aspose.Slides Java PowerPoint-Verarbeitungs-API
description: Verbessern Sie PowerPoint-Präsentationen mit benutzerdefinierten Schriftstilen, -größen und -farben für einzelne Legenden in Java-Folien mit Aspose.Slides für Java.
type: docs
weight: 12
url: /de/java/customization-and-formatting/font-properties-individual-legend-java-slides/
---

## Einführung in Schriftarteigenschaften für einzelne Legenden in Java-Folien

In diesem Tutorial erfahren Sie, wie Sie mithilfe von Aspose.Slides für Java Schriftarteigenschaften für eine einzelne Legende in Java Slides festlegen. Durch Anpassen der Schriftarteigenschaften können Sie Ihre Legenden in Ihren PowerPoint-Präsentationen optisch ansprechender und informativer gestalten.

## Voraussetzungen

 Bevor Sie beginnen, stellen Sie sicher, dass die Aspose.Slides for Java-Bibliothek in Ihr Projekt integriert ist. Sie können es hier herunterladen[Aspose.Slides für Java-Dokumentation](https://reference.aspose.com/slides/java/).

## Schritt 1: Präsentation initialisieren und Diagramm hinzufügen

Beginnen wir zunächst mit der Initialisierung einer PowerPoint-Präsentation und dem Hinzufügen eines Diagramms. In diesem Beispiel verwenden wir zur Veranschaulichung ein gruppiertes Säulendiagramm.

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "test.pptx");

try {
    IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 50, 50, 600, 400);
    // Der Rest des Codes kommt hierher
} finally {
    if (pres != null) pres.dispose();
}
```

 Ersetzen`"Your Document Directory"` mit dem tatsächlichen Verzeichnis, in dem sich Ihr PowerPoint-Dokument befindet.

## Schritt 2: Passen Sie die Schriftarteigenschaften für die Legende an

Passen wir nun die Schriftarteigenschaften für einen einzelnen Legendeneintrag im Diagramm an. In diesem Beispiel zielen wir auf den zweiten Legendeneintrag (Index 1), Sie können den Index jedoch entsprechend Ihren spezifischen Anforderungen anpassen.

```java
IChartTextFormat tf = chart.getLegend().getEntries().get_Item(1).getTextFormat();
tf.getPortionFormat().setFontBold(NullableBool.True);
tf.getPortionFormat().setFontHeight(20);
tf.getPortionFormat().setFontItalic(NullableBool.True);
tf.getPortionFormat().getFillFormat().setFillType(FillType.Solid);
tf.getPortionFormat().getFillFormat().getSolidFillColor().setColor(Color.BLUE);
```

Hier erfahren Sie, was jede Codezeile bewirkt:

- `get_Item(1)` ruft den zweiten Legendeneintrag (Index 1) ab. Sie können den Index ändern, um auf einen anderen Legendeneintrag abzuzielen.
- `setFontBold(NullableBool.True)` Setzt die Schriftart auf Fett.
- `setFontHeight(20)` Setzt die Schriftgröße auf 20 Punkte.
- `setFontItalic(NullableBool.True)` setzt die Schriftart auf kursiv.
- `setFillType(FillType.Solid)` Gibt an, dass der Text des Legendeneintrags eine durchgehende Füllung haben soll.
- `getSolidFillColor().setColor(Color.BLUE)` Setzt die Füllfarbe auf Blau. Sie können ersetzen`Color.BLUE` mit Ihrer Wunschfarbe.

## Schritt 3: Speichern Sie die geänderte Präsentation

Speichern Sie abschließend die geänderte Präsentation in einer neuen Datei, um Ihre Änderungen beizubehalten.

```java
pres.save(dataDir + "output.pptx", SaveFormat.Pptx);
```

 Ersetzen`"output.pptx"` mit Ihrem bevorzugten Ausgabedateinamen.

Das ist es! Sie haben die Schriftarteigenschaften für einen einzelnen Legendeneintrag in einer Java Slides-Präsentation mit Aspose.Slides für Java erfolgreich angepasst.

## Vollständiger Quellcode für Schriftarteigenschaften für einzelne Legenden in Java-Folien

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "test.pptx");
try
{
	IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 50, 50, 600, 400);
	IChartTextFormat tf = chart.getLegend().getEntries().get_Item(1).getTextFormat();
	tf.getPortionFormat().setFontBold(NullableBool.True);
	tf.getPortionFormat().setFontHeight(20);
	tf.getPortionFormat().setFontItalic(NullableBool.True);
	tf.getPortionFormat().getFillFormat().setFillType(FillType.Solid);
	tf.getPortionFormat().getFillFormat().getSolidFillColor().setColor(Color.BLUE);
	pres.save(dataDir + "output.pptx", SaveFormat.Pptx);
}
finally
{
	if (pres != null) pres.dispose();
}
```

## Abschluss

In diesem Tutorial haben wir gelernt, wie man mit Aspose.Slides für Java Schriftarteigenschaften für eine einzelne Legende in Java Slides anpasst. Durch Anpassen von Schriftstilen, -größen und -farben können Sie die visuelle Attraktivität und Klarheit Ihrer PowerPoint-Präsentationen verbessern.

## FAQs

### Wie kann ich die Schriftfarbe ändern?

 Um die Schriftfarbe zu ändern, verwenden Sie`tf.getPortionFormat().getFontColor().setColor(yourColor)` anstatt die Füllfarbe zu ändern. Ersetzen`yourColor` mit der gewünschten Schriftfarbe.

### Wie ändere ich andere Legendeneigenschaften?

Sie können verschiedene andere Eigenschaften der Legende ändern, z. B. Position, Größe und Format. Ausführliche Informationen zum Arbeiten mit Legenden finden Sie in der Dokumentation zu Aspose.Slides für Java.

### Kann ich diese Änderungen auf mehrere Legendeneinträge anwenden?

 Ja, Sie können Legendeneinträge durchlaufen und diese Änderungen auf mehrere Einträge anwenden, indem Sie den Index anpassen`get_Item(index)` und Wiederholen des Anpassungscodes.

Denken Sie daran, das Präsentationsobjekt zu entsorgen, wenn Sie mit der Freigabe der Ressourcen fertig sind:

```java
if (pres != null) pres.dispose();
```