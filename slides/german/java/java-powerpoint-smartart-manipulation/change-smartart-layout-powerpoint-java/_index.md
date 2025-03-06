---
title: SmartArt-Layout in PowerPoint mit Java ändern
linktitle: SmartArt-Layout in PowerPoint mit Java ändern
second_title: Aspose.Slides Java PowerPoint-Verarbeitungs-API
description: Erfahren Sie, wie Sie mit Aspose.Slides für Java SmartArt-Layouts in PowerPoint-Präsentationen mit Java bearbeiten.
weight: 19
url: /de/java/java-powerpoint-smartart-manipulation/change-smartart-layout-powerpoint-java/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# SmartArt-Layout in PowerPoint mit Java ändern

## Einführung
In diesem Tutorial erfahren Sie, wie Sie SmartArt-Layouts in PowerPoint-Präsentationen mit Java bearbeiten können. SmartArt ist eine leistungsstarke Funktion in PowerPoint, mit der Benutzer optisch ansprechende Grafiken für verschiedene Zwecke erstellen können, beispielsweise zur Veranschaulichung von Prozessen, Hierarchien, Beziehungen und mehr.
## Voraussetzungen
Bevor wir mit dem Tutorial beginnen, stellen Sie sicher, dass Sie über Folgendes verfügen:
1. Java-Entwicklungsumgebung: Stellen Sie sicher, dass Sie Java Development Kit (JDK) auf Ihrem System installiert haben.
2.  Aspose.Slides-Bibliothek: Laden Sie die Aspose.Slides-Bibliothek für Java herunter und installieren Sie sie von[Hier](https://releases.aspose.com/slides/java/).
3. Grundlegende Kenntnisse in Java: Kenntnisse der Grundlagen der Programmiersprache Java sind hilfreich.
4. Integrierte Entwicklungsumgebung (IDE): Wählen Sie eine IDE Ihrer Wahl, beispielsweise Eclipse oder IntelliJ IDEA.

## Pakete importieren
Importieren Sie zunächst die erforderlichen Pakete in Ihr Java-Projekt:
```java
import com.aspose.slides.ISmartArt;
import com.aspose.slides.Presentation;
import com.aspose.slides.SaveFormat;
import com.aspose.slides.SmartArtLayoutType;
```
## Schritt 1: Richten Sie Ihre Java-Projektumgebung ein
Stellen Sie sicher, dass Ihr Java-Projekt in der von Ihnen gewählten IDE richtig eingerichtet ist. Erstellen Sie ein neues Java-Projekt und schließen Sie die Aspose.Slides-Bibliothek in die Abhängigkeiten Ihres Projekts ein.
## Schritt 2: Erstellen Sie eine neue Präsentation
Instanziieren Sie ein neues Präsentationsobjekt, um eine neue PowerPoint-Präsentation zu erstellen.
```java
Presentation presentation = new Presentation();
```
## Schritt 3: SmartArt-Grafik hinzufügen
Fügen Sie Ihrer Präsentation eine SmartArt-Grafik hinzu. Geben Sie die Position und Abmessungen der SmartArt-Grafik auf der Folie an.
```java
ISmartArt smart = presentation.getSlides().get_Item(0).getShapes().addSmartArt(10, 10, 400, 300, SmartArtLayoutType.BasicBlockList);
```
## Schritt 4: SmartArt-Layout ändern
Ändern Sie das Layout der SmartArt-Grafik in den gewünschten Layouttyp.
```java
smart.setLayout(SmartArtLayoutType.BasicProcess);
```
## Schritt 5: Präsentation speichern
Speichern Sie die geänderte Präsentation in einem angegebenen Verzeichnis auf Ihrem System.
```java
presentation.save(dataDir + "ChangeSmartArtLayout_out.pptx", SaveFormat.Pptx);
```

## Abschluss
Die Bearbeitung von SmartArt-Layouts in PowerPoint-Präsentationen mit Java ist mit Aspose.Slides für Java ein unkomplizierter Vorgang. Mit diesem Tutorial können Sie SmartArt-Grafiken ganz einfach an Ihre Präsentationsanforderungen anpassen.
## Häufig gestellte Fragen
### Kann ich das Erscheinungsbild von SmartArt-Grafiken mit Aspose.Slides für Java anpassen?
Ja, Sie können verschiedene Aspekte von SmartArt-Grafiken anpassen, beispielsweise Farben, Stile und Effekte.
### Ist Aspose.Slides mit verschiedenen Versionen von PowerPoint kompatibel?
Aspose.Slides unterstützt PowerPoint-Präsentationen, die in verschiedenen PowerPoint-Versionen erstellt wurden, und gewährleistet so die Kompatibilität zwischen verschiedenen Plattformen.
### Bietet Aspose.Slides Unterstützung für andere Programmiersprachen?
Ja, Aspose.Slides ist für mehrere Programmiersprachen verfügbar, darunter .NET, Python und JavaScript.
### Kann ich mit Aspose.Slides SmartArt-Grafiken von Grund auf neu erstellen?
Natürlich können Sie SmartArt-Grafiken programmgesteuert erstellen oder vorhandene Ihren Anforderungen entsprechend ändern.
### Gibt es ein Community-Forum, in dem ich Hilfe zu Aspose.Slides erhalten kann?
 Ja, Sie können das Aspose.Slides-Forum besuchen[Hier](https://forum.aspose.com/c/slides/11) um Fragen zu stellen und mit der Community zu interagieren.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
