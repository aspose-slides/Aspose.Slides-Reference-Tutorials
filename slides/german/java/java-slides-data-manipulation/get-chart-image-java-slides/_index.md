---
"description": "Erfahren Sie, wie Sie mit Aspose.Slides für Java Diagrammbilder in Java Slides erstellen. Diese Schritt-für-Schritt-Anleitung enthält Quellcode und Tipps für eine nahtlose Integration."
"linktitle": "Diagrammbild in Java-Folien abrufen"
"second_title": "Aspose.Slides Java PowerPoint-Verarbeitungs-API"
"title": "Diagrammbild in Java-Folien abrufen"
"url": "/de/java/data-manipulation/get-chart-image-java-slides/"
"weight": 19
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Diagrammbild in Java-Folien abrufen


## Einführung zum Abrufen von Diagrammbildern in Java-Folien

Aspose.Slides für Java ist eine leistungsstarke Bibliothek, mit der Sie programmgesteuert mit PowerPoint-Präsentationen arbeiten können. Mit dieser Bibliothek können Sie verschiedene Elemente aus Präsentationen, einschließlich Diagrammen, erstellen, bearbeiten und extrahieren. Eine häufige Anforderung besteht darin, Diagrammbilder aus Folien zu extrahieren. In dieser Anleitung zeigen wir Ihnen, wie das geht.

## Voraussetzungen

Bevor wir uns in den Code vertiefen, stellen Sie sicher, dass die folgenden Voraussetzungen erfüllt sind:

- Auf Ihrem System ist das Java Development Kit (JDK) installiert.
- Aspose.Slides für Java-Bibliothek heruntergeladen und in Ihrem Projekt konfiguriert. Sie können es herunterladen von [Hier](https://releases.aspose.com/slides/java/).

## Schritt 1: Richten Sie Ihr Projekt ein

Erstellen Sie zunächst ein Java-Projekt in Ihrer bevorzugten integrierten Entwicklungsumgebung (IDE). Stellen Sie sicher, dass Sie die Bibliothek Aspose.Slides für Java zu den Abhängigkeiten Ihres Projekts hinzugefügt haben.

## Schritt 2: Initialisieren der Präsentation

Zunächst müssen Sie eine PowerPoint-Präsentation initialisieren. In diesem Beispiel gehen wir davon aus, dass sich in Ihrem Dokumentverzeichnis eine PowerPoint-Datei mit dem Namen „test.pptx“ befindet.

```java
// Der Pfad zum Dokumentenverzeichnis.
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "test.pptx");
```

## Schritt 3: Fügen Sie ein Diagramm hinzu und holen Sie sich das Bild

Anschließend können Sie einer Folie ein Diagramm hinzufügen und dessen Bild abrufen. In diesem Beispiel fügen wir ein gruppiertes Säulendiagramm hinzu.

```java
try {
    IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 50, 50, 600, 400);
    BufferedImage img = chart.getThumbnail();
    ImageIO.write(img, ".png", new File(dataDir + "image.png"));
} finally {
    if (pres != null) pres.dispose();
}
```

In diesem Codeausschnitt erstellen wir auf der ersten Folie der Präsentation ein gruppiertes Säulendiagramm und erhalten anschließend dessen Miniaturbild. Das Bild wird als „image.png“ im angegebenen Verzeichnis gespeichert.

## Vollständiger Quellcode zum Abrufen von Diagrammbildern in Java-Folien

```java
// Der Pfad zum Dokumentenverzeichnis.
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "test.pptx");
try
{
	IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 50, 50, 600, 400);
	BufferedImage img = chart.getThumbnail();
	ImageIO.write(img, ".png", new File(dataDir + "image.png"));
}
finally
{
	if (pres != null) pres.dispose();
}
```

## Abschluss

Das Abrufen von Diagrammbildern aus Java-Folien mit Aspose.Slides für Java ist unkompliziert. Mit dem bereitgestellten Code können Sie diese Funktionalität problemlos in Ihre Java-Anwendungen integrieren und so effektiv mit PowerPoint-Präsentationen arbeiten.

## Häufig gestellte Fragen

### Wie installiere ich Aspose.Slides für Java?

Die Installation von Aspose.Slides für Java ist einfach. Sie können die Bibliothek herunterladen von [Hier](https://releases.aspose.com/slides/java/) und befolgen Sie die Installationsanweisungen in der Dokumentation.

### Kann ich das Diagramm anpassen, bevor ich sein Bild erhalte?

Ja, Sie können das Erscheinungsbild, die Daten und andere Eigenschaften des Diagramms anpassen, bevor Sie das Bild erhalten. Aspose.Slides für Java bietet umfangreiche Optionen zur Diagrammanpassung.

### Welche weiteren Funktionen bietet Aspose.Slides für Java?

Aspose.Slides für Java bietet zahlreiche Funktionen für die Arbeit mit PowerPoint-Präsentationen, darunter Folienerstellung, Textbearbeitung, Formbearbeitung und vieles mehr. Detaillierte Informationen finden Sie in der Dokumentation.

### Ist Aspose.Slides für Java für die kommerzielle Nutzung geeignet?

Ja, Aspose.Slides für Java kann kommerziell genutzt werden. Es bietet Lizenzoptionen, die sowohl für Einzelentwickler als auch für Unternehmen geeignet sind.

### Kann ich das Diagrammbild in einem anderen Format speichern?

Sicher! Sie können das Diagrammbild in verschiedenen Formaten wie JPEG oder GIF speichern, indem Sie die entsprechende Dateierweiterung im `ImageIO.write` Verfahren.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}