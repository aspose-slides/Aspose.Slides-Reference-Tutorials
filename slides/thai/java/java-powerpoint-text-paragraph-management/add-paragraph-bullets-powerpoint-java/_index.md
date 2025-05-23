---
"description": "เรียนรู้วิธีการเพิ่มจุดหัวข้อย่อยในสไลด์ PowerPoint โดยใช้ Aspose.Slides สำหรับ Java บทช่วยสอนนี้จะแนะนำคุณทีละขั้นตอนพร้อมตัวอย่างโค้ด"
"linktitle": "เพิ่มหัวข้อย่อยในย่อหน้าใน PowerPoint โดยใช้ Java"
"second_title": "API การประมวลผล Java PowerPoint ของ Aspose.Slides"
"title": "เพิ่มหัวข้อย่อยในย่อหน้าใน PowerPoint โดยใช้ Java"
"url": "/th/java/java-powerpoint-text-paragraph-management/add-paragraph-bullets-powerpoint-java/"
"weight": 15
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# เพิ่มหัวข้อย่อยในย่อหน้าใน PowerPoint โดยใช้ Java

## การแนะนำ
การเพิ่มจุดหัวข้อย่อยในย่อหน้าจะช่วยให้การนำเสนอ PowerPoint ของคุณอ่านง่ายขึ้นและมีโครงสร้างที่ดีขึ้น Aspose.Slides สำหรับ Java มอบเครื่องมือที่มีประสิทธิภาพในการจัดการการนำเสนอด้วยโปรแกรม รวมถึงความสามารถในการจัดรูปแบบข้อความด้วยรูปแบบจุดหัวข้อย่อยต่างๆ ในบทช่วยสอนนี้ คุณจะได้เรียนรู้วิธีการผสานจุดหัวข้อย่อยเข้ากับสไลด์ PowerPoint โดยใช้โค้ด Java โดยใช้ประโยชน์จาก Aspose.Slides
## ข้อกำหนดเบื้องต้น
ก่อนที่คุณจะเริ่มต้น ให้แน่ใจว่าคุณมีสิ่งต่อไปนี้:
- ความรู้พื้นฐานเกี่ยวกับการเขียนโปรแกรมภาษา Java
- JDK (Java Development Kit) ติดตั้งอยู่บนระบบของคุณ
- Aspose.Slides สำหรับไลบรารี Java คุณสามารถดาวน์โหลดได้จาก [ที่นี่](https://releases-aspose.com/slides/java/).

## แพ็คเกจนำเข้า
ในการเริ่มต้น ให้ทำการนำเข้าแพ็กเกจ Aspose.Slides ที่จำเป็นลงในโปรเจ็กต์ Java ของคุณ:
```java
import com.aspose.slides.*;
import java.awt.*;
import java.io.File;
```
## ขั้นตอนที่ 1: ตั้งค่าโครงการของคุณ
ขั้นแรก ให้สร้างโปรเจ็กต์ Java ใหม่ และเพิ่มไลบรารี Aspose.Slides สำหรับ Java ลงในเส้นทางการสร้างโปรเจ็กต์ของคุณ
## ขั้นตอนที่ 2: เริ่มต้นการนำเสนอ
เริ่มต้นวัตถุการนำเสนอ (`Presentation`) เพื่อเริ่มทำงานกับสไลด์
```java
// เส้นทางไปยังไดเร็กทอรีเอกสาร
String dataDir = "Your Document Directory";
// การสร้างอินสแตนซ์การนำเสนอ
Presentation pres = new Presentation();
```
## ขั้นตอนที่ 3: เข้าถึงสไลด์และกรอบข้อความ
เข้าถึงสไลด์ (`ISlide`) และกรอบข้อความ (`ITextFrame`) ที่คุณต้องการเพิ่มหัวข้อย่อย
```java
// การเข้าถึงสไลด์แรก
ISlide slide = pres.getSlides().get_Item(0);
// การเพิ่มและการเข้าถึง Autoshape
IAutoShape aShp = slide.getShapes().addAutoShape(ShapeType.Rectangle, 200, 200, 400, 200);
// การเข้าถึงกรอบข้อความของรูปร่างอัตโนมัติที่สร้างขึ้น
ITextFrame txtFrm = aShp.getTextFrame();
```
## ขั้นตอนที่ 4: สร้างและจัดรูปแบบย่อหน้าด้วยเครื่องหมายหัวข้อย่อย
สร้างย่อหน้า (`Paragraph`) และตั้งค่ารูปแบบหัวข้อย่อย การเยื้อง และข้อความ
```java
// การสร้างย่อหน้า
Paragraph para = new Paragraph();
para.getParagraphFormat().getBullet().setType(BulletType.Symbol);
para.getParagraphFormat().getBullet().setChar((char) 8226);
para.setText("Welcome to Aspose.Slides");
para.getParagraphFormat().setIndent(25);
txtFrm.getParagraphs().add(para);
// การสร้างย่อหน้าใหม่
Paragraph para2 = new Paragraph();
para2.getParagraphFormat().getBullet().setType(BulletType.Numbered);
para2.getParagraphFormat().getBullet().setNumberedBulletStyle(NumberedBulletStyle.BulletCircleNumWDBlackPlain);
para2.setText("This is numbered bullet");
para2.getParagraphFormat().setIndent(25);
txtFrm.getParagraphs().add(para2);
```
## ขั้นตอนที่ 5: บันทึกการนำเสนอ
บันทึกการนำเสนอที่แก้ไขแล้วลงในไฟล์ PowerPoint (`PPTX`-
```java
// การเขียนการนำเสนอเป็นไฟล์ PPTX
pres.save(dataDir + "Bullet_out.pptx", SaveFormat.Pptx);
```
## ขั้นตอนที่ 6: ทำความสะอาดทรัพยากร
กำจัดวัตถุการนำเสนอเพื่อปล่อยทรัพยากร
```java
// กำจัดวัตถุการนำเสนอ
if (pres != null) {
    pres.dispose();
}
```

## บทสรุป
การเพิ่มจุดหัวข้อย่อยใน PowerPoint โดยใช้ Aspose.Slides สำหรับ Java นั้นทำได้ง่ายด้วยตัวอย่างโค้ดที่ให้มา ปรับแต่งรูปแบบและการจัดรูปแบบจุดหัวข้อย่อยให้เหมาะกับความต้องการในการนำเสนอของคุณได้อย่างราบรื่น

## คำถามที่พบบ่อย
### ฉันสามารถปรับแต่งสีหัวข้อย่อยได้ไหม
ใช่ คุณสามารถตั้งค่าสีที่กำหนดเองสำหรับกระสุนได้โดยใช้ Aspose.Slides API
### ฉันจะเพิ่มหัวข้อย่อยซ้อนกันได้อย่างไร?
การใส่หัวข้อย่อยแบบซ้อนกันเกี่ยวข้องกับการเพิ่มย่อหน้าภายในย่อหน้า โดยปรับการเยื้องให้เหมาะสม
### ฉันสามารถสร้างรูปแบบหัวข้อย่อยที่แตกต่างกันสำหรับสไลด์ต่างๆ ได้หรือไม่
ใช่ คุณสามารถนำรูปแบบสัญลักษณ์หัวข้อย่อยเฉพาะไปใช้กับสไลด์ต่างๆ ได้ด้วยโปรแกรม
### Aspose.Slides เข้ากันได้กับ Java 11 หรือไม่
ใช่ Aspose.Slides รองรับ Java 11 และเวอร์ชันที่สูงกว่า
### ฉันสามารถหาตัวอย่างและเอกสารเพิ่มเติมได้ที่ไหน
เยี่ยม [เอกสาร Aspose.Slides สำหรับ Java](https://reference.aspose.com/slides/java/) สำหรับคำแนะนำและตัวอย่างที่ครอบคลุม

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}