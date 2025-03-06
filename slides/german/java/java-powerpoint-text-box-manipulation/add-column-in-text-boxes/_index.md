---
title: Spalten in Textfeldern hinzufügen mit Aspose.Slides für Java
linktitle: Spalten in Textfeldern hinzufügen mit Aspose.Slides für Java
second_title: Aspose.Slides Java PowerPoint-Verarbeitungs-API
description: Erfahren Sie, wie Sie mit Aspose.Slides für Java Spalten zu Textfeldern in PowerPoint hinzufügen. Verbessern Sie Ihre Präsentationen mit dieser Schritt-für-Schritt-Anleitung.
weight: 10
url: /de/java/java-powerpoint-text-box-manipulation/add-column-in-text-boxes/
---

{< blocks/products/pf/main-wrap-class >}
{< blocks/products/pf/main-container >}
{< blocks/products/pf/tutorial-page-section >}

## Einführung
In diesem Tutorial erfahren Sie, wie Sie Textfelder durch Hinzufügen von Spalten mithilfe von Aspose.Slides für Java verbessern können. Aspose.Slides ist eine leistungsstarke Java-Bibliothek, mit der Entwickler PowerPoint-Präsentationen programmgesteuert erstellen, bearbeiten und konvertieren können, ohne Microsoft Office zu benötigen. Das Hinzufügen von Spalten zu Textfeldern kann die Lesbarkeit und Organisation von Inhalten in Folien erheblich verbessern und Ihre Präsentationen ansprechender und professioneller gestalten.
## Voraussetzungen
Bevor wir beginnen, stellen Sie sicher, dass Sie die folgenden Voraussetzungen erfüllen:
- Grundkenntnisse der Java-Programmierung.
- JDK (Java Development Kit) auf Ihrem Computer installiert.
-  Aspose.Slides für Java-Bibliothek. Sie können es herunterladen von[Hier](https://releases.aspose.com/slides/java/).

## Pakete importieren
Um zu beginnen, müssen Sie die erforderlichen Aspose.Slides-Klassen in Ihre Java-Datei importieren. So können Sie das tun:
```java
import com.aspose.slides.*;
```
## Schritt 1: Präsentation und Folie initialisieren
Erstellen Sie zunächst eine neue PowerPoint-Präsentation und initialisieren Sie die erste Folie.
```java
// Der Pfad zum Dokumentverzeichnis.
String dataDir = "Your Document Directory";
Presentation presentation = new Presentation();
try {
    // Holen Sie sich die erste Folie der Präsentation
    ISlide slide = presentation.getSlides().get_Item(0);
```
## Schritt 2: AutoForm (Rechteck) hinzufügen
Fügen Sie als Nächstes der Folie eine AutoForm vom Typ „Rechteck“ hinzu.
```java
    // Fügen Sie eine AutoForm vom Typ „Rechteck“ hinzu
    IAutoShape aShape = slide.getShapes().addAutoShape(ShapeType.Rectangle, 100, 100, 300, 300);
```
## Schritt 3: TextFrame zum Rechteck hinzufügen
Fügen Sie nun der rechteckigen Autoform einen Textrahmen hinzu und legen Sie seinen Anfangstext fest.
```java
    // TextFrame zum Rechteck hinzufügen
    aShape.addTextFrame("All these columns are limited to be within a single text container -- " +
            "you can add or delete text and the new or remaining text automatically adjusts " +
            "itself to flow within the container. You cannot have text flow from one container " +
            "to other though -- we told you PowerPoint's column options for text are limited!");
```
## Schritt 4: Anzahl der Spalten festlegen
Geben Sie die Anzahl der Spalten innerhalb des TextFrames an.
```java
    // Textformat des TextFrame abrufen
    ITextFrameFormat format = aShape.getTextFrame().getTextFrameFormat();
    // Anzahl der Spalten im TextFrame festlegen
    format.setColumnCount(3);
```
## Schritt 5: Spaltenabstand anpassen
Legen Sie den Abstand zwischen den Spalten im TextFrame fest.
```java
    // Abstand zwischen Spalten festlegen
    format.setColumnSpacing(10);
```
## Schritt 6: Speichern Sie die Präsentation
Speichern Sie die geänderte Präsentation abschließend als PowerPoint-Datei.
```java
    // Erstellte Präsentation speichern
    presentation.save(dataDir + "ColumnCount.pptx", SaveFormat.Pptx);
} finally {
    if (presentation != null) presentation.dispose();
}
```

## Abschluss
Wenn Sie diese Schritte befolgen, können Sie mit Aspose.Slides für Java ganz einfach Spalten zu Textfeldern in PowerPoint-Präsentationen hinzufügen. Mit dieser Funktion können Sie die Struktur und Lesbarkeit Ihrer Folien verbessern und sie optisch ansprechender und professioneller gestalten.
## Häufig gestellte Fragen
### Kann ich einem Textfeld mehr als drei Spalten hinzufügen?
Ja, Sie können mit Aspose.Slides programmgesteuert eine beliebige Anzahl von Spalten angeben.
### Ist Aspose.Slides mit Java 11 kompatibel?
Ja, Aspose.Slides unterstützt Java 11 und höhere Versionen.
### Wie kann ich eine temporäre Lizenz für Aspose.Slides erhalten?
 Sie können eine temporäre Lizenz erhalten[Hier](https://purchase.aspose.com/temporary-license/).
### Ist für Aspose.Slides eine Installation von Microsoft Office erforderlich?
Nein, für Aspose.Slides muss Microsoft Office nicht auf dem Computer installiert sein.
### Wo finde ich weitere Dokumentation zu Aspose.Slides für Java?
 Detaillierte Dokumentation ist verfügbar[Hier](https://reference.aspose.com/slides/java/).
{< /blocks/products/pf/tutorial-page-section >}

{< /blocks/products/pf/main-container >}
{< /blocks/products/pf/main-wrap-class >}

{< blocks/products/products-backtop-button >}
