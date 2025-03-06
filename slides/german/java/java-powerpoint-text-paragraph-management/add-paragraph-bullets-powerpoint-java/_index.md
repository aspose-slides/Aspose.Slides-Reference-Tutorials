---
title: Hinzufügen von Absatzaufzählungszeichen in PowerPoint mit Java
linktitle: Hinzufügen von Absatzaufzählungszeichen in PowerPoint mit Java
second_title: Aspose.Slides Java PowerPoint-Verarbeitungs-API
description: Erfahren Sie, wie Sie mit Aspose.Slides für Java Absatzaufzählungszeichen in PowerPoint-Folien einfügen. Dieses Tutorial führt Sie Schritt für Schritt mit Codebeispielen durch.
weight: 15
url: /de/java/java-powerpoint-text-paragraph-management/add-paragraph-bullets-powerpoint-java/
---

{< blocks/products/pf/main-wrap-class >}
{< blocks/products/pf/main-container >}
{< blocks/products/pf/tutorial-page-section >}

## Einführung
Das Hinzufügen von Aufzählungszeichen verbessert die Lesbarkeit und Struktur von PowerPoint-Präsentationen. Aspose.Slides für Java bietet robuste Tools zur programmgesteuerten Bearbeitung von Präsentationen, einschließlich der Möglichkeit, Text mit verschiedenen Aufzählungszeichenstilen zu formatieren. In diesem Tutorial erfahren Sie, wie Sie mithilfe von Java-Code und Aspose.Slides Aufzählungszeichen in PowerPoint-Folien integrieren.
## Voraussetzungen
Bevor Sie beginnen, stellen Sie sicher, dass Sie über Folgendes verfügen:
- Grundkenntnisse der Java-Programmierung.
- JDK (Java Development Kit) auf Ihrem System installiert.
-  Aspose.Slides für Java-Bibliothek. Sie können es herunterladen von[Hier](https://releases.aspose.com/slides/java/).

## Pakete importieren
Importieren Sie zunächst die erforderlichen Aspose.Slides-Pakete in Ihr Java-Projekt:
```java
import com.aspose.slides.*;
import java.awt.*;
import java.io.File;
```
## Schritt 1: Richten Sie Ihr Projekt ein
Erstellen Sie zunächst ein neues Java-Projekt und fügen Sie die Bibliothek Aspose.Slides für Java zum Build-Pfad Ihres Projekts hinzu.
## Schritt 2: Initialisieren einer Präsentation
Initialisieren Sie ein Präsentationsobjekt (`Presentation`), um mit der Arbeit mit Folien zu beginnen.
```java
// Der Pfad zum Dokumentverzeichnis.
String dataDir = "Your Document Directory";
// Erstellen einer Präsentationsinstanz
Presentation pres = new Presentation();
```
## Schritt 3: Zugriff auf die Folie und den Textrahmen
Greifen Sie auf die Folie zu (`ISlide`und dessen Textrahmen (`ITextFrame`), wo Sie Aufzählungszeichen hinzufügen möchten.
```java
// Zugriff auf die erste Folie
ISlide slide = pres.getSlides().get_Item(0);
// Hinzufügen und Zugreifen auf Autoshape
IAutoShape aShp = slide.getShapes().addAutoShape(ShapeType.Rectangle, 200, 200, 400, 200);
// Zugriff auf den Textrahmen der erstellten AutoForm
ITextFrame txtFrm = aShp.getTextFrame();
```
## Schritt 4: Absätze mit Aufzählungszeichen erstellen und formatieren
Absätze erstellen (`Paragraph`) und legen Sie Aufzählungszeichenstile, Einrückungen und Texte fest.
```java
// Erstellen eines Absatzes
Paragraph para = new Paragraph();
para.getParagraphFormat().getBullet().setType(BulletType.Symbol);
para.getParagraphFormat().getBullet().setChar((char) 8226);
para.setText("Welcome to Aspose.Slides");
para.getParagraphFormat().setIndent(25);
txtFrm.getParagraphs().add(para);
// Einen weiteren Absatz erstellen
Paragraph para2 = new Paragraph();
para2.getParagraphFormat().getBullet().setType(BulletType.Numbered);
para2.getParagraphFormat().getBullet().setNumberedBulletStyle(NumberedBulletStyle.BulletCircleNumWDBlackPlain);
para2.setText("This is numbered bullet");
para2.getParagraphFormat().setIndent(25);
txtFrm.getParagraphs().add(para2);
```
## Schritt 5: Speichern Sie die Präsentation
Speichern Sie die geänderte Präsentation in einer PowerPoint-Datei (`PPTX`).
```java
// Schreiben der Präsentation als PPTX-Datei
pres.save(dataDir + "Bullet_out.pptx", SaveFormat.Pptx);
```
## Schritt 6: Ressourcen bereinigen
Entsorgen Sie das Präsentationsobjekt, um Ressourcen freizugeben.
```java
// Entsorgen Sie das Präsentationsobjekt
if (pres != null) {
    pres.dispose();
}
```

## Abschluss
Das Hinzufügen von Absatzaufzählungszeichen in PowerPoint mit Aspose.Slides für Java ist mit den bereitgestellten Codebeispielen ganz einfach. Passen Sie Aufzählungszeichenstile und Formatierungen nahtlos an Ihre Präsentationsanforderungen an.

## FAQs
### Kann ich die Farben der Aufzählungszeichen anpassen?
Ja, Sie können mit der Aspose.Slides-API benutzerdefinierte Farben für Aufzählungszeichen festlegen.
### Wie füge ich verschachtelte Aufzählungszeichen hinzu?
Beim Verschachteln von Aufzählungszeichen werden Absätze innerhalb von Absätzen hinzugefügt und die Einrückung entsprechend angepasst.
### Kann ich für unterschiedliche Folien unterschiedliche Aufzählungszeichenstile erstellen?
Ja, Sie können programmgesteuert unterschiedlichen Folien einzigartige Aufzählungszeichenstile zuweisen.
### Ist Aspose.Slides mit Java 11 kompatibel?
Ja, Aspose.Slides unterstützt Java 11 und höhere Versionen.
### Wo finde ich weitere Beispiele und Dokumentation?
 Besuchen[Aspose.Slides für Java-Dokumentation](https://reference.aspose.com/slides/java/) für umfassende Anleitungen und Beispiele.
{< /blocks/products/pf/tutorial-page-section >}

{< /blocks/products/pf/main-container >}
{< /blocks/products/pf/main-wrap-class >}

{< blocks/products/products-backtop-button >}
