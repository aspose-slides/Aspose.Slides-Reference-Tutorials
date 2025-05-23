---
"description": "เรียนรู้วิธีการตั้งค่าหมายเลขหัวข้อย่อยแบบกำหนดเองใน Java PowerPoint ด้วย Aspose.Slides เพื่อปรับปรุงความชัดเจนและโครงสร้างการนำเสนอในโปรแกรม"
"linktitle": "ตั้งค่าหมายเลขหัวข้อย่อยแบบกำหนดเองใน Java PowerPoint"
"second_title": "API การประมวลผล Java PowerPoint ของ Aspose.Slides"
"title": "ตั้งค่าหมายเลขหัวข้อย่อยแบบกำหนดเองใน Java PowerPoint"
"url": "/th/java/java-powerpoint-text-font-customization/set-custom-bullets-number-java-powerpoint/"
"weight": 15
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# ตั้งค่าหมายเลขหัวข้อย่อยแบบกำหนดเองใน Java PowerPoint

## การแนะนำ
ในยุคดิจิทัลทุกวันนี้ การสร้างงานนำเสนอแบบไดนามิกถือเป็นสิ่งสำคัญสำหรับการสื่อสารแนวคิดและข้อมูลอย่างมีประสิทธิภาพ Aspose.Slides สำหรับ Java มอบชุดเครื่องมืออันทรงพลังสำหรับการจัดการงานนำเสนอ PowerPoint ด้วยโปรแกรม ซึ่งมีคุณลักษณะมากมายเพื่อเพิ่มประสิทธิภาพกระบวนการสร้างงานนำเสนอของคุณ บทความนี้จะเจาะลึกเกี่ยวกับการตั้งค่าหมายเลขหัวข้อแบบกำหนดเองในงานนำเสนอ PowerPoint ด้วย Java โดยใช้ Aspose.Slides ไม่ว่าคุณจะเป็นนักพัฒนาที่มีประสบการณ์หรือเป็นมือใหม่ บทช่วยสอนนี้จะแนะนำคุณทีละขั้นตอนตลอดกระบวนการ เพื่อให้แน่ใจว่าคุณสามารถใช้ความสามารถนี้ได้อย่างมีประสิทธิภาพ
## ข้อกำหนดเบื้องต้น
ก่อนจะดำดิ่งลงไปในบทช่วยสอน ให้แน่ใจว่าคุณได้ตั้งค่าข้อกำหนดเบื้องต้นต่อไปนี้ไว้ในสภาพแวดล้อมการพัฒนาของคุณแล้ว:
- ติดตั้ง Java Development Kit (JDK) แล้ว
- สภาพแวดล้อมการพัฒนาแบบบูรณาการ (IDE) เช่น IntelliJ IDEA หรือ Eclipse
- Aspose.Slides สำหรับไลบรารี Java คุณสามารถดาวน์โหลดได้จาก [ที่นี่](https://releases.aspose.com/slides/java/)
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
แทรกรูปร่างอัตโนมัติ (สี่เหลี่ยมผืนผ้า) ลงในสไลด์และเข้าถึงกรอบข้อความ
```java
IAutoShape shape = presentation.getSlides().get_Item(0).getShapes().addAutoShape(ShapeType.Rectangle, 200, 200, 400, 200);
ITextFrame textFrame = shape.getTextFrame();
```
## ขั้นตอนที่ 3: ลบย่อหน้าเริ่มต้น
ลบย่อหน้าที่มีอยู่เริ่มต้นออกจากกรอบข้อความ
```java
textFrame.getParagraphs().removeAt(0);
```
## ขั้นตอนที่ 4: เพิ่มหัวข้อย่อยที่มีหมายเลข
เพิ่มย่อหน้าด้วยการกำหนดหมายเลขหัวข้อย่อยโดยเริ่มจากหมายเลขเฉพาะ
```java
// ตัวอย่างย่อหน้าที่มีจุดเริ่มตั้งแต่ 2
Paragraph paragraph1 = new Paragraph();
paragraph1.setText("bullet 2");
paragraph1.getParagraphFormat().setDepth((short) 4);
paragraph1.getParagraphFormat().getBullet().setNumberedBulletStartWith((short) 2);
paragraph1.getParagraphFormat().getBullet().setType(BulletType.Numbered);
textFrame.getParagraphs().add(paragraph1);
// ตัวอย่างย่อหน้าที่มีจุดหัวข้อเริ่มต้นที่ 3
Paragraph paragraph2 = new Paragraph();
paragraph2.setText("bullet 3");
paragraph2.getParagraphFormat().setDepth((short) 4);
paragraph2.getParagraphFormat().getBullet().setNumberedBulletStartWith((short) 3);
paragraph2.getParagraphFormat().getBullet().setType(BulletType.Numbered);
textFrame.getParagraphs().add(paragraph2);
// ตัวอย่างย่อหน้าที่มีหัวข้อย่อยเริ่มต้นที่ 7
Paragraph paragraph3 = new Paragraph();
paragraph3.setText("bullet 7");
paragraph3.getParagraphFormat().setDepth((short) 4);
paragraph3.getParagraphFormat().getBullet().setNumberedBulletStartWith((short) 7);
paragraph3.getParagraphFormat().getBullet().setType(BulletType.Numbered);
textFrame.getParagraphs().add(paragraph3);
```
## ขั้นตอนที่ 5: บันทึกการนำเสนอ
สุดท้ายให้บันทึกการนำเสนอที่แก้ไขแล้วลงในตำแหน่งที่คุณต้องการ
```java
presentation.save(dataDir + "SetCustomBulletsNumber-slides.pptx", SaveFormat.Pptx);
```

## บทสรุป
โดยสรุป Aspose.Slides สำหรับ Java ช่วยลดความยุ่งยากของกระบวนการกำหนดหมายเลขหัวข้อย่อยแบบกำหนดเองในงานนำเสนอ PowerPoint ด้วยโปรแกรม โดยทำตามขั้นตอนที่ระบุไว้ในบทช่วยสอนนี้ คุณสามารถปรับปรุงความชัดเจนของภาพและโครงสร้างของงานนำเสนอของคุณได้อย่างมีประสิทธิภาพ
## คำถามที่พบบ่อย
### ฉันสามารถปรับแต่งลักษณะที่ปรากฏของกระสุนเพิ่มเติมได้หรือไม่
ใช่ Aspose.Slides มีตัวเลือกมากมายในการปรับแต่งประเภทกระสุน ขนาด สี และอื่นๆ อีกมากมาย
### Aspose.Slides เข้ากันได้กับ PowerPoint ทุกเวอร์ชันหรือไม่
Aspose.Slides รองรับรูปแบบ PowerPoint ตั้งแต่ 97-2003 ถึงเวอร์ชันล่าสุด
### ฉันจะได้รับการสนับสนุนด้านเทคนิคสำหรับ Aspose.Slides ได้อย่างไร
เยี่ยม [ฟอรั่ม Aspose.Slides](https://forum.aspose.com/c/slides/11) สำหรับความช่วยเหลือด้านเทคนิค
### ฉันสามารถทดลองใช้ Aspose.Slides ก่อนซื้อได้หรือไม่?
ใช่ คุณสามารถดาวน์โหลดรุ่นทดลองใช้งานฟรีได้จาก [ที่นี่](https://releases-aspose.com/).
### ฉันสามารถซื้อ Aspose.Slides ได้จากที่ไหน
คุณสามารถซื้อ Aspose.Slides ได้จาก [ที่นี่](https://purchase-aspose.com/buy).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}