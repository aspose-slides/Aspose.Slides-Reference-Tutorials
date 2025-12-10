---
date: '2025-12-10'
description: Scopri come aggiungere testo a una tabella e disegnare cornici attorno
  al testo in PowerPoint usando Aspose.Slides per Java. Questa guida copre la creazione
  di tabelle, l'impostazione dell'allineamento del testo e la creazione di cornici
  intorno al contenuto.
keywords:
- Aspose.Slides for Java
- table manipulation in presentations
- frame drawing in PowerPoint
title: Aspose.Slides per Java – aggiungere testo a tabella e manipolazione del frame
url: /it/java/animations-transitions/aspose-slides-java-enhance-presentations/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Mastering Table and Frame Manipulation in Presentations with Aspose.Slides for Java

## Introduction

Presentare i dati in modo efficace può essere una sfida in PowerPoint. Che tu sia uno sviluppatore software o un designer di presentazioni, **add text to table** celle e disegnare cornici attorno a paragrafi chiave per far risaltare le tue slide. In questo tutorial vedrai esattamente come aggiungere testo a una tabella, allinearlo e disegnare cornici attorno al testo — tutto con Aspose.Slides for Java. Alla fine, sarai in grado di creare deck raffinati che evidenziano le informazioni giuste al momento giusto.

Pronto a trasformare le tue presentazioni? Iniziamo!

## Quick Answers
- **What does “add text to table” mean?** It means inserting or updating the textual content of individual table cells programmatically.  
- **Which method saves the file?** `pres.save("output.pptx", SaveFormat.Pptx)` – this **save presentation as pptx** step finalizes your changes.  
- **How can I align text inside a shape?** Use `TextAlignment.Left` (or Center/Right) via `autoShape.getTextFrame().getParagraphs().get_Item(0).getParagraphFormat().setAlignment(...)`.  
- **Can I draw a rectangle around a paragraph?** Yes – iterate over paragraphs, get their bounding rectangle, and add an `IAutoShape` with no fill and a black line.  
- **Do I need a license?** A temporary license works for evaluation; a full license is required for production use.

## Prerequisites

Before diving into the code, ensure you have the following:

### Required Libraries
You'll need Aspose.Slides for Java. Here's how to include it using Maven or Gradle:

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

### Environment Setup
Ensure you have a Java Development Kit (JDK) installed, preferably JDK 16 or later, as this example uses the `jdk16` classifier.

### Knowledge Prerequisites
- Basic understanding of Java programming.  
- Familiarity with presentation software like PowerPoint.  
- Experience using an Integrated Development Environment (IDE) such as IntelliJ IDEA or Eclipse.

## Setting Up Aspose.Slides for Java

To start using Aspose.Slides, follow these steps:

1. **Install the Library**: Use Maven or Gradle to manage dependencies, or download it directly from [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/).

2. **License Acquisition**:
   - Start with a free trial by downloading a temporary license from [Temporary License](https://purchase.aspose.com/temporary-license/).
   - For full access, consider purchasing a license at [Purchase Aspose.Slides](https://purchase.aspose.com/buy).

3. **Basic Initialization**:
Initialize your presentation environment with the following code snippet:
```java
import com.aspose.slides.*;

Presentation pres = new Presentation();
try {
    // Your code here
} finally {
    if (pres != null) pres.dispose();
}
```

## Why add text to table and draw frames?

Adding text to a table lets you present structured data clearly, while drawing frames around paragraphs or specific portions (e.g., those containing the character **'0'**) draws the audience’s eye to important values. This combination is perfect for financial reports, dashboards, or any slide where you need to highlight key numbers without clutter.

## How to add text to table in Aspose.Slides for Java

### Feature 1: Create Table and Add Text to Cells

#### Overview
This feature demonstrates how to **how to create table**, then **add text to table** cells and later **save presentation as pptx**.

#### Steps

**1. Create a Table**  
First, initialize your presentation and add a table at position (50, 50) with specified column widths and row heights.
```java
Presentation pres = new Presentation();
try {
    ITable tbl = pres.getSlides().get_Item(0).getShapes().addTable(
        50, 50, new double[]{50, 70}, new double[]{50, 50, 50});
```

**2. Add Text to Cells**  
Create paragraphs with portions of text and add them to a specific cell.
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

**3. Save the Presentation**  
```java
    pres.save("YOUR_OUTPUT_DIRECTORY/GetRect_Out.pptx", SaveFormat.Pptx);
} finally {
    if (pres != null) pres.dispose();
}
```

### Feature 2: Add TextFrame to AutoShape and Set Alignment

#### Overview
Learn how to add a text frame with specific alignment to an auto shape—an example of **set text alignment java**.

#### Steps

**1. Add an AutoShape**  
Add a rectangle as an AutoShape at position (400, 100) with specified dimensions.
```java
Presentation pres = new Presentation();
try {
    IAutoShape autoShape = pres.getSlides().get_Item(0).getShapes().addAutoShape(
        ShapeType.Rectangle, 400, 100, 60, 120);
```

**2. Set Text Alignment**  
Set the text to “Text in shape” and align it to the left.
```java
    autoShape.getTextFrame().setText("Text in shape");
    autoShape.getTextFrame().getParagraphs().get_Item(0).getParagraphFormat().setAlignment(TextAlignment.Left);
```

**3. Save the Presentation**  
```java
    pres.save("YOUR_OUTPUT_DIRECTORY/GetRect_Out.pptx", SaveFormat.Pptx);
} finally {
    if (pres != null) pres.dispose();
}
```

### Feature 3: Draw Frames around Paragraphs and Portions in Table Cells

#### Overview
This feature focuses on **draw frames around text** and even **draw rectangle around paragraph** for portions containing the character ‘0’.

#### Steps

**1. Create a Table**  
Reuse the code from “Create Table and Add Text to Cells” for initial setup.
```java
Presentation pres = new Presentation();
try {
    ITable tbl = pres.getSlides().get_Item(0).getShapes().addTable(
        50, 50, new double[]{50, 70}, new double[]{50, 50, 50});
```

**2. Add Paragraphs**  
Reuse the paragraph creation code from the previous feature.
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

**3. Draw Frames**  
Iterate over paragraphs and portions to draw frames around them.
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

**4. Save the Presentation**  
```java
    pres.save("YOUR_OUTPUT_DIRECTORY/GetRect_Out.pptx", SaveFormat.Pptx);
} finally {
    if (pres != null) pres.dispose();
}
```

## Conclusion
By following this guide, you can **add text to table**, align text inside shapes, and **draw frames around text** to emphasize important information. Mastering these techniques lets you create highly polished, data‑driven presentations with Aspose.Slides for Java. For further exploration, try combining these features with charts, animations, or exporting to PDF.

## Frequently Asked Questions

**Q: Can I use these APIs with older JDK versions?**  
A: The library supports JDK 8 onward, but the `jdk16` classifier gives the best performance on newer runtimes.

**Q: How do I change the frame color?**  
A: Modify the line format fill color, e.g., `shape.getLineFormat().getFillFormat().setSolidFillColor(Color.BLUE);`.

**Q: Is it possible to export the final slide as an image?**  
A: Yes—use `pres.getSlides().get_Item(0).getImage(Export.ImageFormat.Png)` and then save the byte array.

**Q: What if I need to highlight only the word “Total” inside a cell?**  
A: Iterate through `cell.getTextFrame().getParagraphs()`, locate the portion containing “Total”, and draw a rectangle around that portion’s bounding box.

**Q: Does Aspose.Slides handle large presentations efficiently?**  
A: The API streams data and releases resources when `pres.dispose()` is called, which helps with memory management for large files.

---

{{< blocks/products/products-backtop-button >}}

**Last Updated:** 2025-12-10  
**Tested With:** Aspose.Slides for Java 25.4 (jdk16)  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}