---
title: Miniaturbilder von Formen in PowerPoint erstellen
linktitle: Miniaturbilder von Formen in PowerPoint erstellen
second_title: Aspose.Slides Java PowerPoint-Verarbeitungs-API
description: Erfahren Sie, wie Sie mit Aspose.Slides für Java Miniaturansichten von Formen in PowerPoint-Präsentationen erstellen. Eine Schritt-für-Schritt-Anleitung wird bereitgestellt.
weight: 14
url: /de/java/java-powerpoint-shape-thumbnail-creation/create-shape-thumbnail-powerpoint/
---

{< blocks/products/pf/main-wrap-class >}
{< blocks/products/pf/main-container >}
{< blocks/products/pf/tutorial-page-section >}

## Einführung
In diesem Tutorial beschäftigen wir uns mit der Erstellung von Formvorschaubildern in PowerPoint-Präsentationen mithilfe von Aspose.Slides für Java. Aspose.Slides ist eine leistungsstarke Bibliothek, die es Entwicklern ermöglicht, programmgesteuert mit PowerPoint-Dateien zu arbeiten und verschiedene Aufgaben zu automatisieren, darunter auch die Generierung von Formvorschaubildern.
## Voraussetzungen
Bevor wir beginnen, stellen Sie sicher, dass Sie die folgenden Voraussetzungen erfüllen:
- Grundkenntnisse der Java-Programmierung.
- Auf Ihrem System ist Java Development Kit (JDK) installiert.
-  Aspose.Slides für Java-Bibliothek heruntergeladen und in Ihrem Projekt eingerichtet. Sie können es herunterladen von[Hier](https://releases.aspose.com/slides/java/).

## Pakete importieren
Zunächst müssen Sie die erforderlichen Pakete in Ihren Java-Code importieren, um die Funktionen von Aspose.Slides nutzen zu können. Fügen Sie am Anfang Ihrer Java-Datei die folgenden Importanweisungen ein:
```java
import com.aspose.slides.Presentation;

import javax.imageio.ImageIO;
import java.awt.image.BufferedImage;
import java.io.File;
import java.io.IOException;
```
## Schritt 1: Dokumentverzeichnis definieren
```java
String dataDir = "Your Document Directory";
```
 Ersetzen`"Your Document Directory"` durch den Pfad zum Verzeichnis, das Ihre PowerPoint-Datei enthält.
## Schritt 2: Präsentationsobjekt instanziieren
```java
Presentation presentation = new Presentation(dataDir + "HelloWorld.pptx");
```
 Erstellen Sie eine neue Instanz des`Presentation` Klasse und übergeben Sie den Pfad zu Ihrer PowerPoint-Datei als Parameter.
## Schritt 3: Form-Miniaturansicht generieren
```java
BufferedImage bitmap = presentation.getSlides().get_Item(0).getShapes().get_Item(0).getThumbnail();
```
Rufen Sie die Miniaturansicht der gewünschten Form von der ersten Folie der Präsentation ab.
## Schritt 4: Miniaturbild speichern
```java
ImageIO.write(bitmap, ".png", new File(dataDir + "Shape_thumbnail_out.png"));
```
Speichern Sie das generierte Miniaturbild im PNG-Format unter dem angegebenen Dateinamen auf der Festplatte.

## Abschluss
Abschließend hat dieses Tutorial gezeigt, wie Sie mit Aspose.Slides für Java Miniaturbilder von Formen in PowerPoint-Präsentationen erstellen. Indem Sie der Schritt-für-Schritt-Anleitung folgen und die bereitgestellten Codeausschnitte verwenden, können Sie Miniaturbilder von Formen effizient programmgesteuert erstellen.

## Häufig gestellte Fragen
### Kann ich auf jeder Folie der Präsentation Miniaturansichten für Formen erstellen?
Ja, Sie können den Code ändern, um Formen auf jeder Folie anzusprechen, indem Sie den Folienindex entsprechend anpassen.
### Unterstützt Aspose.Slides andere Bildformate zum Speichern von Miniaturansichten?
Ja, neben PNG unterstützt Aspose.Slides das Speichern von Miniaturansichten in verschiedenen Bildformaten wie JPEG, GIF und BMP.
### Ist Aspose.Slides für die kommerzielle Nutzung geeignet?
 Ja, Aspose.Slides bietet kommerzielle Lizenzen für Unternehmen und Organisationen an. Sie können eine Lizenz erwerben bei[Hier](https://purchase.aspose.com/buy).
### Kann ich Aspose.Slides vor dem Kauf ausprobieren?
 Absolut! Sie können eine kostenlose Testversion von Aspose.Slides herunterladen von[Hier](https://releases.aspose.com/) um seine Funktionen und Fähigkeiten zu bewerten.
### Wo finde ich Unterstützung für Aspose.Slides?
 Wenn Sie Fragen haben oder Hilfe zu Aspose.Slides benötigen, besuchen Sie die[Aspose.Slides-Forum](https://forum.aspose.com/c/slides/11) zur Unterstützung.
{< /blocks/products/pf/tutorial-page-section >}

{< /blocks/products/pf/main-container >}
{< /blocks/products/pf/main-wrap-class >}

{< blocks/products/products-backtop-button >}
