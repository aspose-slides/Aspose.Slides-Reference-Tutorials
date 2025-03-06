---
title: หมุนข้อความใน PowerPoint โดยใช้ Java
linktitle: หมุนข้อความใน PowerPoint โดยใช้ Java
second_title: Aspose.Slides Java PowerPoint การประมวลผล API
description: เรียนรู้วิธีการหมุนข้อความใน PowerPoint โดยใช้ Java กับ Aspose.Slides บทช่วยสอนทีละขั้นตอนสำหรับผู้เริ่มต้นถึงผู้ใช้ขั้นสูง
weight: 10
url: /th/java/java-powerpoint-text-font-customization/rotate-text-powerpoint-java/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# หมุนข้อความใน PowerPoint โดยใช้ Java

## การแนะนำ
ในบทช่วยสอนนี้ เราจะสำรวจวิธีการหมุนข้อความในงานนำเสนอ PowerPoint โดยทางโปรแกรมโดยใช้ Java และ Aspose.Slides การหมุนข้อความอาจเป็นคุณสมบัติที่มีประโยชน์เมื่อออกแบบสไลด์เพื่อสร้างงานนำเสนอที่ดึงดูดสายตา
## ข้อกำหนดเบื้องต้น
ก่อนที่เราจะเริ่ม ตรวจสอบให้แน่ใจว่าคุณมีสิ่งต่อไปนี้:
- ความรู้พื้นฐานเกี่ยวกับภาษาการเขียนโปรแกรม Java
- JDK ติดตั้งอยู่บนระบบของคุณ
-  Aspose.Slides สำหรับไลบรารี Java คุณสามารถดาวน์โหลดได้จาก[ที่นี่](https://releases.aspose.com/slides/java/).
- IDE (Integrated Development Environment) เช่น IntelliJ IDEA หรือ Eclipse ที่ตั้งค่าไว้บนเครื่องของคุณ
## แพ็คเกจนำเข้า
ประการแรก คุณต้องนำเข้าคลาส Aspose.Slides ที่จำเป็นเพื่อทำงานกับไฟล์ PowerPoint ใน Java:
```java
import com.aspose.slides.*;
import java.awt.*;
```
## ขั้นตอนที่ 1: ตั้งค่าโครงการของคุณ
เริ่มต้นด้วยการสร้างโปรเจ็กต์ Java ใหม่ใน IDE ของคุณ และเพิ่มไฟล์ JAR ของ Aspose.Slides ลงในพาธการ build ของโปรเจ็กต์ของคุณ
## ขั้นตอนที่ 2: เริ่มต้นการนำเสนอและวัตถุสไลด์
```java
// เส้นทางไปยังไดเร็กทอรีที่คุณต้องการบันทึกงานนำเสนอ
String dataDir = "Your_Document_Directory/";
// สร้างอินสแตนซ์ของคลาสการนำเสนอ
Presentation presentation = new Presentation();
// รับสไลด์แรก
ISlide slide = presentation.getSlides().get_Item(0);
```
## ขั้นตอนที่ 3: เพิ่มรูปร่างสี่เหลี่ยมผืนผ้า
```java
// เพิ่มประเภทสี่เหลี่ยมผืนผ้ารูปร่างอัตโนมัติ
IAutoShape ashp = slide.getShapes().addAutoShape(ShapeType.Rectangle, 150, 75, 350, 350);
```
## ขั้นตอนที่ 4: เพิ่มข้อความลงในรูปร่างสี่เหลี่ยมผืนผ้า
```java
// เพิ่ม TextFrame ให้กับสี่เหลี่ยมผืนผ้า
ashp.addTextFrame(" ");
ashp.getFillFormat().setFillType(FillType.NoFill);
// การเข้าถึงกรอบข้อความ
ITextFrame txtFrame = ashp.getTextFrame();
txtFrame.getTextFrameFormat().setTextVerticalType(TextVerticalType.Vertical270);
```
## ขั้นตอนที่ 5: ตั้งค่าเนื้อหาข้อความและการจัดรูปแบบ
```java
// สร้างวัตถุย่อหน้าสำหรับกรอบข้อความ
IParagraph para = txtFrame.getParagraphs().get_Item(0);
// สร้างวัตถุส่วนสำหรับย่อหน้า
IPortion portion = para.getPortions().get_Item(0);
portion.setText("A quick brown fox jumps over the lazy dog. A quick brown fox jumps over the lazy dog.");
portion.getPortionFormat().getFillFormat().setFillType(FillType.Solid);
portion.getPortionFormat().getFillFormat().getSolidFillColor().setColor(Color.BLACK);
```
## ขั้นตอนที่ 6: บันทึกการนำเสนอ
```java
// บันทึกการนำเสนอ
presentation.save(dataDir + "RotateText_out.pptx", SaveFormat.Pptx);
```

## บทสรุป
ในบทช่วยสอนนี้ เราได้เรียนรู้วิธีหมุนข้อความในงานนำเสนอ PowerPoint โดยใช้ Java และ Aspose.Slides ด้วยการทำตามขั้นตอนเหล่านี้ คุณสามารถจัดการการวางแนวข้อความในสไลด์ของคุณแบบไดนามิกเพื่อเพิ่มผลกระทบทางภาพได้
## คำถามที่พบบ่อย
### ฉันสามารถหมุนข้อความไปที่มุมใดก็ได้ใน PowerPoint โดยใช้ Aspose.Slides สำหรับ Java ได้หรือไม่
ได้ คุณสามารถระบุมุมที่ต้องการสำหรับการหมุนข้อความโดยทางโปรแกรมได้
### Aspose.Slides รองรับตัวเลือกการจัดรูปแบบข้อความอื่นๆ เช่น ขนาดตัวอักษรและการจัดแนวหรือไม่
แน่นอนว่า Aspose.Slides มี API ที่ครอบคลุมเพื่อรองรับข้อกำหนดการจัดรูปแบบข้อความที่หลากหลาย
### ฉันจะเริ่มต้นใช้งาน Aspose.Slides สำหรับ Java ได้อย่างไร
 คุณสามารถดาวน์โหลด Aspose.Slides รุ่นทดลองใช้ฟรีได้จาก[ที่นี่](https://releases.aspose.com/) เพื่อสำรวจคุณลักษณะต่างๆ
### ฉันจะหาเอกสารและการสนับสนุนเพิ่มเติมสำหรับ Aspose.Slides ได้ที่ไหน
 สำหรับเอกสารโดยละเอียด โปรดไปที่[Aspose.Slides สำหรับเอกสาร Java](https://reference.aspose.com/slides/java/) - คุณยังสามารถรับการสนับสนุนจากชุมชนได้ที่[ฟอรั่ม Aspose.Slides](https://forum.aspose.com/c/slides/11).
### ฉันจะขอรับใบอนุญาตชั่วคราวสำหรับ Aspose.Slides ได้อย่างไร
 คุณสามารถขอรับใบอนุญาตชั่วคราวได้จาก[ที่นี่](https://purchase.aspose.com/temporary-license/)เพื่อประเมิน Aspose.Slides โดยไม่มีข้อจำกัด
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
