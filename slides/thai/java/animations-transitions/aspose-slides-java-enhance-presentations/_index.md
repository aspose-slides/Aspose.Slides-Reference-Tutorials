---
date: '2026-06-23'
description: เรียนรู้วิธีสร้างตารางใน PowerPoint, เพิ่มข้อความลงในเซลล์ของตาราง, วาดกรอบรอบข้อความ,
  และบันทึกงานนำเสนอเป็นไฟล์ pptx ด้วย Aspose.Slides for Java.
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
title: วิธีสร้างตารางใน PowerPoint และวาดกรอบด้วย Aspose.Slides for Java
url: /th/java/animations-transitions/aspose-slides-java-enhance-presentations/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# วิธีสร้างตารางใน PowerPoint และวาดกรอบด้วย Aspose.Slides for Java

## บทนำ

การสร้าง **create table in PowerPoint** แบบโปรแกรมสามารถช่วยคุณประหยัดเวลาหลายชั่วโมงจากการจัดรูปแบบด้วยมือ โดยเฉพาะเมื่อคุณต้องการเน้นตัวเลขสำคัญหรือเพิ่มหมายเหตุอธิบาย ในบทเรียนนี้คุณจะได้เรียนรู้วิธีเพิ่มข้อความลงในเซลล์ของตาราง, วาดกรอบรอบย่อหน้าที่ระบุ, ตั้งค่าการจัดแนวข้อความอย่างแม่นยำ, และสุดท้าย **save presentation as pptx** – ทั้งหมดนี้ด้วย Aspose.Slides for Java API ที่ทรงพลัง เมื่อเสร็จสิ้นคุณจะได้สไลด์ที่ดูเรียบร้อย อ่านง่าย และดึงดูดความสนใจของผู้ชมไปยังข้อมูลที่สำคัญที่สุดโดยทันที

## คำตอบสั้น
- **What does “add text to table” mean?** หมายถึงการแทรกหรืออัปเดตเนื้อหาข้อความของเซลล์ตารางแต่ละเซลล์แบบโปรแกรม  
- **Which method saves the file?** `pres.save("output.pptx", SaveFormat.Pptx)` – ขั้นตอน **save presentation as pptx** นี้ทำให้การเปลี่ยนแปลงของคุณเสร็จสมบูรณ์  
- **How can I align text inside a shape?** ใช้ `TextAlignment.Left` (หรือ Center/Right) ผ่าน `autoShape.getTextFrame().getParagraphs().get_Item(0).getParagraphFormat().setAlignment(...)`  
- **Can I draw a rectangle around a paragraph?** ได้ – ทำการวนลูปผ่านย่อหน้า, รับสี่เหลี่ยมขอบเขตของพวกมัน, แล้วเพิ่ม `IAutoShape` ที่ไม่มีการเติมสีและเส้นสีดำ  
- **Do I need a license?** ใบอนุญาตชั่วคราวใช้ได้สำหรับการประเมิน; จำเป็นต้องมีใบอนุญาตเต็มสำหรับการใช้งานจริง  

## ทำไมต้องวาดกรอบรอบข้อความ?

การวาดกรอบ (หรือสี่เหลี่ยม) รอบย่อหน้าหรือส่วนเฉพาะ—เช่นข้อความใด ๆ ที่มีอักขระ **'0'**—จะดึงความสนใจของผู้ชมไปยังเนื้อหานั้นทันที มันให้สัญญาณภาพที่ชัดเจนโดยไม่ต้องเปลี่ยนแปลงข้อความเดิม ทำให้เหมาะสำหรับการเน้นตัวเลขสำคัญ, คำเตือน, หรือแยกส่วนต่าง ๆ ภายในสไลด์

## ข้อกำหนดเบื้องต้น

ก่อนจะลงลึกในโค้ด, โปรดตรวจสอบว่าคุณมีสิ่งต่อไปนี้:

### ไลบรารีที่จำเป็น
คุณจะต้องใช้ Aspose.Slides for Java. นี่คือวิธีการรวมเข้าด้วย Maven หรือ Gradle:

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
ตรวจสอบให้แน่ใจว่าคุณได้ติดตั้ง Java Development Kit (JDK) แล้ว, แนะนำให้ใช้ JDK 16 หรือใหม่กว่า, เนื่องจากตัวอย่างนี้ใช้ classifier `jdk16`.

### ความรู้ที่ต้องมีล่วงหน้า
- ความเข้าใจพื้นฐานของการเขียนโปรแกรม Java.  
- คุ้นเคยกับซอฟต์แวร์นำเสนอเช่น PowerPoint.  
- ประสบการณ์การใช้ Integrated Development Environment (IDE) เช่น IntelliJ IDEA หรือ Eclipse.

## การตั้งค่า Aspose.Slides for Java

`Presentation` เป็นคลาสหลักของ Aspose.Slides ที่แทนไฟล์ PowerPoint ในหน่วยความจำและให้การเข้าถึงสไลด์, รูปร่าง, และตาราง เพื่อเริ่มใช้ Aspose.Slides ให้ทำตามขั้นตอนต่อไปนี้:

1. **Install the Library**: ใช้ Maven หรือ Gradle เพื่อจัดการ dependencies, หรือดาวน์โหลดโดยตรงจาก [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/).

2. **License Acquisition**:
   - เริ่มต้นด้วยการทดลองใช้ฟรีโดยดาวน์โหลดใบอนุญาตชั่วคราวจาก [Temporary License](https://purchase.aspose.com/temporary-license/).
   - หากต้องการการเข้าถึงเต็ม, พิจารณาซื้อใบอนุญาตที่ [Purchase Aspose.Slides](https://purchase.aspose.com/buy).

3. **Basic Initialization**:  
   เริ่มต้นสภาพแวดล้อมการนำเสนอของคุณด้วยโค้ดตัวอย่างต่อไปนี้:  
   ```java
import com.aspose.slides.*;

Presentation pres = new Presentation();
try {
    // Your code here
} finally {
    if (pres != null) pres.dispose();
}
```  

## วิธีเพิ่มข้อความลงในตารางใน Aspose.Slides for Java?

โหลด `Presentation` ใหม่, สร้างตารางที่ตำแหน่งที่ต้องการ, เติมเซลล์ด้วยอ็อบเจ็กต์ `TextFrame`, และสุดท้ายเรียก `pres.save("output.pptx", SaveFormat.Pptx)`. ลำดับนี้จะสร้าง **create table in PowerPoint**, แทรกข้อความที่กำหนดลงในแต่ละเซลล์, และบันทึกผลลัพธ์เป็นไฟล์ PPTX ในขั้นตอนเดียวที่มีประสิทธิภาพ

### ฟีเจอร์ 1: สร้างตารางและเพิ่มข้อความลงในเซลล์

#### ภาพรวม
ฟีเจอร์นี้แสดงวิธี **create table**, จากนั้น **add text to table** ในเซลล์และต่อมาทำ **save presentation as pptx**.

#### ขั้นตอน

**1. Create a Table**  
แรกเริ่มให้เริ่มต้นการนำเสนอของคุณและเพิ่มตารางที่ตำแหน่ง (50, 50) พร้อมความกว้างคอลัมน์และความสูงแถวที่กำหนด.  
```java
Presentation pres = new Presentation();
try {
    ITable tbl = pres.getSlides().get_Item(0).getShapes().addTable(
        50, 50, new double[]{50, 70}, new double[]{50, 50, 50});
```  

**2. Add Text to Cells**  
สร้างย่อหน้าที่มีส่วนของข้อความและเพิ่มลงในเซลล์ที่ระบุ.  
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
เรียนรู้วิธีเพิ่ม TextFrame พร้อมการจัดแนวเฉพาะไปยัง AutoShape — ตัวอย่างของ **set text alignment java**.

#### ขั้นตอน

AutoShape คือรูปทรงที่สามารถบรรจุข้อความและกราฟิกได้.

**1. Add an AutoShape**  
เพิ่มสี่เหลี่ยมเป็น AutoShape ที่ตำแหน่ง (400, 100) พร้อมขนาดที่กำหนด.  
```java
Presentation pres = new Presentation();
try {
    IAutoShape autoShape = pres.getSlides().get_Item(0).getShapes().addAutoShape(
        ShapeType.Rectangle, 400, 100, 60, 120);
```  

`TextAlignment` enum กำหนดตัวเลือกการจัดแนวแนวนอนสำหรับข้อความภายในรูปทรง.

**2. Set Text Alignment**  
ตั้งค่าข้อความเป็น “Text in shape” และจัดแนวไปทางซ้าย.  
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

`IAutoShape` แทนอ็อบเจ็กต์รูปทรงที่สามารถวาดบนสไลด์, เช่นสี่เหลี่ยมที่ใช้เป็นกรอบ.

**1. Create a Table**  
ใช้โค้ดจาก “Create Table and Add Text to Cells” สำหรับการตั้งค่าเริ่มต้น.  
```java
Presentation pres = new Presentation();
try {
    ITable tbl = pres.getSlides().get_Item(0).getShapes().addTable(
        50, 50, new double[]{50, 70}, new double[]{50, 50, 50});
```  

**2. Add Paragraphs**  
ใช้โค้ดการสร้างย่อหน้าจากฟีเจอร์ก่อนหน้า.  
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
วนลูปผ่านย่อหน้าและส่วนต่าง ๆ เพื่อวาดกรอบรอบพวกมัน.  
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

## ข้อผิดพลาดทั่วไปและเคล็ดลับ

- **Null checks** – ควรห่อการใช้ `Presentation` ของคุณในบล็อก try‑finally เพื่อให้แน่ใจว่า `pres.dispose()` ทำงานและปล่อยทรัพยากรเนทีฟ.  
- **Bounding rectangle accuracy** – สี่เหลี่ยมที่ `para.getRect()` คืนค่าจะสะท้อนการจัดวางปัจจุบัน; หากคุณเปลี่ยนขนาดฟอนต์หรือระยะขอบ, ควรคำนวณสี่เหลี่ยมใหม่ก่อนวาดกรอบ.  
- **Performance** – เมื่อทำงานกับตารางขนาดใหญ่มาก, พิจารณาเพิ่มรูปทรงเป็นชุดหรือใช้ `IAutoShape` ตัวเดียวที่อัปเดตเรขาคณิตเพื่อ ลดการใช้หน่วยความจำ.  

## คำถามที่พบบ่อย

**Q: Can I use these APIs with older JDK versions?**  
A: ไลบรารีรองรับ JDK 8 ขึ้นไป, แต่ classifier `jdk16` ให้ประสิทธิภาพที่ดีที่สุดบน runtime รุ่นใหม่.

**Q: How do I change the frame color?**  
A: ปรับสีเติมของรูปแบบเส้น, เช่น `shape.getLineFormat().getFillFormat().setSolidFillColor(Color.BLUE);`.

**Q: Is it possible to export the final slide as an image?**  
A: ได้ — ใช้ `pres.getSlides().get_Item(0).getImage(Export.ImageFormat.Png)` แล้วบันทึกอาร์เรย์ไบต์.

**Q: What if I need to highlight only the word “Total” inside a cell?**  
A: วนลูปผ่าน `cell.getTextFrame().getParagraphs()`, ค้นหาส่วนที่มี “Total”, แล้ววาดสี่เหลี่ยมรอบกล่องขอบของส่วนนั้น.

**Q: Does Aspose.Slides handle large presentations efficiently?**  
A: API จะสตรีมข้อมูลและปล่อยทรัพยากรเมื่อเรียก `pres.dispose()` ซึ่งช่วยจัดการหน่วยความจำสำหรับไฟล์ขนาดใหญ่.

---

**อัปเดตล่าสุด:** 2026-06-23  
**ทดสอบกับ:** Aspose.Slides for Java 25.4 (jdk16)  
**ผู้เขียน:** Aspose  

{{< blocks/products/products-backtop-button >}}

## บทแนะนำที่เกี่ยวข้อง

- [Aspose.Slides for Java: การควบคุมตาราง PPTX & การจัดการข้อความในงานนำเสนอ PowerPoint](/slides/java/tables/aspose-slides-java-pptx-table-text-manipulation-guide/)
- [วิธีสร้างกรอบข้อความแบบไดนามิกใน PowerPoint ด้วย Aspose.Slides for Java](/slides/java/shapes-text-frames/dynamic-text-frames-powerpoint-aspose-slides-java/)
- [เพิ่มคอลัมน์ใน Text Frame ด้วย Aspose.Slides for Java](/slides/java/java-powerpoint-text-box-manipulation/add-columns-in-text-frame/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}