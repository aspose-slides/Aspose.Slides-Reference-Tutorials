---
title: Einfache Linie zur Folie hinzufügen
linktitle: Einfache Linie zur Folie hinzufügen
second_title: Aspose.Slides Java PowerPoint-Verarbeitungs-API
description: Erfahren Sie, wie Sie mit Aspose.Slides für Java programmgesteuert eine einfache Linie zu einer PowerPoint-Folie hinzufügen. Steigern Sie Ihre Produktivität mit dieser Schritt-für-Schritt-Anleitung.
type: docs
weight: 14
url: /de/java/java-powerpoint-shape-media-insertion/add-plain-line-slide/
---
## Einführung
Aspose.Slides für Java ist eine leistungsstarke Bibliothek, die es Java-Entwicklern ermöglicht, programmgesteuert mit PowerPoint-Präsentationen zu arbeiten. Mit Aspose.Slides können Sie PowerPoint-Dateien ganz einfach erstellen, ändern und konvertieren und so Zeit und Mühe sparen. In diesem Tutorial führen wir Sie durch den Vorgang, mit Aspose.Slides für Java einer Folie in einer PowerPoint-Präsentation eine einfache Linie hinzuzufügen.
## Voraussetzungen
Bevor wir beginnen, stellen Sie sicher, dass Sie die folgenden Voraussetzungen erfüllen:
- Auf Ihrem System ist Java Development Kit (JDK) installiert.
- Aspose.Slides für Java-Bibliothek heruntergeladen und zu Ihrem Java-Projekt hinzugefügt
- Grundkenntnisse der Programmiersprache Java

## Pakete importieren
Zu Beginn müssen Sie die erforderlichen Pakete in Ihren Java-Code importieren. So können Sie das tun:
```java
import com.aspose.slides.ISlide;
import com.aspose.slides.Presentation;
import com.aspose.slides.SaveFormat;
import com.aspose.slides.ShapeType;
import com.aspose.slides.examples.RunExamples;
import java.io.File;
```
## Schritt 1: Einrichten der Umgebung
 Erstellen Sie zunächst ein neues Java-Projekt und fügen Sie die Bibliothek Aspose.Slides für Java zum Klassenpfad Ihres Projekts hinzu. Sie können die Bibliothek von herunterladen[Hier](https://releases.aspose.com/slides/java/).
## Schritt 2: Erstellen Sie eine neue Präsentation
 Als nächstes instantiieren Sie den`Presentation` Klasse, um eine neue PowerPoint-Präsentation zu erstellen.
```java
Presentation pres = new Presentation();
```
## Schritt 3: Eine Folie hinzufügen
Holen Sie sich die erste Folie der Präsentation und speichern Sie sie in einer Variablen.
```java
ISlide slide = pres.getSlides().get_Item(0);
```
## Schritt 4: Eine Linienform hinzufügen
Fügen Sie der Folie jetzt eine AutoForm vom Typ „Linie“ hinzu.
```java
slide.getShapes().addAutoShape(ShapeType.Line, 50, 150, 300, 0);
```
## Schritt 5: Speichern Sie die Präsentation
Speichern Sie die Präsentation abschließend auf der Festplatte.
```java
pres.save("Your Document Directory/LineShape1_out.pptx", SaveFormat.Pptx);
```

## Abschluss
Herzlichen Glückwunsch! Sie haben mit Aspose.Slides für Java erfolgreich eine einfache Linie zu einer Folie in einer PowerPoint-Präsentation hinzugefügt. Mit Aspose.Slides können Sie PowerPoint-Dateien problemlos programmgesteuert bearbeiten und so eine Welt voller Möglichkeiten für Ihre Java-Anwendungen eröffnen.

## Häufig gestellte Fragen
### Kann ich die Eigenschaften der Linienform anpassen?
Ja, Sie können verschiedene Eigenschaften wie Linienfarbe, Breite, Stil und mehr mit der Aspose.Slides API anpassen.
### Ist Aspose.Slides mit verschiedenen Versionen von PowerPoint kompatibel?
Ja, Aspose.Slides unterstützt verschiedene PowerPoint-Formate, darunter PPT, PPTX und andere, und gewährleistet so die Kompatibilität zwischen verschiedenen Versionen.
### Bietet Aspose.Slides Unterstützung für das Hinzufügen anderer Formen außer Linien?
Auf jeden Fall! Aspose.Slides bietet eine große Auswahl an Formtypen, darunter Rechtecke, Kreise, Pfeile und mehr.
### Kann ich der Folie zusätzlich zur Linienform Text hinzufügen?
Ja, Sie können der Folie mit der Aspose.Slides-API Text, Bilder und andere Inhalte hinzufügen.
### Gibt es eine kostenlose Testversion für Aspose.Slides?
Ja, Sie können eine kostenlose Testversion von Aspose.Slides herunterladen von[Hier](https://releases.aspose.com/).