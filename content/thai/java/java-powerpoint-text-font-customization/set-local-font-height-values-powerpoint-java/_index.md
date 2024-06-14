---
title: ตั้งค่าความสูงของแบบอักษรในเครื่องใน PowerPoint โดยใช้ Java
linktitle: ตั้งค่าความสูงของแบบอักษรในเครื่องใน PowerPoint โดยใช้ Java
second_title: Aspose.Slides Java PowerPoint การประมวลผล API
description: เรียนรู้วิธีปรับความสูงของแบบอักษรในงานนำเสนอ PowerPoint โดยใช้ Java กับ Aspose.Slides ปรับปรุงการจัดรูปแบบข้อความในสไลด์ของคุณได้อย่างง่ายดาย
type: docs
weight: 17
url: /th/java/java-powerpoint-text-font-customization/set-local-font-height-values-powerpoint-java/
---
## การแนะนำ
ในบทช่วยสอนนี้ คุณจะได้เรียนรู้วิธีจัดการความสูงของแบบอักษรในระดับต่างๆ ภายในงานนำเสนอ PowerPoint โดยใช้ Aspose.Slides สำหรับ Java การควบคุมขนาดตัวอักษรเป็นสิ่งสำคัญสำหรับการสร้างงานนำเสนอที่ดึงดูดสายตาและมีโครงสร้าง เราจะอธิบายตัวอย่างทีละขั้นตอนเพื่อแสดงวิธีตั้งค่าความสูงของแบบอักษรสำหรับองค์ประกอบข้อความต่างๆ
## ข้อกำหนดเบื้องต้น
ก่อนที่คุณจะเริ่มต้น ตรวจสอบให้แน่ใจว่าคุณมีสิ่งต่อไปนี้:
- ติดตั้ง Java Development Kit (JDK) บนระบบของคุณ
-  Aspose.Slides สำหรับไลบรารี Java คุณสามารถดาวน์โหลดได้[ที่นี่](https://releases.aspose.com/slides/java/).
- ความเข้าใจพื้นฐานเกี่ยวกับการเขียนโปรแกรม Java และการนำเสนอ PowerPoint
## แพ็คเกจนำเข้า
ตรวจสอบให้แน่ใจว่าได้รวมแพ็คเกจ Aspose.Slides ที่จำเป็นไว้ในไฟล์ Java ของคุณ:
```java
import com.aspose.slides.*;
```
## ขั้นตอนที่ 1: เริ่มต้นวัตถุการนำเสนอ
ขั้นแรก สร้างวัตถุการนำเสนอ PowerPoint ใหม่:
```java
Presentation pres = new Presentation();
```
## ขั้นตอนที่ 2: เพิ่มรูปร่างและกรอบข้อความ
เพิ่มรูปร่างอัตโนมัติพร้อมกรอบข้อความลงในสไลด์แรก:
```java
IAutoShape newShape = pres.getSlides().get_Item(0).getShapes().addAutoShape(ShapeType.Rectangle, 100, 100, 400, 75, false);
newShape.addTextFrame("");
```
## ขั้นตอนที่ 3: สร้างส่วนข้อความ
กำหนดส่วนข้อความด้วยความสูงของแบบอักษรที่แตกต่างกัน:
```java
IPortion portion0 = new Portion("Sample text with first portion");
IPortion portion1 = new Portion(" and second portion.");
newShape.getTextFrame().getParagraphs().get_Item(0).getPortions().add(portion0);
newShape.getTextFrame().getParagraphs().get_Item(0).getPortions().add(portion1);
```
## ขั้นตอนที่ 4: ตั้งค่าความสูงของแบบอักษร
ตั้งค่าความสูงของแบบอักษรในระดับต่างๆ:
```java
pres.getDefaultTextStyle().getLevel(0).getDefaultPortionFormat().setFontHeight(24);
newShape.getTextFrame().getParagraphs().get_Item(0).getParagraphFormat().getDefaultPortionFormat().setFontHeight(40);
newShape.getTextFrame().getParagraphs().get_Item(0).getPortions().get_Item(0).getPortionFormat().setFontHeight(55);
newShape.getTextFrame().getParagraphs().get_Item(0).getPortions().get_Item(1).getPortionFormat().setFontHeight(18);
```
## ขั้นตอนที่ 5: บันทึกการนำเสนอ
บันทึกงานนำเสนอที่แก้ไขแล้วลงในไฟล์:
```java
pres.save("YourOutputDirectory/SetLocalFontHeightValues.pptx", SaveFormat.Pptx);
```

## บทสรุป
บทช่วยสอนนี้สาธิตวิธีการปรับความสูงของแบบอักษรภายในสไลด์ PowerPoint โดยทางโปรแกรมโดยใช้ Aspose.Slides สำหรับ Java ด้วยการจัดการขนาดแบบอักษรในระดับต่างๆ (ทั่วทั้งงานนำเสนอ ย่อหน้า และส่วน) คุณสามารถควบคุมการจัดรูปแบบข้อความในงานนำเสนอของคุณได้อย่างแม่นยำ
## คำถามที่พบบ่อย
### Aspose.Slides สำหรับ Java คืออะไร
Aspose.Slides สำหรับ Java เป็น API ที่ทรงพลังสำหรับจัดการงานนำเสนอ PowerPoint โดยทางโปรแกรม
### ฉันจะหาเอกสารประกอบสำหรับ Aspose.Slides สำหรับ Java ได้ที่ไหน
 คุณสามารถค้นหาเอกสาร[ที่นี่](https://reference.aspose.com/slides/java/).
### ฉันสามารถลองใช้ Aspose.Slides สำหรับ Java ก่อนซื้อได้หรือไม่
 ใช่ คุณสามารถทดลองใช้ฟรีได้[ที่นี่](https://releases.aspose.com/).
### ฉันจะรับการสนับสนุนสำหรับ Aspose.Slides สำหรับ Java ได้อย่างไร
 สำหรับการสนับสนุนโปรดไปที่[ฟอรั่ม Aspose.Slides](https://forum.aspose.com/c/slides/11).
### ฉันจะซื้อใบอนุญาตสำหรับ Aspose.Slides สำหรับ Java ได้ที่ไหน
 คุณสามารถซื้อใบอนุญาตได้[ที่นี่](https://purchase.aspose.com/buy).