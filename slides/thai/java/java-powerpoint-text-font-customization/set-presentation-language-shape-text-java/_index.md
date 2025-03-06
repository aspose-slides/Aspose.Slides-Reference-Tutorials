---
title: ตั้งค่าภาษาการนำเสนอและข้อความรูปร่างใน Java
linktitle: ตั้งค่าภาษาการนำเสนอและข้อความรูปร่างใน Java
second_title: Aspose.Slides Java PowerPoint การประมวลผล API
description: เรียนรู้วิธีการนำเสนอ PowerPoint อัตโนมัติโดยใช้ Aspose.Slides สำหรับ Java สร้าง แก้ไข และปรับปรุงสไลด์โดยทางโปรแกรมได้อย่างง่ายดาย
type: docs
weight: 19
url: /th/java/java-powerpoint-text-font-customization/set-presentation-language-shape-text-java/
---
## การแนะนำ
การสร้างและจัดการงานนำเสนอ PowerPoint โดยทางโปรแกรมใน Java สามารถปรับปรุงเวิร์กโฟลว์อัตโนมัติและปรับปรุงประสิทธิภาพการทำงานได้ Aspose.Slides สำหรับ Java มอบชุดเครื่องมือที่มีประสิทธิภาพเพื่อให้บรรลุงานเหล่านี้ได้อย่างมีประสิทธิภาพ บทช่วยสอนนี้จะแนะนำคุณตลอดขั้นตอนสำคัญในการตั้งค่าภาษาการนำเสนอและรูปร่างข้อความโดยใช้ Aspose.Slides สำหรับ Java
## ข้อกำหนดเบื้องต้น
ก่อนที่จะเข้าสู่บทช่วยสอน ตรวจสอบให้แน่ใจว่าคุณมีสิ่งต่อไปนี้:
- ติดตั้ง Java Development Kit (JDK) แล้ว
-  Aspose.Slides สำหรับไลบรารี Java ซึ่งคุณสามารถดาวน์โหลดได้[ที่นี่](https://releases.aspose.com/slides/java/)
- สภาพแวดล้อมการพัฒนาแบบรวม (IDE) เช่น IntelliJ IDEA หรือ Eclipse ที่ตั้งค่าบนระบบของคุณ
- ความรู้พื้นฐานเกี่ยวกับภาษาการเขียนโปรแกรม Java
## แพ็คเกจนำเข้า
ในการเริ่มต้น ให้นำเข้าแพ็คเกจ Aspose.Slides ที่จำเป็นในไฟล์ Java ของคุณ:
```java
import com.aspose.slides.IAutoShape;
import com.aspose.slides.Presentation;
import com.aspose.slides.SaveFormat;
import com.aspose.slides.ShapeType;
```
## ขั้นตอนที่ 1: สร้างวัตถุการนำเสนอ
 เริ่มต้นด้วยการเริ่มต้น a`Presentation` วัตถุ:
```java
Presentation pres = new Presentation();
```
สิ่งนี้จะสร้างงานนำเสนอ PowerPoint ใหม่
## ขั้นตอนที่ 2: เพิ่มและกำหนดค่ารูปร่างอัตโนมัติ
ถัดไป เพิ่มรูปร่างอัตโนมัติให้กับสไลด์แรกและกำหนดค่าคุณสมบัติ:
```java
ISlide slide = pres.getSlides().get_Item(0);
IAutoShape shape = slide.getShapes().addAutoShape(ShapeType.Rectangle, 50, 50, 200, 50);
```
ที่นี่ เราเพิ่มรูปร่างอัตโนมัติรูปสี่เหลี่ยมผืนผ้าที่พิกัด (50, 50) โดยมีขนาด 200x50 พิกเซล
## ขั้นตอนที่ 3: ตั้งค่าข้อความและภาษา
ตั้งค่าเนื้อหาข้อความและระบุภาษาสำหรับการตรวจตัวสะกด:
```java
shape.addTextFrame("Text to apply spellcheck language");
shape.getTextFrame().getParagraphs().get_Item(0).getPortions().get_Item(0).getPortionFormat().setLanguageId("en-EN");
```
 แทนที่`"Text to apply spellcheck language"` พร้อมข้อความที่คุณต้องการ รหัสภาษา`"en-EN"`ระบุภาษาอังกฤษ (สหรัฐอเมริกา)
## ขั้นตอนที่ 4: บันทึกการนำเสนอ
บันทึกการนำเสนอที่แก้ไขไปยังไดเร็กทอรีเอาต์พุตที่ระบุ:
```java
pres.save("Your Output Directory" + "test1.pptx", SaveFormat.Pptx);
```
 ให้แน่ใจว่าจะเปลี่ยน`"Your Output Directory"` ด้วยเส้นทางไดเรกทอรีจริงของคุณที่คุณต้องการบันทึกไฟล์
## ขั้นตอนที่ 5: กำจัดทรัพยากร
 กำจัดทิ้งอย่างเหมาะสม`Presentation` คัดค้านการปล่อยทรัพยากร:
```java
pres.dispose();
```
ขั้นตอนนี้มีความสำคัญอย่างยิ่งในการหลีกเลี่ยงการรั่วไหลของหน่วยความจำ

## บทสรุป
โดยสรุป Aspose.Slides สำหรับ Java ช่วยให้กระบวนการสร้างและจัดการงานนำเสนอ PowerPoint โดยทางโปรแกรมง่ายขึ้น ด้วยการทำตามขั้นตอนเหล่านี้ คุณสามารถตั้งค่าภาษาของการนำเสนอและกำหนดค่าคุณสมบัติข้อความตามความต้องการของคุณได้อย่างมีประสิทธิภาพ
## คำถามที่พบบ่อย
### ฉันสามารถใช้ Aspose.Slides สำหรับ Java เพื่อสร้างงานนำเสนอ PowerPoint ตั้งแต่เริ่มต้นได้หรือไม่
ใช่ Aspose.Slides มี API ที่ครอบคลุมเพื่อสร้างการนำเสนอโดยทางโปรแกรมทั้งหมด
### ฉันจะใช้แบบอักษรที่แตกต่างกันกับข้อความในสไลด์ PowerPoint โดยใช้ Aspose.Slides สำหรับ Java ได้อย่างไร
 คุณสามารถตั้งค่าคุณสมบัติแบบอักษรผ่าน`IPortionFormat` วัตถุที่เกี่ยวข้องกับส่วนข้อความ
### มีรุ่นทดลองใช้งานสำหรับ Aspose.Slides สำหรับ Java หรือไม่
 ใช่ คุณสามารถทดลองใช้ฟรีได้จาก[ที่นี่](https://releases.aspose.com/).
### ฉันจะหาเอกสารประกอบสำหรับ Aspose.Slides สำหรับ Java ได้ที่ไหน
 มีเอกสารรายละเอียดให้[ที่นี่](https://reference.aspose.com/slides/java/).
### ตัวเลือกการสนับสนุนใดบ้างสำหรับ Aspose.Slides สำหรับ Java
 คุณสามารถเยี่ยมชมฟอรัม Aspose.Slides[ที่นี่](https://forum.aspose.com/c/slides/11) เพื่อสนับสนุนชุมชน