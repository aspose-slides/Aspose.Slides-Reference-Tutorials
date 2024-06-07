---
title: Skalierungsfaktor-Vorschaubild erstellen
linktitle: Skalierungsfaktor-Vorschaubild erstellen
second_title: Aspose.Slides Java PowerPoint-Verarbeitungs-API
description: Erfahren Sie, wie Sie mit Aspose.Slides für Java Miniaturansichten mit Skalierungsfaktor in Java erstellen. Einfach verständliche Anleitung mit Schritt-für-Schritt-Anweisungen.
type: docs
weight: 12
url: /de/java/java-powerpoint-shape-thumbnail-creation/create-scaling-factor-thumbnail/
---
## Einführung
In diesem Tutorial führen wir Sie durch den Prozess der Erstellung einer Miniaturansicht mit Skalierungsfaktor mithilfe von Aspose.Slides für Java. Befolgen Sie diese Schritt-für-Schritt-Anleitung, um das gewünschte Ergebnis zu erzielen.
## Voraussetzungen
Stellen Sie zunächst sicher, dass die folgenden Voraussetzungen erfüllt sind:
- Auf Ihrem System ist Java Development Kit (JDK) installiert.
- Aspose.Slides für die Java-Bibliothek heruntergeladen und in Ihrem Java-Projekt eingerichtet.
- Grundlegende Kenntnisse der Programmiersprache Java.

## Pakete importieren
Importieren Sie zunächst die erforderlichen Pakete, die für die Arbeit mit Aspose.Slides in Ihren Java-Code erforderlich sind. 
```java
import com.aspose.slides.Presentation;
import com.aspose.slides.ShapeThumbnailBounds;
import com.aspose.slides.examples.RunExamples;
import javax.imageio.ImageIO;
import java.awt.image.BufferedImage;
import java.io.File;
import java.io.IOException;
```

Lassen Sie uns nun das bereitgestellte Beispiel in mehrere Schritte aufteilen:
## Schritt 1: Dokumentverzeichnis festlegen
Geben Sie den Pfad zu Ihrem Dokumentverzeichnis an, in dem sich die PowerPoint-Präsentationsdatei befindet.
```java
String dataDir = "Your Document Directory";
```
 Ersetzen`"Your Document Directory"` durch den Pfad zu Ihrem aktuellen Dokumentverzeichnis.
## Schritt 2: Instanziieren des Präsentationsobjekts
Erstellen Sie eine Instanz der Präsentationsklasse, um die PowerPoint-Präsentationsdatei darzustellen.
```java
Presentation p = new Presentation(dataDir + "HelloWorld.pptx");
```
 Stellen Sie sicher, dass Sie ersetzen`"HelloWorld.pptx"` durch den Namen Ihrer PowerPoint-Präsentationsdatei.
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
 Stellen Sie sicher, dass Sie ersetzen`"Scaling Factor Thumbnail_out.png"` durch den gewünschten Ausgabedateinamen.

## Abschluss
Abschließend haben Sie mit Aspose.Slides für Java erfolgreich eine Miniaturansicht mit Skalierungsfaktor erstellt. Indem Sie die angegebenen Schritte befolgen, können Sie diese Funktionalität problemlos in Ihre Java-Anwendungen integrieren.
## Häufig gestellte Fragen
### Kann ich Aspose.Slides für Java mit jeder Java-IDE verwenden?
Ja, Aspose.Slides für Java kann mit jeder Java Integrated Development Environment (IDE) wie Eclipse, IntelliJ IDEA oder NetBeans verwendet werden.
### Gibt es eine kostenlose Testversion für Aspose.Slides für Java?
 Ja, Sie können eine kostenlose Testversion von Aspose.Slides für Java nutzen, indem Sie die[Webseite](https://releases.aspose.com/).
### Wo finde ich Unterstützung für Aspose.Slides für Java?
 Support für Aspose.Slides für Java finden Sie auf der[Aspose.Slides-Forum](https://forum.aspose.com/c/slides/11).
### Wie kann ich Aspose.Slides für Java kaufen?
 Sie können Aspose.Slides für Java erwerben bei der[Kaufseite](https://purchase.aspose.com/buy).
### Benötige ich eine temporäre Lizenz, um Aspose.Slides für Java zu verwenden?
 Ja, Sie können eine vorläufige Lizenz erhalten bei der[Seite mit der temporären Lizenz](https://purchase.aspose.com/temporary-license/).