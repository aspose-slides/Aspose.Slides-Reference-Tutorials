---
"description": "Erfahren Sie, wie Sie mit Aspose.Slides mithilfe von Java das Aufzählungszeichenformat in SmartArt festlegen. Schritt-für-Schritt-Anleitung zur effizienten Präsentationsbearbeitung."
"linktitle": "Legen Sie das Aufzählungszeichen-Füllformat in SmartArt mit Java fest"
"second_title": "Aspose.Slides Java PowerPoint-Verarbeitungs-API"
"title": "Legen Sie das Aufzählungszeichen-Füllformat in SmartArt mit Java fest"
"url": "/de/java/java-powerpoint-smartart-manipulation/set-bullet-fill-format-smartart-java/"
"weight": 18
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Legen Sie das Aufzählungszeichen-Füllformat in SmartArt mit Java fest

## Einführung
In der Java-Programmierung ist die effiziente Bearbeitung von Präsentationen eine häufige Anforderung, insbesondere bei SmartArt-Elementen. Aspose.Slides für Java erweist sich als leistungsstarkes Tool für solche Aufgaben und bietet zahlreiche Funktionen zur programmgesteuerten Bearbeitung von Präsentationen. In diesem Tutorial erfahren Sie Schritt für Schritt, wie Sie das Aufzählungszeichenformat in SmartArt mithilfe von Java und Aspose.Slides festlegen.
## Voraussetzungen
Bevor wir mit diesem Tutorial beginnen, stellen Sie sicher, dass die folgenden Voraussetzungen erfüllt sind:
### Java Development Kit (JDK)
Sie müssen JDK auf Ihrem System installiert haben. Sie können es von der [Webseite](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html) und folgen Sie den Installationsanweisungen.
### Aspose.Slides für Java
Laden Sie Aspose.Slides für Java herunter und installieren Sie es von der [Download-Link](https://releases.aspose.com/slides/java/). Befolgen Sie die Installationsanweisungen in der Dokumentation zu Ihrem spezifischen Betriebssystem.

## Pakete importieren
Importieren Sie zunächst die erforderlichen Pakete in Ihr Java-Projekt:
```java
import com.aspose.slides.*;
import javax.imageio.ImageIO;
import java.awt.image.BufferedImage;
import java.io.File;
import java.io.IOException;
```
#Lassen Sie uns das bereitgestellte Beispiel in mehrere Schritte aufteilen, um ein klares Verständnis dafür zu erhalten, wie Sie mit Java und Aspose.Slides das Aufzählungszeichenformat in SmartArt festlegen.
## Schritt 1: Präsentationsobjekt erstellen
```java
Presentation presentation = new Presentation();
```
Erstellen Sie zunächst eine neue Instanz der Klasse „Präsentation“, die eine PowerPoint-Präsentation darstellt.
## Schritt 2: SmartArt hinzufügen
```java
ISmartArt smart = presentation.getSlides().get_Item(0).getShapes().addSmartArt(10, 10, 500, 400, SmartArtLayoutType.VerticalPictureList);
```
Fügen Sie als Nächstes der Folie eine SmartArt-Form hinzu. Diese Codezeile initialisiert eine neue SmartArt-Form mit den angegebenen Abmessungen und dem angegebenen Layout.
## Schritt 3: Zugriff auf den SmartArt-Knoten
```java
ISmartArtNode node = smart.getAllNodes().get_Item(0);
```
Greifen Sie nun auf den ersten Knoten (oder einen beliebigen Knoten) innerhalb der SmartArt-Form zu, um dessen Eigenschaften zu ändern.
## Schritt 4: Aufzählungsformat festlegen
```java
if (node.getBulletFillFormat() != null) {
    BufferedImage img = ImageIO.read(new File(dataDir + "aspose-logo.jpg"));
    IPPImage image = presentation.getImages().addImage(img);
    node.getBulletFillFormat().setFillType(FillType.Picture);
    node.getBulletFillFormat().getPictureFillFormat().getPicture().setImage(image);
    node.getBulletFillFormat().getPictureFillFormat().setPictureFillMode(PictureFillMode.Stretch);
}
```
Hier prüfen wir, ob das Aufzählungszeichenformat unterstützt wird. Wenn ja, laden wir eine Bilddatei und legen sie als Aufzählungszeichen für den SmartArt-Knoten fest.
## Schritt 5: Präsentation speichern
```java
presentation.save(dataDir + "out.pptx", SaveFormat.Pptx);
```
Speichern Sie die geänderte Präsentation abschließend an einem angegebenen Ort.

## Abschluss
Herzlichen Glückwunsch! Sie haben erfolgreich gelernt, wie Sie mit Aspose.Slides in Java das Aufzählungszeichenformat in SmartArt festlegen. Diese Funktion eröffnet Ihnen unzählige Möglichkeiten für dynamische und optisch ansprechende Präsentationen in Java-Anwendungen.
## Häufig gestellte Fragen
### Kann ich Aspose.Slides für Java verwenden, um Präsentationen von Grund auf neu zu erstellen?
Absolut! Aspose.Slides bietet umfassende APIs zum Erstellen, Ändern und Bearbeiten von Präsentationen vollständig über Code.
### Ist Aspose.Slides mit verschiedenen Versionen von PowerPoint kompatibel?
Ja, Aspose.Slides gewährleistet die Kompatibilität mit verschiedenen Versionen von Microsoft PowerPoint und ermöglicht so eine nahtlose Integration in Ihren Arbeitsablauf.
### Kann ich SmartArt-Elemente über das Aufzählungsformat hinaus anpassen?
Tatsächlich ermöglicht Ihnen Aspose.Slides, jeden Aspekt von SmartArt-Formen anzupassen, einschließlich Layout, Stil, Inhalt und mehr.
### Gibt es eine Testversion für Aspose.Slides für Java?
Ja, Sie können die Funktionen von Aspose.Slides mit einer kostenlosen Testversion erkunden. Laden Sie es einfach von der [Webseite](https://releases.aspose.com/slides/java/) und beginnen Sie mit der Erkundung.
### Wo finde ich Unterstützung für Aspose.Slides für Java?
Bei Fragen oder Hilfe können Sie das Aspose.Slides-Forum unter besuchen. [dieser Link](https://forum.aspose.com/c/slides/11).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}