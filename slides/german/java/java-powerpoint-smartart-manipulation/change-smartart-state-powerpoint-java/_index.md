---
title: SmartArt-Status in PowerPoint mit Java ändern
linktitle: SmartArt-Status in PowerPoint mit Java ändern
second_title: Aspose.Slides Java PowerPoint-Verarbeitungs-API
description: Erfahren Sie, wie Sie SmartArt-Zustände in PowerPoint-Präsentationen mit Java und Aspose.Slides ändern. Verbessern Sie Ihre Fähigkeiten zur Präsentationsautomatisierung.
weight: 21
url: /de/java/java-powerpoint-smartart-manipulation/change-smartart-state-powerpoint-java/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

## Einführung
In diesem Tutorial erfahren Sie, wie Sie SmartArt-Objekte in PowerPoint-Präsentationen mithilfe von Java und der Aspose.Slides-Bibliothek bearbeiten. SmartArt ist eine leistungsstarke Funktion in PowerPoint, mit der Sie optisch ansprechende Diagramme und Grafiken erstellen können.
## Voraussetzungen
Bevor Sie beginnen, stellen Sie sicher, dass Sie über Folgendes verfügen:
1.  Java Development Kit (JDK): Stellen Sie sicher, dass Java auf Ihrem System installiert ist. Sie können es von der[Oracle-Website](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html).
2.  Aspose.Slides für Java: Laden Sie die Aspose.Slides für Java-Bibliothek herunter und installieren Sie sie von der[Webseite](https://releases.aspose.com/slides/java/).

## Pakete importieren
Um mit Aspose.Slides in Ihrem Java-Projekt zu arbeiten, importieren Sie die erforderlichen Pakete:
```java
import com.aspose.slides.ISmartArt;
import com.aspose.slides.Presentation;
import com.aspose.slides.SaveFormat;
import com.aspose.slides.SmartArtLayoutType;
```
Lassen Sie uns nun den bereitgestellten Beispielcode in mehrere Schritte aufteilen:
## Schritt 1: Präsentationsobjekt initialisieren
```java
Presentation presentation = new Presentation();
```
 Hier erstellen wir ein neues`Presentation` Objekt, das eine PowerPoint-Präsentation darstellt.
## Schritt 2: SmartArt-Objekt hinzufügen
```java
ISmartArt smart = presentation.getSlides().get_Item(0).getShapes().addSmartArt(10, 10, 400, 300, SmartArtLayoutType.BasicProcess);
```
 In diesem Schritt wird der ersten Folie der Präsentation ein SmartArt-Objekt hinzugefügt. Wir legen die Position und Abmessungen des SmartArt-Objekts sowie den Layouttyp fest (in diesem Fall`BasicProcess`).
## Schritt 3: SmartArt-Status festlegen
```java
smart.setReversed(true);
```
Hier legen wir den Status des SmartArt-Objekts fest. In diesem Beispiel kehren wir die Richtung des SmartArt um.
## Schritt 4: SmartArt-Status prüfen
```java
boolean flag = smart.isReversed();
```
 Wir können auch den aktuellen Status des SmartArt-Objekts überprüfen. Diese Zeile ruft ab, ob das SmartArt umgekehrt ist oder nicht und speichert es in der`flag` Variable.
## Schritt 5: Präsentation speichern
```java
presentation.save(dataDir + "ChangeSmartArtState_out.pptx", SaveFormat.Pptx);
```
Abschließend speichern wir die geänderte Präsentation an einem bestimmten Ort auf der Festplatte.

## Abschluss
In diesem Tutorial haben wir gelernt, wie man den Status von SmartArt-Objekten in PowerPoint-Präsentationen mit Java und der Aspose.Slides-Bibliothek ändert. Mit diesem Wissen können Sie dynamische und ansprechende Präsentationen programmgesteuert erstellen.
## Häufig gestellte Fragen
### Kann ich mit Aspose.Slides für Java andere Eigenschaften von SmartArt ändern?
Ja, Sie können mit Aspose.Slides verschiedene Aspekte von SmartArt-Objekten wie Farben, Stile und Layouts ändern.
### Ist Aspose.Slides mit verschiedenen Versionen von PowerPoint kompatibel?
Ja, Aspose.Slides unterstützt PowerPoint-Präsentationen in verschiedenen Versionen und gewährleistet so Kompatibilität und nahtlose Integration.
### Kann ich mit Aspose.Slides benutzerdefinierte SmartArt-Layouts erstellen?
Auf jeden Fall! Aspose.Slides bietet APIs zum Erstellen benutzerdefinierter SmartArt-Layouts, die auf Ihre spezifischen Anforderungen zugeschnitten sind.
### Bietet Aspose.Slides Unterstützung für andere Dateiformate außer PowerPoint?
Ja, Aspose.Slides unterstützt eine Vielzahl von Dateiformaten, darunter PPTX, PPT, PDF und mehr.
### Gibt es ein Community-Forum, in dem ich Hilfe zu Fragen zu Aspose.Slides bekomme?
 Ja, Sie können das Aspose.Slides-Forum unter besuchen.[Hier](https://forum.aspose.com/c/slides/11) für Hilfestellung und Diskussionen.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
