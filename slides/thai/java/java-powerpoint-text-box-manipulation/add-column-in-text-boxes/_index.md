---
title: เพิ่มคอลัมน์ในกล่องข้อความด้วย Aspose.Slides สำหรับ Java
linktitle: เพิ่มคอลัมน์ในกล่องข้อความด้วย Aspose.Slides สำหรับ Java
second_title: Aspose.Slides Java PowerPoint การประมวลผล API
description: เรียนรู้วิธีเพิ่มคอลัมน์ลงในกล่องข้อความใน PowerPoint โดยใช้ Aspose.Slides สำหรับ Java ปรับปรุงการนำเสนอของคุณด้วยคำแนะนำทีละขั้นตอนนี้
type: docs
weight: 10
url: /th/java/java-powerpoint-text-box-manipulation/add-column-in-text-boxes/
---
## การแนะนำ
ในบทช่วยสอนนี้ เราจะสำรวจวิธีปรับปรุงกล่องข้อความโดยการเพิ่มคอลัมน์โดยใช้ Aspose.Slides สำหรับ Java Aspose.Slides เป็นไลบรารี Java อันทรงพลังที่ช่วยให้นักพัฒนาสามารถสร้าง จัดการ และแปลงงานนำเสนอ PowerPoint โดยทางโปรแกรมโดยไม่ต้องใช้ Microsoft Office การเพิ่มคอลัมน์ลงในกล่องข้อความสามารถปรับปรุงความสามารถในการอ่านและการจัดระเบียบเนื้อหาภายในสไลด์ได้อย่างมาก ทำให้การนำเสนอของคุณน่าสนใจและเป็นมืออาชีพมากขึ้น
## ข้อกำหนดเบื้องต้น
ก่อนที่เราจะเริ่มต้น ตรวจสอบให้แน่ใจว่าคุณมีข้อกำหนดเบื้องต้นดังต่อไปนี้:
- ความรู้พื้นฐานเกี่ยวกับการเขียนโปรแกรม Java
- ติดตั้ง JDK (Java Development Kit) บนเครื่องของคุณ
-  Aspose.Slides สำหรับไลบรารี Java คุณสามารถดาวน์โหลดได้จาก[ที่นี่](https://releases.aspose.com/slides/java/).

## แพ็คเกจนำเข้า
ในการเริ่มต้น คุณต้องนำเข้าคลาส Aspose.Slides ที่จำเป็นลงในไฟล์ Java ของคุณ ต่อไปนี้คือวิธีที่คุณสามารถทำได้:
```java
import com.aspose.slides.*;
```
## ขั้นตอนที่ 1: เริ่มต้นการนำเสนอและสไลด์
ขั้นแรก สร้างงานนำเสนอ PowerPoint ใหม่และเริ่มต้นสไลด์แรก
```java
// เส้นทางไปยังไดเร็กทอรีเอกสาร
String dataDir = "Your Document Directory";
Presentation presentation = new Presentation();
try {
    // รับสไลด์แรกของการนำเสนอ
    ISlide slide = presentation.getSlides().get_Item(0);
```
## ขั้นตอนที่ 2: เพิ่มรูปร่างอัตโนมัติ (สี่เหลี่ยมผืนผ้า)
จากนั้น เพิ่มรูปร่างอัตโนมัติประเภทสี่เหลี่ยมผืนผ้าลงในสไลด์
```java
    // เพิ่มประเภทสี่เหลี่ยมผืนผ้ารูปร่างอัตโนมัติ
    IAutoShape aShape = slide.getShapes().addAutoShape(ShapeType.Rectangle, 100, 100, 300, 300);
```
## ขั้นตอนที่ 3: เพิ่ม TextFrame ให้กับสี่เหลี่ยมผืนผ้า
ตอนนี้ เพิ่ม TextFrame ให้กับสี่เหลี่ยมผืนผ้าอัตโนมัติและตั้งค่าข้อความเริ่มต้น
```java
    // เพิ่ม TextFrame ให้กับสี่เหลี่ยมผืนผ้า
    aShape.addTextFrame("All these columns are limited to be within a single text container -- " +
            "you can add or delete text and the new or remaining text automatically adjusts " +
            "itself to flow within the container. You cannot have text flow from one container " +
            "to other though -- we told you PowerPoint's column options for text are limited!");
```
## ขั้นตอนที่ 4: กำหนดจำนวนคอลัมน์
ระบุจำนวนคอลัมน์ภายใน TextFrame
```java
    // รับรูปแบบข้อความของ TextFrame
    ITextFrameFormat format = aShape.getTextFrame().getTextFrameFormat();
    // ระบุจำนวนคอลัมน์ใน TextFrame
    format.setColumnCount(3);
```
## ขั้นตอนที่ 5: ปรับระยะห่างของคอลัมน์
กำหนดระยะห่างระหว่างคอลัมน์ใน TextFrame
```java
    // ระบุระยะห่างระหว่างคอลัมน์
    format.setColumnSpacing(10);
```
## ขั้นตอนที่ 6: บันทึกการนำเสนอ
สุดท้าย บันทึกงานนำเสนอที่แก้ไขแล้วลงในไฟล์ PowerPoint
```java
    // บันทึกการนำเสนอที่สร้างขึ้น
    presentation.save(dataDir + "ColumnCount.pptx", SaveFormat.Pptx);
} finally {
    if (presentation != null) presentation.dispose();
}
```

## บทสรุป
เมื่อทำตามขั้นตอนเหล่านี้ คุณจะสามารถเพิ่มคอลัมน์ลงในกล่องข้อความในงานนำเสนอ PowerPoint ได้อย่างง่ายดายโดยใช้ Aspose.Slides สำหรับ Java คุณลักษณะนี้ช่วยให้คุณสามารถปรับปรุงโครงสร้างและความสามารถในการอ่านสไลด์ของคุณ ทำให้สไลด์ดูน่าดึงดูดและเป็นมืออาชีพมากขึ้น
## คำถามที่พบบ่อย
### ฉันสามารถเพิ่มมากกว่าสามคอลัมน์ลงในกล่องข้อความได้หรือไม่
ใช่ คุณสามารถระบุจำนวนคอลัมน์เท่าใดก็ได้โดยใช้โปรแกรม Aspose.Slides
### Aspose.Slides เข้ากันได้กับ Java 11 หรือไม่
ใช่ Aspose.Slides รองรับ Java 11 และเวอร์ชันที่สูงกว่า
### ฉันจะรับใบอนุญาตชั่วคราวสำหรับ Aspose.Slides ได้อย่างไร
 คุณสามารถขอรับใบอนุญาตชั่วคราวได้[ที่นี่](https://purchase.aspose.com/temporary-license/).
### Aspose.Slides จำเป็นต้องติดตั้ง Microsoft Office หรือไม่
ไม่ Aspose.Slides ไม่จำเป็นต้องติดตั้ง Microsoft Office บนเครื่อง
### ฉันจะหาเอกสารเพิ่มเติมเกี่ยวกับ Aspose.Slides สำหรับ Java ได้ที่ไหน
 มีเอกสารรายละเอียดให้[ที่นี่](https://reference.aspose.com/slides/java/).