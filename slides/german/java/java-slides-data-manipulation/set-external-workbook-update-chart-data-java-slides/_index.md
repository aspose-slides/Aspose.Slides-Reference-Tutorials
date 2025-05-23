---
"description": "Erfahren Sie, wie Sie mit Aspose.Slides für Java externe Arbeitsmappen einrichten und Diagrammdaten in Java Slides aktualisieren. Verbessern Sie Ihre PowerPoint-Automatisierungsfähigkeiten."
"linktitle": "Externe Arbeitsmappe mit aktualisierten Diagrammdaten in Java-Folien einrichten"
"second_title": "Aspose.Slides Java PowerPoint-Verarbeitungs-API"
"title": "Externe Arbeitsmappe mit aktualisierten Diagrammdaten in Java-Folien einrichten"
"url": "/de/java/data-manipulation/set-external-workbook-update-chart-data-java-slides/"
"weight": 20
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Externe Arbeitsmappe mit aktualisierten Diagrammdaten in Java-Folien einrichten


## Einführung in das Festlegen einer externen Arbeitsmappe mit aktualisierten Diagrammdaten in Java-Folien

In dieser umfassenden Anleitung führen wir Sie durch die Einrichtung einer externen Arbeitsmappe mit aktualisierten Diagrammdaten in Java Slides mithilfe der Aspose.Slides für Java API. Diese leistungsstarke Bibliothek ermöglicht Ihnen die programmgesteuerte Bearbeitung von PowerPoint-Präsentationen und vereinfacht die Automatisierung von Aufgaben wie der Aktualisierung von Diagrammdaten aus einer externen Quelle. Am Ende dieses Tutorials verstehen Sie dies anhand einer Schritt-für-Schritt-Anleitung und des zugehörigen Java-Codes.

## Voraussetzungen

Bevor wir mit der Implementierung beginnen, stellen Sie sicher, dass die folgenden Voraussetzungen erfüllt sind:

1. Aspose.Slides für Java: Sie sollten die Bibliothek Aspose.Slides für Java installiert haben. Sie können sie herunterladen von [Hier](https://releases.aspose.com/slides/java/).

2. Java-Entwicklungsumgebung: Stellen Sie sicher, dass auf Ihrem System eine Java-Entwicklungsumgebung eingerichtet ist.

## Schritt 1: Erstellen Sie eine neue Präsentation

Erstellen wir zunächst eine neue PowerPoint-Präsentation mit Aspose.Slides für Java. Hier ist der Java-Code dafür:

```java
// Der Pfad zum Dokumentenverzeichnis.
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
```

## Schritt 2: Diagramm hinzufügen

Fügen wir nun unserer Präsentation ein Diagramm hinzu. In diesem Beispiel erstellen wir ein Kreisdiagramm:

```java
IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.Pie, 50, 50, 400, 600, true);
```

## Schritt 3: Externe Arbeitsmappe festlegen

Hier legen wir die externe Arbeitsmappe als Datenquelle für unser Diagramm fest. Sie müssen die URL zur externen Arbeitsmappe angeben, auch wenn diese noch nicht existiert:

```java
IChartData chartData = chart.getChartData();
chartData.setExternalWorkbook("http://Pfad/existiert/nicht", false);
```

## Schritt 4: Speichern Sie die Präsentation

Speichern Sie abschließend die Präsentation mit den aktualisierten Diagrammdaten:

```java
pres.save(dataDir + "SetExternalWorkbookWithUpdateChartData.pptx", SaveFormat.Pptx);
```

## Vollständiger Quellcode zum Festlegen einer externen Arbeitsmappe mit aktualisierten Diagrammdaten in Java-Folien

```java
// Der Pfad zum Dokumentenverzeichnis.
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
try
{
	IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.Pie, 50, 50, 400, 600, true);
	IChartData chartData = chart.getChartData();
	chartData.setExternalWorkbook("http://Pfad/existiert/nicht", false);
	pres.save(dataDir + "SetExternalWorkbookWithUpdateChartData.pptx", SaveFormat.Pptx);
}
finally
{
	if (pres != null) pres.dispose();
}
```

## Abschluss

Herzlichen Glückwunsch! Sie haben gelernt, wie Sie mithilfe von Aspose.Slides für Java eine externe Arbeitsmappe mit aktualisierten Diagrammdaten in Java Slides einrichten. Dies ist äußerst nützlich, um Diagramme in Ihren PowerPoint-Präsentationen dynamisch aus externen Datenquellen zu aktualisieren.

## Häufig gestellte Fragen

### Wie kann ich die externen Arbeitsmappendaten für das Diagramm aktualisieren?

Um die Daten der externen Arbeitsmappe für das Diagramm zu aktualisieren, müssen Sie lediglich die Daten in der externen Arbeitsmappe unter der angegebenen URL ändern. Beim nächsten Öffnen der Präsentation ruft Aspose.Slides für Java die aktualisierten Daten aus der externen Arbeitsmappe ab und aktualisiert das Diagramm entsprechend.

### Kann ich eine lokale Datei als externe Arbeitsmappe verwenden?

Ja, Sie können eine lokale Datei als externe Arbeitsmappe verwenden, indem Sie den Dateipfad anstelle einer URL angeben. Stellen Sie lediglich sicher, dass der Dateipfad korrekt und von Ihrer Java-Anwendung aus zugänglich ist.

### Gibt es Einschränkungen bei der Verwendung externer Arbeitsmappen mit Aspose.Slides für Java?

Die Verwendung externer Arbeitsmappen ist zwar eine leistungsstarke Funktion, die Verfügbarkeit der Daten der externen Arbeitsmappe hängt jedoch von der Verfügbarkeit unter der angegebenen URL oder dem angegebenen Dateipfad ab. Stellen Sie sicher, dass die externe Datenquelle beim Öffnen der Präsentation verfügbar ist, um Probleme beim Datenabruf zu vermeiden.

### Kann ich das Erscheinungsbild des Diagramms anpassen, nachdem ich die externe Arbeitsmappe eingerichtet habe?

Ja, Sie können das Erscheinungsbild des Diagramms, einschließlich Titel, Beschriftungen, Farben und mehr, auch nach dem Einrichten der externen Arbeitsmappe anpassen. Aspose.Slides für Java bietet umfangreiche Diagrammformatierungsoptionen, die Ihren Anforderungen gerecht werden.

### Wo finde ich weitere Dokumentation und Ressourcen für Aspose.Slides für Java?

Ausführliche Dokumentation und zusätzliche Ressourcen finden Sie in der Aspose.Slides-Dokumentation für Java unter [Hier](https://reference.aspose.com/slides/java/).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}