---
title: Formen in PowerPoint mit Bildern füllen
linktitle: Formen in PowerPoint mit Bildern füllen
second_title: Aspose.Slides Java PowerPoint-Verarbeitungs-API
description: Erfahren Sie, wie Sie mit Aspose.Slides für Java Formen in PowerPoint-Präsentationen mit Bildern füllen. Verbessern Sie mühelos die visuelle Attraktivität.
type: docs
weight: 12
url: /de/java/java-powerpoint-shape-formatting-geometry/fill-shapes-picture-powerpoint/
---
## Einführung
PowerPoint-Präsentationen erfordern häufig visuelle Elemente wie mit Bildern gefüllte Formen, um ihre Attraktivität zu steigern und Informationen effektiv zu vermitteln. Aspose.Slides für Java bietet einen leistungsstarken Satz von Tools, um diese Aufgabe nahtlos zu erledigen. In diesem Tutorial lernen wir Schritt für Schritt, wie man mit Aspose.Slides für Java Formen mit Bildern füllt.
## Voraussetzungen
Bevor wir beginnen, stellen Sie sicher, dass Sie über Folgendes verfügen:
1. Auf Ihrem System ist Java Development Kit (JDK) installiert.
2.  Aspose.Slides für Java-Bibliothek heruntergeladen. Sie können es von[Hier](https://releases.aspose.com/slides/java/).
3. Grundkenntnisse der Java-Programmierung.
## Pakete importieren
Importieren Sie in Ihr Java-Projekt die erforderlichen Pakete:
```java
import com.aspose.slides.*;
import com.aspose.slides.examples.RunExamples;
import javax.imageio.ImageIO;
import java.awt.image.BufferedImage;
import java.io.File;
import java.io.IOException;
```
## Schritt 1: Einrichten des Projektverzeichnisses
```java
String dataDir = "Your Document Directory";
boolean isExists = new File(dataDir).exists();
if (!isExists)
    new File(dataDir).mkdirs();
```
 Stellen Sie sicher, dass Sie ersetzen`"Your Document Directory"` durch den Pfad zu Ihrem Projektverzeichnis.
## Schritt 2: Erstellen Sie eine Präsentation
```java
Presentation pres = new Presentation();
```
 Instanziieren Sie den`Presentation` Klasse, um eine neue PowerPoint-Präsentation zu erstellen.
## Schritt 3: Folie und Form hinzufügen
```java
ISlide sld = pres.getSlides().get_Item(0);
IShape shp = sld.getShapes().addAutoShape(ShapeType.Rectangle, 50, 150, 75, 150);
```
Fügen Sie der Präsentation eine Folie hinzu und erstellen Sie darauf eine rechteckige Form.
## Schritt 4: Fülltyp auf Bild einstellen
```java
shp.getFillFormat().setFillType(FillType.Picture);
```
Stellen Sie den Fülltyp der Form auf Bild ein.
## Schritt 5: Bildfüllmodus einstellen
```java
shp.getFillFormat().getPictureFillFormat().setPictureFillMode(PictureFillMode.Tile);
```
Legen Sie den Bildfüllmodus der Form fest.
## Schritt 6: Bild einstellen
```java
BufferedImage img = ImageIO.read(new File(dataDir + "Tulips.jpg"));
IPPImage imgx = pres.getImages().addImage(img);
shp.getFillFormat().getPictureFillFormat().getPicture().setImage(imgx);
```
Laden Sie das Bild und legen Sie es als Füllung für die Form fest.
## Schritt 7: Präsentation speichern
```java
pres.save(dataDir + "RectShpPic_out.pptx", SaveFormat.Pptx);
```
Speichern Sie die geänderte Präsentation in einer Datei.

## Abschluss
Mit Aspose.Slides für Java wird das Füllen von Formen mit Bildern in PowerPoint-Präsentationen zu einem einfachen Vorgang. Indem Sie die in diesem Tutorial beschriebenen Schritte befolgen, können Sie Ihre Präsentationen ganz einfach mit optisch ansprechenden Elementen verbessern.

## Häufig gestellte Fragen
### Kann ich mit Aspose.Slides für Java verschiedene Formen mit Bildern füllen?
Ja, Aspose.Slides für Java unterstützt das Füllen verschiedener Formen mit Bildern und bietet so Flexibilität beim Design.
### Ist Aspose.Slides für Java mit allen Versionen von PowerPoint kompatibel?
Aspose.Slides für Java generiert Präsentationen, die mit PowerPoint 97 und höher kompatibel sind, und gewährleistet so umfassende Kompatibilität.
### Wie kann ich die Größe des Bildes innerhalb der Form ändern?
Sie können die Größe des Bildes innerhalb der Form ändern, indem Sie die Abmessungen der Form anpassen oder das Bild entsprechend skalieren, bevor Sie es als Füllung festlegen.
### Gibt es Einschränkungen hinsichtlich der zum Ausfüllen von Formen unterstützten Bildformate?
Aspose.Slides für Java unterstützt eine Vielzahl von Bildformaten, darunter unter anderem JPEG, PNG, GIF, BMP und TIFF.
### Kann ich auf die ausgefüllten Formen Effekte anwenden?
Ja, Aspose.Slides für Java bietet umfassende APIs zum Anwenden verschiedener Effekte wie Schatten, Reflexionen und 3D-Rotationen auf gefüllte Formen.