---
"description": "Entdecken Sie, wie Sie mit Aspose.Slides mithilfe von Java den SmartArt-Knotentext in PowerPoint aktualisieren und so die Präsentationsanpassung verbessern."
"linktitle": "Ändern Sie den Text auf dem SmartArt-Knoten mit Java"
"second_title": "Aspose.Slides Java PowerPoint-Verarbeitungs-API"
"title": "Ändern Sie den Text auf dem SmartArt-Knoten mit Java"
"url": "/de/java/java-powerpoint-smartart-manipulation/change-text-smartart-node-java/"
"weight": 22
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Ändern Sie den Text auf dem SmartArt-Knoten mit Java

## Einführung
SmartArt in PowerPoint ist eine leistungsstarke Funktion zum Erstellen optisch ansprechender Diagramme. Aspose.Slides für Java bietet umfassende Unterstützung für die programmgesteuerte Bearbeitung von SmartArt-Elementen. In diesem Tutorial führen wir Sie durch die Textänderung in einem SmartArt-Knoten mit Java.
## Voraussetzungen
Bevor Sie beginnen, stellen Sie sicher, dass Sie über Folgendes verfügen:
- Auf Ihrem System ist das Java Development Kit (JDK) installiert.
- Aspose.Slides für die Java-Bibliothek heruntergeladen und in Ihrem Java-Projekt referenziert.
- Grundlegende Kenntnisse der Java-Programmierung.

## Pakete importieren
Importieren Sie zunächst die erforderlichen Pakete, um in Ihrem Java-Code auf die Aspose.Slides-Funktionalität zuzugreifen.
```java
import com.aspose.slides.*;
```
Lassen Sie uns das Beispiel in mehrere Schritte unterteilen:
## Schritt 1: Präsentationsobjekt initialisieren
```java
Presentation presentation = new Presentation();
```
Erstellen Sie eine neue Instanz des `Presentation` Klasse, mit einer PowerPoint-Präsentation zu arbeiten.
## Schritt 2: SmartArt zur Folie hinzufügen
```java
ISmartArt smart = presentation.getSlides().get_Item(0).getShapes().addSmartArt(10, 10, 400, 300, SmartArtLayoutType.BasicCycle);
```
Fügen Sie SmartArt zur ersten Folie hinzu. In diesem Beispiel verwenden wir die `BasicCycle` Layout.
## Schritt 3: Zugriff auf den SmartArt-Knoten
```java
ISmartArtNode node = smart.getNodes().get_Item(1);
```
Holen Sie sich einen Verweis auf den zweiten Stammknoten des SmartArt.
## Schritt 4: Text auf Knoten festlegen
```java
node.getTextFrame().setText("Second root node");
```
Legen Sie den Text für den ausgewählten SmartArt-Knoten fest.
## Schritt 5: Präsentation speichern
```java
presentation.save(dataDir + "ChangeText_On_SmartArt_Node_out.pptx", SaveFormat.Pptx);
```
Speichern Sie die geänderte Präsentation an einem angegebenen Ort.

## Abschluss
In diesem Tutorial haben wir gezeigt, wie Sie Text in einem SmartArt-Knoten mit Java und Aspose.Slides ändern. Mit diesem Wissen können Sie SmartArt-Elemente in Ihren PowerPoint-Präsentationen dynamisch bearbeiten und so deren visuelle Attraktivität und Übersichtlichkeit verbessern.
## Häufig gestellte Fragen
### Kann ich das Layout des SmartArt ändern, nachdem ich es zur Folie hinzugefügt habe?
Ja, Sie können das Layout ändern, indem Sie auf die `SmartArt.setAllNodes(LayoutType)` Verfahren.
### Ist Aspose.Slides mit Java 11 kompatibel?
Ja, Aspose.Slides für Java ist mit Java 11 und neueren Versionen kompatibel.
### Kann ich das Erscheinungsbild von SmartArt-Knoten programmgesteuert anpassen?
Natürlich können Sie verschiedene Eigenschaften wie Farbe, Größe und Form mithilfe der Aspose.Slides-API ändern.
### Unterstützt Aspose.Slides andere Arten von SmartArt-Layouts?
Ja, Aspose.Slides unterstützt eine große Auswahl an SmartArt-Layouts, sodass Sie dasjenige auswählen können, das Ihren Präsentationsanforderungen am besten entspricht.
### Wo finde ich weitere Ressourcen und Support für Aspose.Slides?
Besuchen Sie die [Aspose.Slides-Dokumentation](https://reference.aspose.com/slides/java/) für detaillierte API-Referenzen und Tutorials. Darüber hinaus können Sie Hilfe von der [Aspose.Slides-Forum](https://forum.aspose.com/c/slides/11) oder erwägen Sie den Kauf eines [vorläufige Lizenz](https://purchase.aspose.com/temporary-license/) für professionelle Unterstützung.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}