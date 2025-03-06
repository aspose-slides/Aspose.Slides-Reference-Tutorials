---
title: เพิ่มสัญลักษณ์ย่อย่อหน้าใน PowerPoint โดยใช้ Java
linktitle: เพิ่มสัญลักษณ์ย่อย่อหน้าใน PowerPoint โดยใช้ Java
second_title: Aspose.Slides Java PowerPoint การประมวลผล API
description: เรียนรู้วิธีเพิ่มสัญลักษณ์แสดงหัวข้อย่อยในสไลด์ PowerPoint โดยใช้ Aspose.Slides สำหรับ Java บทช่วยสอนนี้จะแนะนำคุณทีละขั้นตอนพร้อมตัวอย่างโค้ด
weight: 15
url: /th/java/java-powerpoint-text-paragraph-management/add-paragraph-bullets-powerpoint-java/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

## การแนะนำ
การเพิ่มสัญลักษณ์ย่อย่อหน้าช่วยเพิ่มความสามารถในการอ่านและโครงสร้างของงานนำเสนอ PowerPoint Aspose.Slides สำหรับ Java มอบเครื่องมือที่มีประสิทธิภาพในการจัดการงานนำเสนอโดยทางโปรแกรม รวมถึงความสามารถในการจัดรูปแบบข้อความด้วยสไตล์สัญลักษณ์แสดงหัวข้อย่อยต่างๆ ในบทช่วยสอนนี้ คุณจะได้เรียนรู้วิธีรวมสัญลักษณ์แสดงหัวข้อย่อยลงในสไลด์ PowerPoint โดยใช้โค้ด Java โดยใช้ประโยชน์จาก Aspose.Slides
## ข้อกำหนดเบื้องต้น
ก่อนที่คุณจะเริ่มต้น ตรวจสอบให้แน่ใจว่าคุณมีสิ่งต่อไปนี้:
- ความรู้พื้นฐานเกี่ยวกับการเขียนโปรแกรม Java
- ติดตั้ง JDK (Java Development Kit) บนระบบของคุณ
-  Aspose.Slides สำหรับไลบรารี Java คุณสามารถดาวน์โหลดได้จาก[ที่นี่](https://releases.aspose.com/slides/java/).

## แพ็คเกจนำเข้า
ในการเริ่มต้น ให้นำเข้าแพ็คเกจ Aspose.Slides ที่จำเป็นลงในโปรเจ็กต์ Java ของคุณ:
```java
import com.aspose.slides.*;
import java.awt.*;
import java.io.File;
```
## ขั้นตอนที่ 1: ตั้งค่าโครงการของคุณ
ขั้นแรก สร้างโปรเจ็กต์ Java ใหม่ และเพิ่มไลบรารี Aspose.Slides สำหรับ Java ไปยังพาธการ build ของโปรเจ็กต์ของคุณ
## ขั้นตอนที่ 2: เริ่มต้นการนำเสนอ
เริ่มต้นวัตถุการนำเสนอ (`Presentation`) เพื่อเริ่มทำงานกับสไลด์
```java
// เส้นทางไปยังไดเร็กทอรีเอกสาร
String dataDir = "Your Document Directory";
// การสร้างตัวอย่างการนำเสนอ
Presentation pres = new Presentation();
```
## ขั้นตอนที่ 3: เข้าถึงสไลด์และกรอบข้อความ
เข้าถึงสไลด์ (`ISlide`และกรอบข้อความ (`ITextFrame`) ที่คุณต้องการเพิ่มสัญลักษณ์แสดงหัวข้อย่อย
```java
// การเข้าถึงสไลด์แรก
ISlide slide = pres.getSlides().get_Item(0);
// การเพิ่มและการเข้าถึง Autoshape
IAutoShape aShp = slide.getShapes().addAutoShape(ShapeType.Rectangle, 200, 200, 400, 200);
// การเข้าถึงกรอบข้อความของรูปร่างอัตโนมัติที่สร้างขึ้น
ITextFrame txtFrm = aShp.getTextFrame();
```
## ขั้นตอนที่ 4: สร้างและจัดรูปแบบย่อหน้าด้วยสัญลักษณ์แสดงหัวข้อย่อย
สร้างย่อหน้า (`Paragraph`) และตั้งค่ารูปแบบสัญลักษณ์แสดงหัวข้อย่อย การเยื้อง และข้อความ
```java
// การสร้างย่อหน้า
Paragraph para = new Paragraph();
para.getParagraphFormat().getBullet().setType(BulletType.Symbol);
para.getParagraphFormat().getBullet().setChar((char) 8226);
para.setText("Welcome to Aspose.Slides");
para.getParagraphFormat().setIndent(25);
txtFrm.getParagraphs().add(para);
// การสร้างย่อหน้าอื่น
Paragraph para2 = new Paragraph();
para2.getParagraphFormat().getBullet().setType(BulletType.Numbered);
para2.getParagraphFormat().getBullet().setNumberedBulletStyle(NumberedBulletStyle.BulletCircleNumWDBlackPlain);
para2.setText("This is numbered bullet");
para2.getParagraphFormat().setIndent(25);
txtFrm.getParagraphs().add(para2);
```
## ขั้นตอนที่ 5: บันทึกการนำเสนอ
บันทึกงานนำเสนอที่แก้ไขแล้วลงในไฟล์ PowerPoint (`PPTX`-
```java
// การเขียนงานนำเสนอเป็นไฟล์ PPTX
pres.save(dataDir + "Bullet_out.pptx", SaveFormat.Pptx);
```
## ขั้นตอนที่ 6: ทำความสะอาดทรัพยากร
กำจัดวัตถุการนำเสนอเพื่อเผยแพร่ทรัพยากร
```java
// กำจัดวัตถุการนำเสนอ
if (pres != null) {
    pres.dispose();
}
```

## บทสรุป
การเพิ่มสัญลักษณ์ย่อย่อหน้าใน PowerPoint โดยใช้ Aspose.Slides สำหรับ Java นั้นตรงไปตรงมากับตัวอย่างโค้ดที่ให้มา ปรับแต่งสไตล์สัญลักษณ์แสดงหัวข้อย่อยและการจัดรูปแบบให้เหมาะกับความต้องการในการนำเสนอของคุณได้อย่างราบรื่น

## คำถามที่พบบ่อย
### ฉันสามารถปรับแต่งสีสัญลักษณ์แสดงหัวข้อย่อยได้หรือไม่
ใช่ คุณสามารถตั้งค่าสีที่กำหนดเองสำหรับสัญลักษณ์แสดงหัวข้อย่อยได้โดยใช้ Aspose.Slides API
### ฉันจะเพิ่มสัญลักษณ์แสดงหัวข้อย่อยที่ซ้อนกันได้อย่างไร
การซ้อนสัญลักษณ์แสดงหัวข้อย่อยเกี่ยวข้องกับการเพิ่มย่อหน้าภายในย่อหน้า โดยปรับการเยื้องตามนั้น
### ฉันสามารถสร้างสไตล์สัญลักษณ์แสดงหัวข้อย่อยที่แตกต่างกันสำหรับสไลด์ที่แตกต่างกันได้หรือไม่
ได้ คุณสามารถใช้รูปแบบสัญลักษณ์แสดงหัวข้อย่อยที่ไม่ซ้ำกันกับสไลด์ต่างๆ โดยทางโปรแกรม
### Aspose.Slides เข้ากันได้กับ Java 11 หรือไม่
ใช่ Aspose.Slides รองรับ Java 11 และเวอร์ชันที่สูงกว่า
### ฉันจะหาตัวอย่างและเอกสารประกอบเพิ่มเติมได้ที่ไหน
 เยี่ยม[Aspose.Slides สำหรับเอกสาร Java](https://reference.aspose.com/slides/java/) สำหรับคำแนะนำและตัวอย่างที่ครอบคลุม
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
