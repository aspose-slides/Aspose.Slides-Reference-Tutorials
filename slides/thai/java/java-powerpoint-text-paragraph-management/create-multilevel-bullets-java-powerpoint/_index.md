---
title: สร้างสัญลักษณ์แสดงหัวข้อย่อยหลายระดับใน Java PowerPoint
linktitle: สร้างสัญลักษณ์แสดงหัวข้อย่อยหลายระดับใน Java PowerPoint
second_title: Aspose.Slides Java PowerPoint การประมวลผล API
description: เรียนรู้วิธีการสร้างสัญลักษณ์แสดงหัวข้อย่อยหลายระดับใน PowerPoint โดยใช้ Aspose.Slides สำหรับ Java คำแนะนำทีละขั้นตอนพร้อมตัวอย่างโค้ดและคำถามที่พบบ่อย
weight: 14
url: /th/java/java-powerpoint-text-paragraph-management/create-multilevel-bullets-java-powerpoint/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

## การแนะนำ
ในบทช่วยสอนนี้ เราจะสำรวจวิธีสร้างสัญลักษณ์แสดงหัวข้อย่อยหลายระดับในงานนำเสนอ PowerPoint โดยใช้ Aspose.Slides สำหรับ Java การเพิ่มสัญลักษณ์แสดงหัวข้อย่อยเป็นข้อกำหนดทั่วไปสำหรับการสร้างเนื้อหาที่มีการจัดระเบียบและดึงดูดสายตาในงานนำเสนอ เราจะดำเนินการตามกระบวนการทีละขั้นตอน เพื่อให้มั่นใจว่าในตอนท้ายของคู่มือนี้ คุณจะมีความพร้อมที่จะปรับปรุงการนำเสนอของคุณด้วยหัวข้อย่อยที่มีโครงสร้างในหลายระดับ
## ข้อกำหนดเบื้องต้น
ก่อนที่เราจะเริ่ม ตรวจสอบให้แน่ใจว่าคุณได้ตั้งค่าดังต่อไปนี้:
- สภาพแวดล้อมการพัฒนา Java: ตรวจสอบให้แน่ใจว่าติดตั้ง Java Development Kit (JDK) บนระบบของคุณแล้ว
-  Aspose.Slides สำหรับ Java Library: ดาวน์โหลดและติดตั้ง Aspose.Slides สำหรับ Java จาก[ที่นี่](https://releases.aspose.com/slides/java/).
- IDE: ใช้ Java Integrated Development Environment (IDE) ที่คุณต้องการ เช่น IntelliJ IDEA, Eclipse หรืออื่นๆ
- ความรู้พื้นฐาน: ความคุ้นเคยกับการเขียนโปรแกรม Java และแนวคิดพื้นฐานของ PowerPoint จะเป็นประโยชน์

## แพ็คเกจนำเข้า
ก่อนที่จะเข้าสู่บทช่วยสอน เรามานำเข้าแพ็คเกจที่จำเป็นจาก Aspose.Slides สำหรับ Java ที่เราจะใช้ตลอดบทช่วยสอนก่อน
```java
import com.aspose.slides.*;
import java.awt.*;
import java.io.File;
```
## ขั้นตอนที่ 1: ตั้งค่าโครงการของคุณ
ขั้นแรก สร้างโปรเจ็กต์ Java ใหม่ใน IDE ของคุณ และเพิ่ม Aspose.Slides สำหรับ Java ลงในการขึ้นต่อกันของโปรเจ็กต์ของคุณ ตรวจสอบให้แน่ใจว่าไฟล์ Aspose.Slides JAR ที่จำเป็นรวมอยู่ในพาธการ build ของโปรเจ็กต์ของคุณ
```java
// เส้นทางไปยังไดเร็กทอรีเอกสาร
String dataDir = "Your Document Directory";
```
## ขั้นตอนที่ 2: เริ่มต้นวัตถุการนำเสนอ
เริ่มต้นด้วยการสร้างอินสแตนซ์การนำเสนอใหม่ ซึ่งจะทำหน้าที่เป็นเอกสาร PowerPoint ของคุณที่คุณจะเพิ่มสไลด์และเนื้อหา
```java
Presentation pres = new Presentation();
```
## ขั้นตอนที่ 3: เข้าถึงสไลด์
จากนั้น เข้าถึงสไลด์ที่คุณต้องการเพิ่มสัญลักษณ์แสดงหัวข้อย่อยหลายระดับ สำหรับตัวอย่างนี้ เราจะทำงานกับสไลด์แรก (`Slide(0)`-
```java
ISlide slide = pres.getSlides().get_Item(0);
```
## ขั้นตอนที่ 4: เพิ่มรูปร่างอัตโนมัติพร้อมกรอบข้อความ
เพิ่มรูปร่างอัตโนมัติลงในสไลด์ที่คุณจะวางข้อความด้วยสัญลักษณ์แสดงหัวข้อย่อยหลายระดับ
```java
IAutoShape aShp = slide.getShapes().addAutoShape(ShapeType.Rectangle, 200, 200, 400, 200);
```
## ขั้นตอนที่ 5: เข้าถึงกรอบข้อความ
เข้าถึงกรอบข้อความภายในรูปร่างอัตโนมัติที่คุณจะเพิ่มย่อหน้าด้วยสัญลักษณ์แสดงหัวข้อย่อย
```java
ITextFrame text = aShp.addTextFrame("");
text.getParagraphs().clear(); //ล้างย่อหน้าเริ่มต้น
```
## ขั้นตอนที่ 6: เพิ่มย่อหน้าด้วยสัญลักษณ์แสดงหัวข้อย่อย
เพิ่มย่อหน้าด้วยสัญลักษณ์แสดงหัวข้อย่อยในระดับต่างๆ คุณสามารถเพิ่มสัญลักษณ์แสดงหัวข้อย่อยหลายระดับได้ดังนี้:
```java
// ระดับแรก
IParagraph para1 = new Paragraph();
para1.setText("Content");
para1.getParagraphFormat().getBullet().setType(BulletType.Symbol);
para1.getParagraphFormat().getBullet().setChar((char) 8226);
para1.getParagraphFormat().getDefaultPortionFormat().getFillFormat().setFillType(FillType.Solid);
para1.getParagraphFormat().getDefaultPortionFormat().getFillFormat().getSolidFillColor().setColor(Color.BLACK);
para1.getParagraphFormat().setDepth((short) 0);
text.getParagraphs().add(para1);
// ระดับที่สอง
IParagraph para2 = new Paragraph();
para2.setText("Second Level");
para2.getParagraphFormat().getBullet().setType(BulletType.Symbol);
para2.getParagraphFormat().getBullet().setChar('-');
para2.getParagraphFormat().getDefaultPortionFormat().getFillFormat().setFillType(FillType.Solid);
para2.getParagraphFormat().getDefaultPortionFormat().getFillFormat().getSolidFillColor().setColor(Color.BLACK);
para2.getParagraphFormat().setDepth((short) 1);
text.getParagraphs().add(para2);
// ระดับที่สาม
IParagraph para3 = new Paragraph();
para3.setText("Third Level");
para3.getParagraphFormat().getBullet().setType(BulletType.Symbol);
para3.getParagraphFormat().getBullet().setChar((char) 8226);
para3.getParagraphFormat().getDefaultPortionFormat().getFillFormat().setFillType(FillType.Solid);
para3.getParagraphFormat().getDefaultPortionFormat().getFillFormat().getSolidFillColor().setColor(Color.BLACK);
para3.getParagraphFormat().setDepth((short) 2);
text.getParagraphs().add(para3);
// ระดับที่สี่
IParagraph para4 = new Paragraph();
para4.setText("Fourth Level");
para4.getParagraphFormat().getBullet().setType(BulletType.Symbol);
para4.getParagraphFormat().getBullet().setChar('-');
para4.getParagraphFormat().getDefaultPortionFormat().getFillFormat().setFillType(FillType.Solid);
para4.getParagraphFormat().getDefaultPortionFormat().getFillFormat().getSolidFillColor().setColor(Color.BLACK);
para4.getParagraphFormat().setDepth((short) 3);
text.getParagraphs().add(para4);
```
## ขั้นตอนที่ 7: บันทึกการนำเสนอ
สุดท้าย บันทึกงานนำเสนอเป็นไฟล์ PPTX ในไดเร็กทอรีที่คุณต้องการ
```java
pres.save(dataDir + "MultilevelBullet.pptx", SaveFormat.Pptx);
```

## บทสรุป
ในบทช่วยสอนนี้ เราได้กล่าวถึงวิธีสร้างสัญลักษณ์แสดงหัวข้อย่อยหลายระดับในงานนำเสนอ PowerPoint โดยใช้ Aspose.Slides สำหรับ Java เมื่อทำตามขั้นตอนเหล่านี้ คุณจะสามารถจัดโครงสร้างเนื้อหาของคุณได้อย่างมีประสิทธิภาพด้วยสัญลักษณ์แสดงหัวข้อย่อยที่จัดระเบียบในระดับต่างๆ ซึ่งช่วยเพิ่มความชัดเจนและรูปลักษณ์ที่สวยงามของงานนำเสนอของคุณ
## คำถามที่พบบ่อย
### ฉันสามารถปรับแต่งสัญลักษณ์หัวข้อย่อยเพิ่มเติมได้หรือไม่
ได้ คุณสามารถปรับแต่งสัญลักษณ์หัวข้อย่อยได้โดยการปรับอักขระ Unicode หรือใช้รูปร่างที่แตกต่างกัน
### Aspose.Slides รองรับสัญลักษณ์แสดงหัวข้อย่อยประเภทอื่นหรือไม่
ใช่ Aspose.Slides รองรับสัญลักษณ์แสดงหัวข้อย่อยหลายประเภท รวมถึงสัญลักษณ์ ตัวเลข และรูปภาพแบบกำหนดเอง
### Aspose.Slides เข้ากันได้กับ PowerPoint ทุกรุ่นหรือไม่
Aspose.Slides สร้างงานนำเสนอที่เข้ากันได้กับ Microsoft PowerPoint 2007 และเวอร์ชันที่สูงกว่า
### ฉันสามารถสร้างสไลด์อัตโนมัติโดยใช้ Aspose.Slides ได้หรือไม่
ใช่ Aspose.Slides มี API เพื่อสร้าง ปรับเปลี่ยน และจัดการงานนำเสนอ PowerPoint โดยอัตโนมัติ
### ฉันจะรับการสนับสนุนสำหรับ Aspose.Slides สำหรับ Java ได้ที่ไหน
 คุณสามารถรับการสนับสนุนจากชุมชน Aspose.Slides และผู้เชี่ยวชาญได้ที่[ฟอรั่ม Aspose.Slides](https://forum.aspose.com/c/slides/11).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
