---
title: Festlegen des Aufzählungszeichen-Füllformats in SmartArt mithilfe von Java
linktitle: Festlegen des Aufzählungszeichen-Füllformats in SmartArt mithilfe von Java
second_title: Aspose.Slides Java PowerPoint-Verarbeitungs-API
description: Erfahren Sie, wie Sie mit Java und Aspose.Slides das Aufzählungszeichenformat in SmartArt festlegen. Schritt-für-Schritt-Anleitung zur effizienten Präsentationsbearbeitung.
weight: 18
url: /de/java/java-powerpoint-smartart-manipulation/set-bullet-fill-format-smartart-java/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Festlegen des Aufzählungszeichen-Füllformats in SmartArt mithilfe von Java

## Einführung
Im Bereich der Java-Programmierung ist die effiziente Bearbeitung von Präsentationen eine häufige Anforderung, insbesondere beim Umgang mit SmartArt-Elementen. Aspose.Slides für Java erweist sich als leistungsstarkes Tool für solche Aufgaben und bietet eine Reihe von Funktionen zur programmgesteuerten Bearbeitung von Präsentationen. In diesem Tutorial werden wir Schritt für Schritt den Prozess zum Festlegen des Aufzählungszeichenformats in SmartArt mithilfe von Java und Aspose.Slides durchgehen.
## Voraussetzungen
Bevor wir mit diesem Tutorial beginnen, stellen Sie sicher, dass die folgenden Voraussetzungen erfüllt sind:
### Java Development Kit (JDK)
 Sie müssen JDK auf Ihrem System installiert haben. Sie können es von der[Webseite](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html) und folgen Sie den Installationsanweisungen.
### Aspose.Slides für Java
 Laden Sie Aspose.Slides für Java herunter und installieren Sie es von der[Download-Link](https://releases.aspose.com/slides/java/). Befolgen Sie die Installationsanweisungen in der Dokumentation zu Ihrem spezifischen Betriebssystem.

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
Erstellen Sie zunächst eine neue Instanz der Präsentationsklasse, die eine PowerPoint-Präsentation darstellt.
## Schritt 2: SmartArt hinzufügen
```java
ISmartArt smart = presentation.getSlides().get_Item(0).getShapes().addSmartArt(10, 10, 500, 400, SmartArtLayoutType.VerticalPictureList);
```
Fügen Sie als Nächstes der Folie eine SmartArt-Form hinzu. Diese Codezeile initialisiert eine neue SmartArt-Form mit angegebenen Abmessungen und Layout.
## Schritt 3: Zugriff auf SmartArt-Knoten
```java
ISmartArtNode node = smart.getAllNodes().get_Item(0);
```
Greifen Sie jetzt auf den ersten Knoten (oder einen beliebigen Knoten) innerhalb der SmartArt-Form zu, um dessen Eigenschaften zu ändern.
## Schritt 4: Aufzählungszeichenformat festlegen
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
Speichern Sie abschließend die geänderte Präsentation am angegebenen Speicherort.

## Abschluss
Herzlichen Glückwunsch! Sie haben erfolgreich gelernt, wie Sie mit Java und Aspose.Slides das Aufzählungsformat in SmartArt festlegen. Diese Funktion eröffnet eine Welt voller Möglichkeiten für dynamische und optisch ansprechende Präsentationen in Java-Anwendungen.
## Häufig gestellte Fragen
### Kann ich Aspose.Slides für Java verwenden, um Präsentationen von Grund auf neu zu erstellen?
Auf jeden Fall! Aspose.Slides bietet umfassende APIs zum Erstellen, Ändern und Bearbeiten von Präsentationen vollständig über Code.
### Ist Aspose.Slides mit verschiedenen Versionen von PowerPoint kompatibel?
Ja, Aspose.Slides gewährleistet die Kompatibilität mit verschiedenen Versionen von Microsoft PowerPoint und ermöglicht so eine nahtlose Integration in Ihren Arbeitsablauf.
### Kann ich SmartArt-Elemente über das Aufzählungszeichenformat hinaus anpassen?
Tatsächlich können Sie mit Aspose.Slides jeden Aspekt von SmartArt-Formen anpassen, einschließlich Layout, Stil, Inhalt und mehr.
### Gibt es eine Testversion von Aspose.Slides für Java?
 Ja, Sie können die Funktionen von Aspose.Slides mit einer kostenlosen Testversion erkunden. Laden Sie es einfach von der[Webseite](https://releases.aspose.com/slides/java/) und beginnen Sie mit der Erkundung.
### Wo finde ich Unterstützung für Aspose.Slides für Java?
 Bei Fragen oder Hilfe können Sie das Aspose.Slides-Forum unter besuchen.[dieser Link](https://forum.aspose.com/c/slides/11).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
