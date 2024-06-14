---
title: Hochgestellten und tiefgestellten Text in Java PowerPoint hinzufügen
linktitle: Hochgestellten und tiefgestellten Text in Java PowerPoint hinzufügen
second_title: Aspose.Slides Java PowerPoint-Verarbeitungs-API
description: Erfahren Sie, wie Sie mit Aspose.Slides für Java hochgestellten und tiefgestellten Text in Java PowerPoint-Präsentationen einfügen. Perfekt zum Verbessern Ihrer Folien.
type: docs
weight: 13
url: /de/java/java-powerpoint-text-box-manipulation/add-superscript-subscript-text-java-powerpoint/
---
## Einführung
Das Erstellen ansprechender und informativer PowerPoint-Präsentationen erfordert häufig die Verwendung von Formatierungsfunktionen wie hochgestelltem und tiefgestelltem Text. Dieses Tutorial führt Sie durch den Prozess der Einbindung von hochgestelltem und tiefgestelltem Text in Ihre Java PowerPoint-Präsentationen mit Aspose.Slides für Java.
## Voraussetzungen
Bevor Sie beginnen, stellen Sie sicher, dass Sie über Folgendes verfügen:
- Auf Ihrem System ist Java Development Kit (JDK) installiert.
-  Aspose.Slides für Java-Bibliothek. Sie können es herunterladen von[Hier](https://releases.aspose.com/slides/java/).
- Eine integrierte Entwicklungsumgebung (IDE) wie IntelliJ IDEA oder Eclipse, die für die Java-Entwicklung eingerichtet ist.
- Grundlegende Kenntnisse in Java-Programmierung und PowerPoint-Präsentationen.

## Pakete importieren
Importieren Sie zunächst die erforderlichen Pakete von Aspose.Slides für Java:
```java
import com.aspose.slides.*;
```
## Schritt 1: Präsentation vorbereiten
```java
// Der Pfad zum Dokumentverzeichnis.
String dataDir = "Your Document Directory";
Presentation presentation = new Presentation();
```
## Schritt 2: Zugriff auf die Folie
```java
// Holen Sie sich die erste Folie
ISlide slide = presentation.getSlides().get_Item(0);
```
## Schritt 3: Erstellen Sie ein Textfeld
```java
// Erstellen einer AutoForm als Textfeld
IAutoShape shape = slide.getShapes().addAutoShape(ShapeType.Rectangle, 100, 100, 200, 100);
ITextFrame textFrame = shape.getTextFrame();
textFrame.getParagraphs().clear();
```
## Schritt 4: Hochgestellten Text hinzufügen
```java
// Erstellen Sie einen Absatz für den Haupttext
IParagraph mainParagraph = new Paragraph();
IPortion mainPortion = new Portion();
mainPortion.setText("SlideTitle");
mainParagraph.getPortions().add(mainPortion);
// Erstellen Sie einen Abschnitt für den hochgestellten Text
IPortion superPortion = new Portion();
superPortion.getPortionFormat().setEscapement(30); // Escapezeichen für hochgestellte Ziffern festlegen
superPortion.setText("TM");
mainParagraph.getPortions().add(superPortion);
//Fügen Sie den Hauptabsatz mit hochgestellter Zahl zum Textfeld hinzu
textFrame.getParagraphs().add(mainParagraph);
```
## Schritt 5: Tiefgestellten Text hinzufügen
```java
// Einen weiteren Absatz für tiefgestellten Text erstellen
IParagraph subscriptParagraph = new Paragraph();
IPortion subscriptPortion = new Portion();
subscriptPortion.setText("a");
subscriptParagraph.getPortions().add(subscriptPortion);
// Erstellen Sie einen Abschnitt für den tiefgestellten Text
IPortion subPortion = new Portion();
subPortion.getPortionFormat().setEscapement(-25); // Escapezeichen für Index festlegen
subPortion.setText("i");
subscriptParagraph.getPortions().add(subPortion);
// Fügen Sie dem Textfeld den tiefgestellten Absatz hinzu
textFrame.getParagraphs().add(subscriptParagraph);
```
## Schritt 6: Speichern Sie die Präsentation
```java
// Speichern der Präsentation
presentation.save(dataDir + "TestOut.pptx", SaveFormat.Pptx);
```

## Abschluss
In diesem Tutorial haben wir untersucht, wie Sie Ihre Java PowerPoint-Präsentationen mit hochgestelltem und tiefgestelltem Text mithilfe von Aspose.Slides für Java verbessern können. Indem Sie diese Schritte befolgen, können Sie optisch ansprechendere und informativere Folien erstellen, die Ihren Inhalt effektiv vermitteln.

## Häufig gestellte Fragen
### Was ist Aspose.Slides für Java?
Aspose.Slides für Java ist eine robuste Bibliothek, mit der Entwickler PowerPoint-Präsentationen programmgesteuert erstellen, bearbeiten und konvertieren können.
### Wo finde ich weitere Dokumentation zu Aspose.Slides für Java?
 Detaillierte Dokumentation finden Sie[Hier](https://reference.aspose.com/slides/java/).
### Wie kann ich eine temporäre Lizenz für Aspose.Slides für Java erhalten?
 Sie können eine vorübergehende Lizenz erhalten[Hier](https://purchase.aspose.com/temporary-license/).
### Kann ich Aspose.Slides für Java kostenlos testen?
 Ja, Sie können eine kostenlose Testversion herunterladen von[Hier](https://releases.aspose.com/).
### Wo erhalte ich Support für Aspose.Slides für Java?
 Für Unterstützung und Diskussionen besuchen Sie die[Aspose.Slides-Forum](https://forum.aspose.com/c/slides/11).