---
"description": "Erfahren Sie, wie Sie mit Aspose.Slides für Java benutzerdefinierte Bildaufzählungszeichen zu PowerPoint-Folien hinzufügen. Folgen Sie dieser detaillierten Schritt-für-Schritt-Anleitung für eine nahtlose Integration."
"linktitle": "Verwalten von Absatzbildaufzählungszeichen in Java PowerPoint"
"second_title": "Aspose.Slides Java PowerPoint-Verarbeitungs-API"
"title": "Verwalten von Absatzbildaufzählungszeichen in Java PowerPoint"
"url": "/de/java/java-powerpoint-advanced-paragraph-font-properties/manage-paragraph-picture-bullets-java-powerpoint/"
"weight": 11
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Verwalten von Absatzbildaufzählungszeichen in Java PowerPoint

## Einführung
Das Erstellen ansprechender und visuell ansprechender Präsentationen ist in der modernen Geschäftswelt eine wichtige Fähigkeit. Java-Entwickler können Aspose.Slides nutzen, um ihre Präsentationen mit individuellen Bildpunkten in PowerPoint-Folien zu verbessern. Dieses Tutorial führt Sie Schritt für Schritt durch den Prozess und stellt sicher, dass Sie Ihren Präsentationen sicher Bildpunkte hinzufügen können.
## Voraussetzungen
Bevor Sie mit dem Lernprogramm beginnen, stellen Sie sicher, dass die folgenden Voraussetzungen erfüllt sind:
- Java Development Kit (JDK) installiert
- Integrierte Entwicklungsumgebung (IDE) wie Eclipse oder IntelliJ IDEA
- Aspose.Slides für die Java-Bibliothek
- Grundkenntnisse der Java-Programmierung
- Bilddatei für das Aufzählungsbild
Um die Aspose.Slides für Java-Bibliothek herunterzuladen, besuchen Sie die [Download-Seite](https://releases.aspose.com/slides/java/). Die Dokumentation finden Sie im [Dokumentation](https://reference.aspose.com/slides/java/).
## Pakete importieren
Stellen Sie zunächst sicher, dass Sie die erforderlichen Pakete für Ihr Projekt importiert haben. Fügen Sie am Anfang Ihrer Java-Datei die folgenden Importe hinzu:
```java
import com.aspose.slides.*;
import javax.imageio.ImageIO;
import java.awt.image.BufferedImage;
import java.io.File;
import java.io.IOException;
```
Lassen Sie uns den Prozess in überschaubare Schritte unterteilen.
## Schritt 1: Richten Sie Ihr Projektverzeichnis ein
Erstellen Sie ein neues Verzeichnis für Ihr Projekt. Dieses Verzeichnis enthält Ihre Java-Datei, die Aspose.Slides-Bibliothek und die Bilddatei für das Aufzählungszeichen.
```java
String dataDir = "Your Document Directory";
```
## Schritt 2: Initialisieren der Präsentation
Initialisieren Sie eine neue Instanz des `Presentation` Klasse. Dieses Objekt stellt Ihre PowerPoint-Präsentation dar.
```java
Presentation presentation = new Presentation();
```
## Schritt 3: Zugriff auf die erste Folie
Greifen Sie auf die erste Folie der Präsentation zu. Folien sind nullindiziert, die erste Folie befindet sich also am Index 0.
```java
ISlide slide = presentation.getSlides().get_Item(0);
```
## Schritt 4: Laden Sie das Aufzählungszeichenbild
Laden Sie das Bild, das Sie für die Aufzählungszeichen verwenden möchten. Dieses Bild sollte in Ihrem Projektverzeichnis abgelegt werden.
```java
BufferedImage image = ImageIO.read(new File(dataDir + "bullets.png"));
IPPImage ippxImage = presentation.getImages().addImage(image);
```
## Schritt 5: Fügen Sie der Folie eine AutoForm hinzu
Fügen Sie der Folie eine AutoForm hinzu. Die Form enthält den Text mit den benutzerdefinierten Aufzählungspunkten.
```java
IAutoShape autoShape = slide.getShapes().addAutoShape(ShapeType.Rectangle, 200, 200, 400, 200);
```
## Schritt 6: Zugriff auf den Textrahmen
Greifen Sie auf den Textrahmen der AutoForm zu, um dessen Absätze zu bearbeiten.
```java
ITextFrame textFrame = autoShape.getTextFrame();
```
## Schritt 7: Entfernen Sie den Standardabsatz
Entfernen Sie den Standardabsatz, der automatisch zum Textrahmen hinzugefügt wird.
```java
textFrame.getParagraphs().removeAt(0);
```
## Schritt 8: Erstellen Sie einen neuen Absatz
Erstellen Sie einen neuen Absatz und legen Sie dessen Text fest. Dieser Absatz enthält die benutzerdefinierten Bildaufzählungszeichen.
```java
Paragraph paragraph = new Paragraph();
paragraph.setText("Welcome to Aspose.Slides");
```
## Schritt 9: Aufzählungszeichenstil und Bild festlegen
Legen Sie den Aufzählungszeichenstil fest, um das zuvor geladene benutzerdefinierte Bild zu verwenden.
```java
paragraph.getParagraphFormat().getBullet().setType(BulletType.Picture);
paragraph.getParagraphFormat().getBullet().getPicture().setImage(ippxImage);
```
## Schritt 10: Aufzählungshöhe anpassen
Legen Sie die Höhe des Aufzählungszeichens fest, um sicherzustellen, dass es in der Präsentation gut aussieht.
```java
paragraph.getParagraphFormat().getBullet().setHeight(100);
```
## Schritt 11: Fügen Sie den Absatz zum Textrahmen hinzu
Fügen Sie den neu erstellten Absatz zum Textrahmen der AutoForm hinzu.
```java
textFrame.getParagraphs().add(paragraph);
```
## Schritt 12: Speichern Sie die Präsentation
Speichern Sie die Präsentation abschließend sowohl als PPTX- als auch als PPT-Datei.
```java
presentation.save(dataDir + "ParagraphPictureBulletsPPTX_out.pptx", SaveFormat.Pptx);
presentation.save(dataDir + "ParagraphPictureBulletsPPT_out.ppt", SaveFormat.Ppt);
```
## Abschluss
Und da haben Sie es! Mit diesen Schritten können Sie Ihren PowerPoint-Präsentationen mit Aspose.Slides für Java ganz einfach benutzerdefinierte Bildaufzählungszeichen hinzufügen. Diese leistungsstarke Bibliothek bietet zahlreiche Funktionen für die Erstellung professioneller und optisch ansprechender Präsentationen. Entdecken Sie auch die [Dokumentation](https://reference.aspose.com/slides/java/) für erweiterte Funktionen und Anpassungsoptionen.
## Häufig gestellte Fragen
### Was ist Aspose.Slides für Java?
Aspose.Slides für Java ist eine leistungsstarke Bibliothek, mit der Java-Entwickler PowerPoint-Präsentationen programmgesteuert erstellen, ändern und bearbeiten können.
### Kann ich für die Bildaufzählungszeichen ein beliebiges Bild verwenden?
Ja, Sie können für die Bildaufzählungszeichen jedes beliebige Bild verwenden, solange es von Ihrem Projektverzeichnis aus zugänglich ist.
### Benötige ich eine Lizenz, um Aspose.Slides für Java zu verwenden?
Aspose.Slides für Java erfordert eine Lizenz für die volle Funktionalität. Sie erhalten eine temporäre Lizenz von [Hier](https://purchase.aspose.com/temporary-license/) oder erwerben Sie eine Volllizenz [Hier](https://purchase.aspose.com/buy).
### Kann ich in einer AutoForm mehrere Absätze mit unterschiedlichen Aufzählungszeichenstilen hinzufügen?
Ja, Sie können einer einzelnen AutoForm mehrere Absätze mit unterschiedlichen Aufzählungszeichenstilen hinzufügen, indem Sie jeden Absatz einzeln erstellen und konfigurieren.
### Wo finde ich weitere Beispiele und Unterstützung?
Weitere Beispiele finden Sie im [Dokumentation](https://reference.aspose.com/slides/java/) und erhalten Sie Unterstützung von der Aspose-Community auf der [Foren](https://forum.aspose.com/c/slides/11).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}