---
title: สร้างรูปร่างกลุ่มใน PowerPoint
linktitle: สร้างรูปร่างกลุ่มใน PowerPoint
second_title: Aspose.Slides Java PowerPoint การประมวลผล API
description: เรียนรู้วิธีสร้างรูปร่างกลุ่มในงานนำเสนอ PowerPoint โดยใช้ Aspose.Slides สำหรับ Java ปรับปรุงองค์กรและดึงดูดสายตาได้อย่างง่ายดาย
weight: 11
url: /th/java/java-powerpoint-shape-thumbnail-creation/create-group-shape-powerpoint/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# สร้างรูปร่างกลุ่มใน PowerPoint

## การแนะนำ
ในการนำเสนอสมัยใหม่ การผสมผสานองค์ประกอบที่ดึงดูดสายตาและมีโครงสร้างที่ดีเป็นสิ่งสำคัญสำหรับการถ่ายทอดข้อมูลอย่างมีประสิทธิภาพ รูปร่างกลุ่มใน PowerPoint ช่วยให้คุณสามารถจัดระเบียบรูปร่างหลายรูปร่างให้เป็นหน่วยเดียว ช่วยให้จัดการและจัดรูปแบบได้ง่ายขึ้น Aspose.Slides สำหรับ Java มีฟังก์ชันการทำงานที่มีประสิทธิภาพในการสร้างและจัดการรูปร่างของกลุ่มโดยทางโปรแกรม ให้ความยืดหยุ่นและการควบคุมการออกแบบงานนำเสนอของคุณ
## ข้อกำหนดเบื้องต้น
ก่อนที่จะเข้าสู่บทช่วยสอน ตรวจสอบให้แน่ใจว่าคุณได้ตั้งค่าข้อกำหนดเบื้องต้นต่อไปนี้:
1. Java Development Kit (JDK): ตรวจสอบให้แน่ใจว่าคุณได้ติดตั้ง JDK บนระบบของคุณแล้ว
2. Aspose.Slides สำหรับไลบรารี Java: ดาวน์โหลดและรวม Aspose.Slides สำหรับไลบรารี Java ในโปรเจ็กต์ของคุณ คุณสามารถดาวน์โหลดได้จาก[ที่นี่](https://releases.aspose.com/slides/java/).
3. Integrated Development Environment (IDE): เลือก Java IDE ตามที่คุณต้องการ เช่น IntelliJ IDEA หรือ Eclipse

## แพ็คเกจนำเข้า
ในการเริ่มต้น ให้นำเข้าแพ็คเกจที่จำเป็นสำหรับการใช้ Aspose.Slides สำหรับฟังก์ชัน Java:
```java
import com.aspose.slides.*;

```
## ขั้นตอนที่ 1: ตั้งค่าสภาพแวดล้อมของคุณ
 ตรวจสอบให้แน่ใจว่าคุณได้ตั้งค่าไดเรกทอรีสำหรับโครงการของคุณซึ่งคุณสามารถสร้างและบันทึกงานนำเสนอ PowerPoint ได้ แทนที่`"Your Document Directory"` พร้อมเส้นทางไปยังไดเร็กทอรีที่คุณต้องการ
```java
String dataDir = "Your Document Directory";
```
## ขั้นตอนที่ 2: สร้างอินสแตนซ์ของชั้นเรียนการนำเสนอ
 สร้างอินสแตนซ์ของ`Presentation` ชั้นเรียนเพื่อเริ่มต้นงานนำเสนอ PowerPoint ใหม่
```java
Presentation pres = new Presentation();
```
## ขั้นตอนที่ 3: รับคอลเลกชันสไลด์และรูปร่าง
ดึงสไลด์แรกจากงานนำเสนอและเข้าถึงคอลเลกชันรูปร่างของสไลด์นั้น
```java
ISlide sld = pres.getSlides().get_Item(0);
IShapeCollection slideShapes = sld.getShapes();
```
## ขั้นตอนที่ 4: เพิ่มรูปร่างกลุ่ม
 เพิ่มรูปร่างกลุ่มให้กับสไลด์โดยใช้`addGroupShape()` วิธี.
```java
IGroupShape groupShape = slideShapes.addGroupShape();
```
## ขั้นตอนที่ 5: เพิ่มรูปร่างภายในรูปร่างกลุ่ม
เติมรูปร่างกลุ่มโดยการเพิ่มรูปร่างแต่ละแบบเข้าไปข้างใน
```java
groupShape.getShapes().addAutoShape(ShapeType.Rectangle, 300, 100, 100, 100);
groupShape.getShapes().addAutoShape(ShapeType.Rectangle, 500, 100, 100, 100);
groupShape.getShapes().addAutoShape(ShapeType.Rectangle, 300, 300, 100, 100);
groupShape.getShapes().addAutoShape(ShapeType.Rectangle, 500, 300, 100, 100);
```
## ขั้นตอนที่ 6: ปรับแต่งกรอบรูปร่างกลุ่ม
หรือปรับแต่งกรอบรูปร่างของกลุ่มตามความต้องการของคุณ
```java
groupShape.setFrame(new ShapeFrame(100, 300, 500, 40, NullableBool.False, NullableBool.False, 0));
```
## ขั้นตอนที่ 7: บันทึกการนำเสนอ
บันทึกงานนำเสนอ PowerPoint ไปยังไดเร็กทอรีที่คุณระบุ
```java
pres.save(dataDir + "GroupShape_out.pptx", SaveFormat.Pptx);
```

## บทสรุป
การสร้างรูปร่างกลุ่มในงานนำเสนอ PowerPoint โดยใช้ Aspose.Slides สำหรับ Java นำเสนอแนวทางที่มีประสิทธิภาพในการจัดระเบียบและจัดโครงสร้างเนื้อหา ด้วยการทำตามคำแนะนำทีละขั้นตอนที่อธิบายไว้ข้างต้น คุณสามารถรวมรูปร่างกลุ่มไว้ในงานนำเสนอของคุณได้อย่างมีประสิทธิภาพ เพิ่มรูปลักษณ์ที่ดึงดูดใจ และถ่ายทอดข้อมูลได้อย่างมีประสิทธิภาพ

## คำถามที่พบบ่อย
### ฉันสามารถซ้อนรูปร่างกลุ่มภายในรูปร่างกลุ่มอื่นได้หรือไม่
ใช่ Aspose.Slides สำหรับ Java อนุญาตให้ซ้อนรูปร่างกลุ่มภายในกันและกันเพื่อสร้างโครงสร้างลำดับชั้นที่ซับซ้อน
### Aspose.Slides สำหรับ Java เข้ากันได้กับ PowerPoint เวอร์ชันต่างๆ หรือไม่
Aspose.Slides สำหรับ Java สร้างงานนำเสนอ PowerPoint ที่เข้ากันได้กับเวอร์ชันต่างๆ
### Aspose.Slides สำหรับ Java รองรับการเพิ่มรูปภาพลงในรูปร่างกลุ่มหรือไม่
แน่นอน คุณสามารถเพิ่มรูปภาพพร้อมกับรูปร่างอื่นๆ เพื่อจัดกลุ่มรูปร่างโดยใช้ Aspose.Slides สำหรับ Java
### มีข้อจำกัดเกี่ยวกับจำนวนรูปร่างภายในรูปร่างกลุ่มหรือไม่?
Aspose.Slides สำหรับ Java ไม่มีข้อจำกัดที่เข้มงวดเกี่ยวกับจำนวนรูปร่างที่สามารถเพิ่มลงในรูปร่างกลุ่มได้
### ฉันสามารถใช้ภาพเคลื่อนไหวกับรูปร่างกลุ่มโดยใช้ Aspose.Slides สำหรับ Java ได้หรือไม่
ใช่ Aspose.Slides สำหรับ Java ให้การสนับสนุนที่ครอบคลุมสำหรับการใช้ภาพเคลื่อนไหวกับรูปร่างกลุ่ม ซึ่งช่วยให้สามารถนำเสนอแบบไดนามิกได้
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
