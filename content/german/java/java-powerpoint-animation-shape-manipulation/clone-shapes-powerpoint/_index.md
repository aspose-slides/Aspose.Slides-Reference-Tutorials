---
title: Formen in PowerPoint klonen
linktitle: Formen in PowerPoint klonen
second_title: Aspose.Slides Java PowerPoint-Verarbeitungs-API
description: Erfahren Sie, wie Sie mit Aspose.Slides für Java Formen in PowerPoint-Präsentationen klonen. Optimieren Sie Ihren Workflow mit diesem leicht verständlichen Tutorial.
type: docs
weight: 16
url: /de/java/java-powerpoint-animation-shape-manipulation/clone-shapes-powerpoint/
---
## Einführung
In diesem Tutorial erfahren Sie, wie Sie mit Aspose.Slides für Java Formen in PowerPoint-Präsentationen klonen. Durch das Klonen von Formen können Sie vorhandene Formen innerhalb einer Präsentation duplizieren, was besonders nützlich sein kann, um konsistente Layouts zu erstellen oder Elemente über mehrere Folien hinweg zu wiederholen.
## Voraussetzungen
Bevor wir beginnen, stellen Sie sicher, dass Sie die folgenden Voraussetzungen erfüllen:
1.  Java Development Kit (JDK): Stellen Sie sicher, dass Java Development Kit auf Ihrem System installiert ist. Sie können die neueste Version von der Website herunterladen und installieren.[Webseite](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html).
2.  Aspose.Slides für Java-Bibliothek: Laden Sie die Aspose.Slides für Java-Bibliothek herunter und binden Sie sie in Ihr Java-Projekt ein. Den Download-Link finden Sie[Hier](https://releases.aspose.com/slides/java/).

## Pakete importieren
Zu Beginn müssen Sie die erforderlichen Pakete in Ihr Java-Projekt importieren. Diese Pakete bieten die erforderlichen Funktionen zum Arbeiten mit PowerPoint-Präsentationen mit Aspose.Slides für Java.
```java
import com.aspose.slides.*;
import com.aspose.slides.examples.RunExamples;
```
## Schritt 1: Laden Sie die Präsentation
 Zuerst müssen Sie die PowerPoint-Präsentation mit den Formen laden, die Sie klonen möchten. Verwenden Sie die`Presentation` Klasse zum Laden der Quellpräsentation.
```java
String dataDir = "Your Document Directory";
Presentation srcPres = new Presentation(dataDir + "SourceFrame.pptx");
```
## Schritt 2: Die Formen klonen
Als Nächstes klonen Sie die Formen aus der Quellpräsentation und fügen sie einer neuen Folie in derselben Präsentation hinzu. Dazu greifen Sie auf die Quellformen zu, erstellen eine neue Folie und fügen dann die geklonten Formen der neuen Folie hinzu.
```java
IShapeCollection sourceShapes = srcPres.getSlides().get_Item(0).getShapes();
ILayoutSlide blankLayout = srcPres.getMasters().get_Item(0).getLayoutSlides().getByType(SlideLayoutType.Blank);
ISlide destSlide = srcPres.getSlides().addEmptySlide(blankLayout);
IShapeCollection destShapes = destSlide.getShapes();
destShapes.addClone(sourceShapes.get_Item(1), 50, 150 + sourceShapes.get_Item(0).getHeight());
destShapes.addClone(sourceShapes.get_Item(2));
destShapes.insertClone(0, sourceShapes.get_Item(0), 50, 150);
```
## Schritt 3: Speichern Sie die Präsentation
Speichern Sie abschließend die geänderte Präsentation mit den geklonten Formen in einer neuen Datei.
```java
srcPres.save(dataDir + "CloneShape_out.pptx", SaveFormat.Pptx);
```

## Abschluss
Das Klonen von Formen in PowerPoint-Präsentationen mit Aspose.Slides für Java ist ein unkomplizierter Vorgang, der Ihnen dabei helfen kann, Ihren Workflow bei der Präsentationserstellung zu optimieren. Indem Sie die in diesem Tutorial beschriebenen Schritte befolgen, können Sie vorhandene Formen problemlos duplizieren und nach Bedarf anpassen.

## Häufig gestellte Fragen
### Kann ich Formen über verschiedene Folien hinweg klonen?
Ja, Sie können Formen von jeder Folie in der Präsentation klonen und sie mit Aspose.Slides für Java einer anderen Folie hinzufügen.
### Gibt es irgendwelche Einschränkungen beim Klonen von Formen?
Obwohl Aspose.Slides für Java robuste Klonfunktionen bereitstellt, werden komplexe Formen oder Animationen möglicherweise nicht perfekt repliziert.
### Kann ich die geklonten Formen ändern, nachdem ich sie zu einer Folie hinzugefügt habe?
Auf jeden Fall. Sobald die Formen geklont und einer Folie hinzugefügt wurden, können Sie ihre Eigenschaften, ihren Stil und ihren Inhalt nach Bedarf ändern.
### Unterstützt Aspose.Slides für Java das Klonen anderer Elemente außer Formen?
Ja, Sie können mit Aspose.Slides für Java Folien, Text, Bilder und andere Elemente in einer PowerPoint-Präsentation klonen.
### Gibt es eine Testversion von Aspose.Slides für Java?
 Ja, Sie können eine kostenlose Testversion von Aspose.Slides für Java herunterladen von der[Webseite](https://releases.aspose.com/slides/java/).