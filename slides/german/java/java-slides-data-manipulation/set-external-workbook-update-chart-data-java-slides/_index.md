---
title: Externe Arbeitsmappe mit aktualisierten Diagrammdaten in Java-Folien einrichten
linktitle: Externe Arbeitsmappe mit aktualisierten Diagrammdaten in Java-Folien einrichten
second_title: Aspose.Slides Java PowerPoint-Verarbeitungs-API
description: Erfahren Sie, wie Sie mit Aspose.Slides für Java externe Arbeitsmappen einrichten und Diagrammdaten in Java Slides aktualisieren. Verbessern Sie Ihre PowerPoint-Automatisierungsfähigkeiten.
weight: 20
url: /de/java/data-manipulation/set-external-workbook-update-chart-data-java-slides/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}


## Einführung in das Festlegen einer externen Arbeitsmappe mit aktualisierten Diagrammdaten in Java-Folien

In dieser umfassenden Anleitung führen wir Sie durch den Prozess zum Einrichten einer externen Arbeitsmappe mit aktualisierten Diagrammdaten in Java Slides mithilfe der Aspose.Slides für Java-API. Mit dieser leistungsstarken Bibliothek können Sie PowerPoint-Präsentationen programmgesteuert bearbeiten und Aufgaben wie das Aktualisieren von Diagrammdaten aus einer externen Quelle ganz einfach automatisieren. Am Ende dieses Tutorials haben Sie ein klares Verständnis dafür, wie Sie diese Aufgabe mit Schritt-für-Schritt-Anleitungen und begleitendem Java-Code erledigen können.

## Voraussetzungen

Bevor wir mit der Implementierung beginnen, stellen Sie sicher, dass die folgenden Voraussetzungen erfüllt sind:

1.  Aspose.Slides für Java: Sie sollten die Bibliothek Aspose.Slides für Java installiert haben. Sie können sie hier herunterladen:[Hier](https://releases.aspose.com/slides/java/).

2. Java-Entwicklungsumgebung: Stellen Sie sicher, dass auf Ihrem System eine Java-Entwicklungsumgebung eingerichtet ist.

## Schritt 1: Erstellen Sie eine neue Präsentation

Lassen Sie uns zunächst eine neue PowerPoint-Präsentation mit Aspose.Slides für Java erstellen. Hier ist der Java-Code dafür:

```java
// Der Pfad zum Dokumentverzeichnis.
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
```

## Schritt 2: Diagramm hinzufügen

Fügen wir nun unserer Präsentation ein Diagramm hinzu. In diesem Beispiel erstellen wir ein Kreisdiagramm:

```java
IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.Pie, 50, 50, 400, 600, true);
```

## Schritt 3: Externe Arbeitsmappe festlegen

Hier legen wir die externe Arbeitsmappe als Datenquelle für unser Diagramm fest. Sie müssen die URL zur externen Arbeitsmappe angeben, auch wenn diese derzeit noch nicht existiert:

```java
IChartData chartData = chart.getChartData();
chartData.setExternalWorkbook("http://Pfad/existiert/nicht", false);
```

## Schritt 4: Speichern Sie die Präsentation

Speichern Sie abschließend die Präsentation mit den aktualisierten Diagrammdaten:

```java
pres.save(dataDir + "SetExternalWorkbookWithUpdateChartData.pptx", SaveFormat.Pptx);
```

## Vollständiger Quellcode zum Festlegen eines externen Arbeitsbuchs mit aktualisierten Diagrammdaten in Java-Folien

```java
// Der Pfad zum Dokumentverzeichnis.
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

Herzlichen Glückwunsch! Sie haben gelernt, wie Sie mit Aspose.Slides für Java eine externe Arbeitsmappe mit aktualisierten Diagrammdaten in Java Slides einrichten. Dies kann unglaublich nützlich sein, um Diagramme in Ihren PowerPoint-Präsentationen dynamisch aus externen Datenquellen zu aktualisieren.

## Häufig gestellte Fragen

### Wie kann ich die externen Arbeitsmappendaten für das Diagramm aktualisieren?

Um die externen Arbeitsmappendaten für das Diagramm zu aktualisieren, müssen Sie lediglich die Daten in der externen Arbeitsmappe unter der angegebenen URL ändern. Wenn Sie die Präsentation das nächste Mal öffnen, ruft Aspose.Slides für Java die aktualisierten Daten aus der externen Arbeitsmappe ab und aktualisiert das Diagramm entsprechend.

### Kann ich eine lokale Datei als externe Arbeitsmappe verwenden?

Ja, Sie können eine lokale Datei als externe Arbeitsmappe verwenden, indem Sie den Dateipfad anstelle einer URL angeben. Stellen Sie einfach sicher, dass der Dateipfad korrekt ist und von Ihrer Java-Anwendung aus zugänglich ist.

### Gibt es Einschränkungen bei der Verwendung externer Arbeitsmappen mit Aspose.Slides für Java?

Obwohl die Verwendung externer Arbeitsmappen eine leistungsstarke Funktion ist, sollten Sie bedenken, dass die Verfügbarkeit der Daten der externen Arbeitsmappe von der Zugänglichkeit unter der angegebenen URL oder dem angegebenen Dateipfad abhängt. Stellen Sie sicher, dass die externe Datenquelle verfügbar ist, wenn Sie die Präsentation öffnen, um Probleme beim Datenabruf zu vermeiden.

### Kann ich das Erscheinungsbild des Diagramms anpassen, nachdem ich die externe Arbeitsmappe eingerichtet habe?

Ja, Sie können das Erscheinungsbild des Diagramms, einschließlich Titel, Beschriftungen, Farben und mehr, auch nach dem Einrichten der externen Arbeitsmappe anpassen. Aspose.Slides für Java bietet umfangreiche Diagrammformatierungsoptionen, die Ihren Anforderungen entsprechen.

### Wo finde ich weitere Dokumentation und Ressourcen für Aspose.Slides für Java?

 Ausführliche Dokumentation und zusätzliche Ressourcen finden Sie in der Aspose.Slides-Dokumentation für Java unter[Hier](https://reference.aspose.com/slides/java/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
