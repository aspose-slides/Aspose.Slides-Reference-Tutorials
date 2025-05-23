---
"description": "Erfahren Sie, wie Sie mit Aspose.Slides für Java die automatische Füllfarbe von Serien in Java Slides festlegen. Schritt-für-Schritt-Anleitung mit Codebeispielen für dynamische Präsentationen."
"linktitle": "Automatische Serienfüllfarbe in Java-Folien festlegen"
"second_title": "Aspose.Slides Java PowerPoint-Verarbeitungs-API"
"title": "Automatische Serienfüllfarbe in Java-Folien festlegen"
"url": "/de/java/data-manipulation/set-automatic-series-fill-color-java-slides/"
"weight": 14
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Automatische Serienfüllfarbe in Java-Folien festlegen


## Einführung zum Festlegen der automatischen Serienfüllfarbe in Java-Folien

In diesem Tutorial erfahren Sie, wie Sie mithilfe der Aspose.Slides für Java-API die automatische Füllfarbe für Serien in Java-Folien festlegen. Aspose.Slides für Java ist eine leistungsstarke Bibliothek, mit der Sie PowerPoint-Präsentationen programmgesteuert erstellen, bearbeiten und verwalten können. Nach Abschluss dieser Anleitung können Sie mühelos Diagramme erstellen und automatische Füllfarben für Serien festlegen.

## Voraussetzungen

Bevor wir uns in den Code vertiefen, stellen Sie sicher, dass die folgenden Voraussetzungen erfüllt sind:

- Auf Ihrem System ist das Java Development Kit (JDK) installiert.
- Aspose.Slides für Java-Bibliothek zu Ihrem Projekt hinzugefügt. Sie können es herunterladen von [Hier](https://releases.aspose.com/slides/java/).

Nachdem wir nun unsere Gliederung haben, beginnen wir mit der Schritt-für-Schritt-Anleitung.

## Schritt 1: Einführung in Aspose.Slides für Java

Aspose.Slides für Java ist eine Java-API, die Entwicklern die Arbeit mit PowerPoint-Präsentationen ermöglicht. Sie bietet zahlreiche Funktionen, darunter das Erstellen, Bearbeiten und Bearbeiten von Folien, Diagrammen, Formen und mehr.

## Schritt 2: Einrichten Ihres Java-Projekts

Bevor wir mit der Programmierung beginnen, stellen Sie sicher, dass Sie ein Java-Projekt in Ihrer bevorzugten integrierten Entwicklungsumgebung (IDE) eingerichtet haben. Fügen Sie Ihrem Projekt unbedingt die Bibliothek Aspose.Slides für Java hinzu.

## Schritt 3: Erstellen einer PowerPoint-Präsentation

Erstellen Sie zunächst eine neue PowerPoint-Präsentation mit dem folgenden Codeausschnitt:

```java
// Der Pfad zum Dokumentenverzeichnis.
String dataDir = "Your Document Directory";
Presentation presentation = new Presentation();
```

Ersetzen `"Your Document Directory"` durch den Pfad, in dem Sie die Präsentation speichern möchten.

## Schritt 4: Hinzufügen eines Diagramms zur Präsentation

Als Nächstes fügen wir der Präsentation ein gruppiertes Säulendiagramm hinzu. Dazu verwenden wir den folgenden Code:

```java
// Erstellen eines gruppierten Säulendiagramms
IChart chart = presentation.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 100, 50, 600, 400);
```

Dieser Code erstellt auf der ersten Folie der Präsentation ein gruppiertes Säulendiagramm.

## Schritt 5: Automatische Serienfüllfarbe einstellen

Jetzt kommt der entscheidende Teil: das Festlegen der automatischen Füllfarbe für Serien. Wir durchlaufen die Serien des Diagramms und stellen ihr Füllformat auf „Automatisch“ ein:

```java
// Festlegen des Serienfüllformats auf „Automatisch“
for (int i = 0; i < chart.getChartData().getSeries().size(); i++)
{
    chart.getChartData().getSeries().get_Item(i).getAutomaticSeriesColor();
}
```

Dieser Code stellt sicher, dass die Füllfarbe der Serie auf automatisch eingestellt ist.

## Schritt 6: Speichern der Präsentation

Um die Präsentation zu speichern, verwenden Sie den folgenden Code:

```java
// Schreiben Sie die Präsentationsdatei auf die Festplatte
presentation.save(dataDir + "AutoFillSeries_out.pptx", SaveFormat.Pptx);
```

Ersetzen `"AutoFillSeries_out.pptx"` durch den gewünschten Dateinamen.

## Vollständiger Quellcode zum Festlegen der automatischen Serienfüllfarbe in Java-Folien

```java
// Der Pfad zum Dokumentenverzeichnis.
String dataDir = "Your Document Directory";
Presentation presentation = new Presentation();
try
{
	// Erstellen eines gruppierten Säulendiagramms
	IChart chart = presentation.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 100, 50, 600, 400);
	// Festlegen des Serienfüllformats auf „Automatisch“
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

Herzlichen Glückwunsch! Sie haben mit Aspose.Slides für Java erfolgreich die automatische Serienfüllfarbe in einer Java-Folie festgelegt. Nutzen Sie dieses Wissen nun, um dynamische und optisch ansprechende PowerPoint-Präsentationen in Ihren Java-Anwendungen zu erstellen.

## Häufig gestellte Fragen

### Wie kann ich den Diagrammtyp in einen anderen Stil ändern?

Sie können den Diagrammtyp ändern, indem Sie `ChartType.ClusteredColumn` mit dem gewünschten Diagrammtyp, wie zum Beispiel `ChartType.Line` oder `ChartType.Pie`.

### Kann ich das Erscheinungsbild des Diagramms weiter anpassen?

Ja, Sie können das Erscheinungsbild des Diagramms anpassen, indem Sie verschiedene Eigenschaften des Diagramms ändern, z. B. Farben, Schriftarten und Beschriftungen.

### Ist Aspose.Slides für Java für die kommerzielle Nutzung geeignet?

Ja, Aspose.Slides für Java kann sowohl für private als auch für kommerzielle Projekte verwendet werden. Weitere Informationen finden Sie in den Lizenzbedingungen.

### Bietet Aspose.Slides für Java noch weitere Funktionen?

Ja, Aspose.Slides für Java bietet eine breite Palette an Funktionen, darunter Folienbearbeitung, Textformatierung und Animationsunterstützung.

### Wo finde ich weitere Ressourcen und Dokumentation?

Sie können auf die umfassende Dokumentation für Aspose.Slides für Java zugreifen unter [Hier](https://reference.aspose.com/slides/java/).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}