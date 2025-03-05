---
title: ตั้งค่าหมายเลขสัญลักษณ์แสดงหัวข้อย่อยที่กำหนดเองใน Java PowerPoint
linktitle: ตั้งค่าหมายเลขสัญลักษณ์แสดงหัวข้อย่อยที่กำหนดเองใน Java PowerPoint
second_title: Aspose.Slides Java PowerPoint การประมวลผล API
description: เรียนรู้วิธีตั้งค่าหมายเลขสัญลักษณ์แสดงหัวข้อย่อยที่กำหนดเองใน Java PowerPoint ด้วย Aspose.Slides ซึ่งเพิ่มความชัดเจนและโครงสร้างการนำเสนอโดยทางโปรแกรม
type: docs
weight: 15
url: /th/java/java-powerpoint-text-font-customization/set-custom-bullets-number-java-powerpoint/
---
## การแนะนำ
ในยุคดิจิทัลปัจจุบัน การสร้างงานนำเสนอแบบไดนามิกถือเป็นสิ่งสำคัญสำหรับการสื่อสารแนวคิดและข้อมูลอย่างมีประสิทธิภาพ Aspose.Slides for Java มอบชุดเครื่องมืออันทรงพลังในการจัดการงานนำเสนอ PowerPoint โดยทางโปรแกรม โดยนำเสนอฟีเจอร์มากมายเพื่อปรับปรุงกระบวนการสร้างงานนำเสนอของคุณ บทความนี้เจาะลึกเกี่ยวกับการตั้งค่าหมายเลขสัญลักษณ์แสดงหัวข้อย่อยที่กำหนดเองในงานนำเสนอ Java PowerPoint โดยใช้ Aspose.Slides ไม่ว่าคุณจะเป็นนักพัฒนาที่มีประสบการณ์หรือเป็นมือใหม่ บทช่วยสอนนี้จะแนะนำคุณทีละขั้นตอนตลอดกระบวนการ เพื่อให้มั่นใจว่าคุณจะสามารถใช้ประโยชน์จากความสามารถนี้ได้อย่างมีประสิทธิภาพ
## ข้อกำหนดเบื้องต้น
ก่อนที่จะเข้าสู่บทช่วยสอน ตรวจสอบให้แน่ใจว่าคุณได้ตั้งค่าข้อกำหนดเบื้องต้นต่อไปนี้ในสภาพแวดล้อมการพัฒนาของคุณ:
- ติดตั้ง Java Development Kit (JDK) แล้ว
- สภาพแวดล้อมการพัฒนาแบบรวม (IDE) เช่น IntelliJ IDEA หรือ Eclipse
-  Aspose.Slides สำหรับไลบรารี Java คุณสามารถดาวน์โหลดได้จาก[ที่นี่](https://releases.aspose.com/slides/java/)
- ความเข้าใจพื้นฐานเกี่ยวกับภาษาการเขียนโปรแกรม Java และแนวคิดเชิงวัตถุ

## แพ็คเกจนำเข้า
ขั้นแรก นำเข้าคลาส Aspose.Slides ที่จำเป็นและไลบรารีมาตรฐาน Java อื่นๆ:
```java
import com.aspose.slides.*;
```
## ขั้นตอนที่ 1: สร้างวัตถุการนำเสนอ
เริ่มต้นด้วยการสร้างงานนำเสนอ PowerPoint ใหม่โดยใช้ Aspose.Slides
```java
String dataDir = "Your Document Directory";
Presentation presentation = new Presentation();
```
## ขั้นตอนที่ 2: เพิ่มรูปร่างอัตโนมัติพร้อมข้อความ
แทรกรูปร่างอัตโนมัติ (สี่เหลี่ยมผืนผ้า) บนสไลด์และเข้าถึงกรอบข้อความ
```java
IAutoShape shape = presentation.getSlides().get_Item(0).getShapes().addAutoShape(ShapeType.Rectangle, 200, 200, 400, 200);
ITextFrame textFrame = shape.getTextFrame();
```
## ขั้นตอนที่ 3: ลบย่อหน้าเริ่มต้น
ลบย่อหน้าที่มีอยู่ที่เป็นค่าเริ่มต้นออกจากกรอบข้อความ
```java
textFrame.getParagraphs().removeAt(0);
```
## ขั้นตอนที่ 4: เพิ่มสัญลักษณ์แสดงหัวข้อย่อยที่มีหมายเลข
เพิ่มย่อหน้าด้วยสัญลักษณ์แสดงหัวข้อย่อยที่มีหมายเลขแบบกำหนดเองโดยเริ่มจากตัวเลขที่ระบุ
```java
// ตัวอย่างย่อหน้าที่มีสัญลักษณ์แสดงหัวข้อย่อยเริ่มต้นจาก 2
Paragraph paragraph1 = new Paragraph();
paragraph1.setText("bullet 2");
paragraph1.getParagraphFormat().setDepth((short) 4);
paragraph1.getParagraphFormat().getBullet().setNumberedBulletStartWith((short) 2);
paragraph1.getParagraphFormat().getBullet().setType(BulletType.Numbered);
textFrame.getParagraphs().add(paragraph1);
// ตัวอย่างย่อหน้าที่มีสัญลักษณ์แสดงหัวข้อย่อยเริ่มต้นจาก 3
Paragraph paragraph2 = new Paragraph();
paragraph2.setText("bullet 3");
paragraph2.getParagraphFormat().setDepth((short) 4);
paragraph2.getParagraphFormat().getBullet().setNumberedBulletStartWith((short) 3);
paragraph2.getParagraphFormat().getBullet().setType(BulletType.Numbered);
textFrame.getParagraphs().add(paragraph2);
// ตัวอย่างย่อหน้าที่มีสัญลักษณ์แสดงหัวข้อย่อยเริ่มต้นจาก 7
Paragraph paragraph3 = new Paragraph();
paragraph3.setText("bullet 7");
paragraph3.getParagraphFormat().setDepth((short) 4);
paragraph3.getParagraphFormat().getBullet().setNumberedBulletStartWith((short) 7);
paragraph3.getParagraphFormat().getBullet().setType(BulletType.Numbered);
textFrame.getParagraphs().add(paragraph3);
```
## ขั้นตอนที่ 5: บันทึกการนำเสนอ
สุดท้าย ให้บันทึกงานนำเสนอที่แก้ไขแล้วไปยังตำแหน่งที่คุณต้องการ
```java
presentation.save(dataDir + "SetCustomBulletsNumber-slides.pptx", SaveFormat.Pptx);
```

## บทสรุป
โดยสรุป Aspose.Slides สำหรับ Java ช่วยให้กระบวนการตั้งค่าหมายเลขสัญลักษณ์แสดงหัวข้อย่อยที่กำหนดเองในงานนำเสนอ PowerPoint โดยทางโปรแกรมง่ายขึ้น ด้วยการทำตามขั้นตอนที่ระบุไว้ในบทช่วยสอนนี้ คุณจะสามารถเพิ่มความชัดเจนของภาพและโครงสร้างของงานนำเสนอของคุณได้อย่างมีประสิทธิภาพ
## คำถามที่พบบ่อย
### ฉันสามารถปรับแต่งรูปลักษณ์ของกระสุนเพิ่มเติมได้หรือไม่?
ใช่ Aspose.Slides มีตัวเลือกมากมายในการปรับแต่งประเภทสัญลักษณ์แสดงหัวข้อย่อย ขนาด สี และอื่นๆ
### Aspose.Slides เข้ากันได้กับ PowerPoint ทุกรุ่นหรือไม่
Aspose.Slides รองรับรูปแบบ PowerPoint ตั้งแต่ 97-2003 ไปจนถึงเวอร์ชันล่าสุด
### ฉันจะรับการสนับสนุนทางเทคนิคสำหรับ Aspose.Slides ได้อย่างไร
 เยี่ยม[ฟอรั่ม Aspose.Slides](https://forum.aspose.com/c/slides/11) สำหรับความช่วยเหลือด้านเทคนิค
### ฉันสามารถลองใช้ Aspose.Slides ก่อนซื้อได้หรือไม่
 ใช่ คุณสามารถดาวน์โหลดรุ่นทดลองใช้ฟรีได้จาก[ที่นี่](https://releases.aspose.com/).
### ฉันจะซื้อ Aspose.Slides ได้ที่ไหน
 คุณสามารถซื้อ Aspose.Slides ได้จาก[ที่นี่](https://purchase.aspose.com/buy).