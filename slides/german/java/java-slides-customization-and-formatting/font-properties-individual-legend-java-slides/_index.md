---
"description": "Verbessern Sie PowerPoint-Präsentationen mit benutzerdefinierten Schriftarten, -größen und -farben für einzelne Legenden in Java Slides mithilfe von Aspose.Slides für Java."
"linktitle": "Schrifteigenschaften für einzelne Legenden in Java-Folien"
"second_title": "Aspose.Slides Java PowerPoint-Verarbeitungs-API"
"title": "Schrifteigenschaften für einzelne Legenden in Java-Folien"
"url": "/de/java/customization-and-formatting/font-properties-individual-legend-java-slides/"
"weight": 12
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Schrifteigenschaften für einzelne Legenden in Java-Folien


## Einführung in die Schrifteigenschaften für einzelne Legenden in Java-Folien

In diesem Tutorial erfahren Sie, wie Sie mit Aspose.Slides für Java Schrifteigenschaften für eine einzelne Legende in Java Slides festlegen. Durch Anpassen der Schrifteigenschaften können Sie die Legenden in Ihren PowerPoint-Präsentationen optisch ansprechender und informativer gestalten.

## Voraussetzungen

Bevor Sie beginnen, stellen Sie sicher, dass die Aspose.Slides für Java-Bibliothek in Ihr Projekt integriert ist. Sie können sie von der [Aspose.Slides für Java-Dokumentation](https://reference.aspose.com/slides/java/).

## Schritt 1: Präsentation initialisieren und Diagramm hinzufügen

Beginnen wir zunächst mit der Initialisierung einer PowerPoint-Präsentation und dem Hinzufügen eines Diagramms. In diesem Beispiel verwenden wir zur Veranschaulichung ein gruppiertes Säulendiagramm.

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "test.pptx");

try {
    IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 50, 50, 600, 400);
    // Der Rest des Codes kommt hierhin
} finally {
    if (pres != null) pres.dispose();
}
```

Ersetzen `"Your Document Directory"` mit dem tatsächlichen Verzeichnis, in dem sich Ihr PowerPoint-Dokument befindet.

## Schritt 2: Anpassen der Schrifteigenschaften für die Legende

Passen wir nun die Schrifteigenschaften für einen einzelnen Legendeneintrag im Diagramm an. In diesem Beispiel beziehen wir uns auf den zweiten Legendeneintrag (Index 1). Sie können den Index jedoch Ihren spezifischen Anforderungen entsprechend anpassen.

```java
IChartTextFormat tf = chart.getLegend().getEntries().get_Item(1).getTextFormat();
tf.getPortionFormat().setFontBold(NullableBool.True);
tf.getPortionFormat().setFontHeight(20);
tf.getPortionFormat().setFontItalic(NullableBool.True);
tf.getPortionFormat().getFillFormat().setFillType(FillType.Solid);
tf.getPortionFormat().getFillFormat().getSolidFillColor().setColor(Color.BLUE);
```

Die einzelnen Codezeilen bewirken Folgendes:

- `get_Item(1)` Ruft den zweiten Legendeneintrag (Index 1) ab. Sie können den Index ändern, um einen anderen Legendeneintrag anzusprechen.
- `setFontBold(NullableBool.True)` setzt die Schriftart auf fett.
- `setFontHeight(20)` setzt die Schriftgröße auf 20 Punkt.
- `setFontItalic(NullableBool.True)` setzt die Schriftart auf kursiv.
- `setFillType(FillType.Solid)` gibt an, dass der Legendeneintragstext eine einfarbige Füllung haben soll.
- `getSolidFillColor().setColor(Color.BLUE)` setzt die Füllfarbe auf Blau. Sie können ersetzen `Color.BLUE` mit Ihrer Wunschfarbe.

## Schritt 3: Speichern der geänderten Präsentation

Speichern Sie die geänderte Präsentation abschließend in einer neuen Datei, um Ihre Änderungen beizubehalten.

```java
pres.save(dataDir + "output.pptx", SaveFormat.Pptx);
```

Ersetzen `"output.pptx"` durch den von Ihnen bevorzugten Ausgabedateinamen.

Das war's! Sie haben die Schrifteigenschaften für einen einzelnen Legendeneintrag in einer Java Slides-Präsentation mit Aspose.Slides für Java erfolgreich angepasst.

## Vollständiger Quellcode für Schrifteigenschaften für einzelne Legenden in Java-Folien

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

In diesem Tutorial haben wir gelernt, wie Sie die Schrifteigenschaften einer einzelnen Legende in Java Slides mit Aspose.Slides für Java anpassen. Durch die Anpassung von Schriftarten, -größen und -farben können Sie die visuelle Attraktivität und Übersichtlichkeit Ihrer PowerPoint-Präsentationen verbessern.

## Häufig gestellte Fragen

### Wie kann ich die Schriftfarbe ändern?

Um die Schriftfarbe zu ändern, verwenden Sie `tf.getPortionFormat().getFontColor().setColor(yourColor)` anstatt die Füllfarbe zu ändern. Ersetzen `yourColor` mit der gewünschten Schriftfarbe.

### Wie ändere ich andere Legendeneigenschaften?

Sie können verschiedene weitere Eigenschaften der Legende ändern, z. B. Position, Größe und Format. Ausführliche Informationen zum Arbeiten mit Legenden finden Sie in der Dokumentation zu Aspose.Slides für Java.

### Kann ich diese Änderungen auf mehrere Legendeneinträge anwenden?

Ja, Sie können Legendeneinträge durchlaufen und diese Änderungen auf mehrere Einträge anwenden, indem Sie den Index in anpassen `get_Item(index)` und Wiederholen des Anpassungscodes.

Denken Sie daran, das Präsentationsobjekt zu entsorgen, wenn Sie mit der Freigabe der Ressourcen fertig sind:

```java
if (pres != null) pres.dispose();
```

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}