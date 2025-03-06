---
title: เพิ่มคอลัมน์ในกรอบข้อความโดยใช้ Aspose.Slides สำหรับ Java
linktitle: เพิ่มคอลัมน์ในกรอบข้อความโดยใช้ Aspose.Slides สำหรับ Java
second_title: Aspose.Slides Java PowerPoint การประมวลผล API
description: เรียนรู้วิธีเพิ่มคอลัมน์ในกรอบข้อความโดยใช้ Aspose.Slides สำหรับ Java เพื่อปรับปรุงงานนำเสนอ PowerPoint ของคุณ คำแนะนำทีละขั้นตอนของเราทำให้กระบวนการง่ายขึ้น
weight: 11
url: /th/java/java-powerpoint-text-box-manipulation/add-columns-in-text-frame/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

## การแนะนำ
ในบทช่วยสอนนี้ เราจะสำรวจวิธีจัดการกรอบข้อความเพื่อเพิ่มคอลัมน์โดยใช้ Aspose.Slides สำหรับ Java Aspose.Slides เป็นไลบรารีอันทรงพลังที่ช่วยให้นักพัฒนา Java สามารถสร้าง จัดการ และแปลงงานนำเสนอ PowerPoint โดยทางโปรแกรม การเพิ่มคอลัมน์ลงในกรอบข้อความช่วยเพิ่มความดึงดูดสายตาและการจัดระเบียบข้อความภายในสไลด์ ทำให้การนำเสนอน่าสนใจยิ่งขึ้นและอ่านง่ายขึ้น
## ข้อกำหนดเบื้องต้น
ก่อนที่จะเข้าสู่บทช่วยสอนนี้ ตรวจสอบให้แน่ใจว่าคุณมีสิ่งต่อไปนี้:
- ติดตั้ง Java Development Kit (JDK) บนเครื่องของคุณแล้ว
-  Aspose.Slides สำหรับไลบรารี Java คุณสามารถดาวน์โหลดได้จาก[ที่นี่](https://releases.aspose.com/slides/java/).
- ความเข้าใจพื้นฐานเกี่ยวกับการเขียนโปรแกรม Java
- สภาพแวดล้อมการพัฒนาแบบรวม (IDE) เช่น Eclipse หรือ IntelliJ IDEA
- ความคุ้นเคยกับการจัดการการพึ่งพาโครงการโดยใช้เครื่องมือเช่น Maven หรือ Gradle

## แพ็คเกจนำเข้า
ขั้นแรก นำเข้าแพ็คเกจที่จำเป็นจาก Aspose.Slides เพื่อทำงานกับการนำเสนอและกรอบข้อความ:
```java
import com.aspose.slides.*;
```
## ขั้นตอนที่ 1: เริ่มต้นการนำเสนอ
เริ่มต้นด้วยการสร้างวัตถุการนำเสนอ PowerPoint ใหม่:
```java
String dataDir = "Your Document Directory";
String outPptxFileName = dataDir + "ColumnsTest.pptx";
// สร้างวัตถุการนำเสนอใหม่
Presentation pres = new Presentation();
```
## ขั้นตอนที่ 2: เพิ่มรูปร่างอัตโนมัติพร้อมกรอบข้อความ
เพิ่มรูปร่างอัตโนมัติ (เช่น สี่เหลี่ยมผืนผ้า) ให้กับสไลด์แรกและเข้าถึงกรอบข้อความ:
```java
// เพิ่มรูปร่างอัตโนมัติลงในสไลด์แรก
IAutoShape shape1 = pres.getSlides().get_Item(0).getShapes().addAutoShape(ShapeType.Rectangle, 100, 100, 300, 300);
// เข้าถึงกรอบข้อความของรูปร่างอัตโนมัติ
TextFrameFormat format = (TextFrameFormat) shape1.getTextFrame().getTextFrameFormat();
```
## ขั้นตอนที่ 3: ตั้งค่าจำนวนคอลัมน์และข้อความ
กำหนดจำนวนคอลัมน์และเนื้อหาข้อความภายในกรอบข้อความ:
```java
// กำหนดจำนวนคอลัมน์
format.setColumnCount(2);
// ตั้งค่าเนื้อหาข้อความ
shape1.getTextFrame().setText("All these columns are limited to be within a single text container -- " +
    "you can add or delete text and the new or remaining text automatically adjusts " +
    "itself to flow within the container. You cannot have text flow from one container " +
    "to other though -- we told you PowerPoint's column options for text are limited!");
```
## ขั้นตอนที่ 4: บันทึกการนำเสนอ
บันทึกงานนำเสนอหลังจากทำการเปลี่ยนแปลง:
```java
// บันทึกการนำเสนอ
pres.save(outPptxFileName, SaveFormat.Pptx);
```
## ขั้นตอนที่ 5: ปรับระยะห่างของคอลัมน์ (ไม่บังคับ)
หากจำเป็น ให้ปรับระยะห่างระหว่างคอลัมน์:
```java
// ตั้งค่าระยะห่างของคอลัมน์
format.setColumnSpacing(20);
// บันทึกงานนำเสนอด้วยระยะห่างคอลัมน์ที่อัปเดต
pres.save(outPptxFileName, SaveFormat.Pptx);
// คุณสามารถเปลี่ยนจำนวนคอลัมน์และระยะห่างอีกครั้งได้หากจำเป็น
format.setColumnCount(3);
format.setColumnSpacing(15);
pres.save(outPptxFileName, SaveFormat.Pptx);
```

## บทสรุป
ในบทช่วยสอนนี้ เราได้สาธิตวิธีใช้ Aspose.Slides สำหรับ Java เพื่อเพิ่มคอลัมน์ภายในกรอบข้อความในงานนำเสนอ PowerPoint โดยทางโปรแกรม ความสามารถนี้ช่วยเพิ่มการนำเสนอเนื้อหาข้อความด้วยภาพ ปรับปรุงความสามารถในการอ่านและโครงสร้างในสไลด์
## คำถามที่พบบ่อย
### ฉันสามารถเพิ่มมากกว่าสามคอลัมน์ในกรอบข้อความได้หรือไม่
 ใช่ คุณสามารถปรับ`setColumnCount` วิธีการเพิ่มคอลัมน์เพิ่มเติมตามต้องการ
### Aspose.Slides รองรับการปรับความกว้างของคอลัมน์แยกกันหรือไม่
ไม่ Aspose.Slides จะตั้งค่าความกว้างเท่ากันสำหรับคอลัมน์ภายในกรอบข้อความโดยอัตโนมัติ
### มีรุ่นทดลองใช้งานสำหรับ Aspose.Slides สำหรับ Java หรือไม่
 ใช่ คุณสามารถดาวน์โหลดรุ่นทดลองใช้ฟรีได้[ที่นี่](https://releases.aspose.com/).
### ฉันจะหาเอกสารเพิ่มเติมเกี่ยวกับ Aspose.Slides สำหรับ Java ได้ที่ไหน
 มีเอกสารรายละเอียดให้[ที่นี่](https://reference.aspose.com/slides/java/).
### ฉันจะรับการสนับสนุนด้านเทคนิคสำหรับ Aspose.Slides สำหรับ Java ได้อย่างไร
 คุณสามารถขอการสนับสนุนจากชุมชนได้[ที่นี่](https://forum.aspose.com/c/slides/11).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
