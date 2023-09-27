---
title: Holen Sie sich ein Diagrammbild in Java-Folien
linktitle: Holen Sie sich ein Diagrammbild in Java-Folien
second_title: Aspose.Slides Java PowerPoint-Verarbeitungs-API
description: Erfahren Sie, wie Sie mit Aspose.Slides für Java Diagrammbilder in Java Slides erhalten. Diese Schritt-für-Schritt-Anleitung bietet Quellcode und Tipps für eine nahtlose Integration.
type: docs
weight: 19
url: /de/java/data-manipulation/get-chart-image-java-slides/
---

## Einführung in das Abrufen von Diagrammbildern in Java-Folien

Aspose.Slides für Java ist eine leistungsstarke Bibliothek, mit der Sie programmgesteuert mit PowerPoint-Präsentationen arbeiten können. Mit dieser Bibliothek können Sie verschiedene Elemente aus Präsentationen, einschließlich Diagrammen, erstellen, bearbeiten und extrahieren. Eine häufige Anforderung besteht darin, Diagrammbilder von Folien zu erhalten. In diesem Handbuch zeigen wir, wie das geht.

## Voraussetzungen

Bevor wir uns mit dem Code befassen, stellen Sie sicher, dass die folgenden Voraussetzungen erfüllt sind:

- Java Development Kit (JDK) auf Ihrem System installiert.
-  Aspose.Slides für Java-Bibliothek heruntergeladen und in Ihrem Projekt konfiguriert. Sie können es herunterladen unter[Hier](https://releases.aspose.com/slides/java/).

## Schritt 1: Richten Sie Ihr Projekt ein

Erstellen Sie zunächst ein Java-Projekt in Ihrer bevorzugten integrierten Entwicklungsumgebung (IDE). Stellen Sie sicher, dass Sie die Aspose.Slides for Java-Bibliothek zu den Abhängigkeiten Ihres Projekts hinzugefügt haben.

## Schritt 2: Initialisieren Sie die Präsentation

Zunächst müssen Sie eine PowerPoint-Präsentation initialisieren. In diesem Beispiel gehen wir davon aus, dass Sie eine PowerPoint-Datei mit dem Namen „test.pptx“ in Ihrem Dokumentverzeichnis haben.

```java
// Der Pfad zum Dokumentenverzeichnis.
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "test.pptx");
```

## Schritt 3: Fügen Sie ein Diagramm hinzu und rufen Sie das Bild ab

Als Nächstes können Sie einer Folie ein Diagramm hinzufügen und dessen Bild abrufen. In diesem Beispiel fügen wir ein gruppiertes Säulendiagramm hinzu.

```java
try {
    IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 50, 50, 600, 400);
    BufferedImage img = chart.getThumbnail();
    ImageIO.write(img, ".png", new File(dataDir + "image.png"));
} finally {
    if (pres != null) pres.dispose();
}
```

In diesem Codeausschnitt erstellen wir ein gruppiertes Säulendiagramm auf der ersten Folie der Präsentation und rufen dann dessen Miniaturbild ab. Das Bild wird als „image.png“ im angegebenen Verzeichnis gespeichert.

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

Das Abrufen von Diagrammbildern aus Java Slides mit Aspose.Slides für Java ist ein unkomplizierter Prozess. Mit dem bereitgestellten Code können Sie diese Funktionalität einfach in Ihre Java-Anwendungen integrieren und so effektiv mit PowerPoint-Präsentationen arbeiten.

## FAQs

### Wie installiere ich Aspose.Slides für Java?

 Die Installation von Aspose.Slides für Java ist einfach. Sie können die Bibliothek herunterladen unter[Hier](https://releases.aspose.com/slides/java/)und befolgen Sie die Installationsanweisungen in der Dokumentation.

### Kann ich das Diagramm anpassen, bevor ich sein Bild erhalte?

Ja, Sie können das Erscheinungsbild, die Daten und andere Eigenschaften des Diagramms anpassen, bevor Sie das Bild erhalten. Aspose.Slides für Java bietet umfangreiche Optionen zur Diagrammanpassung.

### Welche weiteren Funktionen bietet Aspose.Slides für Java?

Aspose.Slides für Java bietet zahlreiche Funktionen für die Arbeit mit PowerPoint-Präsentationen, darunter Folienerstellung, Textbearbeitung, Formbearbeitung und vieles mehr. Detaillierte Informationen finden Sie in der Dokumentation.

### Ist Aspose.Slides für Java für die kommerzielle Nutzung geeignet?

Ja, Aspose.Slides für Java kann für kommerzielle Zwecke verwendet werden. Es bietet Lizenzoptionen, die sich sowohl an einzelne Entwickler als auch an Unternehmen richten.

### Kann ich das Diagrammbild in einem anderen Format speichern?

Sicherlich! Sie können das Diagrammbild in verschiedenen Formaten wie JPEG oder GIF speichern, indem Sie die entsprechende Dateierweiterung im angeben`ImageIO.write` Methode.