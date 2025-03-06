---
title: เพิ่มกล่องข้อความบนสไลด์โดยทางโปรแกรมด้วย Java
linktitle: เพิ่มกล่องข้อความบนสไลด์โดยทางโปรแกรมด้วย Java
second_title: Aspose.Slides Java PowerPoint การประมวลผล API
description: เรียนรู้วิธีเพิ่มกล่องข้อความลงในสไลด์ PowerPoint โดยใช้โปรแกรม Aspose.Slides สำหรับ Java ปรับปรุงประสิทธิภาพการผลิตของคุณด้วยคำแนะนำทีละขั้นตอนนี้
weight: 24
url: /th/java/java-powerpoint-text-font-customization/add-text-box-slide-programmatically-java/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

## การแนะนำ
การสร้างและจัดการงานนำเสนอ PowerPoint โดยทางโปรแกรมสามารถปรับปรุงเวิร์กโฟลว์จำนวนมาก ตั้งแต่การสร้างรายงานไปจนถึงการนำเสนออัตโนมัติ Aspose.Slides สำหรับ Java มอบ API อันทรงพลังที่ช่วยให้นักพัฒนาทำงานเหล่านี้ได้อย่างมีประสิทธิภาพ ในบทช่วยสอนนี้ เราจะแนะนำคุณตลอดขั้นตอนการเพิ่มกล่องข้อความลงในสไลด์โดยใช้ Aspose.Slides สำหรับ Java เมื่อสิ้นสุดบทช่วยสอนนี้ คุณจะมีความเข้าใจที่ชัดเจนเกี่ยวกับวิธีการรวมฟังก์ชันนี้เข้ากับแอปพลิเคชัน Java ของคุณ
## ข้อกำหนดเบื้องต้น
ก่อนที่เราจะเริ่ม ตรวจสอบให้แน่ใจว่าคุณมีสิ่งต่อไปนี้:
- ติดตั้ง Java Development Kit (JDK) แล้ว
- IDE (สภาพแวดล้อมการพัฒนาแบบรวม) เช่น IntelliJ IDEA หรือ Eclipse
-  Aspose.Slides สำหรับไลบรารี Java คุณสามารถดาวน์โหลดได้จาก[ที่นี่](https://releases.aspose.com/slides/java/)
- ความรู้พื้นฐานเกี่ยวกับการเขียนโปรแกรม Java
## แพ็คเกจนำเข้า
ขั้นแรก นำเข้าแพ็คเกจที่จำเป็นจากไลบรารีหลักของ Aspose.Slides และ Java เพื่อเริ่มการเขียนโค้ด
```java
import com.aspose.slides.*;
import java.io.File;
```
## ขั้นตอนที่ 1: ตั้งค่าโครงการของคุณ
สร้างโปรเจ็กต์ Java ใหม่ใน IDE ของคุณ และเพิ่ม Aspose.Slides สำหรับไลบรารี Java ลงในพาธการ build ของโปรเจ็กต์ของคุณ หากยังไม่ได้ดาวน์โหลด สามารถหาได้จาก[ที่นี่](https://releases.aspose.com/slides/java/).
## ขั้นตอนที่ 2: เริ่มต้นวัตถุการนำเสนอ
 เริ่มต้นก`Presentation` วัตถุซึ่งแสดงถึงไฟล์ PowerPoint
```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
```
## ขั้นตอนที่ 3: เข้าถึงสไลด์และเพิ่มรูปร่างอัตโนมัติ
รับสไลด์แรกจากงานนำเสนอและเพิ่มรูปร่างอัตโนมัติ (สี่เหลี่ยมผืนผ้า) ลงไป
```java
ISlide slide = pres.getSlides().get_Item(0);
IAutoShape shape = slide.getShapes().addAutoShape(ShapeType.Rectangle, 150, 75, 150, 50);
```
## ขั้นตอนที่ 4: เพิ่มกรอบข้อความในรูปร่างอัตโนมัติ
เพิ่มกรอบข้อความให้กับรูปร่างอัตโนมัติเพื่อเก็บข้อความ
```java
shape.addTextFrame(" ");
ITextFrame textFrame = shape.getTextFrame();
```
## ขั้นตอนที่ 5: ตั้งค่าเนื้อหาข้อความ
ตั้งค่าเนื้อหาข้อความภายในกรอบข้อความ
```java
IParagraph para = textFrame.getParagraphs().get_Item(0);
IPortion portion = para.getPortions().get_Item(0);
portion.setText("Aspose TextBox");
```
## ขั้นตอนที่ 6: บันทึกการนำเสนอ
บันทึกงานนำเสนอที่แก้ไขแล้วลงในไฟล์
```java
pres.save(dataDir + "TextBox_out.pptx", SaveFormat.Pptx);
```

## บทสรุป
ในบทช่วยสอนนี้ เราได้สำรวจวิธีการเพิ่มกล่องข้อความลงในสไลด์โดยใช้โปรแกรม Aspose.Slides สำหรับ Java ความสามารถนี้ช่วยให้นักพัฒนาสามารถสร้างและปรับแต่งงานนำเสนอ PowerPoint ได้โดยอัตโนมัติ เพิ่มประสิทธิภาพและประสิทธิภาพในแอปพลิเคชันต่างๆ
## คำถามที่พบบ่อย
### Aspose.Slides สำหรับ Java สามารถจัดการรูปร่างอื่นนอกเหนือจากสี่เหลี่ยมได้หรือไม่
ใช่ Aspose.Slides รองรับรูปร่างต่างๆ เช่น วงกลม เส้น และอื่นๆ
### Aspose.Slides สำหรับ Java เหมาะสำหรับแอปพลิเคชันระดับองค์กรขนาดใหญ่หรือไม่
ได้รับการออกแบบมาเพื่อจัดการงานที่ซับซ้อนได้อย่างมีประสิทธิภาพอย่างแน่นอน
### ฉันจะหาตัวอย่างและเอกสารประกอบเพิ่มเติมสำหรับ Aspose.Slides ได้ที่ไหน
 เยี่ยมชม[เอกสาร Aspose.Slides](https://reference.aspose.com/slides/java/) สำหรับคำแนะนำและตัวอย่างที่ครอบคลุม
### ฉันจะรับใบอนุญาตชั่วคราวสำหรับการทดสอบได้อย่างไร
 คุณสามารถรับก[ใบอนุญาตชั่วคราว](https://purchase.aspose.com/temporary-license/) จากแอสโพส.
### Aspose.Slides รองรับการแปลงงานนำเสนอเป็นรูปแบบอื่นหรือไม่
ใช่ รองรับรูปแบบต่างๆ รวมถึง PDF และรูปภาพ
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
