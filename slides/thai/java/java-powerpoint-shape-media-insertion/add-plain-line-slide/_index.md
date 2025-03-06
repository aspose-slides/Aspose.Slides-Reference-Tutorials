---
title: เพิ่มเส้นธรรมดาลงในสไลด์
linktitle: เพิ่มเส้นธรรมดาลงในสไลด์
second_title: Aspose.Slides Java PowerPoint การประมวลผล API
description: เรียนรู้วิธีเพิ่มเส้นธรรมดาลงในสไลด์ PowerPoint โดยทางโปรแกรมโดยใช้ Aspose.Slides สำหรับ Java เพิ่มประสิทธิภาพการทำงานของคุณด้วยคำแนะนำทีละขั้นตอนนี้
weight: 14
url: /th/java/java-powerpoint-shape-media-insertion/add-plain-line-slide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

## การแนะนำ
Aspose.Slides for Java เป็นไลบรารีอันทรงพลังที่ช่วยให้นักพัฒนา Java สามารถทำงานกับงานนำเสนอ PowerPoint โดยทางโปรแกรม ด้วย Aspose.Slides คุณสามารถสร้าง แก้ไข และแปลงไฟล์ PowerPoint ได้อย่างง่ายดาย ประหยัดเวลาและความพยายาม ในบทช่วยสอนนี้ เราจะแนะนำคุณตลอดขั้นตอนการเพิ่มเส้นธรรมดาให้กับสไลด์ในงานนำเสนอ PowerPoint โดยใช้ Aspose.Slides สำหรับ Java
## ข้อกำหนดเบื้องต้น
ก่อนที่เราจะเริ่มต้น ตรวจสอบให้แน่ใจว่าคุณมีข้อกำหนดเบื้องต้นดังต่อไปนี้:
- ติดตั้ง Java Development Kit (JDK) บนระบบของคุณ
- Aspose.Slides สำหรับไลบรารี Java ที่ดาวน์โหลดและเพิ่มลงในโปรเจ็กต์ Java ของคุณ
- ความรู้พื้นฐานเกี่ยวกับภาษาการเขียนโปรแกรม Java

## แพ็คเกจนำเข้า
ในการเริ่มต้น คุณจะต้องนำเข้าแพ็คเกจที่จำเป็นในโค้ด Java ของคุณ ต่อไปนี้คือวิธีที่คุณสามารถทำได้:
```java
import com.aspose.slides.ISlide;
import com.aspose.slides.Presentation;
import com.aspose.slides.SaveFormat;
import com.aspose.slides.ShapeType;

import java.io.File;
```
## ขั้นตอนที่ 1: ตั้งค่าสภาพแวดล้อม
 ขั้นแรก สร้างโปรเจ็กต์ Java ใหม่ และเพิ่มไลบรารี Aspose.Slides สำหรับ Java ไปยังคลาสพาธของโปรเจ็กต์ของคุณ คุณสามารถดาวน์โหลดห้องสมุดได้จาก[ที่นี่](https://releases.aspose.com/slides/java/).
## ขั้นตอนที่ 2: สร้างงานนำเสนอใหม่
 ถัดไป ยกตัวอย่าง`Presentation` คลาสเพื่อสร้างงานนำเสนอ PowerPoint ใหม่
```java
Presentation pres = new Presentation();
```
## ขั้นตอนที่ 3: เพิ่มสไลด์
รับสไลด์แรกของงานนำเสนอและจัดเก็บไว้ในตัวแปร
```java
ISlide slide = pres.getSlides().get_Item(0);
```
## ขั้นตอนที่ 4: เพิ่มรูปร่างเส้น
ตอนนี้ เพิ่มรูปร่างอัตโนมัติของเส้นประเภทลงในสไลด์
```java
slide.getShapes().addAutoShape(ShapeType.Line, 50, 150, 300, 0);
```
## ขั้นตอนที่ 5: บันทึกการนำเสนอ
สุดท้าย ให้บันทึกงานนำเสนอลงดิสก์
```java
pres.save("Your Document Directory/LineShape1_out.pptx", SaveFormat.Pptx);
```

## บทสรุป
ยินดีด้วย! คุณได้เพิ่มเส้นธรรมดาลงในสไลด์ในงานนำเสนอ PowerPoint เรียบร้อยแล้วโดยใช้ Aspose.Slides สำหรับ Java ด้วย Aspose.Slides คุณสามารถจัดการไฟล์ PowerPoint โดยทางโปรแกรมได้อย่างง่ายดาย เปิดโลกแห่งความเป็นไปได้สำหรับแอปพลิเคชัน Java ของคุณ

## คำถามที่พบบ่อย
### ฉันสามารถปรับแต่งคุณสมบัติของรูปร่างเส้นได้หรือไม่?
ใช่ คุณสามารถปรับแต่งคุณสมบัติต่างๆ ได้ เช่น สีเส้น ความกว้าง สไตล์ และอื่นๆ โดยใช้ Aspose.Slides API
### Aspose.Slides เข้ากันได้กับ PowerPoint เวอร์ชันต่างๆ หรือไม่
ใช่ Aspose.Slides รองรับรูปแบบ PowerPoint ที่หลากหลาย รวมถึง PPT, PPTX และอื่นๆ เพื่อให้มั่นใจถึงความเข้ากันได้ในเวอร์ชันต่างๆ
### Aspose.Slides ให้การสนับสนุนในการเพิ่มรูปร่างอื่นๆ นอกเหนือจากเส้นหรือไม่
อย่างแน่นอน! Aspose.Slides มีประเภทรูปร่างที่หลากหลาย รวมถึงสี่เหลี่ยม วงกลม ลูกศร และอื่นๆ
### ฉันสามารถเพิ่มข้อความลงในสไลด์พร้อมกับรูปร่างเส้นได้หรือไม่
ได้ คุณสามารถเพิ่มข้อความ รูปภาพ และเนื้อหาอื่นๆ ลงในสไลด์ได้โดยใช้ Aspose.Slides API
### มีการทดลองใช้ฟรีสำหรับ Aspose.Slides หรือไม่
 ใช่ คุณสามารถดาวน์โหลด Aspose.Slides รุ่นทดลองใช้ฟรีได้จาก[ที่นี่](https://releases.aspose.com/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
