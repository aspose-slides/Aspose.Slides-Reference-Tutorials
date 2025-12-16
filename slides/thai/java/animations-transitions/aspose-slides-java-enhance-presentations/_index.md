---
date: '2025-12-10'
description: เรียนรู้วิธีเพิ่มข้อความในตารางและวาดกรอบรอบข้อความใน PowerPoint ด้วย
  Aspose.Slides for Java คู่มือนี้ครอบคลุมการสร้างตาราง การตั้งค่าการจัดแนวข้อความ
  และการใส่กรอบให้กับเนื้อหา
keywords:
- Aspose.Slides for Java
- table manipulation in presentations
- frame drawing in PowerPoint
title: Aspose.Slides สำหรับ Java – เพิ่มข้อความในตารางและการจัดการเฟรม
url: /th/java/animations-transitions/aspose-slides-java-enhance-presentations/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# เชี่ยวชาญการจัดการตารางและกรอบในงานนำเสนอด้วย Aspose.Slides for Java

## บทนำ

การนำเสนอข้อมูลอย่างมีประสิทธิภาพอาจเป็นความท้าทายใน PowerPoint ไม่ว่าคุณจะเป็นนักพัฒนาซอฟต์แวร์หรือผู้ออกแบบงานนำเสนอ **add text to table** เซลล์และวาดกรอบรอบย่อหน้าที่สำคัญเพื่อทำให้สไลด์ของคุณโดดเด่น ในบทแนะนำนี้คุณจะได้เห็นวิธีการเพิ่มข้อความในตาราง การจัดแนวข้อความ และการวาดกรอบรอบข้อความ — ทั้งหมดด้วย Aspose.Slides for Java เมื่อเสร็จสิ้น คุณจะสามารถสร้างสไลด์ที่ดูเป็นมืออาชีพและเน้นข้อมูลที่สำคัญในเวลาที่เหมาะสม

พร้อมที่จะเปลี่ยนแปลงงานนำเสนอของคุณหรือยัง? มาเริ่มกันเลย!

## คำตอบอย่างรวดเร็ว
- **What does “add text to table” mean?** It means inserting or updating the textual content of individual table cells programmatically.  
- **Which method saves the file?** `pres.save("output.pptx", SaveFormat.Pptx)` – this **save presentation as pptx** step finalizes your changes.  
- **How can I align text inside a shape?** Use `TextAlignment.Left` (or Center/Right) via `autoShape.getTextFrame().getParagraphs().get_Item(0).getParagraphFormat().setAlignment(...)`.  
- **Can I draw a rectangle around a paragraph?** Yes – iterate over paragraphs, get their bounding rectangle, and add an `IAutoShape` with no fill and a black line.  
- **Do I need a license?** A temporary license works for evaluation; a full license is required for production use.

## ข้อกำหนดเบื้องต้น

ก่อนจะลงลึกในโค้ด โปรดตรวจสอบว่าคุณมีสิ่งต่อไปนี้:

### ไลบรารีที่จำเป็น
คุณจะต้องใช้ Aspose.Slides for Java ด้านล่างนี้คือวิธีการรวมไลบรารีโดยใช้ Maven หรือ Gradle:

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

### การตั้งค่าสภาพแวดล้อม
ตรวจสอบให้แน่ใจว่าคุณได้ติดตั้ง Java Development Kit (JDK) แล้ว โดยแนะนำให้ใช้ JDK 16 หรือใหม่กว่า เนื่องจากตัวอย่างนี้ใช้ classifier `jdk16`.

### ความรู้เบื้องต้นที่จำเป็น
- ความเข้าใจพื้นฐานเกี่ยวกับการเขียนโปรแกรม Java  
- ความคุ้นเคยกับซอฟต์แวร์นำเสนอเช่น PowerPoint  
- ประสบการณ์การใช้ Integrated Development Environment (IDE) เช่น IntelliJ IDEA หรือ Eclipse  

## การตั้งค่า Aspose.Slides for Java

เพื่อเริ่มใช้ Aspose.Slides ให้ทำตามขั้นตอนต่อไปนี้:

1. **Install the Library**: Use Maven or Gradle to manage dependencies, or download it directly from [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/).

2. **License Acquisition**:
   - เริ่มต้นด้วยการทดลองใช้งานฟรีโดยดาวน์โหลดใบอนุญาตชั่วคราวจาก [Temporary License](https://purchase.aspose.com/temporary-license/).
   - หากต้องการการเข้าถึงเต็มรูปแบบ ให้พิจารณาซื้อใบอนุญาตที่ [Purchase Aspose.Slides](https://purchase.aspose.com/buy).

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

## ทำไมต้องเพิ่มข้อความในตารางและวาดกรอบ?

การเพิ่มข้อความในตารางช่วยให้คุณนำเสนอข้อมูลเชิงโครงสร้างได้อย่างชัดเจน ในขณะที่การวาดกรอบรอบย่อหน้าหรือส่วนที่เฉพาะเจาะจง (เช่น ส่วนที่มีอักขระ **'0'**) จะดึงความสนใจของผู้ชมไปยังค่าที่สำคัญ การผสมผสานนี้เหมาะอย่างยิ่งสำหรับรายงานการเงิน, แดชบอร์ด, หรือสไลด์ใด ๆ ที่ต้องการเน้นตัวเลขสำคัญโดยไม่ทำให้หน้าตรก

## วิธีเพิ่มข้อความในตารางด้วย Aspose.Slides for Java

### ฟีเจอร์ 1: สร้างตารางและเพิ่มข้อความในเซลล์

#### ภาพรวม
ฟีเจอร์นี้สาธิตวิธี **how to create table**, จากนั้น **add text to table** เซลล์และต่อมาจะ **save presentation as pptx**.

#### ขั้นตอน

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

### ฟีเจอร์ 2: เพิ่ม TextFrame ไปยัง AutoShape และตั้งค่าการจัดแนว

#### ภาพรวม
Learn how to add a text frame with specific alignment to an auto shape—an example of **set text alignment java**.

#### ขั้นตอน

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

### ฟีเจอร์ 3: วาดกรอบรอบย่อหน้าและส่วนในเซลล์ตาราง

#### ภาพรวม
ฟีเจอร์นี้มุ่งเน้นที่ **draw frames around text** และแม้กระทั่ง **draw rectangle around paragraph** สำหรับส่วนที่มีอักขระ ‘0’.

#### ขั้นตอน

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

## สรุป
โดยการทำตามคู่มือนี้ คุณสามารถ **add text to table**, จัดแนวข้อความภายในรูปทรง, และ **draw frames around text** เพื่อเน้นข้อมูลสำคัญ การเชี่ยวชาญเทคนิคเหล่านี้ทำให้คุณสร้างงานนำเสนอที่มีข้อมูลเชิงลึกและดูเป็นมืออาชีพด้วย Aspose.Slides for Java หากต้องการสำรวจต่อไป ลองผสานฟีเจอร์เหล่านี้กับแผนภูมิ, การเคลื่อนไหว, หรือการส่งออกเป็น PDF

## คำถามที่พบบ่อย

**Q: Can I use these APIs with older JDK versions?**  
A: ไลบรารีรองรับ JDK 8 ขึ้นไป แต่การใช้ classifier `jdk16` จะให้ประสิทธิภาพที่ดีที่สุดบน runtime รุ่นใหม่

**Q: How do I change the frame color?**  
A: แก้ไขสีของ line format เช่น `shape.getLineFormat().getFillFormat().setSolidFillColor(Color.BLUE);`.

**Q: Is it possible to export the final slide as an image?**  
A: ใช่ — ใช้ `pres.getSlides().get_Item(0).getImage(Export.ImageFormat.Png)` แล้วบันทึก byte array

**Q: What if I need to highlight only the word “Total” inside a cell?**  
A: ทำการวนลูป `cell.getTextFrame().getParagraphs()`, ค้นหา portion ที่มีคำว่า “Total”, แล้ววาดสี่เหลี่ยมรอบ bounding box ของ portion นั้น

**Q: Does Aspose.Slides handle large presentations efficiently?**  
A: API จะสตรีมข้อมูลและปล่อยทรัพยากรเมื่อเรียก `pres.dispose()` ซึ่งช่วยจัดการหน่วยความจำสำหรับไฟล์ขนาดใหญ่

{{< blocks/products/products-backtop-button >}}

**อัปเดตล่าสุด:** 2025-12-10  
**ทดสอบด้วย:** Aspose.Slides for Java 25.4 (jdk16)  
**ผู้เขียน:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}