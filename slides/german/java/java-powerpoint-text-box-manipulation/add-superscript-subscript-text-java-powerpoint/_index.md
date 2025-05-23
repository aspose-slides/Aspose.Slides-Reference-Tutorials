---
"description": "Erfahren Sie, wie Sie mit Aspose.Slides für Java hochgestellten und tiefgestellten Text in Java-PowerPoint-Präsentationen hinzufügen. Perfekt zum Optimieren Ihrer Folien."
"linktitle": "Hochgestellten und tiefgestellten Text in Java PowerPoint hinzufügen"
"second_title": "Aspose.Slides Java PowerPoint-Verarbeitungs-API"
"title": "Hochgestellten und tiefgestellten Text in Java PowerPoint hinzufügen"
"url": "/de/java/java-powerpoint-text-box-manipulation/add-superscript-subscript-text-java-powerpoint/"
"weight": 13
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Hochgestellten und tiefgestellten Text in Java PowerPoint hinzufügen

## Einführung
Für ansprechende und informative PowerPoint-Präsentationen sind häufig Formatierungsfunktionen wie hochgestellter und tiefgestellter Text erforderlich. Dieses Tutorial führt Sie durch die Integration von hochgestelltem und tiefgestelltem Text in Ihre Java PowerPoint-Präsentationen mit Aspose.Slides für Java.
## Voraussetzungen
Bevor Sie beginnen, stellen Sie sicher, dass Sie über Folgendes verfügen:
- Auf Ihrem System ist das Java Development Kit (JDK) installiert.
- Aspose.Slides für Java-Bibliothek. Sie können es herunterladen von [Hier](https://releases.aspose.com/slides/java/).
- Eine integrierte Entwicklungsumgebung (IDE) wie IntelliJ IDEA oder Eclipse, die für die Java-Entwicklung eingerichtet ist.
- Grundkenntnisse in Java-Programmierung und PowerPoint-Präsentationen.

## Pakete importieren
Importieren Sie zunächst die erforderlichen Pakete aus Aspose.Slides für Java:
```java
import com.aspose.slides.*;
```
## Schritt 1: Einrichten der Präsentation
```java
// Der Pfad zum Dokumentenverzeichnis.
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
superPortion.getPortionFormat().setEscapement(30); // Escapezeichen für hochgestellte Zeichen festlegen
superPortion.setText("TM");
mainParagraph.getPortions().add(superPortion);
// Fügen Sie den Hauptabsatz mit hochgestellter Zahl zum Textfeld hinzu
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
In diesem Tutorial haben wir untersucht, wie Sie Ihre Java PowerPoint-Präsentationen mit hoch- und tiefgestelltem Text mithilfe von Aspose.Slides für Java verbessern können. Mit diesen Schritten erstellen Sie optisch ansprechendere und informativere Folien, die Ihre Inhalte effektiv vermitteln.

## Häufig gestellte Fragen
### Was ist Aspose.Slides für Java?
Aspose.Slides für Java ist eine robuste Bibliothek, mit der Entwickler PowerPoint-Präsentationen programmgesteuert erstellen, bearbeiten und konvertieren können.
### Wo finde ich weitere Dokumentation zu Aspose.Slides für Java?
Eine ausführliche Dokumentation finden Sie [Hier](https://reference.aspose.com/slides/java/).
### Wie kann ich eine temporäre Lizenz für Aspose.Slides für Java erhalten?
Sie können eine vorübergehende Lizenz erhalten [Hier](https://purchase.aspose.com/temporary-license/).
### Kann ich Aspose.Slides für Java kostenlos testen?
Ja, Sie können eine kostenlose Testversion herunterladen von [Hier](https://releases.aspose.com/).
### Wo erhalte ich Support für Aspose.Slides für Java?
Für Unterstützung und Diskussionen besuchen Sie die [Aspose.Slides-Forum](https://forum.aspose.com/c/slides/11).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}