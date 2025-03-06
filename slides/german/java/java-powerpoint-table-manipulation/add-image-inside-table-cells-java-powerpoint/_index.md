---
title: Fügen Sie in Java PowerPoint ein Bild in Tabellenzellen ein
linktitle: Fügen Sie in Java PowerPoint ein Bild in Tabellenzellen ein
second_title: Aspose.Slides Java PowerPoint-Verarbeitungs-API
description: Erfahren Sie mit dieser ausführlichen Schritt-für-Schritt-Anleitung mit Aspose.Slides für Java, wie Sie Bilder in Tabellenzellen in Java PowerPoint-Präsentationen einfügen.
weight: 10
url: /de/java/java-powerpoint-table-manipulation/add-image-inside-table-cells-java-powerpoint/
---

{< blocks/products/pf/main-wrap-class >}
{< blocks/products/pf/main-container >}
{< blocks/products/pf/tutorial-page-section >}

## Einführung
Wenn Sie Ihre Java PowerPoint-Präsentationen verbessern möchten, indem Sie Bilder in Tabellenzellen einbetten, sind Sie hier genau richtig! Heute tauchen wir in eine detaillierte Schritt-für-Schritt-Anleitung mit Aspose.Slides für Java ein. Dieses Tutorial führt Sie durch den gesamten Prozess und stellt sicher, dass selbst ein Anfänger ihm folgen und beeindruckende Ergebnisse erzielen kann.
## Voraussetzungen
Bevor wir beginnen, stellen wir sicher, dass Sie alles haben, was Sie brauchen:
1.  Java Development Kit (JDK): Stellen Sie sicher, dass JDK auf Ihrem Rechner installiert ist. Sie können es hier herunterladen:[Oracle-Website](https://www.oracle.com/java/technologies/javase-downloads.html).
2.  Aspose.Slides für Java: Laden Sie die Aspose.Slides-Bibliothek herunter von[Webseite](https://releases.aspose.com/slides/java/).
3. Integrierte Entwicklungsumgebung (IDE): Wir empfehlen die Verwendung von IntelliJ IDEA oder Eclipse für die Java-Entwicklung.
4. Bilddatei: Halten Sie eine Bilddatei bereit, die Sie in Ihre PowerPoint-Tabellenzellen einbetten möchten.
Nachdem Sie nun alle Voraussetzungen erfüllt haben, können wir mit dem Importieren der erforderlichen Pakete und dem Schreiben des Codes fortfahren.
## Pakete importieren
Importieren Sie zunächst die erforderlichen Pakete in Ihr Java-Projekt. Mit diesen Paketen können Sie die von Aspose.Slides und der Bildverarbeitung von Java bereitgestellten Funktionen nutzen.
```java
import com.aspose.slides.*;
import javax.imageio.ImageIO;
import java.awt.image.BufferedImage;
import java.io.File;
import java.io.IOException;
```
Lassen Sie uns das Beispiel in mehrere Schritte aufteilen, damit es leichter verständlich ist.
## Schritt 1: Präsentation vorbereiten
Beginnen Sie mit dem Einrichten des Präsentationsobjekts und dem Aufrufen der ersten Folie.
```java
// Definieren Sie den Pfad zu Ihrem Dokumentverzeichnis
String dataDir = "Your Document Directory";
// Instanziieren des Präsentationsklassenobjekts
Presentation presentation = new Presentation();
```
Dieser Codeausschnitt initialisiert eine neue PowerPoint-Präsentation und bereitet sie für weitere Änderungen vor.
## Schritt 2: Zugriff auf die erste Folie
Rufen Sie als Nächstes die erste Folie der Präsentation auf. Diese Folie dient als Leinwand, auf der wir die Tabelle hinzufügen.
```java
try {
    // Greifen Sie auf die erste Folie zu
    ISlide slide = presentation.getSlides().get_Item(0);
```
## Schritt 3: Tabellenabmessungen definieren
Definieren Sie die Spaltenbreiten und Zeilenhöhen für die Tabelle. Dieser Schritt ist wichtig, um sicherzustellen, dass Ihre Tabellenzellen die richtigen Abmessungen haben.
```java
    // Definieren Sie Spalten mit Breiten und Zeilen mit Höhen
    double[] columns = {150, 150, 150, 150};
    double[] rows = {100, 100, 100, 100, 90};
```
## Schritt 4: Tabelle zur Folie hinzufügen
Fügen Sie der Folie die Tabellenform mit den angegebenen Abmessungen hinzu.
```java
    // Tabellenform zur Folie hinzufügen
    ITable table = slide.getShapes().addTable(50, 50, columns, rows);
```
## Schritt 5: Laden Sie das Bild
Laden Sie das Bild, das Sie in die Tabellenzelle einbetten möchten. Stellen Sie sicher, dass die Bilddatei in Ihrem angegebenen Verzeichnis verfügbar ist.
```java
    // Erstellen Sie ein BufferedImage-Objekt zur Aufnahme der Bilddatei
    BufferedImage image = ImageIO.read(new File(dataDir + "aspose-logo.jpg"));
    // Erstellen Sie ein IPPImage-Objekt mit dem Bitmap-Objekt
    IPPImage imgx = presentation.getImages().addImage(image);
```
## Schritt 6: Bild zur Tabellenzelle hinzufügen
Jetzt ist es an der Zeit, das Bild in die erste Zelle der Tabelle einzufügen. Konfigurieren Sie das Füllformat und legen Sie die Bildeigenschaften fest.
```java
    // Bild zur ersten Tabellenzelle hinzufügen
    table.get_Item(0, 0).getCellFormat().getFillFormat().setFillType(FillType.Picture);
    table.get_Item(0, 0).getCellFormat().getFillFormat().getPictureFillFormat().setPictureFillMode(PictureFillMode.Stretch);
    table.get_Item(0, 0).getCellFormat().getFillFormat().getPictureFillFormat().getPicture().setImage(imgx);
```
## Schritt 7: Bildzuschnitt anpassen
Passen Sie den Bildzuschnitt bei Bedarf so an, dass er perfekt in die Zelle passt. Dieser Schritt stellt sicher, dass Ihr Bild genau richtig aussieht.
```java
    table.get_Item(0, 0).getCellFormat().getFillFormat().getPictureFillFormat().setCropRight(20);
    table.get_Item(0, 0).getCellFormat().getFillFormat().getPictureFillFormat().setCropLeft(20);
    table.get_Item(0, 0).getCellFormat().getFillFormat().getPictureFillFormat().setCropTop(20);
    table.get_Item(0, 0).getCellFormat().getFillFormat().getPictureFillFormat().setCropBottom(20);
```
## Schritt 8: Speichern Sie die Präsentation
Speichern Sie abschließend die geänderte Präsentation im gewünschten Verzeichnis.
```java
    // Speichern Sie die PPTX-Datei auf der Festplatte
    presentation.save(dataDir + "Image_In_TableCell_out.pptx", SaveFormat.Pptx);
} catch (IOException e) {
    e.printStackTrace();
} finally {
    if (presentation != null) presentation.dispose();
}
```

## Abschluss
Da haben Sie es! Indem Sie diese Schritte befolgen, können Sie mit Aspose.Slides erfolgreich Bilder in Tabellenzellen einer Java PowerPoint-Präsentation einfügen. In dieser Anleitung wurde alles behandelt, vom Einrichten Ihrer Umgebung bis zum Speichern der endgültigen Präsentation. Ich hoffe, dieses Tutorial hilft Ihnen dabei, optisch ansprechendere Präsentationen zu erstellen.
## Häufig gestellte Fragen
### Was ist Aspose.Slides für Java?
Aspose.Slides für Java ist eine leistungsstarke API zum Erstellen, Ändern und Verwalten von PowerPoint-Präsentationen in Java-Anwendungen.
### Gibt es eine kostenlose Testversion für Aspose.Slides?
 Ja, Sie können eine[Kostenlose Testphase](https://releases.aspose.com/) um Aspose.Slides vor dem Kauf auszuprobieren.
### Kann ich mit Aspose.Slides jedes Bildformat verwenden?
Aspose.Slides unterstützt verschiedene Bildformate, darunter JPEG, PNG, BMP und mehr.
### Wo finde ich ausführlichere Dokumentation?
 Weitere Informationen finden Sie im[Dokumentation](https://reference.aspose.com/slides/java/) für ausführlichere Informationen und Beispiele.
### Wie kann ich Aspose.Slides für Java kaufen?
 Sie können es erwerben bei der[Aspose-Website](https://purchase.aspose.com/buy).
{< /blocks/products/pf/tutorial-page-section >}

{< /blocks/products/pf/main-container >}
{< /blocks/products/pf/main-wrap-class >}

{< blocks/products/products-backtop-button >}
