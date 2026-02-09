---
date: '2026-02-09'
description: เรียนรู้วิธีวาดกรอบรอบข้อความและเพิ่มข้อความลงในเซลล์ตารางใน PowerPoint
  โดยใช้ Aspose.Slides for Java การสอนนี้ครอบคลุมการสร้างตาราง การตั้งค่าการจัดแนวข้อความ
  และการบันทึกงานนำเสนอเป็นไฟล์ pptx.
keywords:
- Aspose.Slides for Java
- table manipulation in presentations
- frame drawing in PowerPoint
title: วิธีวาดกรอบและเพิ่มข้อความในตารางด้วย Aspose.Slides สำหรับ Java
url: /th/java/animations-transitions/aspose-slides-java-enhance-presentations/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# วิธีวาดกรอบและเพิ่มข้อความในตารางในงานนำเสนอด้วย Aspose.Slides for Java

## Introduction

การนำเสนอข้อมูลอย่างชัดเจนใน PowerPoint อาจเป็นอุปสรรคที่ท้าทาย โดยเฉพาะเมื่อคุณต้อง **add text to table** เซลล์และเน้นค่าที่สำคัญด้วยสัญญาณภาพ ในคู่มือนี้คุณจะได้เรียนรู้ **how to draw frames** รอบย่อหน้าที่ระบุ ตั้งค่าการจัดแนวข้อความภายในรูปร่าง และสุดท้าย **save presentation as pptx** —ทั้งหมดโดยใช้ Aspose.Slides for Java เมื่อเสร็จสิ้นคุณจะมีชุดสไลด์ที่ดูเป็นมืออาชีพและดึงดูดความสนใจของผู้ชมตามที่ต้องการ

พร้อมทำให้สไลด์ของคุณโดดเด่นหรือยัง? มาดำเนินการตามขั้นตอนทีละขั้นตอนกันเถอะ

## Quick Answers
- **What does “add text to table” mean?** หมายถึงการแทรกหรืออัปเดตเนื้อหาข้อความของเซลล์ตารางแต่ละเซลล์โดยโปรแกรม  
- **Which method saves the file?** `pres.save("output.pptx", SaveFormat.Pptx)` – ขั้นตอน **save presentation as pptx** นี้ทำให้การเปลี่ยนแปลงของคุณเสร็จสมบูรณ์  
- **How can I align text inside a shape?** ใช้ `TextAlignment.Left` (หรือ Center/Right) ผ่าน `autoShape.getTextFrame().getParagraphs().get_Item(0).getParagraphFormat().setAlignment(...)`  
- **Can I draw a rectangle around a paragraph?** ได้ – ทำการวนลูปผ่านย่อหน้า, รับสี่เหลี่ยมขอบเขตของพวกมัน, แล้วเพิ่ม `IAutoShape` ที่ไม่มีการเติมสีและเส้นสีดำ  
- **Do I need a license?** ใบอนุญาตชั่วคราวใช้ได้สำหรับการประเมิน; จำเป็นต้องมีใบอนุญาตเต็มสำหรับการใช้งานในผลิตภัณฑ์  

## Why draw frames around text?

การวาดกรอบ (หรือสี่เหลี่ยม) รอบย่อหน้าหรือส่วนเฉพาะ (เช่น ข้อความใด ๆ ที่มีอักขระ **'0'**) จะดึงดูดความสนใจทันที เทคนิคนี้เหมาะสำหรับ:

- เน้นตัวเลขทางการเงินสำคัญในตาราง  
- เน้นคำเตือนหรือบันทึกสำคัญในสไลด์  
- สร้างตัวแบ่งภาพโดยไม่ต้องเพิ่มรูปร่างเพิ่มเติมด้วยตนเอง  

## Prerequisites

ก่อนจะลงลึกในโค้ด โปรดตรวจสอบว่าคุณมีสิ่งต่อไปนี้:

### Required Libraries
คุณจะต้องใช้ Aspose.Slides for Java นี่คือวิธีการรวมเข้าด้วย Maven หรือ Gradle:

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
ตรวจสอบว่าคุณได้ติดตั้ง Java Development Kit (JDK) ไว้แล้ว แนะนำให้ใช้ JDK 16 หรือใหม่กว่า เนื่องจากตัวอย่างนี้ใช้ classifier `jdk16`

### Knowledge Prerequisites
- ความเข้าใจพื้นฐานของการเขียนโปรแกรม Java.  
- คุ้นเคยกับซอฟต์แวร์นำเสนอเช่น PowerPoint.  
- มีประสบการณ์ใช้ Integrated Development Environment (IDE) เช่น IntelliJ IDEA หรือ Eclipse.

## Setting Up Aspose.Slides for Java

เพื่อเริ่มใช้ Aspose.Slides ให้ทำตามขั้นตอนต่อไปนี้:

1. **Install the Library**: ใช้ Maven หรือ Gradle เพื่อจัดการ dependencies หรือดาวน์โหลดโดยตรงจาก [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/).

2. **License Acquisition**:
   - เริ่มต้นด้วยการทดลองใช้ฟรีโดยดาวน์โหลดใบอนุญาตชั่วคราวจาก [Temporary License](https://purchase.aspose.com/temporary-license/).
   - สำหรับการเข้าถึงเต็ม, พิจารณาซื้อใบอนุญาตที่ [Purchase Aspose.Slides](https://purchase.aspose.com/buy).

3. **Basic Initialization**: เริ่มต้นสภาพแวดล้อมการนำเสนอของคุณด้วยโค้ดตัวอย่างต่อไปนี้:
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
ฟีเจอร์นี้แสดงวิธี **create table**, จากนั้น **add text to table** เซลล์และต่อมาทำการ **save presentation as pptx**

#### Steps

**1. Create a Table**  
แรกเริ่มให้สร้างการนำเสนอของคุณและเพิ่มตารางที่ตำแหน่ง (50, 50) พร้อมกำหนดความกว้างของคอลัมน์และความสูงของแถวตามที่ระบุ.
```java
Presentation pres = new Presentation();
try {
    ITable tbl = pres.getSlides().get_Item(0).getShapes().addTable(
        50, 50, new double[]{50, 70}, new double[]{50, 50, 50});
```

**2. Add Text to Cells**  
สร้างย่อหน้าที่มีส่วนของข้อความและเพิ่มลงในเซลล์ที่กำหนด.
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
เรียนรู้วิธีเพิ่ม text frame พร้อมการจัดแนวที่กำหนดให้กับ auto shape — ตัวอย่างของ **set text alignment java**

#### Steps

**1. Add an AutoShape**  
เพิ่มสี่เหลี่ยมเป็น AutoShape ที่ตำแหน่ง (400, 100) พร้อมขนาดที่กำหนด.
```java
Presentation pres = new Presentation();
try {
    IAutoShape autoShape = pres.getSlides().get_Item(0).getShapes().addAutoShape(
        ShapeType.Rectangle, 400, 100, 60, 120);
```

**2. Set Text Alignment**  
ตั้งค่าข้อความเป็น “Text in shape” และจัดแนวซ้าย.
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
ฟีเจอร์นี้มุ่งเน้นที่ **draw frames around text** และแม้กระทั่ง **draw rectangle around paragraph** สำหรับส่วนที่มีอักขระ ‘0’

#### Steps

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
วนลูปผ่านย่อหน้าและส่วนต่าง ๆ เพื่อวาดกรอบรอบแต่ละส่วน.
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

- **Null checks** – ควรห่อการใช้ `Presentation` ของคุณด้วยบล็อก try‑finally เพื่อให้แน่ใจว่า `pres.dispose()` จะทำงานและปล่อยทรัพยากรเนทีฟ  
- **Bounding rectangle accuracy** – สี่เหลี่ยมที่ `para.getRect()` คืนค่าจะสะท้อนการจัดวางปัจจุบัน; หากคุณเปลี่ยนขนาดฟอนต์หรือระยะขอบ, คำนวณสี่เหลี่ยมใหม่ก่อนวาดกรอบ  
- **Performance** – เมื่อทำงานกับตารางขนาดใหญ่มาก, พิจารณาเพิ่มรูปร่างเป็นชุดหรือใช้ `IAutoShape` ตัวเดียวที่อัปเดตรูปทรงเพื่อ ลดการใช้หน่วยความจำ  

## Frequently Asked Questions

**Q: Can I use these APIs with older JDK versions?**  
A: ไลบรารีรองรับ JDK 8 ขึ้นไป, แต่ classifier `jdk16` ให้ประสิทธิภาพที่ดีที่สุดบน runtime รุ่นใหม่  

**Q: How do I change the frame color?**  
A: แก้ไขสีเติมของรูปแบบเส้น, ตัวอย่างเช่น `shape.getLineFormat().getFillFormat().setSolidFillColor(Color.BLUE);`  

**Q: Is it possible to export the final slide as an image?**  
A: ได้ — ใช้ `pres.getSlides().get_Item(0).getImage(Export.ImageFormat.Png)` แล้วบันทึกอาเรย์ไบต์  

**Q: What if I need to highlight only the word “Total” inside a cell?**  
A: วนลูปผ่าน `cell.getTextFrame().getParagraphs()`, ค้นหาส่วนที่มี “Total”, แล้ววาดสี่เหลี่ยมรอบกล่องขอบเขตของส่วนนั้น  

**Q: Does Aspose.Slides handle large presentations efficiently?**  
A: API จะสตรีมข้อมูลและปล่อยทรัพยากรเมื่อเรียก `pres.dispose()` ซึ่งช่วยจัดการหน่วยความจำสำหรับไฟล์ขนาดใหญ่  

---

{{< blocks/products/products-backtop-button >}}

**อัปเดตล่าสุด:** 2026-02-09  
**ทดสอบด้วย:** Aspose.Slides for Java 25.4 (jdk16)  
**ผู้เขียน:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}