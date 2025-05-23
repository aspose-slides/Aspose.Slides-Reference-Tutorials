---
"description": "Erfahren Sie in diesem Schritt-für-Schritt-Tutorial, wie Sie mit Aspose.Slides für Java Videoframes in PowerPoint einbetten. Optimieren Sie Ihre Präsentationen ganz einfach."
"linktitle": "Eingebetteter Videorahmen in PowerPoint hinzufügen"
"second_title": "Aspose.Slides Java PowerPoint-Verarbeitungs-API"
"title": "Eingebetteter Videorahmen in PowerPoint hinzufügen"
"url": "/de/java/java-powerpoint-animation-shape-manipulation/add-embedded-video-frame-powerpoint/"
"weight": 21
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Eingebetteter Videorahmen in PowerPoint hinzufügen

## Einführung
Das Hinzufügen von Videos zu Ihren PowerPoint-Präsentationen kann diese ansprechender und informativer gestalten. Mit Aspose.Slides für Java können Sie Videos ganz einfach direkt in Ihre Folien einbetten. In diesem Tutorial führen wir Sie Schritt für Schritt durch den Prozess und stellen sicher, dass Sie jeden Teil des Codes und seine Funktionsweise verstehen. Egal, ob Sie ein erfahrener Entwickler sind oder gerade erst anfangen – dieser Leitfaden hilft Ihnen, Ihre Präsentationen mit eingebetteten Videos zu verbessern.
## Voraussetzungen
Bevor Sie sich in den Code vertiefen, stellen Sie sicher, dass die folgenden Voraussetzungen erfüllt sind:
1. Java Development Kit (JDK): Stellen Sie sicher, dass JDK auf Ihrem Computer installiert ist.
2. Aspose.Slides für Java: Laden Sie die Bibliothek Aspose.Slides für Java herunter und installieren Sie sie.
3. Integrierte Entwicklungsumgebung (IDE): Verwenden Sie eine IDE wie IntelliJ IDEA oder Eclipse für ein besseres Entwicklungserlebnis.
4. Videodatei: Sie haben eine Videodatei, die Sie in Ihre PowerPoint-Präsentation einbetten möchten.
## Pakete importieren
Zunächst müssen Sie die erforderlichen Pakete für die Arbeit mit Aspose.Slides importieren. Diese Importe helfen Ihnen bei der Verwaltung von Folien, Videos und Präsentationsdateien.
```java
import com.aspose.slides.*;

import java.io.File;
import java.io.FileInputStream;
import java.io.FileNotFoundException;
```
## Schritt 1: Richten Sie Ihre Umgebung ein
Bevor Sie mit der Programmierung beginnen, stellen Sie sicher, dass Ihre Umgebung korrekt eingerichtet ist. Dazu gehört das Erstellen der erforderlichen Verzeichnisse und das Vorbereiten der Videodatei.
```java
// Der Pfad zum Dokumentenverzeichnis.
String dataDir = "Your Document Directory";
String videoDir = "Path to Your Video Directory";
String resultPath = "Path to Save Result" + "VideoFrame_out.pptx";
// Erstellen Sie ein Verzeichnis, falls es noch nicht vorhanden ist.
boolean isExists = new File(dataDir).exists();
if (!isExists) new File(dataDir).mkdirs();
```
## Schritt 2: Präsentationsklasse instanziieren
Erstellen Sie eine Instanz des `Presentation` Klasse. Diese Klasse stellt Ihre PowerPoint-Datei dar.
```java
// Instanziieren Sie die Präsentationsklasse, die das PPTX darstellt
Presentation pres = new Presentation();
```
## Schritt 3: Holen Sie sich die erste Folie
Greifen Sie auf die erste Folie der Präsentation zu, in die Sie das Video einbetten möchten.
```java
// Holen Sie sich die erste Folie
ISlide sld = pres.getSlides().get_Item(0);
```
## Schritt 4: Fügen Sie das Video zur Präsentation hinzu
Betten Sie die Videodatei in die Präsentation ein. Stellen Sie sicher, dass der Videopfad korrekt angegeben ist.
```java
// Video in Präsentation einbetten
IVideo vid = pres.getVideos().addVideo(new FileInputStream(videoDir + "Wildlife.mp4"), LoadingStreamBehavior.ReadStreamAndRelease);
```
## Schritt 5: Videorahmen zur Folie hinzufügen
Erstellen Sie einen Videorahmen auf der Folie und legen Sie seine Abmessungen und Position fest.
```java
// Videobild hinzufügen
IVideoFrame vf = sld.getShapes().addVideoFrame(50, 150, 300, 350, vid);
```
## Schritt 6: Videobildeigenschaften konfigurieren
Stellen Sie das Video auf den Videorahmen ein und konfigurieren Sie seine Wiedergabeeinstellungen wie Wiedergabemodus und Lautstärke.
```java
// Video auf Videobild einstellen
vf.setEmbeddedVideo(vid);
// Stellen Sie den Wiedergabemodus und die Lautstärke des Videos ein
vf.setPlayMode(VideoPlayModePreset.Auto);
vf.setVolume(AudioVolumeMode.Loud);
```
## Schritt 7: Speichern Sie die Präsentation
Speichern Sie die Präsentation mit dem eingebetteten Video in Ihrem angegebenen Verzeichnis.
```java
// Schreiben Sie die PPTX-Datei auf die Festplatte
pres.save(resultPath, SaveFormat.Pptx);
```
## Schritt 8: Ressourcen bereinigen
Entsorgen Sie abschließend das Präsentationsobjekt, um Ressourcen freizugeben.
```java
// Entsorgen Sie das Präsentationsobjekt
if (pres != null) pres.dispose();
```
## Abschluss
Das Einbetten eines Videos in Ihre PowerPoint-Präsentationen mit Aspose.Slides für Java ist ganz einfach. Mit den in dieser Anleitung beschriebenen Schritten können Sie Ihre Präsentationen mit ansprechenden Videoinhalten aufwerten. Übung macht den Meister. Probieren Sie verschiedene Videos aus und passen Sie deren Eigenschaften an, um herauszufinden, was am besten zu Ihren Anforderungen passt.
## Häufig gestellte Fragen
### Kann ich mehrere Videos in eine einzelne Folie einbetten?
Ja, Sie können mehrere Videos in eine einzelne Folie einbetten, indem Sie mehrere Videobilder hinzufügen.
### Wie kann ich die Wiedergabe des Videos steuern?
Sie können die Wiedergabe steuern mit dem `setPlayMode` Und `setVolume` Methoden der `IVideoFrame` Klasse.
### Welche Videoformate werden von Aspose.Slides unterstützt?
Aspose.Slides unterstützt verschiedene Videoformate, darunter MP4, AVI und WMV.
### Benötige ich eine Lizenz, um Aspose.Slides zu verwenden?
Ja, Sie benötigen eine gültige Lizenz, um Aspose.Slides nutzen zu können. Sie können eine temporäre Lizenz zur Evaluierung erhalten.
### Kann ich die Größe und Position des Videorahmens anpassen?
Ja, Sie können die Größe und Position anpassen, indem Sie beim Hinzufügen des Videorahmens die entsprechenden Parameter festlegen.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}