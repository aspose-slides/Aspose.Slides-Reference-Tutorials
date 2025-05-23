---
"description": "Erfahren Sie, wie Sie mit Aspose.Slides für Java Miniaturansichten mit Skalierungsfaktor in Java erstellen. Leicht verständliche Anleitung mit Schritt-für-Schritt-Anweisungen."
"linktitle": "Miniaturbild des Skalierungsfaktors erstellen"
"second_title": "Aspose.Slides Java PowerPoint-Verarbeitungs-API"
"title": "Miniaturbild des Skalierungsfaktors erstellen"
"url": "/de/java/java-powerpoint-shape-thumbnail-creation/create-scaling-factor-thumbnail/"
"weight": 12
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Miniaturbild des Skalierungsfaktors erstellen

## Einführung
In diesem Tutorial führen wir Sie durch die Erstellung einer Skalierungsvorschau mit Aspose.Slides für Java. Folgen Sie dieser Schritt-für-Schritt-Anleitung, um das gewünschte Ergebnis zu erzielen.
## Voraussetzungen
Stellen Sie vor dem Beginn sicher, dass die folgenden Voraussetzungen erfüllt sind:
- Auf Ihrem System ist das Java Development Kit (JDK) installiert.
- Aspose.Slides für die Java-Bibliothek heruntergeladen und in Ihrem Java-Projekt eingerichtet.
- Grundlegende Kenntnisse der Programmiersprache Java.

## Pakete importieren
Importieren Sie zunächst die erforderlichen Pakete, die für die Arbeit mit Aspose.Slides in Ihren Java-Code erforderlich sind. 
```java
import com.aspose.slides.Presentation;
import com.aspose.slides.ShapeThumbnailBounds;

import javax.imageio.ImageIO;
import java.awt.image.BufferedImage;
import java.io.File;
import java.io.IOException;
```

Lassen Sie uns nun das bereitgestellte Beispiel in mehrere Schritte unterteilen:
## Schritt 1: Dokumentverzeichnis festlegen
Definieren Sie den Pfad zu Ihrem Dokumentverzeichnis, in dem sich die PowerPoint-Präsentationsdatei befindet.
```java
String dataDir = "Your Document Directory";
```
Ersetzen `"Your Document Directory"` durch den Pfad zu Ihrem aktuellen Dokumentverzeichnis.
## Schritt 2: Instanziieren des Präsentationsobjekts
Erstellen Sie eine Instanz der Präsentationsklasse, um die PowerPoint-Präsentationsdatei darzustellen.
```java
Presentation p = new Presentation(dataDir + "HelloWorld.pptx");
```
Stellen Sie sicher, dass Sie `"HelloWorld.pptx"` durch den Namen Ihrer PowerPoint-Präsentationsdatei.
## Schritt 3: Bild im Originalmaßstab erstellen
Erstellen Sie aus der Präsentation ein maßstabsgetreues Bild der gewünschten Folie.
```java
BufferedImage bitmap = p.getSlides().get_Item(0).getShapes().get_Item(0).getThumbnail(ShapeThumbnailBounds.Shape, 1, 1);
```
Dieser Code ruft die Miniaturansicht der ersten Form auf der ersten Folie der Präsentation ab.
## Schritt 4: Speichern Sie das Bild
Speichern Sie das generierte Bild im PNG-Format auf der Festplatte.
```java
ImageIO.write(bitmap, ".png", new File(dataDir + "Scaling Factor Thumbnail_out.png"));
```
Stellen Sie sicher, dass Sie `"Scaling Factor Thumbnail_out.png"` durch den gewünschten Ausgabedateinamen.

## Abschluss
Abschließend haben Sie mit Aspose.Slides für Java erfolgreich ein Miniaturbild mit Skalierungsfaktor erstellt. Mit den angegebenen Schritten können Sie diese Funktionalität problemlos in Ihre Java-Anwendungen integrieren.
## Häufig gestellte Fragen
### Kann ich Aspose.Slides für Java mit jeder Java-IDE verwenden?
Ja, Aspose.Slides für Java kann mit jeder integrierten Java-Entwicklungsumgebung (IDE) wie Eclipse, IntelliJ IDEA oder NetBeans verwendet werden.
### Gibt es eine kostenlose Testversion für Aspose.Slides für Java?
Ja, Sie können eine kostenlose Testversion von Aspose.Slides für Java nutzen, indem Sie die [Webseite](https://releases.aspose.com/).
### Wo finde ich Unterstützung für Aspose.Slides für Java?
Support für Aspose.Slides für Java finden Sie auf der [Aspose.Slides-Forum](https://forum.aspose.com/c/slides/11).
### Wie kann ich Aspose.Slides für Java kaufen?
Sie können Aspose.Slides für Java von der [Kaufseite](https://purchase.aspose.com/buy).
### Benötige ich eine temporäre Lizenz, um Aspose.Slides für Java zu verwenden?
Ja, Sie können eine vorläufige Lizenz erhalten von der [Seite mit temporärer Lizenz](https://purchase.aspose.com/temporary-license/).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}