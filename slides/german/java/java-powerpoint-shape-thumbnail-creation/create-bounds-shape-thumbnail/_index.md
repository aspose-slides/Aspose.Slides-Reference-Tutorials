---
title: Begrenzungsform-Vorschaubild erstellen
linktitle: Begrenzungsform-Vorschaubild erstellen
second_title: Aspose.Slides Java PowerPoint-Verarbeitungs-API
description: Erfahren Sie, wie Sie mit Aspose.Slides für Java Miniaturansichten von Formen mit Begrenzungen erstellen. Dieses Schritt-für-Schritt-Tutorial führt Sie durch den Vorgang.
weight: 10
url: /de/java/java-powerpoint-shape-thumbnail-creation/create-bounds-shape-thumbnail/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Begrenzungsform-Vorschaubild erstellen

## Einführung
Aspose.Slides für Java ist eine leistungsstarke Bibliothek, mit der Java-Entwickler PowerPoint-Präsentationen programmgesteuert erstellen, bearbeiten und konvertieren können. In diesem Tutorial erfahren Sie, wie Sie mit Aspose.Slides für Java ein Miniaturbild einer Form mit Begrenzungen erstellen.
## Voraussetzungen
Bevor Sie beginnen, stellen Sie sicher, dass Sie über Folgendes verfügen:
1. Auf Ihrem System ist Java Development Kit (JDK) installiert.
2.  Aspose.Slides für Java-Bibliothek heruntergeladen und zu Ihrem Projekt hinzugefügt. Sie können es herunterladen von[Hier](https://releases.aspose.com/slides/java/).

## Pakete importieren
Stellen Sie sicher, dass Sie die erforderlichen Pakete in Ihren Java-Code importieren:
```java
import com.aspose.slides.Presentation;
import com.aspose.slides.ShapeThumbnailBounds;

import javax.imageio.ImageIO;
import java.awt.image.BufferedImage;
import java.io.File;
import java.io.IOException;
```
## Schritt 1: Richten Sie Ihr Projekt ein
Erstellen Sie ein neues Java-Projekt in Ihrer bevorzugten IDE und fügen Sie die Bibliothek Aspose.Slides für Java zu den Abhängigkeiten Ihres Projekts hinzu.
## Schritt 2: Instanziieren eines Präsentationsobjekts
 Instanziieren Sie einen`Presentation` Objekt, indem Sie den Pfad zu Ihrer PowerPoint-Präsentationsdatei angeben.
```java
String dataDir = "Your Document Directory";
Presentation presentation = new Presentation(dataDir + "HelloWorld.pptx");
```
## Schritt 3: Miniaturbild der Begrenzungsform erstellen
Erstellen wir nun ein Miniaturbild einer Form mit Grenzen aus der Präsentation.
```java
try {
    BufferedImage bitmap = presentation.getSlides().get_Item(0).getShapes().get_Item(0).getThumbnail(ShapeThumbnailBounds.Appearance, 1, 1);
    ImageIO.write(bitmap, ".png", new File(dataDir + "Shape_thumbnail_Bound_Shape_out.png"));
} finally {
    if (presentation != null) presentation.dispose();
}
```

## Abschluss
In diesem Tutorial haben wir gelernt, wie man mit Aspose.Slides für Java ein Miniaturbild einer Form mit Begrenzungen erstellt. Indem Sie diese Schritte befolgen, können Sie ganz einfach programmgesteuert Miniaturbilder von Formen in Ihren PowerPoint-Präsentationen erstellen.
## Häufig gestellte Fragen
### Kann ich Miniaturansichten für bestimmte Formen innerhalb einer Folie erstellen?
Ja, Sie können auf einzelne Formen innerhalb einer Folie zugreifen und mit Aspose.Slides für Java Miniaturansichten dafür generieren.
### Ist Aspose.Slides für Java mit allen Versionen von PowerPoint-Dateien kompatibel?
Aspose.Slides für Java unterstützt verschiedene PowerPoint-Dateiformate, darunter PPT, PPTX, PPS, PPSX und mehr.
### Kann ich das Erscheinungsbild der generierten Miniaturbilder anpassen?
Ja, Sie können die Eigenschaften der Miniaturbilder wie Größe und Qualität Ihren Anforderungen entsprechend anpassen.
### Unterstützt Aspose.Slides für Java neben der Miniaturbildgenerierung noch andere Funktionen?
Ja, Aspose.Slides für Java bietet umfangreiche Funktionen für die Arbeit mit PowerPoint-Präsentationen, einschließlich Folienbearbeitung, Textextraktion und Diagrammerstellung.
### Gibt es eine Testversion von Aspose.Slides für Java?
 Ja, Sie können eine kostenlose Testversion herunterladen von[Hier](https://releases.aspose.com/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
