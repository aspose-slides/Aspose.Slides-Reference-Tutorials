---
title: Videoframe aus Webquelle in PowerPoint hinzufügen
linktitle: Videoframe aus Webquelle in PowerPoint hinzufügen
second_title: Aspose.Slides Java PowerPoint-Verarbeitungs-API
description: Erfahren Sie, wie Sie Ihre PowerPoint-Präsentationen verbessern können, indem Sie mit Aspose.Slides für Java Videoframes aus Webquellen hinzufügen.
weight: 18
url: /de/java/java-powerpoint-shape-media-insertion/add-video-frame-web-source-powerpoint/
---

{< blocks/products/pf/main-wrap-class >}
{< blocks/products/pf/main-container >}
{< blocks/products/pf/tutorial-page-section >}

## Einführung
In diesem Tutorial erfahren Sie, wie Sie mithilfe von Aspose.Slides für Java ein Videobild aus einer Webquelle wie YouTube zu einer PowerPoint-Präsentation hinzufügen. Wenn Sie diese Schritt-für-Schritt-Anleitung befolgen, können Sie Ihre Präsentationen durch die Einbindung ansprechender Multimedia-Elemente verbessern.
## Voraussetzungen
Bevor wir beginnen, stellen Sie sicher, dass Sie die folgenden Voraussetzungen erfüllen:
- Grundkenntnisse der Java-Programmierung.
- JDK (Java Development Kit) auf Ihrem System installiert.
-  Aspose.Slides für Java-Bibliothek heruntergeladen und zu Ihrem Java-Projekt hinzugefügt. Sie können es herunterladen von[Hier](https://releases.aspose.com/slides/java/).
- Eine aktive Internetverbindung für den Zugriff auf die Webquelle (z. B. YouTube).

## Pakete importieren
Importieren Sie zunächst die erforderlichen Pakete in Ihr Java-Projekt:
```java
import com.aspose.slides.IVideoFrame;
import com.aspose.slides.Presentation;
import com.aspose.slides.SaveFormat;
import com.aspose.slides.VideoPlayModePreset;

import java.io.ByteArrayOutputStream;
import java.io.IOException;
import java.io.InputStream;
import java.net.URL;
import java.net.URLConnection;
```
## Schritt 1: Erstellen Sie ein PowerPoint-Präsentationsobjekt
Initialisieren Sie ein Präsentationsobjekt, das eine PowerPoint-Präsentation darstellt:
```java
Presentation pres = new Presentation();
```
## Schritt 2: Einen Video-Frame hinzufügen
Fügen wir nun der Präsentation einen Video-Frame hinzu. Dieser Frame enthält das Video aus der Webquelle. Wir verwenden die Methode addVideoFrame:
```java
IVideoFrame videoFrame = pres.getSlides().get_Item(0).getShapes().addVideoFrame(10, 10, 427, 240, "https://www.youtube.com/embed/VIDEO_ID");
```
Ersetzen Sie „VIDEO_ID“ durch die ID des YouTube-Videos, das Sie einbetten möchten.
## Schritt 3: Video-Wiedergabemodus einstellen
Legen Sie den Wiedergabemodus für das Videobild fest. In diesem Beispiel stellen wir ihn auf „Auto“ ein:
```java
videoFrame.setPlayMode(VideoPlayModePreset.Auto);
```
## Schritt 4: Miniaturansicht laden
Um die visuelle Attraktivität zu erhöhen, laden wir das Miniaturbild des Videos. In diesem Schritt wird das Miniaturbild aus der Webquelle abgerufen:
```java
String thumbnailUri = "https://www.youtube.com/watch?v=VIDEO_ID";
URL url = new URL(thumbnailUri);
URLConnection connection = url.openConnection();
connection.setConnectTimeout(5000);
connection.setReadTimeout(10000);
try (InputStream input = connection.getInputStream();
     ByteArrayOutputStream output = new ByteArrayOutputStream()) {
    byte[] buffer = new byte[8192];
    for (int count; (count = input.read(buffer)) > 0;) {
        output.write(buffer, 0, count);
    }
    output.toByteArray();
    videoFrame.getPictureFormat().getPicture().setImage(pres.getImages().addImage(output.toByteArray()));
}
```
## Schritt 5: Speichern Sie die Präsentation
Abschließend speichern Sie die geänderte Präsentation:
```java
pres.save("YOUR_DIRECTORY/AddVideoFrameFromWebSource_out.pptx", SaveFormat.Pptx);
```
Ersetzen Sie „IHR_VERZEICHNIS“ durch das Verzeichnis, in dem Sie die Präsentation speichern möchten.

## Abschluss
Herzlichen Glückwunsch! Sie haben erfolgreich gelernt, wie Sie mit Aspose.Slides für Java einen Videorahmen aus einer Webquelle in PowerPoint einfügen. Die Einbindung von Multimediaelementen wie Videos kann die Wirkung und das Engagement Ihrer Präsentationen erheblich steigern.
## Häufig gestellte Fragen
### Kann ich Videos aus anderen Quellen als YouTube hinzufügen?
Ja, Sie können Videos aus verschiedenen Webquellen hinzufügen, solange diese einen einbettbaren Link bereitstellen.
### Benötige ich eine Internetverbindung, um das eingebettete Video abzuspielen?
Ja, zum Streamen des Videos von der Webquelle ist eine aktive Internetverbindung erforderlich.
### Kann ich das Erscheinungsbild des Videorahmens anpassen?
Auf jeden Fall! Aspose.Slides bietet umfangreiche Optionen zum Anpassen des Erscheinungsbilds und Verhaltens von Video-Frames.
### Ist Aspose.Slides mit allen Versionen von PowerPoint kompatibel?
Aspose.Slides unterstützt eine Vielzahl von PowerPoint-Versionen und gewährleistet so die Kompatibilität zwischen verschiedenen Plattformen.
### Wo finde ich weitere Ressourcen und Support für Aspose.Slides?
 Besuchen Sie die[Aspose.Slides-Forum](https://forum.aspose.com/c/slides/11) für Hilfe, Dokumentation und Community-Support.
{< /blocks/products/pf/tutorial-page-section >}

{< /blocks/products/pf/main-container >}
{< /blocks/products/pf/main-wrap-class >}

{< blocks/products/products-backtop-button >}
