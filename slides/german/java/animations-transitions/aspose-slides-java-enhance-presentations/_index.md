---
date: '2026-06-23'
description: Erfahren Sie, wie Sie in PowerPoint eine Tabelle erstellen, Text zu Tabellenzellen
  hinzufügen, Rahmen um den Text zeichnen und die Präsentation als pptx mit Aspose.Slides
  für Java speichern.
keywords:
- create table in powerpoint
- add text to table
- draw frame around text
- highlight table cells
- save presentation as pptx
schemas:
- author: Aspose
  dateModified: '2026-06-23'
  description: Learn how to create table in PowerPoint, add text to table cells, draw
    frames around text, and save presentation as pptx using Aspose.Slides for Java.
  headline: How to create table in PowerPoint and draw frames with Aspose.Slides for
    Java
  type: TechArticle
- description: Learn how to create table in PowerPoint, add text to table cells, draw
    frames around text, and save presentation as pptx using Aspose.Slides for Java.
  name: How to create table in PowerPoint and draw frames with Aspose.Slides for Java
  steps:
  - name: '**Install the Library**: Use Maven or Gradle to manage dependencies, or
      download it directly from [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/).'
    text: '**Install the Library**: Use Maven or Gradle to manage dependencies, or
      download it directly from [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/).'
  - name: '**License Acquisition**:'
    text: '**License Acquisition**:'
  - name: '**Basic Initialization**:'
    text: '**Basic Initialization**:'
  type: HowTo
- questions:
  - answer: The library supports JDK 8 onward, but the `jdk16` classifier gives the
      best performance on newer runtimes.
    question: Can I use these APIs with older JDK versions?
  - answer: Modify the line format fill color, e.g., `shape.getLineFormat().getFillFormat().setSolidFillColor(Color.BLUE);`.
    question: How do I change the frame color?
  - answer: Yes—use `pres.getSlides().get_Item(0).getImage(Export.ImageFormat.Png)`
      and then save the byte array.
    question: Is it possible to export the final slide as an image?
  - answer: Iterate through `cell.getTextFrame().getParagraphs()`, locate the portion
      containing “Total”, and draw a rectangle around that portion’s bounding box.
    question: What if I need to highlight only the word “Total” inside a cell?
  - answer: The API streams data and releases resources when `pres.dispose()` is called,
      which helps with memory management for large files.
    question: Does Aspose.Slides handle large presentations efficiently?
  type: FAQPage
title: Wie man in PowerPoint eine Tabelle erstellt und Rahmen mit Aspose.Slides für
  Java zeichnet
url: /de/java/animations-transitions/aspose-slides-java-enhance-presentations/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Wie man eine Tabelle in PowerPoint erstellt und Rahmen mit Aspose.Slides für Java zeichnet

## Einführung

Das programmatische **create table in PowerPoint** kann Ihnen Stunden manueller Formatierung ersparen, insbesondere wenn Sie wichtige Zahlen hervorheben oder erläuternde Anmerkungen hinzufügen müssen. In diesem Tutorial erfahren Sie, wie Sie Text zu Tabellenzellen hinzufügen, Rahmen um bestimmte Absätze zeichnen, eine präzise Textausrichtung festlegen und schließlich **save presentation as pptx** – alles mit der leistungsstarken Aspose.Slides für Java API. Am Ende haben Sie eine Folie, die professionell aussieht, leicht zu lesen ist und sofort die Aufmerksamkeit des Publikums auf die wichtigsten Daten lenkt.

## Schnelle Antworten
- **Was bedeutet „add text to table“?** Es bedeutet, den Textinhalt einzelner Tabellenzellen programmgesteuert einzufügen oder zu aktualisieren.  
- **Welche Methode speichert die Datei?** `pres.save("output.pptx", SaveFormat.Pptx)` – dieser **save presentation as pptx**-Schritt finalisiert Ihre Änderungen.  
- **Wie kann ich Text innerhalb einer Form ausrichten?** Verwenden Sie `TextAlignment.Left` (oder Center/Right) über `autoShape.getTextFrame().getParagraphs().get_Item(0).getParagraphFormat().setAlignment(...)`.  
- **Kann ich ein Rechteck um einen Absatz zeichnen?** Ja – iterieren Sie über die Absätze, erhalten Sie deren Begrenzungsrechteck und fügen Sie ein `IAutoShape` ohne Füllung und mit einer schwarzen Linie hinzu.  
- **Brauche ich eine Lizenz?** Eine temporäre Lizenz funktioniert für die Evaluierung; für den Produktionseinsatz ist eine Voll‑Lizenz erforderlich.  

## Warum Rahmen um Text zeichnen?

Das Zeichnen eines Rahmens (oder Rechtecks) um einen Absatz oder einen bestimmten Teil – beispielsweise jeden Text, der das Zeichen **'0'** enthält – lenkt sofort die Aufmerksamkeit des Publikums auf diesen Inhalt. Es bietet einen klaren visuellen Hinweis, ohne den zugrunde liegenden Text zu verändern, und ist ideal, um Schlüsselzahlen, Warnungen hervorzuheben oder Abschnitte innerhalb einer Folie zu trennen.

## Voraussetzungen

Bevor Sie in den Code eintauchen, stellen Sie sicher, dass Sie Folgendes haben:

### Erforderliche Bibliotheken
Sie benötigen Aspose.Slides für Java. So binden Sie es mit Maven oder Gradle ein:

**Maven:**  
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```  

**Gradle:**  
```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```  

### Umgebung einrichten
Stellen Sie sicher, dass ein Java Development Kit (JDK) installiert ist, vorzugsweise JDK 16 oder höher, da dieses Beispiel den `jdk16`‑Classifier verwendet.

### Wissensvoraussetzungen
- Grundlegendes Verständnis der Java‑Programmierung.  
- Vertrautheit mit Präsentationssoftware wie PowerPoint.  
- Erfahrung mit einer integrierten Entwicklungsumgebung (IDE) wie IntelliJ IDEA oder Eclipse.

## Einrichtung von Aspose.Slides für Java

`Presentation` ist die Kernklasse von Aspose.Slides, die eine PowerPoint‑Datei im Speicher repräsentiert und Zugriff auf Folien, Formen und Tabellen bietet. Um Aspose.Slides zu verwenden, folgen Sie diesen Schritten:

1. **Bibliothek installieren**: Verwenden Sie Maven oder Gradle, um Abhängigkeiten zu verwalten, oder laden Sie sie direkt von [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/) herunter.

2. **Lizenzbeschaffung**:
   - Beginnen Sie mit einer kostenlosen Testversion, indem Sie eine temporäre Lizenz von [Temporary License](https://purchase.aspose.com/temporary-license/) herunterladen.
   - Für vollen Zugriff sollten Sie den Kauf einer Lizenz unter [Purchase Aspose.Slides](https://purchase.aspose.com/buy) in Betracht ziehen.

3. **Grundlegende Initialisierung**:  
   Initialisieren Sie Ihre Präsentationsumgebung mit dem folgenden Code‑Snippet:  
   ```java
import com.aspose.slides.*;

Presentation pres = new Presentation();
try {
    // Your code here
} finally {
    if (pres != null) pres.dispose();
}
```  

## Wie fügt man Text zu einer Tabelle in Aspose.Slides für Java hinzu?

Laden Sie eine neue `Presentation`, erstellen Sie eine Tabelle an den gewünschten Koordinaten, füllen Sie die Zellen mit `TextFrame`‑Objekten und rufen Sie schließlich `pres.save("output.pptx", SaveFormat.Pptx)` auf. Diese Reihenfolge erstellt ein **create table in PowerPoint**, fügt jedem Feld benutzerdefinierten Text hinzu und schreibt das Ergebnis in einer einzigen, effizienten Arbeitsablauf in eine PPTX‑Datei.

### Feature 1: Tabelle erstellen und Text zu Zellen hinzufügen

#### Übersicht
Dieses Feature zeigt, wie man **create table** ausführt, dann **add text to table** zu Zellen hinzufügt und später **save presentation as pptx**.

#### Schritte

**1. Tabelle erstellen**  
Zuerst initialisieren Sie Ihre Präsentation und fügen an Position (50, 50) eine Tabelle mit angegebenen Spaltenbreiten und Zeilenhöhen hinzu.  
```java
Presentation pres = new Presentation();
try {
    ITable tbl = pres.getSlides().get_Item(0).getShapes().addTable(
        50, 50, new double[]{50, 70}, new double[]{50, 50, 50});
```  

**2. Text zu Zellen hinzufügen**  
Erstellen Sie Absätze mit Textteilen und fügen Sie sie einer bestimmten Zelle hinzu.  
```java
    IParagraph paragraph0 = new Paragraph();
    paragraph0.getPortions().add(new Portion("Text "));
    paragraph0.getPortions().add(new Portion("in0"));
    paragraph0.getPortions().add(new Portion(" Cell"));

    IParagraph paragraph1 = new Paragraph();
    paragraph1.setText("On0");

    IParagraph paragraph2 = new Paragraph();
    paragraph2.getPortions().add(new Portion("Hi there "));
    paragraph2.getPortions().add(new Portion("col0"));

    ICell cell = tbl.get_Item(1, 1);
    cell.getTextFrame().getParagraphs().clear();
    cell.getTextFrame().getParagraphs().addAll(Arrays.asList(paragraph0, paragraph1, paragraph2));
```  

**3. Präsentation speichern**  
```java
    pres.save("YOUR_OUTPUT_DIRECTORY/GetRect_Out.pptx", SaveFormat.Pptx);
} finally {
    if (pres != null) pres.dispose();
}
```  

### Feature 2: TextFrame zu AutoShape hinzufügen und Ausrichtung festlegen

#### Übersicht
Erfahren Sie, wie Sie einem AutoShape einen TextFrame mit bestimmter Ausrichtung hinzufügen – ein Beispiel für **set text alignment java**.

#### Schritte

Ein AutoShape ist eine Form, die Text und Grafiken enthalten kann.

**1. AutoShape hinzufügen**  
Fügen Sie ein Rechteck als AutoShape an Position (400, 100) mit angegebenen Abmessungen hinzu.  
```java
Presentation pres = new Presentation();
try {
    IAutoShape autoShape = pres.getSlides().get_Item(0).getShapes().addAutoShape(
        ShapeType.Rectangle, 400, 100, 60, 120);
```  

`TextAlignment`‑Enum definiert horizontale Ausrichtungsoptionen für Text innerhalb einer Form.

**2. Textausrichtung festlegen**  
Setzen Sie den Text auf „Text in shape“ und richten Sie ihn linksbündig aus.  
```java
    autoShape.getTextFrame().setText("Text in shape");
    autoShape.getTextFrame().getParagraphs().get_Item(0).getParagraphFormat().setAlignment(TextAlignment.Left);
```  

**3. Präsentation speichern**  
```java
    pres.save("YOUR_OUTPUT_DIRECTORY/GetRect_Out.pptx", SaveFormat.Pptx);
} finally {
    if (pres != null) pres.dispose();
}
```  

### Feature 3: Rahmen um Absätze und Teile in Tabellenzellen zeichnen

#### Übersicht
Dieses Feature konzentriert sich auf **draw frames around text** und sogar **draw rectangle around paragraph** für Teile, die das Zeichen ‘0’ enthalten.

#### Schritte

`IAutoShape` stellt ein Formobjekt dar, das auf einer Folie gezeichnet werden kann, z. B. Rechtecke, die als Rahmen verwendet werden.

**1. Tabelle erstellen**  
Verwenden Sie den Code aus „Create Table and Add Text to Cells“ für die anfängliche Einrichtung erneut.  
```java
Presentation pres = new Presentation();
try {
    ITable tbl = pres.getSlides().get_Item(0).getShapes().addTable(
        50, 50, new double[]{50, 70}, new double[]{50, 50, 50});
```  

**2. Absätze hinzufügen**  
Verwenden Sie den Code zur Absatz‑Erstellung aus dem vorherigen Feature erneut.  
```java
    IParagraph paragraph0 = new Paragraph();
    paragraph0.getPortions().add(new Portion("Text "));
    paragraph0.getPortions().add(new Portion("in0"));
    paragraph0.getPortions().add(new Portion(" Cell"));

    IParagraph paragraph1 = new Paragraph();
    paragraph1.setText("On0");

    IParagraph paragraph2 = new Paragraph();
    paragraph2.getPortions().add(new Portion("Hi there "));
    paragraph2.getPortions().add(new Portion("col0"));

    ICell cell = tbl.get_Item(1, 1);
    cell.getTextFrame().getParagraphs().clear();
    cell.getTextFrame().getParagraphs().addAll(Arrays.asList(paragraph0, paragraph1, paragraph2));
```  

**3. Rahmen zeichnen**  
Iterieren Sie über Absätze und Teile, um Rahmen um sie zu zeichnen.  
```java
    double x = tbl.getX() + cell.getOffsetX();
    double y = tbl.getY() + cell.getOffsetY();

    for (IParagraph para : cell.getTextFrame().getParagraphs()) {
        if ("".equals(para.getText())) continue;

        Rectangle2D.Float rect = (Rectangle2D.Float) para.getRect().clone();
        IAutoShape shape = (IAutoShape) pres.getSlides().get_Item(0).getShapes().addAutoShape(
            ShapeType.Rectangle, rect.x, rect.y, rect.width, rect.height);

        shape.getTextFrame().setText(para.getText());
        shape.setFillFormat(FillFormat.createNoFill());
        shape.getLineFormat().getFillFormat().setSolidFillColor(Color.BLACK);
    }
```  

**4. Präsentation speichern**  
```java
    pres.save("YOUR_OUTPUT_DIRECTORY/GetRect_Out.pptx", SaveFormat.Pptx);
} finally {
    if (pres != null) pres.dispose();
}
```  

## Häufige Fallstricke & Tipps

- **Null‑Prüfungen** – Wickeln Sie die Verwendung von `Presentation` immer in einen try‑finally‑Block, um sicherzustellen, dass `pres.dispose()` ausgeführt wird und native Ressourcen freigibt.  
- **Genauigkeit des Begrenzungsrechtecks** – Das von `para.getRect()` zurückgegebene Rechteck spiegelt das aktuelle Layout wider; wenn Sie Schriftgröße oder Ränder ändern, berechnen Sie das Rechteck erneut, bevor Sie den Rahmen zeichnen.  
- **Leistung** – Bei sehr großen Tabellen sollten Sie das Stapeln von Form‑Additionen in Betracht ziehen oder eine einzelne `IAutoShape`‑Instanz mit aktualisierter Geometrie wiederverwenden, um den Speicherverbrauch zu reduzieren.  

## Häufig gestellte Fragen

**F: Kann ich diese APIs mit älteren JDK‑Versionen verwenden?**  
A: Die Bibliothek unterstützt JDK 8 und höher, aber der `jdk16`‑Classifier bietet die beste Leistung auf neueren Laufzeiten.  

**F: Wie ändere ich die Rahmenfarbe?**  
A: Ändern Sie die Füllfarbe des Linienformats, z. B. `shape.getLineFormat().getFillFormat().setSolidFillColor(Color.BLUE);`.  

**F: Ist es möglich, die finale Folie als Bild zu exportieren?**  
A: Ja – verwenden Sie `pres.getSlides().get_Item(0).getImage(Export.ImageFormat.Png)` und speichern Sie dann das Byte‑Array.  

**F: Was, wenn ich nur das Wort „Total“ in einer Zelle hervorheben muss?**  
A: Iterieren Sie durch `cell.getTextFrame().getParagraphs()`, finden Sie den Teil, der „Total“ enthält, und zeichnen Sie ein Rechteck um die Begrenzungsbox dieses Teils.  

**F: Handhabt Aspose.Slides große Präsentationen effizient?**  
A: Die API streamt Daten und gibt Ressourcen frei, wenn `pres.dispose()` aufgerufen wird, was bei der Speicherverwaltung großer Dateien hilft.  

---

**Zuletzt aktualisiert:** 2026-06-23  
**Getestet mit:** Aspose.Slides for Java 25.4 (jdk16)  
**Author:** Aspose  

{{< blocks/products/products-backtop-button >}}

## Verwandte Tutorials

- [Aspose.Slides für Java: Master PPTX Tabellen- & Textmanipulation in PowerPoint-Präsentationen](/slides/java/tables/aspose-slides-java-pptx-table-text-manipulation-guide/)
- [Wie man dynamische Textrahmen in PowerPoint mit Aspose.Slides für Java erstellt](/slides/java/shapes-text-frames/dynamic-text-frames-powerpoint-aspose-slides-java/)
- [Spalten im TextFrame mit Aspose.Slides für Java hinzufügen](/slides/java/java-powerpoint-text-box-manipulation/add-columns-in-text-frame/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}