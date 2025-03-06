---
title: Ändern des SmartArt-Formstils in PowerPoint mit Java
linktitle: Ändern des SmartArt-Formstils in PowerPoint mit Java
second_title: Aspose.Slides Java PowerPoint-Verarbeitungs-API
description: Erfahren Sie, wie Sie mit Aspose.Slides für Java SmartArt-Stile in PowerPoint-Präsentationen mithilfe von Java ändern. Verbessern Sie Ihre Präsentationen.
weight: 23
url: /de/java/java-powerpoint-smartart-manipulation/change-smartart-shape-style-powerpoint-java/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

## Einführung
In der Welt der Java-Entwicklung ist das Erstellen aussagekräftiger Präsentationen oft eine Voraussetzung. Ob für Geschäftspräsentationen, Bildungszwecke oder einfach zum Teilen von Informationen, PowerPoint-Präsentationen sind ein gängiges Medium. Manchmal erfüllen die von PowerPoint bereitgestellten Standardstile und -formate jedoch nicht vollständig unsere Anforderungen. Hier kommt Aspose.Slides für Java ins Spiel.
Aspose.Slides für Java ist eine robuste Bibliothek, die es Java-Entwicklern ermöglicht, programmgesteuert mit PowerPoint-Präsentationen zu arbeiten. Sie bietet eine breite Palette an Funktionen, darunter die Möglichkeit, Formen, Stile, Animationen und vieles mehr zu bearbeiten. In diesem Tutorial konzentrieren wir uns auf eine bestimmte Aufgabe: das Ändern des SmartArt-Formstils in PowerPoint-Präsentationen mit Java.
## Voraussetzungen
Bevor Sie mit dem Lernprogramm beginnen, müssen einige Voraussetzungen erfüllt sein:
1. Java Development Kit (JDK): Stellen Sie sicher, dass JDK auf Ihrem System installiert ist. Sie können die neueste Version von der Oracle-Website herunterladen und installieren.
2. Aspose.Slides für Java-Bibliothek: Sie müssen die Aspose.Slides für Java-Bibliothek herunterladen und in Ihr Projekt einbinden. Den Download-Link finden Sie[Hier](https://releases.aspose.com/slides/java/).
3. Integrierte Entwicklungsumgebung (IDE): Wählen Sie Ihre bevorzugte IDE für die Java-Entwicklung. Beliebte Optionen sind IntelliJ IDEA, Eclipse oder NetBeans.

## Pakete importieren
Bevor wir mit dem Codieren beginnen, importieren wir die erforderlichen Pakete in unser Java-Projekt. Diese Pakete ermöglichen uns die nahtlose Arbeit mit den Funktionen von Aspose.Slides.
```java
import com.aspose.slides.*;
```
## Schritt 1: Laden Sie die Präsentation
Zuerst müssen wir die PowerPoint-Präsentation laden, die wir ändern möchten.
```java
String dataDir = "Your Document Directory";
Presentation presentation = new Presentation(dataDir + "AccessSmartArtShape.pptx");
```
## Schritt 2: Durch Formen navigieren
Als Nächstes gehen wir jede Form innerhalb der ersten Folie der Präsentation durch.
```java
for (IShape shape : presentation.getSlides().get_Item(0).getShapes())
```
## Schritt 3: SmartArt-Typ prüfen
Wir prüfen bei jeder Form, ob es sich um eine SmartArt-Form handelt.
```java
if (shape instanceof ISmartArt)
```
## Schritt 4: In SmartArt umwandeln
 Wenn die Form ein SmartArt ist, konvertieren wir sie in`ISmartArt` Schnittstelle.
```java
ISmartArt smart = (ISmartArt) shape;
```
## Schritt 5: Stil prüfen und ändern
Anschließend prüfen wir den aktuellen Stil des SmartArt und ändern ihn bei Bedarf.
```java
if (smart.getQuickStyle() == SmartArtQuickStyleType.SimpleFill)
{
    smart.setQuickStyle(SmartArtQuickStyleType.Cartoon);
}
```
## Schritt 6: Präsentation speichern
Abschließend speichern wir die geänderte Präsentation in einer neuen Datei.
```java
presentation.save(dataDir + "ChangeSmartArtStyle_out.pptx", SaveFormat.Pptx);
```

## Abschluss
In diesem Tutorial haben wir gelernt, wie man den SmartArt-Formstil in PowerPoint-Präsentationen mit Java und der Aspose.Slides-Bibliothek für Java ändert. Indem Sie der Schritt-für-Schritt-Anleitung folgen, können Sie das Erscheinungsbild von SmartArt-Formen ganz einfach anpassen, um es besser an Ihre Präsentationsanforderungen anzupassen.
## Häufig gestellte Fragen
### Kann ich Aspose.Slides für Java mit anderen Java-Bibliotheken verwenden?
Ja, Aspose.Slides für Java kann nahtlos in andere Java-Bibliotheken integriert werden, um die Funktionalität Ihrer Anwendungen zu verbessern.
### Gibt es eine kostenlose Testversion für Aspose.Slides für Java?
 Ja, Sie können eine kostenlose Testversion von Aspose.Slides für Java nutzen von[Hier](https://releases.aspose.com/).
### Wie kann ich Support für Aspose.Slides für Java erhalten?
 Sie können Unterstützung für Aspose.Slides für Java erhalten, indem Sie die[Forum](https://forum.aspose.com/c/slides/11).
### Kann ich eine temporäre Lizenz für Aspose.Slides für Java erwerben?
 Ja, Sie können eine temporäre Lizenz für Aspose.Slides für Java erwerben bei[Hier](https://purchase.aspose.com/temporary-license/).
### Wo finde ich eine ausführliche Dokumentation für Aspose.Slides für Java?
 Eine ausführliche Dokumentation zu Aspose.Slides für Java finden Sie[Hier](https://reference.aspose.com/slides/java/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
