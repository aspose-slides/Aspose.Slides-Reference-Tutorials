---
date: '2026-02-09'
description: Học cách vẽ khung quanh văn bản và thêm văn bản vào các ô bảng trong
  PowerPoint bằng Aspose.Slides cho Java. Bài hướng dẫn này bao gồm việc tạo bảng,
  thiết lập căn chỉnh văn bản và lưu bản trình chiếu dưới dạng pptx.
keywords:
- Aspose.Slides for Java
- table manipulation in presentations
- frame drawing in PowerPoint
title: Cách vẽ khung và thêm văn bản vào bảng với Aspose.Slides cho Java
url: /vi/java/animations-transitions/aspose-slides-java-enhance-presentations/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Cách Vẽ Khung và Thêm Văn Bản vào Bảng trong Bản Trình Chiếu với Aspose.Slides cho Java

## Introduction

Việc trình bày dữ liệu một cách rõ ràng trong PowerPoint có thể là một thách thức thực sự, đặc biệt khi bạn cần **add text to table** vào các ô bảng và làm nổi bật các giá trị quan trọng bằng các dấu hiệu trực quan. Trong hướng dẫn này, bạn sẽ học **how to draw frames** quanh các đoạn văn cụ thể, thiết lập căn chỉnh văn bản bên trong các hình dạng, và cuối cùng **save presentation as pptx**—tất cả đều sử dụng Aspose.Slides cho Java. Khi hoàn thành, bạn sẽ có một bộ slide được chỉnh sửa tinh tế, thu hút ánh mắt khán giả đúng nơi bạn muốn.

Sẵn sàng làm cho slide của bạn nổi bật? Hãy cùng đi qua quy trình từng bước.

## Quick Answers
- **What does “add text to table” mean?** It means inserting or updating the textual content of individual table cells programmatically.  
- **Which method saves the file?** `pres.save("output.pptx", SaveFormat.Pptx)` – this **save presentation as pptx** step finalizes your changes.  
- **How can I align text inside a shape?** Use `TextAlignment.Left` (or Center/Right) via `autoShape.getTextFrame().getParagraphs().get_Item(0).getParagraphFormat().setAlignment(...)`.  
- **Can I draw a rectangle around a paragraph?** Yes – iterate over paragraphs, get their bounding rectangle, and add an `IAutoShape` with no fill and a black line.  
- **Do I need a license?** A temporary license works for evaluation; a full license is required for production use.  

## Why draw frames around text?

Vẽ một khung (hoặc hình chữ nhật) quanh một đoạn văn hoặc một phần cụ thể (ví dụ, bất kỳ văn bản nào chứa ký tự **'0'**) ngay lập tức thu hút sự chú ý. Kỹ thuật này lý tưởng cho:

- Làm nổi bật các con số tài chính quan trọng trong bảng.  
- Nhấn mạnh các cảnh báo hoặc ghi chú quan trọng trong slide.  
- Tạo các phân cách trực quan mà không cần thêm các hình dạng thủ công.

## Prerequisites

Trước khi bắt đầu viết mã, hãy đảm bảo bạn có những thứ sau:

### Required Libraries
Bạn sẽ cần Aspose.Slides cho Java. Dưới đây là cách đưa nó vào dự án bằng Maven hoặc Gradle:

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
Đảm bảo bạn đã cài đặt Java Development Kit (JDK), ưu tiên JDK 16 hoặc mới hơn, vì ví dụ này sử dụng classifier `jdk16`.

### Knowledge Prerequisites
- Hiểu biết cơ bản về lập trình Java.  
- Quen thuộc với phần mềm trình chiếu như PowerPoint.  
- Kinh nghiệm sử dụng môi trường phát triển tích hợp (IDE) như IntelliJ IDEA hoặc Eclipse.

## Setting Up Aspose.Slides for Java

Để bắt đầu sử dụng Aspose.Slides, làm theo các bước sau:

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

## How to Add Text to Table in Aspose.Slides for Java

### Feature 1: Create Table and Add Text to Cells

#### Overview
Tính năng này minh họa cách **create table**, sau đó **add text to table** vào các ô và cuối cùng **save presentation as pptx**.

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
Tìm hiểu cách thêm một khung văn bản với căn chỉnh cụ thể vào một auto shape—ví dụ của **set text alignment java**.

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
Tính năng này tập trung vào **draw frames around text** và thậm chí **draw rectangle around paragraph** cho các phần chứa ký tự ‘0’.

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

## Common Pitfalls & Tips

- **Null checks** – Always wrap your `Presentation` usage in a try‑finally block to ensure `pres.dispose()` runs and frees native resources.  
- **Bounding rectangle accuracy** – The rectangle returned by `para.getRect()` reflects the current layout; if you change font size or margins, recompute the rectangle before drawing the frame.  
- **Performance** – When working with very large tables, consider batching shape additions or reusing a single `IAutoShape` instance with updated geometry to reduce memory overhead.

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

**Last Updated:** 2026-02-09  
**Tested With:** Aspose.Slides for Java 25.4 (jdk16)  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}