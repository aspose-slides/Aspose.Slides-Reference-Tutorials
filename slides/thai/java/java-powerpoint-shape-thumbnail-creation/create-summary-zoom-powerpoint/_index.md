---
title: สร้างการซูมสรุปใน PowerPoint
linktitle: สร้างการซูมสรุปใน PowerPoint
second_title: Aspose.Slides Java PowerPoint การประมวลผล API
description: เรียนรู้วิธีสร้างการซูมสรุปใน PowerPoint โดยใช้ Aspose.Slides สำหรับ Java ด้วยบทช่วยสอนแบบทีละขั้นตอนที่ครอบคลุมนี้
weight: 16
url: /th/java/java-powerpoint-shape-thumbnail-creation/create-summary-zoom-powerpoint/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

## การแนะนำ
ยินดีต้อนรับสู่บทช่วยสอนที่ครอบคลุมของเราเกี่ยวกับการสร้างการซูมสรุปใน PowerPoint โดยใช้ Aspose.Slides สำหรับ Java หากคุณต้องการเพิ่มองค์ประกอบแบบไดนามิกและโต้ตอบให้กับงานนำเสนอของคุณ Summary Zoom ถือเป็นคุณสมบัติที่ยอดเยี่ยม ช่วยให้คุณสร้างสไลด์เดียวที่สามารถซูมเข้าไปในส่วนต่างๆ ของงานนำเสนอของคุณ มอบประสบการณ์ที่น่าดึงดูดและนำทางได้มากขึ้นสำหรับผู้ชมของคุณ
ในคำแนะนำทีละขั้นตอนนี้ เราจะแนะนำคุณตลอดกระบวนการทั้งหมด ตั้งแต่การตั้งค่าสภาพแวดล้อมการพัฒนาไปจนถึงการสร้างและปรับแต่งเฟรมการซูมสรุป ไม่ว่าคุณจะเป็นนักพัฒนา Java ที่มีประสบการณ์หรือเพิ่งเริ่มต้น คุณจะพบว่าคู่มือนี้ง่ายต่อการปฏิบัติตามและอัดแน่นไปด้วยข้อมูลเชิงลึกอันมีค่า
## ข้อกำหนดเบื้องต้น
ก่อนที่จะเจาะลึกโค้ด โปรดตรวจสอบให้แน่ใจว่าคุณมีทุกสิ่งที่จำเป็นในการเริ่มต้น:
1.  Java Development Kit (JDK): ตรวจสอบให้แน่ใจว่าคุณได้ติดตั้ง JDK บนเครื่องของคุณแล้ว คุณสามารถดาวน์โหลดได้จาก[เว็บไซต์ออราเคิล](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html).
2.  Aspose.Slides สำหรับ Java: ดาวน์โหลดไลบรารีจาก[กำหนดหน้าการเผยแพร่](https://releases.aspose.com/slides/java/).
3. สภาพแวดล้อมการพัฒนาแบบรวม (IDE): ใช้ IDE เช่น IntelliJ IDEA, Eclipse หรือ NetBeans เพื่อประสบการณ์การพัฒนาที่ราบรื่นยิ่งขึ้น
4. ความรู้พื้นฐานของ Java: ความคุ้นเคยกับแนวคิดการเขียนโปรแกรม Java จะช่วยให้คุณเข้าใจและดำเนินการตามขั้นตอนในคู่มือนี้
## แพ็คเกจนำเข้า
ก่อนที่เราจะเริ่ม คุณต้องนำเข้าแพ็คเกจที่จำเป็นก่อน ตรวจสอบให้แน่ใจว่าคุณได้รวม Aspose.Slides สำหรับ Java ไว้ในการอ้างอิงโปรเจ็กต์ของคุณ
```java
import com.aspose.slides.*;

import java.awt.*;
```
## ขั้นตอนที่ 1: ตั้งค่าโครงการของคุณ
ขั้นแรก ตรวจสอบให้แน่ใจว่าสภาพแวดล้อมการพัฒนาของคุณได้รับการตั้งค่าอย่างถูกต้อง ทำตามขั้นตอนเหล่านี้เพื่อกำหนดค่าโครงการของคุณ:
### สร้างโครงการใหม่
1. เปิด IDE ของคุณ
2. สร้างโปรเจ็กต์ Java ใหม่
3.  เพิ่มไลบรารี Aspose.Slides สำหรับ Java ลงในเส้นทางการ build ของโปรเจ็กต์ของคุณ คุณสามารถดาวน์โหลดไฟล์ JAR ได้จากไฟล์[กำหนดหน้าการเผยแพร่](https://releases.aspose.com/slides/java/) และรวมไว้ในโครงการของคุณ
### เริ่มต้นการนำเสนอ
จากนั้น เริ่มต้นวัตถุการนำเสนอใหม่ที่คุณจะเพิ่มสไลด์และส่วนต่างๆ ของคุณ
```java
Presentation pres = new Presentation();
```
## ขั้นตอนที่ 2: เพิ่มสไลด์และส่วนต่างๆ
ในขั้นตอนนี้ เราจะเพิ่มสไลด์ลงในงานนำเสนอและจัดระเบียบเป็นส่วนต่างๆ องค์กรนี้มีความสำคัญอย่างยิ่งต่อการสร้างการซูมสรุป
### เพิ่มสไลด์ใหม่และส่วน
1. เพิ่มสไลด์เปล่า: เพิ่มสไลด์ใหม่ลงในงานนำเสนอ
2. ปรับแต่งพื้นหลังสไลด์: ตั้งค่าสีเติมทึบสำหรับพื้นหลังสไลด์
3. เพิ่มส่วน: จัดกลุ่มสไลด์เป็นส่วนๆ
นี่คือรหัสเพื่อให้บรรลุเป้าหมายนี้:
```java
// เพิ่มสไลด์แรก
ISlide slide = pres.getSlides().addEmptySlide(pres.getSlides().get_Item(0).getLayoutSlide());
slide.getBackground().getFillFormat().setFillType(FillType.Solid);
slide.getBackground().getFillFormat().getSolidFillColor().setColor(Color.GRAY);
slide.getBackground().setType(BackgroundType.OwnBackground);
// เพิ่มส่วนแรก
pres.getSections().addSection("Section 1", slide);
```
### ทำซ้ำสำหรับส่วนเพิ่มเติม
ทำซ้ำขั้นตอนนี้เพื่อเพิ่มสไลด์และส่วนต่างๆ:
```java
// เพิ่มสไลด์และส่วนที่สอง
slide = pres.getSlides().addEmptySlide(pres.getSlides().get_Item(0).getLayoutSlide());
slide.getBackground().getFillFormat().setFillType(FillType.Solid);
slide.getBackground().getFillFormat().getSolidFillColor().setColor(Color.CYAN);
slide.getBackground().setType(BackgroundType.OwnBackground);
pres.getSections().addSection("Section 2", slide);
// เพิ่มสไลด์และส่วนที่สาม
slide = pres.getSlides().addEmptySlide(pres.getSlides().get_Item(0).getLayoutSlide());
slide.getBackground().getFillFormat().setFillType(FillType.Solid);
slide.getBackground().getFillFormat().getSolidFillColor().setColor(Color.MAGENTA);
slide.getBackground().setType(BackgroundType.OwnBackground);
pres.getSections().addSection("Section 3", slide);
// เพิ่มสไลด์และส่วนที่สี่
slide = pres.getSlides().addEmptySlide(pres.getSlides().get_Item(0).getLayoutSlide());
slide.getBackground().getFillFormat().setFillType(FillType.Solid);
slide.getBackground().getFillFormat().getSolidFillColor().setColor(Color.GREEN);
slide.getBackground().setType(BackgroundType.OwnBackground);
pres.getSections().addSection("Section 4", slide);
```
## ขั้นตอนที่ 3: สร้างกรอบการซูมสรุป
ตอนนี้ เราจะสร้างกรอบการซูมสรุปบนสไลด์แรก เฟรมนี้จะทำหน้าที่เป็นองค์ประกอบเชิงโต้ตอบที่ช่วยให้ผู้ใช้สามารถซูมไปยังส่วนต่างๆ ได้

1. ค้นหาสไลด์แรก: ดึงสไลด์แรกที่คุณจะเพิ่มกรอบการซูมสรุป
2.  เพิ่มกรอบการซูมสรุป: ใช้`addSummaryZoomFrame` วิธีการเพิ่มเฟรม
```java
ISummaryZoomFrame summaryZoomFrame = pres.getSlides().get_Item(0).getShapes().addSummaryZoomFrame(150, 50, 300, 200);
```
## ขั้นตอนที่ 4: บันทึกการนำเสนอ
สุดท้าย บันทึกงานนำเสนอไปยังตำแหน่งที่คุณต้องการ ขั้นตอนนี้ช่วยให้แน่ใจว่าการเปลี่ยนแปลงทั้งหมดของคุณจะถูกเขียนลงในไฟล์
### บันทึกไฟล์
1. กำหนดเส้นทางเอาต์พุต: ระบุเส้นทางที่จะบันทึกการนำเสนอ
2.  บันทึกการนำเสนอ: ใช้`save` วิธีการบันทึกไฟล์ในรูปแบบ PPTX
```java
String resultPath = "Your Output Directory" + "SummaryZoomPresentation.pptx";
pres.save(resultPath, SaveFormat.Pptx);
```
### กำจัดวัตถุการนำเสนอ
กำจัดออบเจ็กต์การนำเสนอเพื่อเผยแพร่ทรัพยากรใดๆ ที่ใช้:
```java
if (pres != null) pres.dispose();
```
## บทสรุป
 ยินดีด้วย! คุณสร้างการซูมสรุปใน PowerPoint สำเร็จโดยใช้ Aspose.Slides สำหรับ Java คุณลักษณะนี้ปรับปรุงการนำเสนอของคุณโดยทำให้มีการโต้ตอบและมีส่วนร่วมมากขึ้น เมื่อทำตามคำแนะนำนี้ คุณจะมีทักษะในการใช้ฟีเจอร์นี้ในโครงการของคุณเอง อย่าลืมสำรวจ[Aspose.Slides สำหรับเอกสาร Java](https://reference.aspose.com/slides/java/)สำหรับคุณสมบัติขั้นสูงและตัวเลือกการปรับแต่งเพิ่มเติม
## คำถามที่พบบ่อย
### Aspose.Slides สำหรับ Java คืออะไร
Aspose.Slides สำหรับ Java เป็นไลบรารีอันทรงพลังที่ช่วยให้นักพัฒนาสามารถสร้าง แก้ไข และจัดการงานนำเสนอ PowerPoint โดยทางโปรแกรมโดยใช้ Java
### ฉันสามารถใช้ Aspose.Slides สำหรับ Java เพื่อสร้างเนื้อหาประเภทอื่นๆ ใน PowerPoint ได้หรือไม่
ใช่ Aspose.Slides สำหรับ Java รองรับคุณสมบัติที่หลากหลาย รวมถึงการสร้างสไลด์ การเพิ่มรูปร่าง แผนภูมิ ตาราง และอื่นๆ อีกมากมาย
### มีการทดลองใช้ฟรีสำหรับ Aspose.Slides สำหรับ Java หรือไม่
ใช่ คุณสามารถดาวน์โหลด Aspose.Slides สำหรับ Java รุ่นทดลองใช้ฟรีได้จาก[เว็บไซต์](https://releases.aspose.com/).
### ฉันจะรับใบอนุญาตชั่วคราวสำหรับ Aspose.Slides สำหรับ Java ได้อย่างไร
 คุณสามารถขอรับใบอนุญาตชั่วคราวได้จาก[กำหนดหน้าการซื้อ](https://purchase.aspose.com/temporary-license/).
### ฉันจะหาตัวอย่างเพิ่มเติมและการสนับสนุนสำหรับ Aspose.Slides สำหรับ Java ได้ที่ไหน
 คุณสามารถค้นหาตัวอย่างเพิ่มเติมและขอการสนับสนุนได้ที่[ฟอรั่มการสนับสนุน Aspose.Slides](https://forum.aspose.com/c/slides/11).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
