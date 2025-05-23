---
"description": "เรียนรู้วิธีเพิ่มคอลัมน์ลงในกล่องข้อความใน PowerPoint โดยใช้ Aspose.Slides สำหรับ Java ปรับปรุงการนำเสนอของคุณด้วยคู่มือทีละขั้นตอนนี้"
"linktitle": "เพิ่มคอลัมน์ในกล่องข้อความด้วย Aspose.Slides สำหรับ Java"
"second_title": "API การประมวลผล Java PowerPoint ของ Aspose.Slides"
"title": "เพิ่มคอลัมน์ในกล่องข้อความด้วย Aspose.Slides สำหรับ Java"
"url": "/th/java/java-powerpoint-text-box-manipulation/add-column-in-text-boxes/"
"weight": 10
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# เพิ่มคอลัมน์ในกล่องข้อความด้วย Aspose.Slides สำหรับ Java

## การแนะนำ
ในบทช่วยสอนนี้ เราจะมาเรียนรู้วิธีการปรับปรุงกล่องข้อความโดยการเพิ่มคอลัมน์โดยใช้ Aspose.Slides สำหรับ Java Aspose.Slides เป็นไลบรารี Java ที่มีประสิทธิภาพที่ช่วยให้ผู้พัฒนาสามารถสร้าง จัดการ และแปลงงานนำเสนอ PowerPoint ได้ด้วยโปรแกรมโดยไม่ต้องใช้ Microsoft Office การเพิ่มคอลัมน์ลงในกล่องข้อความสามารถปรับปรุงการอ่านและการจัดระเบียบเนื้อหาภายในสไลด์ได้อย่างมาก ทำให้การนำเสนอของคุณน่าสนใจและเป็นมืออาชีพมากขึ้น
## ข้อกำหนดเบื้องต้น
ก่อนที่เราจะเริ่ม ให้แน่ใจว่าคุณมีข้อกำหนดเบื้องต้นดังต่อไปนี้:
- ความรู้พื้นฐานเกี่ยวกับการเขียนโปรแกรมภาษา Java
- JDK (Java Development Kit) ติดตั้งอยู่บนเครื่องของคุณ
- Aspose.Slides สำหรับไลบรารี Java คุณสามารถดาวน์โหลดได้จาก [ที่นี่](https://releases-aspose.com/slides/java/).

## แพ็คเกจนำเข้า
ในการเริ่มต้น คุณต้องนำเข้าคลาส Aspose.Slides ที่จำเป็นลงในไฟล์ Java ของคุณ โดยคุณสามารถทำได้ดังนี้:
```java
import com.aspose.slides.*;
```
## ขั้นตอนที่ 1: เริ่มต้นการนำเสนอและสไลด์
ขั้นแรก ให้สร้างการนำเสนอ PowerPoint ใหม่และเริ่มต้นสไลด์แรก
```java
// เส้นทางไปยังไดเร็กทอรีเอกสาร
String dataDir = "Your Document Directory";
Presentation presentation = new Presentation();
try {
    // รับสไลด์แรกของการนำเสนอ
    ISlide slide = presentation.getSlides().get_Item(0);
```
## ขั้นตอนที่ 2: เพิ่ม AutoShape (สี่เหลี่ยมผืนผ้า)
ขั้นตอนต่อไป เพิ่ม AutoShape ที่เป็นชนิดสี่เหลี่ยมผืนผ้าลงในสไลด์
```java
    // เพิ่มรูปร่างอัตโนมัติของชนิดสี่เหลี่ยมผืนผ้า
    IAutoShape aShape = slide.getShapes().addAutoShape(ShapeType.Rectangle, 100, 100, 300, 300);
```
## ขั้นตอนที่ 3: เพิ่ม TextFrame ลงในสี่เหลี่ยมผืนผ้า
ตอนนี้ เพิ่ม TextFrame ลงใน Rectangle AutoShape และตั้งค่าข้อความเริ่มต้น
```java
    // เพิ่ม TextFrame ลงในสี่เหลี่ยมผืนผ้า
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
## ขั้นตอนที่ 5: ปรับระยะห่างระหว่างคอลัมน์
กำหนดระยะห่างระหว่างคอลัมน์ใน TextFrame
```java
    // ระบุระยะห่างระหว่างคอลัมน์
    format.setColumnSpacing(10);
```
## ขั้นตอนที่ 6: บันทึกการนำเสนอ
สุดท้ายให้บันทึกงานนำเสนอที่ปรับเปลี่ยนแล้วลงในไฟล์ PowerPoint
```java
    // บันทึกการนำเสนอที่สร้างขึ้น
    presentation.save(dataDir + "ColumnCount.pptx", SaveFormat.Pptx);
} finally {
    if (presentation != null) presentation.dispose();
}
```

## บทสรุป
หากทำตามขั้นตอนเหล่านี้ คุณสามารถเพิ่มคอลัมน์ลงในกล่องข้อความในงานนำเสนอ PowerPoint ได้อย่างง่ายดายโดยใช้ Aspose.Slides สำหรับ Java ฟีเจอร์นี้ช่วยให้คุณปรับปรุงโครงสร้างและการอ่านสไลด์ของคุณ ทำให้สไลด์ดูน่าสนใจและเป็นมืออาชีพมากขึ้น
## คำถามที่พบบ่อย
### ฉันสามารถเพิ่มคอลัมน์มากกว่าสามคอลัมน์ในกล่องข้อความได้ไหม
ใช่ คุณสามารถระบุจำนวนคอลัมน์ได้ตามต้องการด้วยโปรแกรมโดยใช้ Aspose.Slides
### Aspose.Slides เข้ากันได้กับ Java 11 หรือไม่
ใช่ Aspose.Slides รองรับ Java 11 และเวอร์ชันที่สูงกว่า
### ฉันจะได้รับใบอนุญาตชั่วคราวสำหรับ Aspose.Slides ได้อย่างไร
คุณสามารถขอใบอนุญาตชั่วคราวได้ [ที่นี่](https://purchase-aspose.com/temporary-license/).
### Aspose.Slides จำเป็นต้องติดตั้ง Microsoft Office หรือไม่
ไม่ Aspose.Slides ไม่จำเป็นต้องติดตั้ง Microsoft Office บนเครื่อง
### ฉันสามารถหาเอกสารเพิ่มเติมเกี่ยวกับ Aspose.Slides สำหรับ Java ได้ที่ไหน
เอกสารรายละเอียดมีให้ [ที่นี่](https://reference-aspose.com/slides/java/).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}