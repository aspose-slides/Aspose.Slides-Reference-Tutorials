---
"description": "Entdecken Sie, wie Sie mit Java und Aspose.Slides Knoten an bestimmten Positionen in SmartArt hinzufügen. Erstellen Sie mühelos dynamische Präsentationen."
"linktitle": "Fügen Sie mit Java Knoten an bestimmten Positionen in SmartArt hinzu"
"second_title": "Aspose.Slides Java PowerPoint-Verarbeitungs-API"
"title": "Fügen Sie mit Java Knoten an bestimmten Positionen in SmartArt hinzu"
"url": "/de/java/java-powerpoint-smartart-manipulation/add-nodes-specific-position-smartart-java/"
"weight": 16
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Fügen Sie mit Java Knoten an bestimmten Positionen in SmartArt hinzu

## Einführung
In diesem Tutorial führen wir Sie durch das Hinzufügen von Knoten an bestimmten Positionen in SmartArt mithilfe von Java und Aspose.Slides. SmartArt ist eine PowerPoint-Funktion, mit der Sie optisch ansprechende Diagramme und Tabellen erstellen können.
## Voraussetzungen
Bevor Sie beginnen, stellen Sie sicher, dass Sie über Folgendes verfügen:
1. Auf Ihrem System ist das Java Development Kit (JDK) installiert.
2. Aspose.Slides für Java-Bibliothek heruntergeladen. Sie können es herunterladen von [Hier](https://releases.aspose.com/slides/java/).
3. Grundkenntnisse der Programmiersprache Java.

## Pakete importieren
Importieren wir zunächst die erforderlichen Pakete in unseren Java-Code:
```java
import com.aspose.slides.*;
import java.io.File;
```
## Schritt 1: Erstellen einer Präsentationsinstanz
Beginnen Sie mit der Erstellung einer Instanz der Klasse „Präsentation“:
```java
Presentation pres = new Presentation();
```
## Schritt 2: Zugriff auf die Präsentationsfolie
Greifen Sie auf die Folie zu, der Sie das SmartArt hinzufügen möchten:
```java
ISlide slide = pres.getSlides().get_Item(0);
```
## Schritt 3: SmartArt-Form hinzufügen
Fügen Sie der Folie eine SmartArt-Form hinzu:
```java
ISmartArt smart = slide.getShapes().addSmartArt(0, 0, 400, 400, SmartArtLayoutType.StackedList);
```
## Schritt 4: Zugriff auf den SmartArt-Knoten
Greifen Sie am gewünschten Index auf den SmartArt-Knoten zu:
```java
ISmartArtNode node = smart.getAllNodes().get_Item(0);
```
## Schritt 5: Untergeordneten Knoten an einer bestimmten Position hinzufügen
Fügen Sie an einer bestimmten Position im übergeordneten Knoten einen neuen untergeordneten Knoten hinzu:
```java
SmartArtNode chNode = (SmartArtNode) ((SmartArtNodeCollection) node.getChildNodes()).addNodeByPosition(2);
```
## Schritt 6: Text zum Knoten hinzufügen
Legen Sie den Text für den neu hinzugefügten Knoten fest:
```java
chNode.getTextFrame().setText("Sample Text Added");
```
## Schritt 7: Speichern Sie die Präsentation
Speichern Sie die geänderte Präsentation:
```java
pres.save(dataDir + "AddSmartArtNodeByPosition_out.pptx", SaveFormat.Pptx);
```

## Abschluss
In diesem Tutorial haben Sie gelernt, wie Sie mithilfe von Java und Aspose.Slides Knoten an bestimmten Positionen in SmartArt hinzufügen. Mit diesen Schritten können Sie SmartArt-Formen programmgesteuert bearbeiten, um dynamische Präsentationen zu erstellen.
## Häufig gestellte Fragen
### Kann ich mehrere Knoten gleichzeitig hinzufügen?
Ja, Sie können programmgesteuert mehrere Knoten hinzufügen, indem Sie über die gewünschten Positionen iterieren.
### Ist Aspose.Slides mit allen Versionen von PowerPoint kompatibel?
Aspose.Slides unterstützt verschiedene PowerPoint-Formate und gewährleistet die Kompatibilität mit den meisten Versionen.
### Kann ich das Erscheinungsbild von SmartArt-Knoten anpassen?
Ja, Sie können das Erscheinungsbild von Knoten anpassen, einschließlich Größe, Farbe und Stil.
### Bietet Aspose.Slides Unterstützung für andere Programmiersprachen?
Ja, Aspose.Slides bietet Bibliotheken für mehrere Programmiersprachen, darunter .NET und Python.
### Gibt es eine Testversion für Aspose.Slides?
Ja, Sie können eine kostenlose Testversion herunterladen von [Hier](https://releases.aspose.com/).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}