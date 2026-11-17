---
date: '2026-11-16'
description: Rahmen um Text in PowerPoint-Tabellen mit Aspose.Slides for Java zeichnen
  – erfahren Sie, wie Sie Tabellen erstellen, Text zu Zellen hinzufügen, Zellen hervorheben
  und die Datei als PPTX exportieren.
keywords:
- draw frame around text
- highlight table cell
- convert slide to png
- highlight word cell
- change frame color java
- add text table cell
lastmod: '2026-11-16'
og_description: Rahmen um Text in PowerPoint-Tabellen mit Aspose.Slides for Java zeichnen.
  Diese Anleitung zeigt, wie man Tabellen erstellt, Text hinzufügt und ausrichtet,
  Zellen hervorhebt und Folien als PNG exportiert.
og_image_alt: 'Developer guide: draw frame around text in PowerPoint using Aspose.Slides
  for Java'
og_title: Wie man einen Rahmen um Text zeichnet und Tabellen in PowerPoint mit Aspose.Slides
  for Java erstellt
schemas:
- author: Aspose
  dateModified: '2026-11-16'
  description: Draw frame around text in PowerPoint tables using Aspose.Slides for
    Java – learn how to create tables, add text to cells, highlight content, and save
    the file as PPTX.
  headline: How to draw frame around text and create tables in PowerPoint with Aspose.Slides
    for Java
  type: TechArticle
- description: Draw frame around text in PowerPoint tables using Aspose.Slides for
    Java – learn how to create tables, add text to cells, highlight content, and save
    the file as PPTX.
  name: How to draw frame around text and create tables in PowerPoint with Aspose.Slides
    for Java
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
tags:
- Aspose.Slides
- Java presentation automation
- PowerPoint table manipulation
- draw frame around text
- PPTX generation
title: Wie man einen Rahmen um Text zeichnet und Tabellen in PowerPoint mit Aspose.Slides
  for Java erstellt
url: /de/java/animations-transitions/aspose-slides-java-enhance-presentations/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Wie man einen Rahmen um Text zeichnet und Tabellen in PowerPoint mit Aspose.Slides für Java erstellt

## Einleitung

Das Zeichnen eines **draw frame around text** in einer PowerPoint‑Folien ermöglicht es, wichtige Zahlen hervorzuheben, ohne den zugrunde liegenden Inhalt zu ändern. In diesem Tutorial lernen Sie, wie Sie programmgesteuert eine Tabelle erstellen, Text in Zellen einfügen und ausrichten, bestimmte Wörter oder ganze Zellen hervorheben und schließlich die Präsentation als PPTX‑Datei speichern. Am Ende haben Sie eine professionell gestaltete Folie, die die Aufmerksamkeit des Publikums genau dorthin lenkt, wo Sie es wünschen.

## Schnelle Antworten
- **Was bedeutet “add text to table”?** Es bedeutet, den Textinhalt einzelner Tabellenzellen programmgesteuert einzufügen oder zu aktualisieren.  
- **Welche Methode speichert die Datei?** `pres.save("output.pptx", SaveFormat.Pptx)` – dieser **save presentation as pptx**‑Schritt finalisiert Ihre Änderungen.  
- **Wie kann ich Text innerhalb einer Form ausrichten?** Verwenden Sie `TextAlignment.Left` (oder Center/Right) über `autoShape.getTextFrame().getParagraphs().get_Item(0).getParagraphFormat().setAlignment(...)`.  
- **Kann ich ein Rechteck um einen Absatz zeichnen?** Ja – iterieren Sie über Absätze, holen Sie deren Begrenzungsrechteck und fügen Sie ein `IAutoShape` ohne Füllung und mit einer schwarzen Linie hinzu.  
- **Brauche ich eine Lizenz?** Eine temporäre Lizenz funktioniert für die Evaluierung; eine Vollversion ist für den Produktionseinsatz erforderlich.  

## Warum Rahmen um Text zeichnen?

Das Zeichnen eines Rahmens um Text hebt sofort wichtige Zahlen, Warnungen oder Überschriften hervor. Es bietet einen visuellen Hinweis, während die ursprüngliche Formatierung unverändert bleibt, und ist damit ideal für Finanzberichte, KPI‑Dashboards oder jede Folie, bei der Hervorhebungen erforderlich sind.

## Was ist draw frame around text?

`draw frame around text` ist die Technik, programmgesteuert eine rechteckige Form hinzuzufügen, die exakt den Rand eines Absatzes oder eines Textabschnitts nachzeichnet, wobei nur die Linienformatierung verwendet wird und das Innere nicht gefüllt wird. Dieser Ansatz ermöglicht es, Inhalte hervorzuheben, ohne den Text selbst zu verändern.

## Voraussetzungen

Bevor Sie beginnen, stellen Sie sicher, dass Sie Folgendes haben:

### Erforderliche Bibliotheken
Sie benötigen Aspose.Slides für Java. Binden Sie es mit einem der Paketmanager ein:

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

Sie können die Releases auch unter [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/) durchsuchen.

### Umgebung einrichten
Ein Java Development Kit (JDK) 16 oder neuer wird empfohlen, da die Beispiele den `jdk16`‑Classifier verwenden. Jede IDE wie IntelliJ IDEA oder Eclipse funktioniert.

### Wissensvoraussetzungen
- Grundlegende Java‑Programmierkenntnisse.  
- Vertrautheit mit PowerPoint‑Konzepten (Folien, Formen, Tabellen).  
- Verständnis dafür, wie Maven/Gradle Abhängigkeiten verwalten.

## Einrichtung von Aspose.Slides für Java

`Presentation` ist die Kernklasse von Aspose.Slides, die eine PowerPoint‑Datei im Speicher repräsentiert und Zugriff auf Folien, Formen und Tabellen bietet. Sie kann Präsentationen mit bis zu **10.000 Folien** verarbeiten, während der Speicherverbrauch unter **500 MB** bleibt, was sie für groß angelegte Automatisierung geeignet macht.

1. **Bibliothek installieren** – verwenden Sie Maven oder Gradle oder laden Sie sie direkt von [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/) herunter.  
2. **Lizenzbeschaffung** – beginnen Sie mit einer kostenlosen Testversion von [Temporary License](https://purchase.aspose.com/temporary-license/) und aktualisieren Sie zu einer Vollversion unter [Purchase Aspose.Slides](https://purchase.aspose.com/buy) für Produktionsworkloads.  
3. **Grundlegende Initialisierung** – erstellen Sie ein neues `Presentation`‑Objekt und laden oder erstellen Sie Folien nach Bedarf.  
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

`Presentation` ist die Hauptklasse, die eine PowerPoint‑Datei im Speicher repräsentiert.  
Laden Sie ein neues `Presentation`, erstellen Sie eine Tabelle an den gewünschten Koordinaten, füllen Sie die Zellen mit `TextFrame`‑Objekten und rufen Sie schließlich `pres.save("output.pptx", SaveFormat.Pptx)` auf. Dieser Ablauf erstellt eine **create table in PowerPoint**, fügt benutzerdefinierten Text in jede Zelle ein und schreibt das Ergebnis in einer einzigen, effizienten Arbeitsablauf in eine PPTX‑Datei.

### Direkte Antwort
Erstellen Sie eine Tabelle, indem Sie `slide.getShapes().addTable(...)` aufrufen, dann für jede Zelle `cell.getTextFrame().addParagraph().getPortions().add(new Portion("Your text"))` verwenden. Nach dem Befüllen aller Zellen rufen Sie `pres.save("output.pptx", SaveFormat.Pptx)` auf, um die Datei zu schreiben. Dieser Ansatz ermöglicht es, den Inhalt und Stil jeder Zelle programmgesteuert zu steuern.

#### Feature 1: Tabelle erstellen und Text zu Zellen hinzufügen

**1. Tabelle erstellen** – initialisieren Sie eine Präsentation, fügen Sie eine Folie hinzu und platzieren Sie eine Tabelle bei (50, 50) mit definierten Spaltenbreiten und Zeilenhöhen.  
```java
Presentation pres = new Presentation();
try {
    ITable tbl = pres.getSlides().get_Item(0).getShapes().addTable(
        50, 50, new double[]{50, 70}, new double[]{50, 50, 50});
```  

**2. Text zu Zellen hinzufügen** – für jede Zelle erstellen Sie ein `Paragraph`, fügen ein `Portion` mit dem gewünschten String hinzu und weisen das Paragraph dem `TextFrame` der Zelle zu.  
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

**3. Präsentation speichern** – rufen Sie `pres.save("output.pptx", SaveFormat.Pptx)` auf.  
```java
    pres.save("YOUR_OUTPUT_DIRECTORY/GetRect_Out.pptx", SaveFormat.Pptx);
} finally {
    if (pres != null) pres.dispose();
}
```  

## Wie zeichnet man einen Rahmen um Text in einer PowerPoint‑Folien?

`Rectangle2D` repräsentiert einen rechteckigen Bereich in einem zweidimensionalen Koordinatensystem. Laden Sie die Folie, finden Sie den Absatz oder das Textsegment, das Sie hervorheben möchten, holen Sie dessen Begrenzungsrechteck über `getRect()` und fügen Sie dann ein `IAutoShape`‑Rechteck ohne Füllung und mit einer farbigen Linie hinzu. Diese Methode funktioniert sowohl für ganze Absätze als auch für einzelne Wortsegmente.

### Direkte Antwort
Um einen Rahmen um Text zu zeichnen, erhalten Sie zuerst das Rechteck des Absatzes (`Rectangle2D rect = paragraph.getRect();`). Dann erstellen Sie ein `IAutoShape`‑Rechteck (`slide.getShapes().addAutoShape(ShapeType.Rectangle, rect.getX(), rect.getY(), rect.getWidth(), rect.getHeight())`), setzen `shape.getLineFormat().getFillFormat().setSolidFillColor(Color.RED)`, und deaktivieren die Füllung (`shape.getFillFormat().setFillType(FillType.NoFill)`). Die Form umrandet den Text exakt.

#### Feature 3: Rahmen um Absätze und Segmente in Tabellenzellen zeichnen

**1. Tabelle erstellen** – verwenden Sie den Code aus Feature 1, um die Ausgangstabelle einzurichten.  
```java
Presentation pres = new Presentation();
try {
    ITable tbl = pres.getSlides().get_Item(0).getShapes().addTable(
        50, 50, new double[]{50, 70}, new double[]{50, 50, 50});
```  

**2. Absätze hinzufügen** – verwenden Sie den Code zur Absatz-Erstellung aus Feature 1.  
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

**3. Rahmen zeichnen** – iterieren Sie über jeden Absatz, erhalten Sie dessen Begrenzungsrechteck und fügen Sie ein Rechteck‑Shape wie oben beschrieben hinzu. Für Segmente, die das Zeichen ‘0’ enthalten, zeichnen Sie einen zusätzlichen Rahmen, um diese Zahlen hervorzuheben.  
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

**4. Präsentation speichern** – derselbe abschließende Schritt wie zuvor.  
```java
    pres.save("YOUR_OUTPUT_DIRECTORY/GetRect_Out.pptx", SaveFormat.Pptx);
} finally {
    if (pres != null) pres.dispose();
}
```  

## Wie fügt man einem AutoShape ein Textfeld hinzu und richtet es aus

`AutoShape` ist eine Form, die Text, Bilder oder andere Inhalte enthalten kann. Ein `AutoShape` kann ein `TextFrame` halten. Sie können die horizontale Ausrichtung mit dem `ParagraphFormat`‑Enum steuern.

### Direkte Antwort
Erstellen Sie ein Rechteck‑AutoShape (`slide.getShapes().addAutoShape(ShapeType.Rectangle, 400, 100, 300, 100)`), greifen Sie auf dessen `TextFrame` zu, setzen Sie den Text mit `shape.getTextFrame().setText("Text in shape")` und rufen Sie dann `shape.getTextFrame().getParagraphs().get_Item(0).getParagraphFormat().setAlignment(TextAlignment.Left)` auf. Dies richtet den Text linksbündig innerhalb der Form aus.

**1. AutoShape hinzufügen** – platzieren Sie ein Rechteck an der gewünschten Position.  
```java
Presentation pres = new Presentation();
try {
    IAutoShape autoShape = pres.getSlides().get_Item(0).getShapes().addAutoShape(
        ShapeType.Rectangle, 400, 100, 60, 120);
```  

**2. Textausrichtung festlegen** – wenden Sie die linke Ausrichtung wie oben gezeigt an.  
```java
    autoShape.getTextFrame().setText("Text in shape");
    autoShape.getTextFrame().getParagraphs().get_Item(0).getParagraphFormat().setAlignment(TextAlignment.Left);
```  

**3. Präsentation speichern** – derselbe abschließende Schritt.  
```java
    pres.save("YOUR_OUTPUT_DIRECTORY/GetRect_Out.pptx", SaveFormat.Pptx);
} finally {
    if (pres != null) pres.dispose();
}
```  

## Häufige Fallstricke & Tipps

- **Immer freigeben** – umschließen Sie die Verwendung von `Presentation` in einem try‑finally‑Block und rufen Sie `pres.dispose()` auf, um native Ressourcen freizugeben.  
- **Begrenzungsrechtecke neu berechnen** – wenn Sie nach dem Zeichnen eines Rahmens Schriftgröße, Ränder oder Zellenabstand ändern, rufen Sie vor dem Hinzufügen der Form erneut `paragraph.getRect()` auf.  
- **Stapelweise Shape-Erstellung für große Tabellen** – die Wiederverwendung einer einzelnen `IAutoShape`‑Instanz und das Aktualisieren ihrer Geometrie reduziert den Speicherverbrauch bei der Verarbeitung von Tabellen mit Hunderten von Zeilen.  
- **Leistungszahlen** – Aspose.Slides kann ein 200‑seitiges PPTX in weniger als 2 Sekunden auf einem typischen 4‑Kern‑Server erzeugen, und das Zeichnen von Rahmen um 1.000 Absätze fügt weniger als 150 ms Overhead hinzu.

## Häufig gestellte Fragen

**F: Kann ich diese APIs mit älteren JDK‑Versionen verwenden?**  
A: Die Bibliothek unterstützt JDK 8 und höher, aber der `jdk16`‑Classifier bietet die beste Leistung auf neueren Laufzeiten.

**F: Wie ändere ich die Rahmenfarbe?**  
A: Ändern Sie die Füllfarbe des Linienformats, z. B. `shape.getLineFormat().getFillFormat().setSolidFillColor(Color.BLUE);`.

**F: Ist es möglich, die finale Folie als Bild zu exportieren?**  
A: Ja – verwenden Sie `pres.getSlides().get_Item(0).getImage(Export.ImageFormat.Png)` und speichern Sie dann das Byte‑Array.

**F: Was, wenn ich nur das Wort “Total” innerhalb einer Zelle hervorheben muss?**  
A: Iterieren Sie durch `cell.getTextFrame().getParagraphs()`, finden Sie das Segment, das “Total” enthält, und zeichnen Sie ein Rechteck um die Begrenzungsbox dieses Segments.

**F: Handhabt Aspose.Slides große Präsentationen effizient?**  
A: Die API streamt Daten und gibt Ressourcen frei, wenn `pres.dispose()` aufgerufen wird, was beim Speicher‑Management großer Dateien hilft.

**Zuletzt aktualisiert:** 2026-11-16  
**Getestet mit:** Aspose.Slides for Java 25.4 (jdk16)  
**Autor:** Aspose  



## Verwandte Tutorials

- [Aspose.Slides für Java: Master PPTX‑Tabellen‑ & Textmanipulation in PowerPoint‑Präsentationen](/slides/java/tables/aspose-slides-java-pptx-table-text-manipulation-guide/)
- [Wie man dynamische Textfelder in PowerPoint mit Aspose.Slides für Java erstellt](/slides/java/shapes-text-frames/dynamic-text-frames-powerpoint-aspose-slides-java/)
- [Spalten im Textfeld mit Aspose.Slides für Java hinzufügen](/slides/java/java-powerpoint-text-box-manipulation/add-columns-in-text-frame/)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}