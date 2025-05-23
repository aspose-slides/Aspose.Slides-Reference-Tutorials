---
"description": "Erfahren Sie in diesem ausführlichen Schritt-für-Schritt-Tutorial, wie Sie mit Aspose.Slides für Java ein Portionsrechteck in PowerPoint erstellen. Perfekt für Java-Entwickler."
"linktitle": "Holen Sie sich Portion Rectangle in PowerPoint mit Java"
"second_title": "Aspose.Slides Java PowerPoint-Verarbeitungs-API"
"title": "Holen Sie sich Portion Rectangle in PowerPoint mit Java"
"url": "/de/java/java-powerpoint-advanced-paragraph-font-properties/get-portion-rectangle-powerpoint-java/"
"weight": 12
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Holen Sie sich Portion Rectangle in PowerPoint mit Java

## Einführung
Mit Aspose.Slides für Java ist das Erstellen dynamischer Präsentationen in Java ein Kinderspiel. In diesem Tutorial erfahren Sie alles über die Erstellung eines Portionsrechtecks in PowerPoint mit Aspose.Slides. Wir behandeln alles, von der Einrichtung Ihrer Umgebung bis hin zur schrittweisen Analyse des Codes. Also, los geht’s!
## Voraussetzungen
Bevor wir uns in den Code stürzen, stellen wir sicher, dass Sie alles haben, was Sie brauchen, um reibungslos mitmachen zu können:
1. Java Development Kit (JDK): Stellen Sie sicher, dass JDK 8 oder höher auf Ihrem Computer installiert ist.
2. Aspose.Slides für Java: Laden Sie die neueste Version herunter von [Hier](https://releases.aspose.com/slides/java/).
3. Integrierte Entwicklungsumgebung (IDE): Eclipse, IntelliJ IDEA oder eine andere Java-IDE Ihrer Wahl.
4. Grundkenntnisse in Java: Kenntnisse der Java-Programmierung sind unerlässlich.
## Pakete importieren
Zuerst importieren wir die notwendigen Pakete. Dazu gehören Aspose.Slides und einige andere, um unsere Aufgabe effizient zu erledigen.
```java
import com.aspose.slides.*;
import com.aspose.slides.examples.RunExamples;
import java.awt.*;
import java.awt.geom.Rectangle2D;
```
## Schritt 1: Einrichten der Präsentation
Der erste Schritt besteht darin, eine neue Präsentation zu erstellen. Diese dient als Grundlage für unsere Arbeit.
```java
Presentation pres = new Presentation();
```
## Schritt 2: Erstellen einer Tabelle
Fügen wir nun der ersten Folie unserer Präsentation eine Tabelle hinzu. Diese Tabelle enthält die Zellen, in die wir unseren Text einfügen.
```java
ITable tbl = pres.getSlides().get_Item(0).getShapes().addTable(50, 50, new double[]{50, 70}, new double[]{50, 50, 50});
```
## Schritt 3: Absätze zu Zellen hinzufügen
Als Nächstes erstellen wir Absätze und fügen sie einer bestimmten Zelle in der Tabelle hinzu. Dazu löschen wir den vorhandenen Text und fügen dann neue Absätze hinzu.
```java
// Absätze erstellen
IParagraph paragraph0 = new Paragraph();
paragraph0.getPortions().add(new Portion("Text "));
paragraph0.getPortions().add(new Portion("in0"));
paragraph0.getPortions().add(new Portion(" Cell"));
IParagraph paragraph1 = new Paragraph();
paragraph1.setText("On0");
IParagraph paragraph2 = new Paragraph();
paragraph2.getPortions().add(new Portion("Hi there "));
paragraph2.getPortions().add(new Portion("col0"));
// Fügen Sie Text in die Tabellenzelle ein
ICell cell = tbl.get_Item(1, 1);
cell.getTextFrame().getParagraphs().clear();
cell.getTextFrame().getParagraphs().add(paragraph0);
cell.getTextFrame().getParagraphs().add(paragraph1);
cell.getTextFrame().getParagraphs().add(paragraph2);
```
## Schritt 4: Hinzufügen eines Textrahmens zu einer AutoForm
Um unsere Präsentation dynamischer zu gestalten, fügen wir einer AutoForm einen Textrahmen hinzu und legen seine Ausrichtung fest.
```java
IAutoShape autoShape = pres.getSlides().get_Item(0).getShapes().addAutoShape(ShapeType.Rectangle, 400, 100, 60, 120);
autoShape.getTextFrame().setText("Text in shape");
autoShape.getTextFrame().getParagraphs().get_Item(0).getParagraphFormat().setAlignment(TextAlignment.Left);
```
## Schritt 5: Koordinaten berechnen
Wir benötigen die Koordinaten der oberen linken Ecke der Tabellenzelle. Dies hilft uns, die Formen präzise zu platzieren.
```java
double x = tbl.getX() + cell.getOffsetX();
double y = tbl.getY() + cell.getOffsetY();
```
## Schritt 6: Hinzufügen von Rahmen zu Absätzen und Abschnitten
Verwenden des `IParagraph.getRect()` Und `IPortion.getRect()` Mithilfe dieser Methoden können wir unseren Absätzen und Abschnitten Rahmen hinzufügen. Dazu durchlaufen wir die Absätze und Abschnitte, erstellen Formen um sie herum und passen ihr Erscheinungsbild an.
```java
for (IParagraph para : cell.getTextFrame().getParagraphs()) {
    if ("".equals(para.getText())) continue;
    Rectangle2D.Float rect = (Rectangle2D.Float) para.getRect().clone();
    IAutoShape shape = pres.getSlides().get_Item(0).getShapes().addAutoShape(
        ShapeType.Rectangle,
        (float) rect.getX() + (float) x,
        (float) rect.getY() + (float) y,
        (float) rect.getWidth(),
        (float) rect.getHeight()
    );
    shape.getFillFormat().setFillType(FillType.NoFill);
    shape.getLineFormat().getFillFormat().getSolidFillColor().setColor(Color.YELLOW);
    shape.getLineFormat().getFillFormat().setFillType(FillType.Solid);
    for (IPortion portion : para.getPortions()) {
        if (portion.getText().contains("0")) {
            rect = portion.getRect();
            shape = pres.getSlides().get_Item(0).getShapes().addAutoShape(
                ShapeType.Rectangle,
                (float) rect.getX() + (float) x,
                (float) rect.getY() + (float) y,
                (float) rect.getWidth(),
                (float) rect.getHeight()
            );
            shape.getFillFormat().setFillType(FillType.NoFill);
        }
    }
}
```
## Schritt 7: Rahmen zu AutoForm-Absätzen hinzufügen
Auf ähnliche Weise fügen wir den Absätzen in unserer AutoForm Rahmen hinzu, um die visuelle Attraktivität der Präsentation zu steigern.
```java
for (IParagraph para : autoShape.getTextFrame().getParagraphs()) {
    Rectangle2D.Float rect = (Rectangle2D.Float) para.getRect().clone();
    IAutoShape shape = pres.getSlides().get_Item(0).getShapes().addAutoShape(
        ShapeType.Rectangle,
        (float) rect.getX() + autoShape.getX(),
        (float) rect.getY() + autoShape.getY(),
        (float) rect.getWidth(),
        (float) rect.getHeight()
    );
    shape.getFillFormat().setFillType(FillType.NoFill);
    shape.getLineFormat().getFillFormat().getSolidFillColor().setColor(Color.YELLOW);
    shape.getLineFormat().getFillFormat().setFillType(FillType.Solid);
}
```
## Schritt 8: Speichern der Präsentation
Abschließend speichern wir unsere Präsentation unter einem angegebenen Pfad.
```java
String outPath = "path_to_output_directory";
pres.save(outPath + "GetRect_Out.pptx", SaveFormat.Pptx);
```
## Schritt 9: Aufräumen
Es empfiehlt sich, das Präsentationsobjekt zu entsorgen, um Ressourcen freizugeben.
```java
if (pres != null) pres.dispose();
```
## Abschluss
Herzlichen Glückwunsch! Sie haben erfolgreich gelernt, wie Sie mit Aspose.Slides für Java das Portionsrechteck in PowerPoint erstellen. Diese leistungsstarke Bibliothek eröffnet Ihnen unzählige Möglichkeiten für die programmgesteuerte Erstellung dynamischer und optisch ansprechender Präsentationen. Tauchen Sie tiefer in Aspose.Slides ein und entdecken Sie weitere Funktionen, um Ihre Präsentationen weiter zu verbessern.
## Häufig gestellte Fragen
### Was ist Aspose.Slides für Java?
Aspose.Slides für Java ist eine leistungsstarke Bibliothek, mit der Entwickler PowerPoint-Präsentationen programmgesteuert erstellen, ändern und bearbeiten können.
### Kann ich Aspose.Slides für Java in kommerziellen Projekten verwenden?
Ja, Aspose.Slides für Java kann in kommerziellen Projekten verwendet werden. Sie können eine Lizenz erwerben bei [Hier](https://purchase.aspose.com/buy).
### Gibt es eine kostenlose Testversion für Aspose.Slides für Java?
Ja, Sie können eine kostenlose Testversion herunterladen von [Hier](https://releases.aspose.com/).
### Wo finde ich die Dokumentation für Aspose.Slides für Java?
Die Dokumentation ist verfügbar [Hier](https://reference.aspose.com/slides/java/).
### Wie erhalte ich Support für Aspose.Slides für Java?
Sie können Unterstützung vom Aspose-Forum erhalten [Hier](https://forum.aspose.com/c/slides/11).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}