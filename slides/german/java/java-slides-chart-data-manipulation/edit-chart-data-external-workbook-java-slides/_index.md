---
"description": "Erfahren Sie, wie Sie Diagrammdaten in einer externen Arbeitsmappe mit Aspose.Slides für Java bearbeiten. Schritt-für-Schritt-Anleitung mit Quellcode."
"linktitle": "Bearbeiten Sie Diagrammdaten in einer externen Arbeitsmappe in Java Slides"
"second_title": "Aspose.Slides Java PowerPoint-Verarbeitungs-API"
"title": "Bearbeiten Sie Diagrammdaten in einer externen Arbeitsmappe in Java Slides"
"url": "/de/java/chart-data-manipulation/edit-chart-data-external-workbook-java-slides/"
"weight": 17
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Bearbeiten Sie Diagrammdaten in einer externen Arbeitsmappe in Java Slides


## Einführung in das Bearbeiten von Diagrammdaten in externen Arbeitsmappen in Java-Folien

In dieser Anleitung zeigen wir Ihnen, wie Sie Diagrammdaten in einer externen Arbeitsmappe mit Aspose.Slides für Java bearbeiten. Sie erfahren, wie Sie Diagrammdaten in einer PowerPoint-Präsentation programmgesteuert ändern. Stellen Sie sicher, dass die Aspose.Slides-Bibliothek für Java in Ihrem Projekt installiert und konfiguriert ist.

## Voraussetzungen

- Aspose.Slides für Java
- Java-Entwicklungsumgebung

## Schritt 1: Laden Sie die Präsentation

Zuerst müssen wir die PowerPoint-Präsentation laden, die das Diagramm enthält, dessen Daten wir bearbeiten möchten. Ersetzen `"Your Document Directory"` durch den tatsächlichen Pfad zu Ihrer Präsentationsdatei.

```java
// Der Pfad zum Dokumentenverzeichnis.
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "presentation.pptx");
```

## Schritt 2: Zugriff auf das Diagramm

Sobald die Präsentation geladen ist, müssen wir innerhalb der Präsentation auf das Diagramm zugreifen. In diesem Beispiel gehen wir davon aus, dass sich das Diagramm auf der ersten Folie befindet und die erste Form auf dieser Folie darstellt.

```java
IChart chart = (IChart) pres.getSlides().get_Item(0).getShapes().get_Item(0);
```

## Schritt 3: Diagrammdaten ändern

Ändern wir nun die Diagrammdaten. Wir konzentrieren uns auf die Änderung eines bestimmten Datenpunkts im Diagramm. In diesem Beispiel setzen wir den Wert des ersten Datenpunkts in der ersten Reihe auf 100. Sie können diesen Wert nach Bedarf anpassen.

```java
ChartData chartData = (ChartData) chart.getChartData();
chartData.getSeries().get_Item(0).getDataPoints().get_Item(0).getValue().getAsCell().setValue(100);
```

## Schritt 4: Speichern Sie die Präsentation

Nachdem Sie die erforderlichen Änderungen an den Diagrammdaten vorgenommen haben, speichern Sie die geänderte Präsentation in einer neuen Datei. Sie können den Ausgabedateipfad und das Format entsprechend Ihren Anforderungen festlegen.

```java
pres.save("output.pptx", SaveFormat.Pptx);
```

## Schritt 5: Aufräumen

Vergessen Sie nicht, das Präsentationsobjekt zu entsorgen, um Ressourcen freizugeben.

```java
if (pres != null) pres.dispose();
```

Sie haben die Diagrammdaten nun erfolgreich in einer externen Arbeitsmappe innerhalb Ihrer PowerPoint-Präsentation mit Aspose.Slides für Java bearbeitet. Sie können diesen Code an Ihre spezifischen Bedürfnisse anpassen und in Ihre Java-Anwendungen integrieren.

## Vollständiger Quellcode

```java
        // Beachten Sie, dass der Pfad zur externen Arbeitsmappe in der Präsentation kaum gespeichert wird.
        // Kopieren Sie daher bitte die Datei externalWorkbook.xlsx aus dem Daten-/Diagrammverzeichnis D:\Aspose.Slides\Aspose.Slides-for-.NET-master\Examples\Data\Charts\, bevor Sie das Beispiel ausführen
        // Der Pfad zum Dokumentenverzeichnis.
        String dataDir = "Your Document Directory";
        Presentation pres = new Presentation(dataDir + "presentation.pptx");
        try
        {
            IChart chart = (IChart) pres.getSlides().get_Item(0).getShapes().get_Item(0);
            ChartData chartData = (ChartData) chart.getChartData();
            chartData.getSeries().get_Item(0).getDataPoints().get_Item(0).getValue().getAsCell().setValue(100);
            pres.save("Your Output Directory" + "presentation_out.pptx", SaveFormat.Pptx);
        }
        finally
        {
            if (pres != null) pres.dispose();
        }
```
## Abschluss

In dieser umfassenden Anleitung haben wir untersucht, wie Sie Diagrammdaten in externen Arbeitsmappen in PowerPoint-Präsentationen mit Aspose.Slides für Java bearbeiten. Durch Befolgen der Schritt-für-Schritt-Anleitungen und Quellcodebeispiele haben Sie das Wissen und die Fähigkeiten erworben, Diagrammdaten problemlos programmgesteuert zu ändern.

## Häufig gestellte Fragen

### Wie gebe ich ein anderes Diagramm oder eine andere Folie an?

Um auf ein anderes Diagramm oder eine andere Folie zuzugreifen, ändern Sie den entsprechenden Index in der `getSlides().get_Item()` Und `getShapes().get_Item()` Methoden. Denken Sie daran, dass die Indizierung bei 0 beginnt.

### Kann ich Daten in mehreren Diagrammen innerhalb derselben Präsentation bearbeiten?

Ja, Sie können Daten in mehreren Diagrammen innerhalb derselben Präsentation bearbeiten, indem Sie die Schritte zum Ändern der Diagrammdaten für jedes Diagramm wiederholen.

### Was ist, wenn ich Daten in einer externen Arbeitsmappe mit einem anderen Format bearbeiten möchte?

Sie können den Code anpassen, um verschiedene externe Arbeitsmappenformate zu verarbeiten, indem Sie die entsprechenden Aspose.Cells-Klassen und -Methoden zum Lesen und Schreiben von Daten in diesem Format verwenden.

### Wie kann ich diesen Prozess für mehrere Präsentationen automatisieren?

Sie können eine Schleife erstellen, um mehrere Präsentationen zu verarbeiten, indem Sie jede einzelne laden, die gewünschten Änderungen vornehmen und die geänderten Präsentationen nacheinander speichern.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}