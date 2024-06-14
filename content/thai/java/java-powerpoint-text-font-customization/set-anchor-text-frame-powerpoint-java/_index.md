---
title: ตั้งค่า Anchor ของ Text Frame ใน PowerPoint ด้วย Java
linktitle: ตั้งค่า Anchor ของ Text Frame ใน PowerPoint ด้วย Java
second_title: Aspose.Slides Java PowerPoint การประมวลผล API
description: เรียนรู้วิธีการตั้งค่าจุดยึดกรอบข้อความใน PowerPoint โดยใช้ Java กับ Aspose.Slides ปรับปรุงการนำเสนอของคุณ
type: docs
weight: 13
url: /th/java/java-powerpoint-text-font-customization/set-anchor-text-frame-powerpoint-java/
---
## การแนะนำ
ในบทช่วยสอนนี้ คุณจะได้เรียนรู้วิธีการตั้งค่าจุดยึดของกรอบข้อความในงานนำเสนอ PowerPoint โดยใช้ Java ด้วยความช่วยเหลือของ Aspose.Slides การยึดกรอบข้อความช่วยให้คุณควบคุมตำแหน่งและพฤติกรรมของข้อความภายในรูปร่างได้อย่างแม่นยำ ทำให้มั่นใจได้ว่าสไลด์ของคุณจะดึงดูดสายตาและมีการจัดโครงสร้างอย่างมีประสิทธิภาพ
## ข้อกำหนดเบื้องต้น
ก่อนที่คุณจะเริ่มต้น ตรวจสอบให้แน่ใจว่าคุณมีข้อกำหนดเบื้องต้นต่อไปนี้:
- ติดตั้ง Java Development Kit (JDK) บนระบบของคุณ
-  Aspose.Slides สำหรับไลบรารี Java คุณสามารถดาวน์โหลดได้จาก[ที่นี่](https://releases.aspose.com/slides/java/)
- ความเข้าใจพื้นฐานเกี่ยวกับภาษาการเขียนโปรแกรม Java และแนวคิดเชิงวัตถุ
## แพ็คเกจนำเข้า
ในการเริ่มต้น ให้รวมไลบรารี Aspose.Slides ที่จำเป็นในโปรเจ็กต์ Java ของคุณ:
```java
import com.aspose.slides.*;
import java.awt.*;
```
## ขั้นตอนที่ 1: ตั้งค่าโครงการของคุณ
ตรวจสอบให้แน่ใจว่าคุณได้ตั้งค่าโปรเจ็กต์ Java ใน Integrated Development Environment (IDE) ที่คุณต้องการ ตรวจสอบให้แน่ใจว่าได้เพิ่มไฟล์ JAR ของ Aspose.Slides ลงในเส้นทางการ build ของโปรเจ็กต์ของคุณ
## ขั้นตอนที่ 2: สร้างวัตถุการนำเสนอ
```java
String dataDir = "Your Document Directory";
Presentation presentation = new Presentation();
```
นี่เป็นการเริ่มต้นวัตถุการนำเสนอ PowerPoint ใหม่
## ขั้นตอนที่ 3: เข้าถึงสไลด์และเพิ่มรูปร่าง
```java
ISlide slide = presentation.getSlides().get_Item(0);
IAutoShape ashp = slide.getShapes().addAutoShape(ShapeType.Rectangle, 150, 75, 350, 350);
```
ที่นี่ รูปร่างสี่เหลี่ยมผืนผ้าจะถูกเพิ่มลงในสไลด์ตามพิกัดและขนาดเฉพาะ
## ขั้นตอนที่ 4: เพิ่มกรอบข้อความให้กับรูปร่าง
```java
ashp.addTextFrame(" ");
ashp.getFillFormat().setFillType(FillType.NoFill);
ITextFrame txtFrame = ashp.getTextFrame();
txtFrame.getTextFrameFormat().setAnchoringType(TextAnchorType.Bottom);
```
 กรอบข้อความจะถูกเพิ่มให้กับรูปร่างสี่เหลี่ยมผืนผ้า และประเภทการยึดถูกตั้งค่าเป็น`Bottom`เพื่อให้แน่ใจว่าข้อความจะยึดอยู่ที่ด้านล่างของรูปร่าง
## ขั้นตอนที่ 5: แทรกข้อความลงในกรอบข้อความ
```java
IParagraph para = txtFrame.getParagraphs().get_Item(0);
IPortion portion = para.getPortions().get_Item(0);
portion.setText("A quick brown fox jumps over the lazy dog. A quick brown fox jumps over the lazy dog.");
portion.getPortionFormat().getFillFormat().setFillType(FillType.Solid);
portion.getPortionFormat().getFillFormat().getSolidFillColor().setColor(Color.BLACK);
```
ซึ่งจะเป็นการเพิ่มเนื้อหาข้อความลงในกรอบข้อความและปรับใช้การจัดรูปแบบ เช่น การตั้งค่าสีข้อความให้เป็นสีดำ
## ขั้นตอนที่ 6: บันทึกการนำเสนอ
```java
presentation.save(dataDir + "AnchorText_out.pptx", SaveFormat.Pptx);
```
สุดท้าย ให้บันทึกงานนำเสนอที่แก้ไขแล้วไปยังตำแหน่งที่ระบุบนดิสก์ของคุณ

## บทสรุป
การตั้งค่าจุดยึดของกรอบข้อความใน PowerPoint โดยใช้ Java เป็นสิ่งจำเป็นสำหรับการสร้างงานนำเสนอที่มีการจัดระเบียบอย่างดี ด้วยการทำตามขั้นตอนเหล่านี้และใช้ประโยชน์จาก Aspose.Slides สำหรับ Java คุณสามารถจัดการการวางตำแหน่งข้อความภายในรูปร่างได้อย่างมีประสิทธิภาพ เพื่อปรับปรุงรูปลักษณ์ที่น่าดึงดูดและความชัดเจนของสไลด์ของคุณ

## คำถามที่พบบ่อย
### Aspose.Slides สำหรับ Java คืออะไร
Aspose.Slides สำหรับ Java เป็นไลบรารีอันทรงพลังที่ช่วยให้นักพัฒนา Java สามารถสร้าง อ่าน จัดการ และแปลงงานนำเสนอ PowerPoint
### ฉันจะหาเอกสารสำหรับ Aspose.Slides สำหรับ Java ได้ที่ไหน
 คุณสามารถเข้าถึงเอกสารประกอบ[ที่นี่](https://reference.aspose.com/slides/java/).
### ฉันจะขอรับใบอนุญาตชั่วคราวสำหรับ Aspose.Slides สำหรับ Java ได้อย่างไร
 คุณสามารถรับใบอนุญาตชั่วคราวได้[ที่นี่](https://purchase.aspose.com/temporary-license/).
### ฉันสามารถลองใช้ Aspose.Slides สำหรับ Java ได้ฟรีหรือไม่
 ใช่ คุณสามารถดาวน์โหลดรุ่นทดลองใช้ฟรีได้[ที่นี่](https://releases.aspose.com/).
### ฉันจะรับการสนับสนุนสำหรับ Aspose.Slides สำหรับ Java ได้ที่ไหน
 คุณสามารถเยี่ยมชมฟอรั่มการสนับสนุน[ที่นี่](https://forum.aspose.com/c/slides/11) หากมีข้อสงสัยหรือความช่วยเหลือ