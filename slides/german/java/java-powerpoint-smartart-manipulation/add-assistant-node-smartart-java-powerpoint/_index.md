---
title: Assistenzknoten zu SmartArt in Java PowerPoint hinzufügen
linktitle: Assistenzknoten zu SmartArt in Java PowerPoint hinzufügen
second_title: Aspose.Slides Java PowerPoint-Verarbeitungs-API
description: Erfahren Sie, wie Sie mit Aspose.Slides einen Assistentenknoten zu SmartArt in Java PowerPoint-Präsentationen hinzufügen. Verbessern Sie Ihre PowerPoint-Bearbeitungsfähigkeiten.
weight: 17
url: /de/java/java-powerpoint-smartart-manipulation/add-assistant-node-smartart-java-powerpoint/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

## Einführung
In diesem Tutorial führen wir Sie durch den Prozess des Hinzufügens eines Assistentenknotens zu SmartArt in Java PowerPoint-Präsentationen mithilfe von Aspose.Slides.
## Voraussetzungen
Bevor wir beginnen, stellen Sie sicher, dass die folgenden Voraussetzungen erfüllt sind:
1.  Java Development Kit (JDK): Stellen Sie sicher, dass Java auf Ihrem System installiert ist. Sie können das neueste JDK von herunterladen und installieren.[Hier](https://www.oracle.com/java/technologies/javase-jdk15-downloads.html).
2.  Aspose.Slides für Java: Laden Sie die Aspose.Slides für Java-Bibliothek herunter und installieren Sie sie von[dieser Link](https://releases.aspose.com/slides/java/).

## Pakete importieren
Importieren Sie zunächst die erforderlichen Pakete in Ihren Java-Code:
```java
import com.aspose.slides.*;
```
## Schritt 1: Präsentation vorbereiten
Beginnen Sie mit der Erstellung einer Präsentationsinstanz unter Verwendung des Pfads zu Ihrer PowerPoint-Datei:
```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "AssistantNode.pptx");
```
## Schritt 2: Durch Formen navigieren
Gehen Sie alle Formen auf der ersten Folie der Präsentation durch:
```java
for (IShape shape : pres.getSlides().get_Item(0).getShapes())
```
## Schritt 3: Nach SmartArt-Formen suchen
Überprüfen Sie, ob die Form vom Typ SmartArt ist:
```java
if (shape instanceof ISmartArt)
```
## Schritt 4: Durch SmartArt-Knoten navigieren
Durchlaufen Sie alle Knoten der SmartArt-Form:
```java
for (ISmartArtNode node : smart.getAllNodes())
```
## Schritt 5: Suchen Sie nach einem Assistenzknoten
Überprüfen Sie, ob der Knoten ein Assistentknoten ist:
```java
if (node.isAssistant())
```
## Schritt 6: Stellen Sie den Assistentenknoten auf Normal
Wenn der Knoten ein Assistenzknoten ist, legen Sie ihn als normalen Knoten fest:
```java
node.setAssistant(false);
```
## Schritt 7: Präsentation speichern
Speichern Sie die geänderte Präsentation:
```java
pres.save(dataDir + "ChangeAssistantNode_out.pptx", SaveFormat.Pptx);
```

## Abschluss
Herzlichen Glückwunsch! Sie haben mit Aspose.Slides erfolgreich einen Assistentenknoten zu SmartArt in Ihrer Java PowerPoint-Präsentation hinzugefügt.

## Häufig gestellte Fragen
### Kann ich einem SmartArt in der Präsentation mehrere Assistentknoten hinzufügen?
Ja, Sie können mehrere Assistentknoten hinzufügen, indem Sie den Vorgang für jeden Knoten wiederholen.
### Funktioniert dieses Tutorial sowohl für PowerPoint als auch für PowerPoint-Vorlagen?
Ja, Sie können dieses Tutorial sowohl auf PowerPoint-Präsentationen als auch auf Vorlagen anwenden.
### Ist Aspose.Slides mit allen Versionen von PowerPoint kompatibel?
Aspose.Slides unterstützt PowerPoint-Versionen von 97-2003 bis zur neuesten Version.
### Kann ich das Erscheinungsbild des Assistenzknotens anpassen?
Ja, Sie können das Erscheinungsbild mithilfe verschiedener von Aspose.Slides bereitgestellter Eigenschaften und Methoden anpassen.
### Gibt es eine Begrenzung für die Anzahl der Knoten in einem SmartArt?
SmartArt in PowerPoint unterstützt eine große Anzahl von Knoten, es wird jedoch empfohlen, diese zur besseren Lesbarkeit überschaubar zu halten.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
