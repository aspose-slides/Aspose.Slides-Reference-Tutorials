---
"description": "เรียนรู้วิธีสร้างจุดแสดงหัวข้อย่อยหลายระดับใน PowerPoint โดยใช้ Aspose.Slides สำหรับ Java คำแนะนำทีละขั้นตอนพร้อมตัวอย่างโค้ดและคำถามที่พบบ่อย"
"linktitle": "สร้างจุดหัวข้อหลายระดับใน Java PowerPoint"
"second_title": "API การประมวลผล Java PowerPoint ของ Aspose.Slides"
"title": "สร้างจุดหัวข้อหลายระดับใน Java PowerPoint"
"url": "/th/java/java-powerpoint-text-paragraph-management/create-multilevel-bullets-java-powerpoint/"
"weight": 14
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# สร้างจุดหัวข้อหลายระดับใน Java PowerPoint

## การแนะนำ
ในบทช่วยสอนนี้ เราจะมาเรียนรู้วิธีการสร้างจุดหัวข้อย่อยหลายระดับในงานนำเสนอ PowerPoint โดยใช้ Aspose.Slides สำหรับ Java การเพิ่มจุดหัวข้อย่อยเป็นข้อกำหนดทั่วไปในการสร้างเนื้อหาที่เป็นระเบียบและน่าสนใจในงานนำเสนอ เราจะอธิบายกระบวนการทีละขั้นตอนเพื่อให้แน่ใจว่าเมื่ออ่านคู่มือนี้จบ คุณจะพร้อมที่จะปรับปรุงงานนำเสนอของคุณด้วยจุดหัวข้อย่อยที่มีโครงสร้างในหลายระดับ
## ข้อกำหนดเบื้องต้น
ก่อนที่เราจะเริ่ม โปรดตรวจสอบให้แน่ใจว่าคุณได้ตั้งค่าสิ่งต่อไปนี้แล้ว:
- สภาพแวดล้อมการพัฒนา Java: ตรวจสอบให้แน่ใจว่ามีการติดตั้ง Java Development Kit (JDK) ในระบบของคุณ
- ไลบรารี Aspose.Slides สำหรับ Java: ดาวน์โหลดและติดตั้ง Aspose.Slides สำหรับ Java จาก [ที่นี่](https://releases-aspose.com/slides/java/).
- IDE: ใช้ Java Integrated Development Environment (IDE) ที่คุณต้องการ เช่น IntelliJ IDEA, Eclipse หรืออื่นๆ
- ความรู้พื้นฐาน: ความคุ้นเคยกับการเขียนโปรแกรม Java และแนวคิดพื้นฐานของ PowerPoint จะเป็นประโยชน์

## แพ็คเกจนำเข้า
ก่อนที่จะเริ่มบทช่วยสอน ให้เราลองนำเข้าแพ็กเกจที่จำเป็นจาก Aspose.Slides สำหรับ Java ที่เราจะใช้ตลอดบทช่วยสอนกันก่อน
```java
import com.aspose.slides.*;
import java.awt.*;
import java.io.File;
```
## ขั้นตอนที่ 1: ตั้งค่าโครงการของคุณ
ขั้นแรก ให้สร้างโปรเจ็กต์ Java ใหม่ใน IDE ของคุณ และเพิ่ม Aspose.Slides สำหรับ Java ลงในส่วนที่ต้องมีของโปรเจ็กต์ของคุณ ตรวจสอบว่ามีไฟล์ JAR Aspose.Slides ที่จำเป็นอยู่ในเส้นทางการสร้างของโปรเจ็กต์ของคุณหรือไม่
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
ขั้นตอนต่อไปคือเข้าถึงสไลด์ที่คุณต้องการเพิ่มจุดหัวข้อย่อยหลายระดับ สำหรับตัวอย่างนี้ เราจะทำงานกับสไลด์แรก (`Slide(0)`-
```java
ISlide slide = pres.getSlides().get_Item(0);
```
## ขั้นตอนที่ 4: เพิ่ม AutoShape ด้วยกรอบข้อความ
เพิ่ม AutoShape ลงในสไลด์ที่คุณจะวางข้อความโดยใช้หัวข้อย่อยหลายระดับ
```java
IAutoShape aShp = slide.getShapes().addAutoShape(ShapeType.Rectangle, 200, 200, 400, 200);
```
## ขั้นตอนที่ 5: เข้าถึงกรอบข้อความ
เข้าถึงกรอบข้อความภายใน AutoShape ซึ่งคุณจะเพิ่มย่อหน้าพร้อมจุดหัวข้อย่อย
```java
ITextFrame text = aShp.addTextFrame("");
text.getParagraphs().clear(); // ล้างย่อหน้าเริ่มต้น
```
## ขั้นตอนที่ 6: เพิ่มย่อหน้าด้วยเครื่องหมายหัวข้อย่อย
เพิ่มย่อหน้าด้วยระดับของจุดหัวข้อย่อยที่แตกต่างกัน คุณสามารถเพิ่มจุดหัวข้อย่อยหลายระดับได้ดังนี้:
```java
// ระดับที่หนึ่ง
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
สุดท้ายให้บันทึกการนำเสนอเป็นไฟล์ PPTX ในไดเร็กทอรีที่คุณต้องการ
```java
pres.save(dataDir + "MultilevelBullet.pptx", SaveFormat.Pptx);
```

## บทสรุป
ในบทช่วยสอนนี้ เราได้กล่าวถึงวิธีการสร้างจุดหัวข้อย่อยหลายระดับในงานนำเสนอ PowerPoint โดยใช้ Aspose.Slides สำหรับ Java เมื่อทำตามขั้นตอนเหล่านี้แล้ว คุณจะสามารถจัดโครงสร้างเนื้อหาของคุณได้อย่างมีประสิทธิภาพด้วยจุดหัวข้อย่อยที่จัดระเบียบในระดับต่างๆ ซึ่งช่วยเพิ่มความชัดเจนและความสวยงามให้กับงานนำเสนอของคุณ
## คำถามที่พบบ่อย
### ฉันสามารถปรับแต่งสัญลักษณ์หัวข้อย่อยเพิ่มเติมได้หรือไม่
ใช่ คุณสามารถปรับแต่งสัญลักษณ์หัวข้อย่อยได้โดยการปรับอักขระ Unicode หรือใช้รูปร่างอื่น
### Aspose.Slides รองรับประเภทกระสุนอื่น ๆ หรือไม่?
ใช่ Aspose.Slides รองรับประเภทหัวข้อย่อยต่างๆ รวมถึงสัญลักษณ์ ตัวเลข และรูปภาพที่กำหนดเอง
### Aspose.Slides เข้ากันได้กับ PowerPoint ทุกเวอร์ชันหรือไม่
Aspose.Slides สร้างงานนำเสนอที่เข้ากันได้กับ Microsoft PowerPoint 2007 และเวอร์ชันที่สูงกว่า
### ฉันสามารถสร้างสไลด์แบบอัตโนมัติโดยใช้ Aspose.Slides ได้หรือไม่
ใช่ Aspose.Slides มี API สำหรับการสร้าง การปรับเปลี่ยน และการจัดการการนำเสนอ PowerPoint โดยอัตโนมัติ
### ฉันจะได้รับการสนับสนุนสำหรับ Aspose.Slides สำหรับ Java ได้จากที่ไหน
คุณสามารถรับการสนับสนุนจากชุมชน Aspose.Slides และผู้เชี่ยวชาญได้ที่ [ฟอรั่ม Aspose.Slides](https://forum-aspose.com/c/slides/11).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}