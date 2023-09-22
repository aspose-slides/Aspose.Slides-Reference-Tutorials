---
title: Legen Sie die automatische Reihenfüllfarbe in Java-Folien fest
linktitle: Legen Sie die automatische Reihenfüllfarbe in Java-Folien fest
second_title: Aspose.Slides Java PowerPoint-Verarbeitungs-API
description: Erfahren Sie, wie Sie mit Aspose.Slides für Java die automatische Serienfüllfarbe in Java Slides festlegen. Schritt-für-Schritt-Anleitung mit Codebeispielen für dynamische Präsentationen.
type: docs
weight: 14
url: /de/java/data-manipulation/set-automatic-series-fill-color-java-slides/
---

## Einführung in das Festlegen der automatischen Reihenfüllfarbe in Java-Folien

In diesem Tutorial erfahren Sie, wie Sie mithilfe der Aspose.Slides für Java-API die automatische Serienfüllfarbe in Java Slides festlegen. Aspose.Slides für Java ist eine leistungsstarke Bibliothek, mit der Sie PowerPoint-Präsentationen programmgesteuert erstellen, bearbeiten und verwalten können. Am Ende dieses Leitfadens werden Sie mühelos in der Lage sein, Diagramme zu erstellen und automatische Reihenfüllfarben festzulegen.

## Voraussetzungen

Bevor wir uns mit dem Code befassen, stellen Sie sicher, dass die folgenden Voraussetzungen erfüllt sind:

- Java Development Kit (JDK) auf Ihrem System installiert.
-  Aspose.Slides für Java-Bibliothek zu Ihrem Projekt hinzugefügt. Sie können es herunterladen unter[Hier](https://releases.aspose.com/slides/java/).

Nachdem wir nun unsere Gliederung erstellt haben, beginnen wir mit der Schritt-für-Schritt-Anleitung.

## Schritt 1: Einführung in Aspose.Slides für Java

Aspose.Slides für Java ist eine Java-API, die es Entwicklern ermöglicht, mit PowerPoint-Präsentationen zu arbeiten. Es bietet eine breite Palette an Funktionen, darunter das Erstellen, Bearbeiten und Bearbeiten von Folien, Diagrammen, Formen und mehr.

## Schritt 2: Einrichten Ihres Java-Projekts

Bevor wir mit dem Codieren beginnen, stellen Sie sicher, dass Sie ein Java-Projekt in Ihrer bevorzugten integrierten Entwicklungsumgebung (IDE) eingerichtet haben. Stellen Sie sicher, dass Sie die Aspose.Slides for Java-Bibliothek zu Ihrem Projekt hinzufügen.

## Schritt 3: Erstellen einer PowerPoint-Präsentation

Erstellen Sie zunächst eine neue PowerPoint-Präsentation mit dem folgenden Codeausschnitt:

```java
// Der Pfad zum Dokumentenverzeichnis.
String dataDir = "Your Document Directory";
Presentation presentation = new Presentation();
```

 Ersetzen`"Your Document Directory"` mit dem Pfad, in dem Sie die Präsentation speichern möchten.

## Schritt 4: Hinzufügen eines Diagramms zur Präsentation

Als Nächstes fügen wir der Präsentation ein gruppiertes Säulendiagramm hinzu. Um dies zu erreichen, verwenden wir den folgenden Code:

```java
// Erstellen eines gruppierten Säulendiagramms
IChart chart = presentation.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 100, 50, 600, 400);
```

Dieser Code erstellt ein gruppiertes Säulendiagramm auf der ersten Folie der Präsentation.

## Schritt 5: Einstellen der automatischen Serienfüllfarbe

Jetzt kommt der entscheidende Teil – das Festlegen der automatischen Serienfüllfarbe. Wir durchlaufen die Diagrammreihen und stellen deren Füllformat auf „Automatisch“ ein:

```java
// Serienfüllformat auf „Automatisch“ einstellen
for (int i = 0; i < chart.getChartData().getSeries().size(); i++)
{
    chart.getChartData().getSeries().get_Item(i).getAutomaticSeriesColor();
}
```

Dieser Code stellt sicher, dass die Füllfarbe der Serie auf „Automatisch“ eingestellt ist.

## Schritt 6: Speichern der Präsentation

Um die Präsentation zu speichern, verwenden Sie den folgenden Code:

```java
// Schreiben Sie die Präsentationsdatei auf die Festplatte
presentation.save(dataDir + "AutoFillSeries_out.pptx", SaveFormat.Pptx);
```

 Ersetzen`"AutoFillSeries_out.pptx"` mit dem gewünschten Dateinamen.

## Vollständiger Quellcode zum Festlegen der automatischen Reihenfüllfarbe in Java-Folien

```java
// Der Pfad zum Dokumentenverzeichnis.
String dataDir = "Your Document Directory";
Presentation presentation = new Presentation();
try
{
	// Erstellen eines gruppierten Säulendiagramms
	IChart chart = presentation.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 100, 50, 600, 400);
	// Serienfüllformat auf „Automatisch“ einstellen
	for (int i = 0; i < chart.getChartData().getSeries().size(); i++)
	{
		chart.getChartData().getSeries().get_Item(i).getAutomaticSeriesColor();
	}
	// Schreiben Sie die Präsentationsdatei auf die Festplatte
	presentation.save(dataDir + "AutoFillSeries_out.pptx", SaveFormat.Pptx);
}
finally
{
	if (presentation != null) presentation.dispose();
}
```

## Abschluss

Glückwunsch! Sie haben mit Aspose.Slides für Java erfolgreich die automatische Reihenfüllfarbe in einer Java-Folie festgelegt. Dieses Wissen können Sie nun nutzen, um dynamische und optisch ansprechende PowerPoint-Präsentationen in Ihren Java-Anwendungen zu erstellen.

## FAQs

### Wie kann ich den Diagrammtyp in einen anderen Stil ändern?

 Sie können den Diagrammtyp durch Ersetzen ändern`ChartType.ClusteredColumn` mit dem gewünschten Diagrammtyp, z`ChartType.Line` oder`ChartType.Pie`.

### Kann ich das Erscheinungsbild des Diagramms weiter anpassen?

Ja, Sie können das Erscheinungsbild des Diagramms anpassen, indem Sie verschiedene Eigenschaften des Diagramms ändern, z. B. Farben, Schriftarten und Beschriftungen.

### Ist Aspose.Slides für Java für die kommerzielle Nutzung geeignet?

Ja, Aspose.Slides für Java kann sowohl für persönliche als auch für kommerzielle Projekte verwendet werden. Weitere Einzelheiten finden Sie in den Lizenzbedingungen.

### Gibt es weitere Funktionen von Aspose.Slides für Java?

Ja, Aspose.Slides für Java bietet eine breite Palette an Funktionen, einschließlich Folienmanipulation, Textformatierung und Animationsunterstützung.

### Wo finde ich weitere Ressourcen und Dokumentation?

 Eine umfassende Dokumentation zu Aspose.Slides für Java finden Sie unter[Hier](https://reference.aspose.com/slides/java/).