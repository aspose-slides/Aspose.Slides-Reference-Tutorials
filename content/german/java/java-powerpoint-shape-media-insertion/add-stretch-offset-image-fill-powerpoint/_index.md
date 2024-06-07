---
title: Streckungsversatz für Bildfüllung in PowerPoint hinzufügen
linktitle: Streckungsversatz für Bildfüllung in PowerPoint hinzufügen
second_title: Aspose.Slides Java PowerPoint-Verarbeitungs-API
description: Erfahren Sie, wie Sie mit Aspose.Slides für Java einen Streckungsoffset für die Bildfüllung in PowerPoint-Präsentationen hinzufügen. Schritt-für-Schritt-Anleitung enthalten.
type: docs
weight: 16
url: /de/java/java-powerpoint-shape-media-insertion/add-stretch-offset-image-fill-powerpoint/
---
## Einführung
In diesem Tutorial erfahren Sie, wie Sie mit Aspose.Slides für Java einen Streckungsoffset für die Bildfüllung in PowerPoint-Präsentationen hinzufügen. Mit dieser Funktion können Sie Bilder in Ihren Folien bearbeiten und so deren Erscheinungsbild besser steuern.
## Voraussetzungen
Bevor Sie beginnen, stellen Sie sicher, dass Sie über Folgendes verfügen:
1. Auf Ihrem System ist Java Development Kit (JDK) installiert.
2. Aspose.Slides für die Java-Bibliothek heruntergeladen und in Ihrem Java-Projekt eingerichtet.
## Pakete importieren
Importieren Sie zunächst die erforderlichen Pakete in Ihr Java-Projekt:
```java
import com.aspose.slides.*;
import com.aspose.slides.examples.RunExamples;
import javax.imageio.ImageIO;
import java.awt.image.BufferedImage;
import java.io.File;
import java.io.IOException;
```
## Schritt 1: Richten Sie Ihr Dokumentverzeichnis ein
Legen Sie das Verzeichnis fest, in dem sich Ihr PowerPoint-Dokument befindet:
```java
String dataDir = "Your Document Directory";
```
## Schritt 2: Präsentationsobjekt erstellen
Instanziieren Sie die Klasse „Presentation“, um die PowerPoint-Datei darzustellen:
```java
Presentation pres = new Presentation();
```
## Schritt 3: Bild zur Folie hinzufügen
Rufen Sie die erste Folie ab und fügen Sie ihr ein Bild hinzu:
```java
ISlide sld = pres.getSlides().get_Item(0);
BufferedImage img = ImageIO.read(new File(dataDir + "aspose-logo.jpg"));
IPPImage imgx = pres.getImages().addImage(img);
```
## Schritt 4: Bilderrahmen hinzufügen
Erstellen Sie einen Bilderrahmen mit den Abmessungen, die dem Bild entsprechen:
```java
sld.getShapes().addPictureFrame(ShapeType.Rectangle, 50, 150, imgx.getWidth(), imgx.getHeight(), imgx);
```
## Schritt 5: Speichern Sie die Präsentation
Speichern Sie die geänderte PowerPoint-Datei:
```java
pres.save(dataDir + "AddStretchOffsetForImageFill_out.pptx", SaveFormat.Pptx);
```

## Abschluss
Herzlichen Glückwunsch! Sie haben erfolgreich gelernt, wie Sie mit Aspose.Slides für Java einen Streckungsoffset für die Bildfüllung in PowerPoint hinzufügen. Diese Funktion eröffnet Ihnen eine Welt voller Möglichkeiten, Ihre Präsentationen mit benutzerdefinierten Bildern zu verbessern.
## Häufig gestellte Fragen
### Kann ich mit dieser Methode Bilder zu bestimmten Folien einer Präsentation hinzufügen?
Ja, Sie können beim Abrufen des Folienobjekts den Folienindex angeben, um auf eine bestimmte Folie abzuzielen.
### Unterstützt Aspose.Slides für Java andere Bildformate außer JPEG?
Ja, Aspose.Slides für Java unterstützt verschiedene Bildformate, darunter unter anderem PNG, GIF und BMP.
### Gibt es eine Größenbeschränkung für die Bilder, die ich mit dieser Methode hinzufügen kann?
Aspose.Slides für Java kann Bilder verschiedener Größen verarbeiten, es wird jedoch empfohlen, Bilder für eine bessere Leistung in Präsentationen zu optimieren.
### Kann ich nach dem Hinzufügen zu den Folien zusätzliche Effekte oder Transformationen auf die Bilder anwenden?
Ja, Sie können mit der umfangreichen API von Aspose.Slides für Java eine Vielzahl von Effekten und Transformationen auf Bilder anwenden.
### Wo finde ich weitere Ressourcen und Support für Aspose.Slides für Java?
 Besuchen Sie die[Aspose.Slides für Java-Dokumentation](https://reference.aspose.com/slides/java/) für detaillierte Anleitungen und erkunden Sie die[Aspose.Slides-Forum](https://forum.aspose.com/c/slides/11) für die Unterstützung der Community.