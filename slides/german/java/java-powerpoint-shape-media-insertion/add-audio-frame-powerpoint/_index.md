---
title: Audiorahmen in PowerPoint hinzufügen
linktitle: Audiorahmen in PowerPoint hinzufügen
second_title: Aspose.Slides Java PowerPoint-Verarbeitungs-API
description: Erfahren Sie, wie Sie mit Aspose.Slides für Java Audiorahmen zu PowerPoint-Präsentationen hinzufügen. Werten Sie Ihre Präsentationen mühelos mit ansprechenden Audioelementen auf.
weight: 12
url: /de/java/java-powerpoint-shape-media-insertion/add-audio-frame-powerpoint/
---

{< blocks/products/pf/main-wrap-class >}
{< blocks/products/pf/main-container >}
{< blocks/products/pf/tutorial-page-section >}

## Einführung
Das Anreichern von Präsentationen mit Audioelementen kann deren Wirkung und Engagement deutlich steigern. Mit Aspose.Slides für Java wird das Integrieren von Audioframes in PowerPoint-Präsentationen zu einem nahtlosen Prozess. Dieses Tutorial führt Sie Schritt für Schritt durch den Prozess des Hinzufügens von Audioframes zu Ihren Präsentationen mit Aspose.Slides für Java.
## Voraussetzungen
Stellen Sie zunächst sicher, dass die folgenden Voraussetzungen erfüllt sind:
1. Java Development Kit (JDK): Stellen Sie sicher, dass Java auf Ihrem System installiert ist.
2.  Aspose.Slides für Java-Bibliothek: Laden Sie die Aspose.Slides für Java-Bibliothek herunter und installieren Sie sie. Sie können sie von der[Aspose.Slides für Java-Dokumentation](https://reference.aspose.com/slides/java/).
3. Audiodatei: Bereiten Sie die Audiodatei (z. B. im WAV-Format) vor, die Sie Ihrer Präsentation hinzufügen möchten.
## Pakete importieren
Importieren Sie die erforderlichen Pakete in Ihr Java-Projekt:
```java
import com.aspose.slides.*;

import java.io.File;
import java.io.FileInputStream;
import java.io.FileNotFoundException;
```
## Schritt 1: Richten Sie Ihr Projektverzeichnis ein
Stellen Sie sicher, dass Sie für Ihr Projekt eine Verzeichnisstruktur eingerichtet haben. Wenn nicht, erstellen Sie eine, um Ihre Dateien effektiv zu organisieren.
```java
String dataDir = "Your Document Directory";
boolean isExists = new File(dataDir).exists();
if (!isExists)
    new File(dataDir).mkdirs();
```
## Schritt 2: Präsentationsklasse instanziieren
 Instanziieren Sie den`Presentation` Klasse zur Darstellung der PowerPoint-Präsentation.
```java
Presentation pres = new Presentation();
```
## Schritt 3: Folie abrufen und Audiodatei laden
Rufen Sie die erste Folie ab und laden Sie die Audiodatei aus Ihrem Verzeichnis.
```java
ISlide sld = pres.getSlides().get_Item(0);
FileInputStream fstr = new FileInputStream(dataDir + "sampleaudio.wav");
```
## Schritt 4: Audio-Frame hinzufügen
Fügen Sie der Folie den Audiorahmen hinzu.
```java
IAudioFrame audioFrame = sld.getShapes().addAudioFrameEmbedded(50, 150, 100, 100, fstr);
```
## Schritt 5: Audioeigenschaften festlegen
Legen Sie Eigenschaften wie „Wiedergabe über mehrere Folien“, „Audio zurückspulen“, „Wiedergabemodus“ und „Lautstärke“ fest.
```java
audioFrame.setPlayAcrossSlides(true);
audioFrame.setRewindAudio(true);
audioFrame.setPlayMode(AudioPlayModePreset.Auto);
audioFrame.setVolume(AudioVolumeMode.Loud);
```
## Schritt 6: Speichern Sie die Präsentation
Speichern Sie die geänderte Präsentation mit dem hinzugefügten Audiorahmen.
```java
pres.save(dataDir + "AudioFrameEmbed_out.pptx", SaveFormat.Pptx);
```

## Abschluss
Durch die Einbindung von Audioelementen in Ihre PowerPoint-Präsentationen können Sie deren Wirksamkeit steigern und Ihr Publikum fesseln. Mit Aspose.Slides für Java wird das Hinzufügen von Audioframes zum Kinderspiel, sodass Sie mühelos dynamische und ansprechende Präsentationen erstellen können.

## Häufig gestellte Fragen
### Kann ich meiner Präsentation Audiodateien in unterschiedlichen Formaten hinzufügen?
Ja, Aspose.Slides für Java unterstützt verschiedene Audioformate, darunter WAV, MP3 und mehr.
### Ist es möglich, das Timing der Audiowiedergabe in Folien anzupassen?
Auf jeden Fall. Sie können die Audiowiedergabe mit bestimmten Folienübergängen synchronisieren, indem Sie Aspose.Slides für Java verwenden.
### Bietet Aspose.Slides für Java Unterstützung für plattformübergreifende Kompatibilität?
Ja, Sie können PowerPoint-Präsentationen mit eingebetteten Audiorahmen erstellen, die plattformübergreifend kompatibel sind.
### Kann ich das Erscheinungsbild des Audioplayers in der Präsentation anpassen?
Aspose.Slides für Java bietet umfangreiche Anpassungsoptionen, mit denen Sie das Erscheinungsbild des Audioplayers Ihren Wünschen entsprechend anpassen können.
### Gibt es eine Testversion von Aspose.Slides für Java?
 Ja, Sie können eine kostenlose Testversion von Aspose.Slides für Java über deren[Webseite](https://releases.aspose.com/).
{< /blocks/products/pf/tutorial-page-section >}

{< /blocks/products/pf/main-container >}
{< /blocks/products/pf/main-wrap-class >}

{< blocks/products/products-backtop-button >}
