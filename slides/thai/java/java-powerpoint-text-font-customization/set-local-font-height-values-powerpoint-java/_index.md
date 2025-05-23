---
"description": "เรียนรู้วิธีการปรับความสูงของแบบอักษรในงานนำเสนอ PowerPoint โดยใช้ Java กับ Aspose.Slides ปรับปรุงการจัดรูปแบบข้อความในสไลด์ของคุณได้อย่างง่ายดาย"
"linktitle": "ตั้งค่าความสูงของฟอนต์ท้องถิ่นใน PowerPoint โดยใช้ Java"
"second_title": "API การประมวลผล Java PowerPoint ของ Aspose.Slides"
"title": "ตั้งค่าความสูงของฟอนต์ท้องถิ่นใน PowerPoint โดยใช้ Java"
"url": "/th/java/java-powerpoint-text-font-customization/set-local-font-height-values-powerpoint-java/"
"weight": 17
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# ตั้งค่าความสูงของฟอนต์ท้องถิ่นใน PowerPoint โดยใช้ Java

## การแนะนำ
ในบทช่วยสอนนี้ คุณจะได้เรียนรู้วิธีการจัดการความสูงของแบบอักษรในระดับต่างๆ ในงานนำเสนอ PowerPoint โดยใช้ Aspose.Slides สำหรับ Java การควบคุมขนาดแบบอักษรเป็นสิ่งสำคัญสำหรับการสร้างงานนำเสนอที่ดึงดูดสายตาและมีโครงสร้างที่ชัดเจน เราจะแนะนำตัวอย่างทีละขั้นตอนเพื่ออธิบายวิธีตั้งค่าความสูงของแบบอักษรสำหรับองค์ประกอบข้อความต่างๆ
## ข้อกำหนดเบื้องต้น
ก่อนที่คุณจะเริ่มต้น ให้แน่ใจว่าคุณมีสิ่งต่อไปนี้:
- ติดตั้ง Java Development Kit (JDK) บนระบบของคุณ
- Aspose.Slides สำหรับไลบรารี Java คุณสามารถดาวน์โหลดได้ [ที่นี่](https://releases-aspose.com/slides/java/).
- ความเข้าใจพื้นฐานเกี่ยวกับการเขียนโปรแกรม Java และการนำเสนอ PowerPoint
## แพ็คเกจนำเข้า
อย่าลืมรวมแพ็กเกจ Aspose.Slides ที่จำเป็นไว้ในไฟล์ Java ของคุณ:
```java
import com.aspose.slides.*;
```
## ขั้นตอนที่ 1: เริ่มต้นวัตถุการนำเสนอ
ขั้นแรก ให้สร้างวัตถุการนำเสนอ PowerPoint ใหม่:
```java
Presentation pres = new Presentation();
```
## ขั้นตอนที่ 2: เพิ่มกรอบรูปร่างและข้อความ
เพิ่มรูปร่างอัตโนมัติพร้อมกรอบข้อความลงในสไลด์แรก:
```java
IAutoShape newShape = pres.getSlides().get_Item(0).getShapes().addAutoShape(ShapeType.Rectangle, 100, 100, 400, 75, false);
newShape.addTextFrame("");
```
## ขั้นตอนที่ 3: สร้างส่วนข้อความ
กำหนดส่วนข้อความที่มีความสูงของตัวอักษรต่างกัน:
```java
IPortion portion0 = new Portion("Sample text with first portion");
IPortion portion1 = new Portion(" and second portion.");
newShape.getTextFrame().getParagraphs().get_Item(0).getPortions().add(portion0);
newShape.getTextFrame().getParagraphs().get_Item(0).getPortions().add(portion1);
```
## ขั้นตอนที่ 4: ตั้งค่าความสูงของแบบอักษร
ตั้งค่าความสูงของแบบอักษรในระดับที่แตกต่างกัน:
```java
pres.getDefaultTextStyle().getLevel(0).getDefaultPortionFormat().setFontHeight(24);
newShape.getTextFrame().getParagraphs().get_Item(0).getParagraphFormat().getDefaultPortionFormat().setFontHeight(40);
newShape.getTextFrame().getParagraphs().get_Item(0).getPortions().get_Item(0).getPortionFormat().setFontHeight(55);
newShape.getTextFrame().getParagraphs().get_Item(0).getPortions().get_Item(1).getPortionFormat().setFontHeight(18);
```
## ขั้นตอนที่ 5: บันทึกการนำเสนอ
บันทึกการนำเสนอที่แก้ไขแล้วลงในไฟล์:
```java
pres.save("YourOutputDirectory/SetLocalFontHeightValues.pptx", SaveFormat.Pptx);
```

## บทสรุป
บทช่วยสอนนี้สาธิตวิธีการปรับความสูงของแบบอักษรภายในสไลด์ PowerPoint โดยใช้โปรแกรม Aspose.Slides สำหรับ Java คุณสามารถควบคุมการจัดรูปแบบข้อความในงานนำเสนอได้อย่างแม่นยำโดยปรับขนาดแบบอักษรในระดับต่างๆ (ทั้งงานนำเสนอ ย่อหน้า และส่วนต่างๆ)
## คำถามที่พบบ่อย
### Aspose.Slides สำหรับ Java คืออะไร?
Aspose.Slides สำหรับ Java เป็น API อันทรงพลังสำหรับการจัดการการนำเสนอ PowerPoint ด้วยโปรแกรม
### ฉันสามารถหาเอกสารสำหรับ Aspose.Slides สำหรับ Java ได้ที่ไหน
คุณสามารถค้นหาเอกสารประกอบได้ [ที่นี่](https://reference-aspose.com/slides/java/).
### ฉันสามารถทดลองใช้ Aspose.Slides สำหรับ Java ก่อนซื้อได้หรือไม่
ใช่ คุณสามารถรับการทดลองใช้ฟรีได้ [ที่นี่](https://releases-aspose.com/).
### ฉันจะได้รับการสนับสนุนสำหรับ Aspose.Slides สำหรับ Java ได้อย่างไร
หากต้องการความช่วยเหลือ โปรดไปที่ [ฟอรั่ม Aspose.Slides](https://forum-aspose.com/c/slides/11).
### ฉันสามารถซื้อใบอนุญาตสำหรับ Aspose.Slides สำหรับ Java ได้ที่ไหน
คุณสามารถซื้อใบอนุญาตได้ [ที่นี่](https://purchase-aspose.com/buy).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}