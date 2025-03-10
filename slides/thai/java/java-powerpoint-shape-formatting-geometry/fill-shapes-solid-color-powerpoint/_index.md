---
title: เติมรูปร่างด้วยสีทึบใน PowerPoint
linktitle: เติมรูปร่างด้วยสีทึบใน PowerPoint
second_title: Aspose.Slides Java PowerPoint การประมวลผล API
description: เรียนรู้วิธีเติมรูปร่างด้วยสีทึบใน PowerPoint โดยใช้ Aspose.Slides สำหรับ Java คำแนะนำทีละขั้นตอนสำหรับนักพัฒนา
weight: 13
url: /th/java/java-powerpoint-shape-formatting-geometry/fill-shapes-solid-color-powerpoint/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# เติมรูปร่างด้วยสีทึบใน PowerPoint

## การแนะนำ
หากคุณเคยทำงานกับงานนำเสนอ PowerPoint คุณจะรู้ว่าการเพิ่มรูปร่างและปรับแต่งสีอาจเป็นส่วนสำคัญในการทำให้สไลด์ของคุณดูน่าดึงดูดและให้ข้อมูล ด้วย Aspose.Slides สำหรับ Java กระบวนการนี้กลายเป็นเรื่องง่าย ไม่ว่าคุณจะเป็นนักพัฒนาที่ต้องการสร้างงานนำเสนอ PowerPoint โดยอัตโนมัติ หรือผู้ที่สนใจจะเพิ่มสีสันให้กับสไลด์ของคุณ บทช่วยสอนนี้จะแนะนำคุณตลอดขั้นตอนการเติมรูปร่างด้วยสีทึบโดยใช้ Aspose.Slides สำหรับ Java
## ข้อกำหนดเบื้องต้น
ก่อนที่เราจะเจาะลึกโค้ด มีข้อกำหนดเบื้องต้นบางประการที่คุณต้องมี:
1.  Java Development Kit (JDK): ตรวจสอบให้แน่ใจว่าคุณได้ติดตั้ง JDK บนระบบของคุณ คุณสามารถดาวน์โหลดได้จาก[เว็บไซต์ออราเคิล](https://www.oracle.com/java/technologies/javase-downloads.html).
2.  Aspose.Slides สำหรับ Java: ดาวน์โหลดไลบรารี Aspose.Slides สำหรับ Java จากไฟล์[เว็บไซต์กำหนด](https://releases.aspose.com/slides/java/).
3. สภาพแวดล้อมการพัฒนาแบบรวม (IDE): IDE เช่น IntelliJ IDEA หรือ Eclipse จะทำให้กระบวนการพัฒนาของคุณราบรื่นยิ่งขึ้น
4. ความรู้พื้นฐานของ Java: ความคุ้นเคยกับการเขียนโปรแกรม Java จะช่วยให้คุณเข้าใจและนำโค้ดไปใช้ได้อย่างมีประสิทธิภาพ

## แพ็คเกจนำเข้า
หากต้องการเริ่มใช้ Aspose.Slides สำหรับ Java คุณต้องนำเข้าแพ็คเกจที่จำเป็น ต่อไปนี้คือวิธีที่คุณสามารถทำได้:
```java
import com.aspose.slides.*;

import java.awt.*;
```
## ขั้นตอนที่ 1: ตั้งค่าโครงการของคุณ
 ขั้นแรก คุณต้องตั้งค่าโปรเจ็กต์ Java ของคุณและรวม Aspose.Slides สำหรับ Java ในการขึ้นต่อกันของโปรเจ็กต์ของคุณ หากคุณใช้ Maven ให้เพิ่มการพึ่งพาต่อไปนี้ให้กับ your`pom.xml` ไฟล์:
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>XX.X</version> <!-- Replace XX.X with the latest version -->
</dependency>
```
 หากคุณไม่ได้ใช้ Maven ให้ดาวน์โหลดไฟล์ JAR จากไฟล์[เว็บไซต์กำหนด](https://releases.aspose.com/slides/java/) และเพิ่มลงในเส้นทางการสร้างโครงการของคุณ
## ขั้นตอนที่ 2: เริ่มต้นการนำเสนอ
 สร้างอินสแตนซ์ของ`Presentation` ระดับ. ชั้นเรียนนี้แสดงถึงการนำเสนอ PowerPoint ที่คุณจะใช้งาน
```java
// เส้นทางไปยังไดเร็กทอรีเอกสาร
String dataDir = "Your Document Directory";
// สร้างอินสแตนซ์ของคลาสการนำเสนอ
Presentation presentation = new Presentation();
```
## ขั้นตอนที่ 3: เข้าถึงสไลด์แรก
ถัดไป คุณจะต้องได้สไลด์แรกของงานนำเสนอที่คุณจะเพิ่มรูปร่างของคุณ
```java
// รับสไลด์แรก
ISlide slide = presentation.getSlides().get_Item(0);
```
## ขั้นตอนที่ 4: เพิ่มรูปร่างให้กับสไลด์
ตอนนี้ เรามาเพิ่มรูปทรงสี่เหลี่ยมผืนผ้าลงในสไลด์กัน คุณสามารถปรับแต่งตำแหน่งและขนาดของรูปร่างได้โดยการปรับพารามิเตอร์
```java
// เพิ่มรูปร่างอัตโนมัติของประเภทสี่เหลี่ยมผืนผ้า
IShape shape = slide.getShapes().addAutoShape(ShapeType.Rectangle, 50, 150, 75, 150);
```
## ขั้นตอนที่ 5: ตั้งค่าประเภทการเติมเป็น Solid
 หากต้องการเติมรูปร่างด้วยสีทึบ ให้ตั้งค่าประเภทการเติมเป็น`Solid`.
```java
// ตั้งค่าประเภทการเติมเป็น Solid
shape.getFillFormat().setFillType(FillType.Solid);
```
## ขั้นตอนที่ 6: เลือกและใช้สี
เลือกสีสำหรับรูปร่าง ในภาพนี้เราใช้สีเหลือง แต่คุณสามารถเลือกสีใดก็ได้ตามที่คุณต้องการ
```java
//กำหนดสีของสี่เหลี่ยม
shape.getFillFormat().getSolidFillColor().setColor(Color.YELLOW);
```
## ขั้นตอนที่ 7: บันทึกการนำเสนอ
สุดท้าย ให้บันทึกงานนำเสนอที่แก้ไขแล้วลงในไฟล์
```java
// เขียนไฟล์ PPTX ลงดิสก์
presentation.save(dataDir + "RectShpSolid_out.pptx", SaveFormat.Pptx);
```

## บทสรุป
และคุณก็ได้แล้ว! คุณเติมรูปร่างด้วยสีทึบในงานนำเสนอ PowerPoint ได้สำเร็จโดยใช้ Aspose.Slides สำหรับ Java ไลบรารีนี้มีชุดคุณลักษณะที่มีประสิทธิภาพซึ่งสามารถช่วยให้คุณทำงานอัตโนมัติและปรับแต่งงานนำเสนอของคุณได้อย่างง่ายดาย ไม่ว่าคุณจะสร้างรายงาน สร้างสื่อการเรียนรู้ หรือออกแบบสไลด์ธุรกิจ Aspose.Slides สำหรับ Java สามารถเป็นเครื่องมืออันล้ำค่าได้
## คำถามที่พบบ่อย
### Aspose.Slides สำหรับ Java คืออะไร
Aspose.Slides for Java เป็นไลบรารีที่มีประสิทธิภาพสำหรับการทำงานกับงานนำเสนอ PowerPoint ใน Java ช่วยให้คุณสร้าง แก้ไข และแปลงงานนำเสนอโดยทางโปรแกรม
### ฉันจะติดตั้ง Aspose.Slides สำหรับ Java ได้อย่างไร
 คุณสามารถดาวน์โหลดได้จาก[เว็บไซต์กำหนด](https://releases.aspose.com/slides/java/) และเพิ่มไฟล์ JAR ในโครงการของคุณ หรือใช้ตัวจัดการการพึ่งพาเช่น Maven เพื่อรวมไว้
### ฉันสามารถใช้ Aspose.Slides สำหรับ Java เพื่อแก้ไขงานนำเสนอที่มีอยู่ได้หรือไม่
ใช่ Aspose.Slides สำหรับ Java ช่วยให้คุณสามารถเปิด แก้ไข และบันทึกงานนำเสนอ PowerPoint ที่มีอยู่ได้
### มีการทดลองใช้ฟรีสำหรับ Aspose.Slides สำหรับ Java หรือไม่
 ใช่ คุณสามารถดาวน์โหลดรุ่นทดลองใช้ฟรีได้จาก[เว็บไซต์กำหนด](https://releases.aspose.com/).
### ฉันจะหาเอกสารและความช่วยเหลือเพิ่มเติมได้จากที่ไหน?
 เอกสารรายละเอียดมีอยู่ที่[เว็บไซต์กำหนด](https://reference.aspose.com/slides/java/)และคุณสามารถขอรับการสนับสนุนได้ที่[กำหนดฟอรั่ม](https://forum.aspose.com/c/slides/11).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
