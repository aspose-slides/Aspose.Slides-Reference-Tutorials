---
title: Erstellen Sie mehrstufige Aufzählungszeichen in Java PowerPoint
linktitle: Erstellen Sie mehrstufige Aufzählungszeichen in Java PowerPoint
second_title: Aspose.Slides Java PowerPoint-Verarbeitungs-API
description: Erfahren Sie, wie Sie mit Aspose.Slides für Java mehrstufige Aufzählungszeichen in PowerPoint erstellen. Schritt-für-Schritt-Anleitung mit Codebeispielen und FAQs.
weight: 14
url: /de/java/java-powerpoint-text-paragraph-management/create-multilevel-bullets-java-powerpoint/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

## Einführung
In diesem Tutorial erfahren Sie, wie Sie mit Aspose.Slides für Java mehrstufige Aufzählungszeichen in PowerPoint-Präsentationen erstellen. Das Hinzufügen von Aufzählungszeichen ist eine häufige Voraussetzung für die Erstellung organisierter und optisch ansprechender Inhalte in Präsentationen. Wir gehen den Prozess Schritt für Schritt durch und stellen sicher, dass Sie am Ende dieses Handbuchs in der Lage sind, Ihre Präsentationen mit strukturierten Aufzählungszeichen auf mehreren Ebenen zu verbessern.
## Voraussetzungen
Bevor wir beginnen, stellen Sie sicher, dass Sie Folgendes eingerichtet haben:
- Java-Entwicklungsumgebung: Stellen Sie sicher, dass das Java Development Kit (JDK) auf Ihrem System installiert ist.
-  Aspose.Slides für Java-Bibliothek: Laden Sie Aspose.Slides für Java herunter und installieren Sie es von[Hier](https://releases.aspose.com/slides/java/).
- IDE: Verwenden Sie Ihre bevorzugte Java Integrated Development Environment (IDE) wie IntelliJ IDEA, Eclipse oder andere.
- Grundkenntnisse: Kenntnisse in der Java-Programmierung und grundlegenden PowerPoint-Konzepten sind hilfreich.

## Pakete importieren
Bevor wir in das Tutorial eintauchen, importieren wir die erforderlichen Pakete aus Aspose.Slides für Java, die wir im gesamten Tutorial verwenden werden.
```java
import com.aspose.slides.*;
import java.awt.*;
import java.io.File;
```
## Schritt 1: Richten Sie Ihr Projekt ein
Erstellen Sie zunächst ein neues Java-Projekt in Ihrer IDE und fügen Sie Aspose.Slides für Java zu den Abhängigkeiten Ihres Projekts hinzu. Stellen Sie sicher, dass die erforderliche Aspose.Slides-JAR-Datei im Build-Pfad Ihres Projekts enthalten ist.
```java
// Der Pfad zum Dokumentverzeichnis.
String dataDir = "Your Document Directory";
```
## Schritt 2: Präsentationsobjekt initialisieren
Beginnen Sie mit der Erstellung einer neuen Präsentationsinstanz. Diese dient als Ihr PowerPoint-Dokument, in das Sie Folien und Inhalte einfügen.
```java
Presentation pres = new Presentation();
```
## Schritt 3: Zugriff auf die Folie
Rufen Sie als Nächstes die Folie auf, auf der Sie die mehrstufigen Aufzählungszeichen hinzufügen möchten. In diesem Beispiel arbeiten wir mit der ersten Folie (`Slide(0)`).
```java
ISlide slide = pres.getSlides().get_Item(0);
```
## Schritt 4: AutoForm mit Textrahmen hinzufügen
Fügen Sie der Folie eine AutoForm hinzu, in der Sie Ihren Text mit mehrstufigen Aufzählungszeichen platzieren.
```java
IAutoShape aShp = slide.getShapes().addAutoShape(ShapeType.Rectangle, 200, 200, 400, 200);
```
## Schritt 5: Auf Textrahmen zugreifen
Greifen Sie auf den Textrahmen innerhalb der AutoForm zu, wo Sie Absätze mit Aufzählungszeichen hinzufügen.
```java
ITextFrame text = aShp.addTextFrame("");
text.getParagraphs().clear(); //Standardabsätze löschen
```
## Schritt 6: Absätze mit Aufzählungszeichen hinzufügen
Fügen Sie Absätze mit Aufzählungszeichen unterschiedlicher Ebenen hinzu. So können Sie Aufzählungszeichen mit mehreren Ebenen hinzufügen:
```java
// Erste Ebene
IParagraph para1 = new Paragraph();
para1.setText("Content");
para1.getParagraphFormat().getBullet().setType(BulletType.Symbol);
para1.getParagraphFormat().getBullet().setChar((char) 8226);
para1.getParagraphFormat().getDefaultPortionFormat().getFillFormat().setFillType(FillType.Solid);
para1.getParagraphFormat().getDefaultPortionFormat().getFillFormat().getSolidFillColor().setColor(Color.BLACK);
para1.getParagraphFormat().setDepth((short) 0);
text.getParagraphs().add(para1);
// Zweites Level
IParagraph para2 = new Paragraph();
para2.setText("Second Level");
para2.getParagraphFormat().getBullet().setType(BulletType.Symbol);
para2.getParagraphFormat().getBullet().setChar('-');
para2.getParagraphFormat().getDefaultPortionFormat().getFillFormat().setFillType(FillType.Solid);
para2.getParagraphFormat().getDefaultPortionFormat().getFillFormat().getSolidFillColor().setColor(Color.BLACK);
para2.getParagraphFormat().setDepth((short) 1);
text.getParagraphs().add(para2);
// Drittes Level
IParagraph para3 = new Paragraph();
para3.setText("Third Level");
para3.getParagraphFormat().getBullet().setType(BulletType.Symbol);
para3.getParagraphFormat().getBullet().setChar((char) 8226);
para3.getParagraphFormat().getDefaultPortionFormat().getFillFormat().setFillType(FillType.Solid);
para3.getParagraphFormat().getDefaultPortionFormat().getFillFormat().getSolidFillColor().setColor(Color.BLACK);
para3.getParagraphFormat().setDepth((short) 2);
text.getParagraphs().add(para3);
// Vierte Ebene
IParagraph para4 = new Paragraph();
para4.setText("Fourth Level");
para4.getParagraphFormat().getBullet().setType(BulletType.Symbol);
para4.getParagraphFormat().getBullet().setChar('-');
para4.getParagraphFormat().getDefaultPortionFormat().getFillFormat().setFillType(FillType.Solid);
para4.getParagraphFormat().getDefaultPortionFormat().getFillFormat().getSolidFillColor().setColor(Color.BLACK);
para4.getParagraphFormat().setDepth((short) 3);
text.getParagraphs().add(para4);
```
## Schritt 7: Speichern Sie die Präsentation
Speichern Sie die Präsentation abschließend als PPTX-Datei im gewünschten Verzeichnis.
```java
pres.save(dataDir + "MultilevelBullet.pptx", SaveFormat.Pptx);
```

## Abschluss
In diesem Tutorial haben wir erläutert, wie Sie mit Aspose.Slides für Java mehrstufige Aufzählungszeichen in PowerPoint-Präsentationen erstellen. Indem Sie diese Schritte befolgen, können Sie Ihren Inhalt mit organisierten Aufzählungszeichen auf verschiedenen Ebenen effektiv strukturieren und so die Klarheit und visuelle Attraktivität Ihrer Präsentationen verbessern.
## Häufig gestellte Fragen
### Kann ich die Aufzählungssymbole weiter anpassen?
Ja, Sie können die Aufzählungssymbole anpassen, indem Sie die Unicode-Zeichen anpassen oder andere Formen verwenden.
### Unterstützt Aspose.Slides andere Aufzählungszeichentypen?
Ja, Aspose.Slides unterstützt eine Vielzahl von Aufzählungszeichentypen, darunter Symbole, Zahlen und benutzerdefinierte Bilder.
### Ist Aspose.Slides mit allen Versionen von PowerPoint kompatibel?
Aspose.Slides generiert Präsentationen, die mit Microsoft PowerPoint 2007 und höheren Versionen kompatibel sind.
### Kann ich die Folienerstellung mit Aspose.Slides automatisieren?
Ja, Aspose.Slides bietet APIs zur Automatisierung der Erstellung, Änderung und Bearbeitung von PowerPoint-Präsentationen.
### Wo erhalte ich Support für Aspose.Slides für Java?
 Sie erhalten Unterstützung von der Aspose.Slides-Community und Experten unter[Aspose.Slides Forum](https://forum.aspose.com/c/slides/11).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
