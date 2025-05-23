---
"description": "Erfahren Sie, wie Sie mit Aspose.Slides für Java Formen in PowerPoint-Präsentationen klonen. Optimieren Sie Ihren Workflow mit diesem leicht verständlichen Tutorial."
"linktitle": "Formen in PowerPoint klonen"
"second_title": "Aspose.Slides Java PowerPoint-Verarbeitungs-API"
"title": "Formen in PowerPoint klonen"
"url": "/de/java/java-powerpoint-animation-shape-manipulation/clone-shapes-powerpoint/"
"weight": 16
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Formen in PowerPoint klonen

## Einführung
In diesem Tutorial erfahren Sie, wie Sie mit Aspose.Slides für Java Formen in PowerPoint-Präsentationen klonen. Durch das Klonen von Formen können Sie vorhandene Formen innerhalb einer Präsentation duplizieren. Dies ist besonders nützlich, um konsistente Layouts zu erstellen oder Elemente über mehrere Folien hinweg zu wiederholen.
## Voraussetzungen
Bevor wir beginnen, stellen Sie sicher, dass Sie die folgenden Voraussetzungen erfüllen:
1. Java Development Kit (JDK): Stellen Sie sicher, dass das Java Development Kit auf Ihrem System installiert ist. Sie können die neueste Version von der Website herunterladen und installieren. [Webseite](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html).
2. Aspose.Slides für Java-Bibliothek: Laden Sie die Aspose.Slides für Java-Bibliothek herunter und binden Sie sie in Ihr Java-Projekt ein. Den Download-Link finden Sie hier. [Hier](https://releases.aspose.com/slides/java/).

## Pakete importieren
Zunächst müssen Sie die erforderlichen Pakete in Ihr Java-Projekt importieren. Diese Pakete bieten die erforderlichen Funktionen für die Arbeit mit PowerPoint-Präsentationen mit Aspose.Slides für Java.
```java
import com.aspose.slides.*;

```
## Schritt 1: Laden Sie die Präsentation
Zuerst müssen Sie die PowerPoint-Präsentation mit den zu klonenden Formen laden. Verwenden Sie die `Presentation` Klasse zum Laden der Quellpräsentation.
```java
String dataDir = "Your Document Directory";
Presentation srcPres = new Presentation(dataDir + "SourceFrame.pptx");
```
## Schritt 2: Klonen Sie die Formen
Als Nächstes klonen Sie die Formen aus der Quellpräsentation und fügen sie einer neuen Folie in derselben Präsentation hinzu. Dazu greifen Sie auf die Quellformen zu, erstellen eine neue Folie und fügen die geklonten Formen der neuen Folie hinzu.
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
Das Klonen von Formen in PowerPoint-Präsentationen mit Aspose.Slides für Java ist ein unkomplizierter Prozess, der Ihren Workflow bei der Präsentationserstellung optimieren kann. Mit den in diesem Tutorial beschriebenen Schritten können Sie vorhandene Formen einfach duplizieren und nach Bedarf anpassen.

## Häufig gestellte Fragen
### Kann ich Formen über verschiedene Folien hinweg klonen?
Ja, Sie können Formen von jeder Folie in der Präsentation klonen und sie mit Aspose.Slides für Java einer anderen Folie hinzufügen.
### Gibt es Einschränkungen beim Klonen von Formen?
Obwohl Aspose.Slides für Java robuste Klonfunktionen bietet, werden komplexe Formen oder Animationen möglicherweise nicht perfekt repliziert.
### Kann ich die geklonten Formen ändern, nachdem ich sie einer Folie hinzugefügt habe?
Absolut. Sobald die Formen geklont und einer Folie hinzugefügt wurden, können Sie ihre Eigenschaften, ihren Stil und ihren Inhalt nach Bedarf ändern.
### Unterstützt Aspose.Slides für Java das Klonen anderer Elemente außer Formen?
Ja, Sie können Folien, Text, Bilder und andere Elemente innerhalb einer PowerPoint-Präsentation mit Aspose.Slides für Java klonen.
### Gibt es eine Testversion für Aspose.Slides für Java?
Ja, Sie können eine kostenlose Testversion von Aspose.Slides für Java von der [Webseite](https://releases.aspose.com/slides/java/).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}