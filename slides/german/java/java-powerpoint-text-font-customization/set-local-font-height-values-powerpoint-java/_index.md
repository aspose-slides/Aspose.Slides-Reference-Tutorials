---
"description": "Erfahren Sie, wie Sie mit Aspose.Slides die Schrifthöhe in PowerPoint-Präsentationen mithilfe von Java anpassen. Optimieren Sie mühelos die Textformatierung in Ihren Folien."
"linktitle": "Festlegen lokaler Schrifthöhenwerte in PowerPoint mit Java"
"second_title": "Aspose.Slides Java PowerPoint-Verarbeitungs-API"
"title": "Festlegen lokaler Schrifthöhenwerte in PowerPoint mit Java"
"url": "/de/java/java-powerpoint-text-font-customization/set-local-font-height-values-powerpoint-java/"
"weight": 17
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Festlegen lokaler Schrifthöhenwerte in PowerPoint mit Java

## Einführung
In diesem Tutorial lernen Sie, wie Sie die Schrifthöhe in PowerPoint-Präsentationen mit Aspose.Slides für Java auf verschiedenen Ebenen anpassen. Die Kontrolle der Schriftgrößen ist entscheidend für optisch ansprechende und strukturierte Präsentationen. Wir zeigen Ihnen Schritt für Schritt anhand von Beispielen, wie Sie die Schrifthöhe für verschiedene Textelemente festlegen.
## Voraussetzungen
Bevor Sie beginnen, stellen Sie sicher, dass Sie über Folgendes verfügen:
- Java Development Kit (JDK) auf Ihrem System installiert
- Aspose.Slides für Java-Bibliothek. Sie können es herunterladen [Hier](https://releases.aspose.com/slides/java/).
- Grundkenntnisse in Java-Programmierung und PowerPoint-Präsentationen
## Pakete importieren
Stellen Sie sicher, dass Sie die erforderlichen Aspose.Slides-Pakete in Ihre Java-Datei aufnehmen:
```java
import com.aspose.slides.*;
```
## Schritt 1: Initialisieren eines Präsentationsobjekts
Erstellen Sie zunächst ein neues PowerPoint-Präsentationsobjekt:
```java
Presentation pres = new Presentation();
```
## Schritt 2: Fügen Sie eine Form und einen Textrahmen hinzu
Fügen Sie der ersten Folie eine automatische Form mit einem Textrahmen hinzu:
```java
IAutoShape newShape = pres.getSlides().get_Item(0).getShapes().addAutoShape(ShapeType.Rectangle, 100, 100, 400, 75, false);
newShape.addTextFrame("");
```
## Schritt 3: Textabschnitte erstellen
Definieren Sie Textabschnitte mit unterschiedlichen Schrifthöhen:
```java
IPortion portion0 = new Portion("Sample text with first portion");
IPortion portion1 = new Portion(" and second portion.");
newShape.getTextFrame().getParagraphs().get_Item(0).getPortions().add(portion0);
newShape.getTextFrame().getParagraphs().get_Item(0).getPortions().add(portion1);
```
## Schritt 4: Schrifthöhen festlegen
Stellen Sie die Schrifthöhe auf unterschiedliche Ebenen ein:
```java
pres.getDefaultTextStyle().getLevel(0).getDefaultPortionFormat().setFontHeight(24);
newShape.getTextFrame().getParagraphs().get_Item(0).getParagraphFormat().getDefaultPortionFormat().setFontHeight(40);
newShape.getTextFrame().getParagraphs().get_Item(0).getPortions().get_Item(0).getPortionFormat().setFontHeight(55);
newShape.getTextFrame().getParagraphs().get_Item(0).getPortions().get_Item(1).getPortionFormat().setFontHeight(18);
```
## Schritt 5: Speichern Sie die Präsentation
Speichern Sie die geänderte Präsentation in einer Datei:
```java
pres.save("YourOutputDirectory/SetLocalFontHeightValues.pptx", SaveFormat.Pptx);
```

## Abschluss
Dieses Tutorial zeigt, wie Sie die Schrifthöhe in PowerPoint-Folien programmgesteuert mit Aspose.Slides für Java anpassen. Durch die Anpassung der Schriftgrößen auf verschiedenen Ebenen (präsentationsweit, Absatz und Teilbereich) können Sie die Textformatierung in Ihren Präsentationen präzise steuern.
## Häufig gestellte Fragen
### Was ist Aspose.Slides für Java?
Aspose.Slides für Java ist eine leistungsstarke API zur programmgesteuerten Bearbeitung von PowerPoint-Präsentationen.
### Wo finde ich Dokumentation für Aspose.Slides für Java?
Die Dokumentation finden Sie [Hier](https://reference.aspose.com/slides/java/).
### Kann ich Aspose.Slides für Java vor dem Kauf testen?
Ja, Sie können eine kostenlose Testversion erhalten [Hier](https://releases.aspose.com/).
### Wie erhalte ich Support für Aspose.Slides für Java?
Für Unterstützung besuchen Sie die [Aspose.Slides-Forum](https://forum.aspose.com/c/slides/11).
### Wo kann ich eine Lizenz für Aspose.Slides für Java erwerben?
Sie können eine Lizenz erwerben [Hier](https://purchase.aspose.com/buy).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}