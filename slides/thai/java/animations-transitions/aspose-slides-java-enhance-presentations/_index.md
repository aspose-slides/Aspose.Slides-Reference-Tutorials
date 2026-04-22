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
# วิธีวาดกรอบข้อความในตารางในการนำเสนอด้วย Aspose.Slides สำหรับ Java

## การแนะนำ

ในอดีตข้อมูลใน PowerPoint มักจะพบที่ความยากลำบากในบางครั้งเมื่อต้องใช้ **เพิ่มข้อความลงในตาราง** เซลล์และเน้นค่าที่สำคัญด้วยสัญญาณภาพในคู่มือนี้คุณจะได้เรียนรู้ **วิธีการวาดเฟรม** รอบย่อหน้าในองค์ประกอบของแนวแนวข้อความภายในรูปร่างและสุดท้าย **บันทึกการนำเสนอเป็น pptx** — ทั้งหมดการพิจารณา Aspose.Slides สำหรับ Java คุณจะมีชุดสไลด์นำเสนอและนำเสนอของผู้ชมตามที่ต้องการ

พร้อมทำให้วิดีโอของคุณโดดเด่นหรือยัง? มาดำเนินการตามขั้นตอนทีละขั้นตอนกันเถอะ

## คำตอบด่วน
- ** “เพิ่มข้อความลงในตาราง” หมายความว่าอย่างไร** การแทรกหรืออัปเดตเนื้อหาข้อความในระดับแต่ละเซลล์โดยโปรแกรม
- **วิธีใดที่จะบันทึกไฟล์** `pres.save("output.pptx", SaveFormat.Pptx)` – ค้นหา **save Presentation as pptx** สิ่งนี้ทำให้การเปลี่ยนแปลงของคุณเกิดขึ้นอีกครั้ง
- **ฉันจะจัดแนวข้อความภายในรูปร่างได้อย่างไร** ใช้ `TextAlignment.Left` (หรือ Center/Right) ผ่าน `autoShape.getTextFrame().getParagraphs().get_Item(0).getParagraphFormat().setAlignment(...)`
- **ฉันสามารถวาดรูปสี่เหลี่ยมผืนผ้ารอบย่อหน้าได้หรือไม่** ได้ – ทำการดำเนินการมากมายผ่านย่อหน้า, รับขอบเขตของพื้นที่และพื้นที่, แล้วเพิ่ม `IAutoShape` ที่ไม่มีการเติมสีและเส้นสีดำ
- **Do I need a License?** เป็นเพียงชั่วคราวที่ใช้ได้กับระบบปฏิบัติการ; เราต้องใช้เวลาเต็มในผลิตภัณฑ์

## ทำไมต้องวาดกรอบรอบข้อความ?

หมายเหตุกรอบ (หรือสี่เหลี่ยม) ชั้นย่อหน้าหรือส่วนเฉพาะ (เช่นว่าสิ่งใดๆ ที่เป็นคำอธิบาย **'0'**) จะเป็นเพียงเทคนิคในทันทีที่เหมาะสำหรับ:

- เน้นตัวเลขที่สำคัญในระดับ
- เน้นคำเตือนหรือบันทึกสำคัญในสไลด์
- สร้างตัวแบ่งภาพเพื่อเพิ่มรูปร่างเพิ่มเติม

## ข้อกำหนดเบื้องต้น

การวินิจฉัยลงลึกในโค้ดกรุณาตรวจสอบคุณอีกครั้ง:

### ห้องสมุดที่จำเป็น
คุณจะต้องใช้ Aspose.Slides สำหรับ Java ก่อนวิธีการรวมเข้าด้วย Maven หรือ Gradle:

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
เมื่อคุณติดตั้ง Java Development Kit (JDK) ไว้แล้ว แนะนำให้ใช้ JDK16 หรือใหม่กว่าปกติตัวอย่างนี้ใช้ classifier `jdk16`

### ข้อกำหนดเบื้องต้นของความรู้
- ความเข้าใจในลักษณะเดียวกับ Java
- ขอนำเสนอเช่น PowerPoint.
- มีประสบการณ์ใช้ Integrated Development Environment (IDE) เช่น IntelliJ IDEA หรือ Eclipse.

## การตั้งค่า Aspose.Slides สำหรับ Java

เพื่อเริ่มใช้ Aspose.Slides ต่อไปในขั้นตอนต่อไป:

1. **ติดตั้งไลบรารี**: ใช้ Maven หรือ Gradle เพื่อจัดการการพึ่งพาหรือดาวน์โหลดการดาวน์โหลด [Aspose.Slides สำหรับ Java releases](https://releases.aspose.com/slides/java/)

2. **การได้มาซึ่งใบอนุญาต**: 
- ตลอดกาลแห่งความอร่อยใช้ฟรีโดยดาวน์โหลดในเวลาชั่วขณะจาก [ใบอนุญาตชั่วคราว](https://purchase.aspose.com/temporary-license/) 
- สำหรับข้อมูลเพิ่มเติม โปรดพิจารณาซื้อทุกครั้งที่ [Purchase Aspose.Slides](https://purchase.aspose.com/buy)

3. **การเริ่มต้นขั้นพื้นฐาน**: เริ่มต้นสภาพแวดล้อมการนำเสนอของคุณด้วยโค้ดตัวอย่างต่อไปนี้:
```java
import com.aspose.slides.*;

Presentation pres = new Presentation();
try {
    // Your code here
} finally {
    if (pres != null) pres.dispose();
}
```

## วิธีเพิ่มข้อความลงในตารางใน Aspose.Slides สำหรับ Java

### คุณสมบัติที่ 1: สร้างตารางและเพิ่มข้อความลงในเซลล์

#### ภาพรวม
Tính năng này minh họa cách **create table**, sau đó **add text to table** vào các ô và cuối cùng **save presentation as pptx**.

#### ขั้นตอน

**1. สร้างตาราง**
ขั้นแรก ให้เริ่มต้นงานนำเสนอของคุณและเพิ่มตารางที่ตำแหน่ง (50,50) โดยกำหนดความกว้างของคอลัมน์และความสูงของแถว
```java
Presentation pres = new Presentation();
try {
    ITable tbl = pres.getSlides().get_Item(0).getShapes().addTable(
        50, 50, new double[]{50, 70}, new double[]{50, 50, 50});
```

**2. เพิ่มข้อความลงในเซลล์**  
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

**3. บันทึกการนำเสนอ**  
```java
    pres.save("YOUR_OUTPUT_DIRECTORY/GetRect_Out.pptx", SaveFormat.Pptx);
} finally {
    if (pres != null) pres.dispose();
}
```

### คุณสมบัติ 2: เพิ่ม TextFrame ให้กับรูปร่างอัตโนมัติและตั้งค่าการจัดตำแหน่ง

#### ภาพรวม
Tìm hiểu cách thêm một khung văn běn với căn chỉnh cụ thể vào một auto shape—ví dụ của **ตั้งค่าการจัดตำแหน่งข้อความ java**.

#### ขั้นตอน

**1. เพิ่มรูปร่างอัตโนมัติ**
เพิ่มสี่เหลี่ยมเป็นรูปร่างอัตโนมัติที่ตำแหน่ง (400,100) ด้วยขนาดที่ระบุ
```java
Presentation pres = new Presentation();
try {
    IAutoShape autoShape = pres.getSlides().get_Item(0).getShapes().addAutoShape(
        ShapeType.Rectangle, 400, 100, 60, 120);
```

**2. ตั้งค่าการจัดแนวข้อความ**  
ตั้งค่าข้อความเป็น “Text in shape” และจัดแนวซ้าย.
```java
    autoShape.getTextFrame().setText("Text in shape");
    autoShape.getTextFrame().getParagraphs().get_Item(0).getParagraphFormat().setAlignment(TextAlignment.Left);
```

**3. บันทึกงานนำเสนอ**
```java
    pres.save("YOUR_OUTPUT_DIRECTORY/GetRect_Out.pptx", SaveFormat.Pptx);
} finally {
    if (pres != null) pres.dispose();
}
```

### คุณสมบัติที่ 3: วาดกรอบรอบย่อหน้าและส่วนต่างๆ ในเซลล์ตาราง

#### ภาพรวม
Tính năng này tập trung vào **draw frames around text** và thậm chí **draw rectangle around paragraph** cho các phần chứa ký tự ‘0’.

#### ขั้นตอน

**1. สร้างตาราง**
ใช้โค้ดจาก “สร้างตารางและเพิ่มข้อความลงในเซลล์” สำหรับการตั้งค่าเริ่มต้น
```java
Presentation pres = new Presentation();
try {
    ITable tbl = pres.getSlides().get_Item(0).getShapes().addTable(
        50, 50, new double[]{50, 70}, new double[]{50, 50, 50});
```

**2. เพิ่มย่อหน้า**
ใช้โค้ดการสร้างย่อหน้าจากคุณสมบัติก่อนหน้า
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

**3. วาดกรอบ**
วนซ้ำกับย่อหน้าและส่วนต่างๆ เพื่อวาดกรอบรอบๆ
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

**4. บันทึกงานนำเสนอ** 
```java
    pres.save("YOUR_OUTPUT_DIRECTORY/GetRect_Out.pptx", SaveFormat.Pptx);
} finally {
    if (pres != null) pres.dispose();
}
```

## ข้อผิดพลาดและเคล็ดลับทั่วไป

- **Null checks** – อาหารห่อการใช้ `Presentation` ส่วนที่เหลือของบล็อก try‑finally `pres.dispose()` สมุนไพรและปล่อยทรัพยากรธรรมชาติ
- **ความแม่นยำของสี่เหลี่ยมล้อมรอบ** – สี่เหลี่ยมที่ `paragetRect()` ตรงนี้จะสะท้อนกลับวางปัจจุบัน; ตรวจสอบการเปลี่ยนขนาดฟอนต์หรือระยะขอบ, คำนวณเครื่องคิดเลขใหม่ก่อนวาดกรอบ
- **Performance** – ในกรณีที่มีระดับขนาดใหญ่มาก, พิจารณาเพิ่มรูปร่างเป็นชุดหรือใช้ `IAutoShape` คนเดียวที่อัปเดตรูปทรงเพื่อลดการใช้พลังงาน

## คำถามที่พบบ่อย

**ถาม: ฉันสามารถใช้ API เหล่านี้กับ JDK เวอร์ชันเก่าได้หรือไม่**
A: ไลบรารีรองรับ JDK8 ขึ้นไป, แต่ลักษณนาม `jdk16` ให้ประสิทธิภาพที่ดีที่สุดบนรันไทม์รุ่นใหม่

**Q: ฉันจะเปลี่ยนสีกรอบได้อย่างไร?**
A: การออกแบบสีเติมของรูปแบบเส้น เช่น `shape.getLineFormat().getFillFormat().setSolidFillColor(Color.BLUE);`

**ถาม: เป็นไปได้ไหมที่จะส่งออกสไลด์สุดท้ายเป็นรูปภาพ**
ตอบ: ได้ — ใช้ `pres.getSlides().get_Item(0).getImage(Export.ImageFormat.Png)` แล้วบันทึกอาเรย์กรีดร้อง

**ถาม: จะต้องทำอย่างไรหากจำเป็น เน้นเฉพาะคำว่า "ทั้งหมด" ภายในเซลล์ใช่ไหม**
A: วนอุทยานแห่งชาติผ่าน `cell.getTextFrame().getParagraphs()`, ค้นหาส่วนที่มี “Total”, แล้วก็วาดสี่เหลี่ยมรอบกล่องขอบเขตของส่วนนั้น

**ถาม: Aspose.Slides จัดการงานนำเสนอขนาดใหญ่ได้อย่างมีประสิทธิภาพหรือไม่**
ตอบ: API จะสตรีมข้อมูลและปล่อยทรัพยากรเมื่อเรียก `pres.dispose()` ซึ่งจะช่วยจัดการกับข้อมูลสำหรับไฟล์ขนาดใหญ่

---

** อัปเดตล่าสุด:** 2026-02-09
**ทดสอบด้วย:** Aspose.Slides for Java 25.4 (jdk16)
**หมายเหตุ:** สมมุติ  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
