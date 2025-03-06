---
title: ตั้งค่าการปรับพอดีอัตโนมัติของกรอบข้อความใน Java PowerPoint
linktitle: ตั้งค่าการปรับพอดีอัตโนมัติของกรอบข้อความใน Java PowerPoint
second_title: Aspose.Slides Java PowerPoint การประมวลผล API
description: เรียนรู้วิธีตั้งค่าการปรับพอดีอัตโนมัติสำหรับกรอบข้อความใน Java PowerPoint โดยใช้ Aspose.Slides สำหรับ Java สร้างงานนำเสนอแบบไดนามิกได้อย่างง่ายดาย
weight: 14
url: /th/java/java-powerpoint-text-font-customization/set-autofit-text-frame-java-powerpoint/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

## การแนะนำ
ในการพัฒนาแอปพลิเคชัน Java การสร้างงานนำเสนอ PowerPoint แบบไดนามิกและดึงดูดสายตาโดยทางโปรแกรมถือเป็นข้อกำหนดทั่วไป Aspose.Slides สำหรับ Java มอบชุด API อันทรงพลังเพื่อให้บรรลุเป้าหมายนี้ได้อย่างง่ายดาย คุณสมบัติที่สำคัญประการหนึ่งคือการตั้งค่าการปรับให้พอดีอัตโนมัติสำหรับกรอบข้อความ เพื่อให้มั่นใจว่าข้อความจะปรับภายในรูปร่างได้อย่างเรียบร้อยโดยไม่ต้องปรับด้วยตนเอง บทช่วยสอนนี้จะแนะนำคุณตลอดกระบวนการทีละขั้นตอน โดยใช้ประโยชน์จาก Aspose.Slides สำหรับ Java เพื่อปรับข้อความให้พอดีในสไลด์ PowerPoint โดยอัตโนมัติ
## ข้อกำหนดเบื้องต้น
ก่อนที่จะเข้าสู่บทช่วยสอน ตรวจสอบให้แน่ใจว่าคุณได้ตั้งค่าข้อกำหนดเบื้องต้นต่อไปนี้:
- ติดตั้ง Java Development Kit (JDK) บนระบบของคุณ
- Aspose.Slides สำหรับไลบรารี Java ที่ดาวน์โหลดและอ้างอิงในโปรเจ็กต์ Java ของคุณ
- สภาพแวดล้อมการพัฒนาแบบรวม (IDE) เช่น IntelliJ IDEA หรือ Eclipse
### แพ็คเกจนำเข้า
ประการแรก ตรวจสอบให้แน่ใจว่าได้นำเข้าคลาส Aspose.Slides ที่จำเป็นในโปรเจ็กต์ Java ของคุณ:
```java
import com.aspose.slides.*;
import java.awt.*;
```
## ขั้นตอนที่ 1: สร้างงานนำเสนอใหม่
เริ่มต้นด้วยการสร้างอินสแตนซ์การนำเสนอ PowerPoint ใหม่ที่คุณจะเพิ่มสไลด์และรูปร่าง
```java
// เส้นทางไปยังไดเร็กทอรีเอกสาร
String dataDir = "Your Document Directory";
// สร้างอินสแตนซ์ของคลาสการนำเสนอ
Presentation presentation = new Presentation();
```
## ขั้นตอนที่ 2: เข้าถึงสไลด์เพื่อเพิ่มรูปร่าง
เข้าถึงสไลด์แรกของงานนำเสนอที่คุณต้องการเพิ่มรูปร่างด้วยการปรับข้อความให้พอดีอัตโนมัติ
```java
// เข้าถึงสไลด์แรก
ISlide slide = presentation.getSlides().get_Item(0);
```
## ขั้นตอนที่ 3: เพิ่มรูปร่างอัตโนมัติ (สี่เหลี่ยมผืนผ้า)
เพิ่มรูปร่างอัตโนมัติ (สี่เหลี่ยมผืนผ้า) ลงในสไลด์ตามพิกัดและขนาดที่ระบุ
```java
// เพิ่มประเภทสี่เหลี่ยมผืนผ้ารูปร่างอัตโนมัติ
IAutoShape ashp = slide.getShapes().addAutoShape(ShapeType.Rectangle, 150, 75, 350, 350);
```
## ขั้นตอนที่ 4: เพิ่ม TextFrame ให้กับสี่เหลี่ยมผืนผ้า
เพิ่มกรอบข้อความให้กับรูปร่างสี่เหลี่ยมผืนผ้า
```java
// เพิ่ม TextFrame ให้กับสี่เหลี่ยมผืนผ้า
ashp.addTextFrame(" ");
ashp.getFillFormat().setFillType(FillType.NoFill);
```
## ขั้นตอนที่ 5: ตั้งค่าปรับพอดีอัตโนมัติสำหรับกรอบข้อความ
ตั้งค่าคุณสมบัติปรับพอดีอัตโนมัติสำหรับกรอบข้อความเพื่อปรับข้อความตามขนาดรูปร่าง
```java
// การเข้าถึงกรอบข้อความ
ITextFrame txtFrame = ashp.getTextFrame();
txtFrame.getTextFrameFormat().setAutofitType(TextAutofitType.Shape);
```
## ขั้นตอนที่ 6: เพิ่มข้อความลงในกรอบข้อความ
เพิ่มเนื้อหาข้อความลงในกรอบข้อความภายในรูปร่าง
```java
// สร้างวัตถุย่อหน้าสำหรับกรอบข้อความ
IParagraph para = txtFrame.getParagraphs().get_Item(0);
// สร้างวัตถุส่วนสำหรับย่อหน้า
IPortion portion = para.getPortions().get_Item(0);
portion.setText("A quick brown fox jumps over the lazy dog. A quick brown fox jumps over the lazy dog.");
portion.getPortionFormat().getFillFormat().setFillType(FillType.Solid);
portion.getPortionFormat().getFillFormat().getSolidFillColor().setColor(Color.BLACK);
```
## ขั้นตอนที่ 7: บันทึกการนำเสนอ
บันทึกงานนำเสนอที่แก้ไขด้วยกรอบข้อความปรับให้พอดีอัตโนมัติ
```java
// บันทึกการนำเสนอ
presentation.save(dataDir + "formatText_out.pptx", SaveFormat.Pptx);
```

## บทสรุป
ในบทช่วยสอนนี้ คุณได้เรียนรู้วิธีตั้งค่าการปรับพอดีอัตโนมัติสำหรับกรอบข้อความในงานนำเสนอ Java PowerPoint โดยใช้ Aspose.Slides สำหรับ Java ด้วยการทำตามขั้นตอนเหล่านี้ คุณสามารถปรับข้อความให้เหมาะสมภายในรูปร่างได้โดยอัตโนมัติ ปรับปรุงความสามารถในการอ่านและความสวยงามของงานนำเสนอของคุณโดยทางโปรแกรม

## คำถามที่พบบ่อย
### Aspose.Slides สำหรับ Java คืออะไร
Aspose.Slides สำหรับ Java เป็น Java API ที่มีประสิทธิภาพซึ่งช่วยให้นักพัฒนาสามารถสร้าง อ่าน จัดการ และแปลงงานนำเสนอ PowerPoint
### ฉันจะดาวน์โหลด Aspose.Slides สำหรับ Java ได้อย่างไร
 คุณสามารถดาวน์โหลด Aspose.Slides สำหรับ Java ได้จาก[ที่นี่](https://releases.aspose.com/slides/java/).
### ฉันสามารถลองใช้ Aspose.Slides สำหรับ Java ได้ฟรีหรือไม่
 ใช่ คุณสามารถทดลองใช้ Aspose.Slides สำหรับ Java ฟรีได้จาก[ที่นี่](https://releases.aspose.com/).
### ฉันจะหาเอกสารประกอบสำหรับ Aspose.Slides สำหรับ Java ได้ที่ไหน
 คุณสามารถดูเอกสารประกอบโดยละเอียดสำหรับ Aspose.Slides สำหรับ Java[ที่นี่](https://reference.aspose.com/slides/java/).
### ฉันจะรับการสนับสนุนสำหรับ Aspose.Slides สำหรับ Java ได้อย่างไร
 คุณสามารถรับการสนับสนุนจากชุมชนและการสนับสนุนระดับมืออาชีพสำหรับ Aspose.Slides สำหรับ Java ได้จาก[ที่นี่](https://forum.aspose.com/c/slides/11).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
