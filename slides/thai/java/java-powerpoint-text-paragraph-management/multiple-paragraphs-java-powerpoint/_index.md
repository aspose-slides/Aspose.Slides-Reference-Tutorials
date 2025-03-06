---
title: หลายย่อหน้าใน Java PowerPoint
linktitle: หลายย่อหน้าใน Java PowerPoint
second_title: Aspose.Slides Java PowerPoint การประมวลผล API
description: เรียนรู้วิธีสร้างหลายย่อหน้าในงานนำเสนอ Java PowerPoint โดยใช้ Aspose.Slides สำหรับ Java คู่มือฉบับสมบูรณ์พร้อมตัวอย่างโค้ด
weight: 13
url: /th/java/java-powerpoint-text-paragraph-management/multiple-paragraphs-java-powerpoint/
---

{< blocks/products/pf/main-wrap-class >}
{< blocks/products/pf/main-container >}
{< blocks/products/pf/tutorial-page-section >}

## การแนะนำ
ในบทช่วยสอนนี้ เราจะสำรวจวิธีสร้างสไลด์ที่มีหลายย่อหน้าใน Java โดยใช้ Aspose.Slides สำหรับ Java Aspose.Slides เป็นไลบรารีอันทรงพลังที่ช่วยให้นักพัฒนาจัดการงานนำเสนอ PowerPoint โดยทางโปรแกรม ทำให้เหมาะสำหรับงานอัตโนมัติที่เกี่ยวข้องกับการสร้างและการจัดรูปแบบสไลด์
## ข้อกำหนดเบื้องต้น
ก่อนที่เราจะเริ่ม ตรวจสอบให้แน่ใจว่าคุณมีสิ่งต่อไปนี้:
- ความรู้พื้นฐานเกี่ยวกับการเขียนโปรแกรม Java
- ติดตั้ง JDK (ชุดพัฒนา Java) แล้ว
- ติดตั้ง IDE (Integrated Development Environment) เช่น IntelliJ IDEA หรือ Eclipse แล้ว
-  Aspose.Slides สำหรับไลบรารี Java คุณสามารถดาวน์โหลดได้จาก[ที่นี่](https://releases.aspose.com/slides/java/).
## แพ็คเกจนำเข้า
เริ่มต้นด้วยการนำเข้าคลาส Aspose.Slides ที่จำเป็นลงในไฟล์ Java ของคุณ:
```java
import com.aspose.slides.*;
import java.awt.*;
import java.io.File;
```
## ขั้นตอนที่ 1: ตั้งค่าโครงการของคุณ
ขั้นแรก สร้างโปรเจ็กต์ Java ใหม่ใน IDE ที่คุณต้องการ และเพิ่มไลบรารี Aspose.Slides สำหรับ Java ลงในพาธการ build ของโปรเจ็กต์ของคุณ
## ขั้นตอนที่ 2: เริ่มต้นการนำเสนอ
 ยกตัวอย่าง`Presentation` วัตถุซึ่งแสดงถึงไฟล์ PowerPoint:
```java
// เส้นทางไปยังไดเร็กทอรีที่คุณต้องการบันทึกงานนำเสนอ
String dataDir = "Your_Document_Directory/";
// สร้างอินสแตนซ์วัตถุการนำเสนอ
Presentation pres = new Presentation();
```
## ขั้นตอนที่ 3: การเข้าถึงสไลด์และการเพิ่มรูปร่าง
เข้าถึงสไลด์แรกของงานนำเสนอและเพิ่มรูปร่างสี่เหลี่ยมผืนผ้า (`IAutoShape`) ไปที่:
```java
// เข้าถึงสไลด์แรก
ISlide slide = pres.getSlides().get_Item(0);
// เพิ่มรูปร่างอัตโนมัติ (สี่เหลี่ยมผืนผ้า) ลงในสไลด์
IAutoShape ashp = slide.getShapes().addAutoShape(ShapeType.Rectangle, 50, 150, 300, 150);
```
## ขั้นตอนที่ 4: เข้าถึง TextFrame และสร้างย่อหน้า
 เข้าถึง`TextFrame` ของ`AutoShape` และสร้างหลายย่อหน้า (`IParagraph`) อยู่ภายใน:
```java
// เข้าถึง TextFrame ของ AutoShape
ITextFrame tf = ashp.getTextFrame();
// สร้างย่อหน้าและส่วนด้วยรูปแบบข้อความที่แตกต่างกัน
IParagraph para0 = tf.getParagraphs().get_Item(0);
IPortion port01 = new Portion();
IPortion port02 = new Portion();
para0.getPortions().add(port01);
para0.getPortions().add(port02);
// สร้างย่อหน้าเพิ่มเติม
IParagraph para1 = new Paragraph();
tf.getParagraphs().add(para1);
IPortion port10 = new Portion();
IPortion port11 = new Portion();
IPortion port12 = new Portion();
para1.getPortions().add(port10);
para1.getPortions().add(port11);
para1.getPortions().add(port12);
IParagraph para2 = new Paragraph();
tf.getParagraphs().add(para2);
IPortion port20 = new Portion();
IPortion port21 = new Portion();
IPortion port22 = new Portion();
para2.getPortions().add(port20);
para2.getPortions().add(port21);
para2.getPortions().add(port22);
```
## ขั้นตอนที่ 5: จัดรูปแบบข้อความและย่อหน้า
จัดรูปแบบข้อความแต่ละส่วนภายในย่อหน้า:
```java
// วนซ้ำย่อหน้าและส่วนต่างๆ เพื่อกำหนดข้อความและการจัดรูปแบบ
for (int i = 0; i < 3; i++) {
    for (int j = 0; j < 3; j++) {
        tf.getParagraphs().get_Item(i).getPortions().get_Item(j).setText("Portion0" + j);
        if (j == 0) {
            // รูปแบบของส่วนแรกในแต่ละย่อหน้า
            tf.getParagraphs().get_Item(i).getPortions().get_Item(j).getPortionFormat().getFillFormat().setFillType(FillType.Solid);
            tf.getParagraphs().get_Item(i).getPortions().get_Item(j).getPortionFormat().getFillFormat().getSolidFillColor().setColor(Color.RED);
            tf.getParagraphs().get_Item(i).getPortions().get_Item(j).getPortionFormat().setFontBold(NullableBool.True);
            tf.getParagraphs().get_Item(i).getPortions().get_Item(j).getPortionFormat().setFontHeight(15);
        } else if (j == 1) {
            // รูปแบบของส่วนที่สองในแต่ละย่อหน้า
            tf.getParagraphs().get_Item(i).getPortions().get_Item(j).getPortionFormat().getFillFormat().setFillType(FillType.Solid);
            tf.getParagraphs().get_Item(i).getPortions().get_Item(j).getPortionFormat().getFillFormat().getSolidFillColor().setColor(Color.BLUE);
            tf.getParagraphs().get_Item(i).getPortions().get_Item(j).getPortionFormat().setFontItalic(NullableBool.True);
            tf.getParagraphs().get_Item(i).getPortions().get_Item(j).getPortionFormat().setFontHeight(18);
        }
    }
}
```
## ขั้นตอนที่ 6: บันทึกการนำเสนอ
สุดท้าย ให้บันทึกงานนำเสนอที่แก้ไขลงในดิสก์:
```java
// บันทึก PPTX ลงดิสก์
pres.save(dataDir + "multiParaPort_out.pptx", SaveFormat.Pptx);
```

## บทสรุป
ในบทช่วยสอนนี้ เราได้กล่าวถึงวิธีใช้ Aspose.Slides สำหรับ Java เพื่อสร้างงานนำเสนอ PowerPoint ที่มีหลายย่อหน้าโดยทางโปรแกรม วิธีการนี้ช่วยให้สามารถสร้างและปรับแต่งเนื้อหาแบบไดนามิกได้โดยตรงจากโค้ด Java

## คำถามที่พบบ่อย
### ฉันสามารถเพิ่มย่อหน้าหรือเปลี่ยนการจัดรูปแบบในภายหลังได้หรือไม่
ได้ คุณสามารถเพิ่มย่อหน้าได้มากเท่าที่ต้องการและปรับแต่งการจัดรูปแบบโดยใช้วิธี API ของ Aspose.Slides
### ฉันจะหาตัวอย่างและเอกสารประกอบเพิ่มเติมได้ที่ไหน
คุณสามารถสำรวจตัวอย่างเพิ่มเติมและเอกสารประกอบโดยละเอียดได้[ที่นี่](https://reference.aspose.com/slides/java/).
### Aspose.Slides เข้ากันได้กับ PowerPoint ทุกรุ่นหรือไม่
Aspose.Slides รองรับรูปแบบ PowerPoint ที่หลากหลาย ทำให้มั่นใจได้ถึงความเข้ากันได้ในเวอร์ชันต่างๆ
### ฉันสามารถทดลองใช้ Aspose.Slides ฟรีก่อนซื้อได้หรือไม่
 ใช่ คุณสามารถดาวน์โหลดเวอร์ชันทดลองใช้ฟรีได้[ที่นี่](https://releases.aspose.com/).
### ฉันจะได้รับการสนับสนุนทางเทคนิคได้อย่างไรหากจำเป็น?
 คุณสามารถรับการสนับสนุนจากชุมชน Aspose.Slides[ที่นี่](https://forum.aspose.com/c/slides/11).
{< /blocks/products/pf/tutorial-page-section >}

{< /blocks/products/pf/main-container >}
{< /blocks/products/pf/main-wrap-class >}

{< blocks/products/products-backtop-button >}
