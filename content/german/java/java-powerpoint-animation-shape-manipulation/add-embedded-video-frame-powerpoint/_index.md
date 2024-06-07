---
title: Eingebetteten Videorahmen in PowerPoint hinzufügen
linktitle: Eingebetteten Videorahmen in PowerPoint hinzufügen
second_title: Aspose.Slides Java PowerPoint-Verarbeitungs-API
description: Erfahren Sie in diesem Schritt-für-Schritt-Tutorial, wie Sie mit Aspose.Slides für Java Videoframes in PowerPoint einbetten. Verbessern Sie Ihre Präsentationen ganz einfach.
type: docs
weight: 21
url: /de/java/java-powerpoint-animation-shape-manipulation/add-embedded-video-frame-powerpoint/
---
## Einführung
Durch das Hinzufügen von Videos zu Ihren PowerPoint-Präsentationen können Sie diese ansprechender und informativer gestalten. Mit Aspose.Slides für Java können Sie Videos ganz einfach direkt in Ihre Folien einbetten. In diesem Tutorial führen wir Sie Schritt für Schritt durch den Vorgang und stellen sicher, dass Sie jeden Teil des Codes und seine Funktionsweise verstehen. Egal, ob Sie ein erfahrener Entwickler sind oder gerade erst anfangen, dieser Leitfaden hilft Ihnen dabei, Ihre Präsentationen mit eingebetteten Videos zu verbessern.
## Voraussetzungen
Bevor Sie in den Code eintauchen, stellen Sie sicher, dass die folgenden Voraussetzungen erfüllt sind:
1. Java Development Kit (JDK): Stellen Sie sicher, dass JDK auf Ihrem Computer installiert ist.
2. Aspose.Slides für Java: Laden Sie die Bibliothek Aspose.Slides für Java herunter und installieren Sie sie.
3. Integrierte Entwicklungsumgebung (IDE): Verwenden Sie für ein besseres Entwicklungserlebnis eine IDE wie IntelliJ IDEA oder Eclipse.
4. Videodatei: Sie haben eine Videodatei, die Sie in Ihre PowerPoint-Präsentation einbetten möchten.
## Pakete importieren
Zuerst müssen Sie die erforderlichen Pakete importieren, um mit Aspose.Slides arbeiten zu können. Diese Importe helfen Ihnen bei der Verwaltung von Folien, Videos und Präsentationsdateien.
```java
import com.aspose.slides.*;
import com.aspose.slides.examples.RunExamples;
import java.io.File;
import java.io.FileInputStream;
import java.io.FileNotFoundException;
```
## Schritt 1: Richten Sie Ihre Umgebung ein
Bevor Sie mit dem Codieren beginnen, stellen Sie sicher, dass Ihre Umgebung richtig eingerichtet ist. Dazu gehört das Erstellen der erforderlichen Verzeichnisse und das Vorbereiten der Videodatei.
```java
// Der Pfad zum Dokumentverzeichnis.
String dataDir = "Your Document Directory";
String videoDir = "Path to Your Video Directory";
String resultPath = "Path to Save Result" + "VideoFrame_out.pptx";
// Erstellen Sie ein Verzeichnis, falls es noch nicht vorhanden ist.
boolean isExists = new File(dataDir).exists();
if (!isExists) new File(dataDir).mkdirs();
```
## Schritt 2: Präsentationsklasse instanziieren
 Erstellen Sie eine Instanz des`Presentation` Klasse. Diese Klasse stellt Ihre PowerPoint-Datei dar.
```java
// Instanziieren Sie die Präsentationsklasse, die PPTX darstellt
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
Erstellen Sie auf der Folie einen Videorahmen und legen Sie seine Abmessungen und Position fest.
```java
// Videobild hinzufügen
IVideoFrame vf = sld.getShapes().addVideoFrame(50, 150, 300, 350, vid);
```
## Schritt 6: Videobildeigenschaften konfigurieren
Stellen Sie das Video auf den Videorahmen ein und konfigurieren Sie seine Wiedergabeeinstellungen wie Wiedergabemodus und Lautstärke.
```java
// Video auf Video-Frame einstellen
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
// Entsorgen des Präsentationsobjekts
if (pres != null) pres.dispose();
```
## Abschluss
Das Einbetten eines Videos in Ihre PowerPoint-Präsentationen mit Aspose.Slides für Java ist ein unkomplizierter Vorgang. Indem Sie die in dieser Anleitung beschriebenen Schritte befolgen, können Sie Ihre Präsentationen mit ansprechenden Videoinhalten verbessern. Denken Sie daran, Übung macht den Meister. Versuchen Sie also, verschiedene Videos einzubetten und ihre Eigenschaften anzupassen, um herauszufinden, was für Ihre Anforderungen am besten geeignet ist.
## Häufig gestellte Fragen
### Kann ich mehrere Videos in eine einzelne Folie einbetten?
Ja, Sie können mehrere Videos in eine einzelne Folie einbetten, indem Sie mehrere Video-Frames hinzufügen.
### Wie kann ich die Wiedergabe des Videos steuern?
 Sie können die Wiedergabe steuern mit dem`setPlayMode` Und`setVolume` Methoden der`IVideoFrame` Klasse.
### Welche Videoformate werden von Aspose.Slides unterstützt?
Aspose.Slides unterstützt verschiedene Videoformate, darunter MP4, AVI und WMV.
### Benötige ich eine Lizenz, um Aspose.Slides zu verwenden?
Ja, Sie benötigen eine gültige Lizenz, um Aspose.Slides zu verwenden. Sie können eine temporäre Lizenz zur Evaluierung erhalten.
### Kann ich die Größe und Position des Videorahmens anpassen?
Ja, Sie können die Größe und Position anpassen, indem Sie beim Hinzufügen des Videorahmens die entsprechenden Parameter festlegen.