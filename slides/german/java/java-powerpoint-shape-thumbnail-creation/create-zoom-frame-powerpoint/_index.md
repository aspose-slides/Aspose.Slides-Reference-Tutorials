---
title: Zoom-Rahmen in PowerPoint erstellen
linktitle: Zoom-Rahmen in PowerPoint erstellen
second_title: Aspose.Slides Java PowerPoint-Verarbeitungs-API
description: Erfahren Sie, wie Sie mit Aspose.Slides für Java ansprechende Zoom-Frames in PowerPoint erstellen. Folgen Sie unserer Anleitung, um Ihren Präsentationen interaktive Elemente hinzuzufügen.
weight: 17
url: /de/java/java-powerpoint-shape-thumbnail-creation/create-zoom-frame-powerpoint/
---

{< blocks/products/pf/main-wrap-class >}
{< blocks/products/pf/main-container >}
{< blocks/products/pf/tutorial-page-section >}

## Einführung
Das Erstellen ansprechender PowerPoint-Präsentationen ist eine Kunst, und manchmal können die kleinsten Ergänzungen einen großen Unterschied machen. Eine solche Funktion ist der Zoom-Rahmen, mit dem Sie in bestimmte Folien oder Bilder hineinzoomen und so eine dynamische und interaktive Präsentation erstellen können. In diesem Tutorial führen wir Sie durch den Prozess zum Erstellen eines Zoom-Rahmens in PowerPoint mit Aspose.Slides für Java.
## Voraussetzungen
Bevor Sie mit dem Lernprogramm beginnen, stellen Sie sicher, dass Sie über Folgendes verfügen:
- Auf Ihrem System ist Java Development Kit (JDK) installiert.
-  Aspose.Slides für Java-Bibliothek. Sie können es herunterladen von[Hier](https://releases.aspose.com/slides/java/).
- Eine integrierte Entwicklungsumgebung (IDE) wie IntelliJ IDEA oder Eclipse.
- Grundkenntnisse der Java-Programmierung.
## Pakete importieren
Zunächst müssen Sie die erforderlichen Pakete in Ihr Java-Projekt importieren. Diese Importe ermöglichen den Zugriff auf die für dieses Tutorial erforderlichen Aspose.Slides-Funktionen.
```java
import com.aspose.slides.*;

import java.awt.*;
import java.io.IOException;
import java.nio.file.Files;
import java.nio.file.Paths;
```
## Schritt 1: Einrichten der Präsentation
Zuerst müssen wir eine neue Präsentation erstellen und ihr ein paar Folien hinzufügen.
```java
// Name der Ausgabedatei
String resultPath = "ZoomFramePresentation.pptx";
// Pfad zum Quellbild
String imagePath = "Your Document Directory/aspose-logo.jpg";
Presentation pres = new Presentation();
try {
    // Neue Folien zur Präsentation hinzufügen
    ISlide slide2 = pres.getSlides().addEmptySlide(pres.getSlides().get_Item(0).getLayoutSlide());
    ISlide slide3 = pres.getSlides().addEmptySlide(pres.getSlides().get_Item(0).getLayoutSlide());
```
## Schritt 2: Folienhintergründe anpassen
Wir möchten unsere Folien durch das Hinzufügen von Hintergrundfarben optisch hervorheben.
### Festlegen des Hintergrunds für die zweite Folie
```java
    // Erstellen Sie einen Hintergrund für die zweite Folie
    slide2.getBackground().setType(BackgroundType.OwnBackground);
    slide2.getBackground().getFillFormat().setFillType(FillType.Solid);
    slide2.getBackground().getFillFormat().getSolidFillColor().setColor(Color.CYAN);
    // Erstellen Sie ein Textfeld für die zweite Folie
    IAutoShape autoshape = slide2.getShapes().addAutoShape(ShapeType.Rectangle, 100, 200, 500, 200);
    autoshape.getTextFrame().setText("Second Slide");
```
### Festlegen des Hintergrunds für die dritte Folie
```java
    // Erstellen Sie einen Hintergrund für die dritte Folie
    slide3.getBackground().setType(BackgroundType.OwnBackground);
    slide3.getBackground().getFillFormat().setFillType(FillType.Solid);
    slide3.getBackground().getFillFormat().getSolidFillColor().setColor(Color.DARK_GRAY);
    // Erstellen Sie ein Textfeld für die dritte Folie
    autoshape = slide3.getShapes().addAutoShape(ShapeType.Rectangle, 100, 200, 500, 200);
    autoshape.getTextFrame().setText("Third Slide");
```
## Schritt 3: Zoom-Rahmen hinzufügen
Fügen wir nun der Präsentation Zoom-Rahmen hinzu. Wir fügen einen Zoom-Rahmen mit einer Folienvorschau und einen weiteren mit einem benutzerdefinierten Bild hinzu.
### Zoom-Rahmen mit Folienvorschau hinzufügen
```java
    // ZoomFrame-Objekte mit Folienvorschau hinzufügen
    IZoomFrame zoomFrame1 = pres.getSlides().get_Item(0).getShapes().addZoomFrame(20, 20, 250, 200, slide2);
```
### Zoomrahmen mit benutzerdefiniertem Bild hinzufügen
```java
    // ZoomFrame-Objekte mit benutzerdefiniertem Bild hinzufügen
    byte[] imageBytes = Files.readAllBytes(Paths.get(imagePath));
    IPPImage image = pres.getImages().addImage(imageBytes);
    IZoomFrame zoomFrame2 = pres.getSlides().get_Item(0).getShapes().addZoomFrame(200, 250, 250, 100, slide3, image);
```
## Schritt 4: Anpassen der Zoomrahmen
Damit unsere Zoom-Rahmen hervorstechen, passen wir ihr Erscheinungsbild an.
### Anpassen des zweiten Zoomrahmens
```java
    // Festlegen eines Zoomrahmenformats für das Objekt „zoomFrame2“
    zoomFrame2.getLineFormat().setWidth(5);
    zoomFrame2.getLineFormat().getFillFormat().setFillType(FillType.Solid);
    zoomFrame2.getLineFormat().getFillFormat().getSolidFillColor().setColor(Color.MAGENTA);
    zoomFrame2.getLineFormat().setDashStyle(LineDashStyle.DashDot);
```
### Hintergrund für das erste Zoom-Bild ausblenden
```java
    // Für das Objekt „zoomFrame1“ keinen Hintergrund anzeigen
    zoomFrame1.setShowBackground(false);
```
## Schritt 5: Speichern der Präsentation
Abschließend speichern wir unsere Präsentation im angegebenen Pfad.
```java
    // Speichern der Präsentation
    pres.save(resultPath, SaveFormat.Pptx);
} catch (IOException e) {
    e.printStackTrace();
} finally {
    if (pres != null) pres.dispose();
}
```
## Abschluss
Das Erstellen von Zoom-Frames in PowerPoint mit Aspose.Slides für Java kann die Interaktivität und das Engagement Ihrer Präsentationen erheblich verbessern. Indem Sie die in diesem Tutorial beschriebenen Schritte befolgen, können Sie ganz einfach sowohl Folienvorschauen als auch benutzerdefinierte Bilder als Zoom-Frames hinzufügen und sie an das Thema Ihrer Präsentation anpassen. Viel Spaß beim Präsentieren!
## Häufig gestellte Fragen
### Was ist Aspose.Slides für Java?
Aspose.Slides für Java ist eine leistungsstarke API zum programmgesteuerten Erstellen und Bearbeiten von PowerPoint-Präsentationen.
### Wie installiere ich Aspose.Slides für Java?
 Sie können Aspose.Slides für Java herunterladen von der[Webseite](https://releases.aspose.com/slides/java/) und fügen Sie es den Abhängigkeiten Ihres Projekts hinzu.
### Kann ich das Erscheinungsbild von Zoom-Rahmen anpassen?
Ja, Aspose.Slides ermöglicht Ihnen die Anpassung verschiedener Eigenschaften von Zoom-Rahmen, wie etwa Linienstil, Farbe und Hintergrundsichtbarkeit.
### Ist es möglich, Zoom-Rahmen Bilder hinzuzufügen?
Auf jeden Fall! Sie können Zoom-Frames benutzerdefinierte Bilder hinzufügen, indem Sie Bilddateien lesen und sie der Präsentation hinzufügen.
### Wo finde ich weitere Beispiele und Dokumentation?
 Ausführliche Dokumentationen und Beispiele finden Sie auf der[Aspose.Slides für Java-Dokumentationsseite](https://reference.aspose.com/slides/java/).
{< /blocks/products/pf/tutorial-page-section >}

{< /blocks/products/pf/main-container >}
{< /blocks/products/pf/main-wrap-class >}

{< blocks/products/products-backtop-button >}
