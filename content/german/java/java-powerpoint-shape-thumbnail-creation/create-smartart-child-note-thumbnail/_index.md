---
title: Miniaturbild einer untergeordneten SmartArt-Notiz erstellen
linktitle: Miniaturbild einer untergeordneten SmartArt-Notiz erstellen
second_title: Aspose.Slides Java PowerPoint-Verarbeitungs-API
description: Erfahren Sie, wie Sie mit Aspose.Slides in Java Miniaturansichten von SmartArt-Unternotizen erstellen und so Ihre PowerPoint-Präsentationen mühelos verbessern.
type: docs
weight: 15
url: /de/java/java-powerpoint-shape-thumbnail-creation/create-smartart-child-note-thumbnail/
---
## Einführung
In diesem Tutorial erfahren Sie, wie Sie mit Aspose.Slides in Java Miniaturbilder für SmartArt-Unternotizen erstellen. Aspose.Slides ist eine leistungsstarke Java-API, mit der Entwickler programmgesteuert mit PowerPoint-Präsentationen arbeiten und Folien mühelos erstellen, ändern und bearbeiten können.
## Voraussetzungen
Bevor wir beginnen, stellen Sie sicher, dass Sie über Folgendes verfügen:
1. Auf Ihrem System ist Java Development Kit (JDK) installiert.
2. Aspose.Slides für Java-Bibliothek heruntergeladen und in Ihrem Projekt konfiguriert. Sie können die Bibliothek herunterladen von[Hier](https://releases.aspose.com/slides/java/).

## Pakete importieren
Stellen Sie sicher, dass Sie die erforderlichen Pakete in Ihre Java-Klasse importieren:
```java
import com.aspose.slides.ISmartArt;
import com.aspose.slides.ISmartArtNode;
import com.aspose.slides.Presentation;
import com.aspose.slides.SmartArtLayoutType;
import com.aspose.slides.examples.RunExamples;
import javax.imageio.ImageIO;
import java.awt.image.BufferedImage;
import java.io.File;
import java.io.IOException;
```
## Schritt 1: Richten Sie Ihr Projekt ein
Stellen Sie sicher, dass Sie ein Java-Projekt eingerichtet und mit der Aspose.Slides-Bibliothek konfiguriert haben.
## Schritt 2: Erstellen Sie eine Präsentation
 Instanziieren Sie den`Presentation` Klasse zur Darstellung der PPTX-Datei:
```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
```
## Schritt 3: SmartArt hinzufügen
Fügen Sie Ihrer Präsentationsfolie SmartArt hinzu:
```java
ISmartArt smart = pres.getSlides().get_Item(0).getShapes().addSmartArt(10, 10, 400, 300, SmartArtLayoutType.BasicCycle);
```
## Schritt 4: Erhalten Sie eine Knotenreferenz
Ermitteln Sie die Referenz eines Knotens anhand seines Indexes:
```java
ISmartArtNode node = smart.getNodes().get_Item(1);
```
## Schritt 5: Miniaturansicht abrufen
Rufen Sie das Miniaturbild des SmartArt-Knotens ab:
```java
BufferedImage bmp = node.getShapes().get_Item(0).getThumbnail();
```
## Schritt 6: Miniaturansicht speichern
Speichern Sie das Miniaturbild in einer Datei:
```java
ImageIO.write(bmp, "jpeg", new File(dataDir + "SmartArt_ChildNote_Thumbnail_out.jpeg"));
```
Wiederholen Sie diese Schritte nach Bedarf für jeden SmartArt-Knoten in Ihrer Präsentation.

## Abschluss
In diesem Tutorial haben wir gelernt, wie man mit Aspose.Slides in Java Miniaturbilder von SmartArt-Unternotizen erstellt. Mit diesem Wissen können Sie Ihre PowerPoint-Präsentationen programmgesteuert verbessern und ganz einfach optisch ansprechende Elemente hinzufügen.
## Häufig gestellte Fragen
### Kann ich Aspose.Slides verwenden, um vorhandene PowerPoint-Dateien zu bearbeiten?
Ja, mit Aspose.Slides können Sie vorhandene PowerPoint-Dateien ändern, einschließlich des Hinzufügens, Entfernens oder Bearbeitens von Folien und deren Inhalten.
### Unterstützt Aspose.Slides den Export von Folien in verschiedene Dateiformate?
Auf jeden Fall! Aspose.Slides unterstützt den Export von Folien in verschiedene Formate, darunter PDF, Bilder und HTML.
### Ist Aspose.Slides für die PowerPoint-Automatisierung auf Unternehmensebene geeignet?
Ja, Aspose.Slides ist darauf ausgelegt, PowerPoint-Automatisierungsaufgaben auf Unternehmensebene effizient und zuverlässig zu erledigen.
### Kann ich mit Aspose.Slides programmgesteuert komplexe SmartArt-Diagramme erstellen?
Sicherlich! Aspose.Slides bietet umfassende Unterstützung für die Erstellung und Bearbeitung von SmartArt-Diagrammen unterschiedlicher Komplexität.
### Bietet Aspose.Slides technischen Support für Entwickler?
 Ja, Aspose.Slides bietet dedizierten technischen Support für Entwickler über ihre[Forum](https://forum.aspose.com/c/slides/11) und andere Kanäle.