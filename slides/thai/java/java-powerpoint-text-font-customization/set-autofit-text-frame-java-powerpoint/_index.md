---
"description": "เรียนรู้วิธีตั้งค่าให้ข้อความในกรอบพอดีโดยอัตโนมัติใน Java PowerPoint โดยใช้ Aspose.Slides สำหรับ Java สร้างการนำเสนอแบบไดนามิกได้อย่างง่ายดาย"
"linktitle": "ตั้งค่าให้ข้อความพอดีอัตโนมัติใน Java PowerPoint"
"second_title": "API การประมวลผล Java PowerPoint ของ Aspose.Slides"
"title": "ตั้งค่าให้ข้อความพอดีอัตโนมัติใน Java PowerPoint"
"url": "/th/java/java-powerpoint-text-font-customization/set-autofit-text-frame-java-powerpoint/"
"weight": 14
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# ตั้งค่าให้ข้อความพอดีอัตโนมัติใน Java PowerPoint

## การแนะนำ
ในการพัฒนาแอปพลิเคชัน Java การสร้างงานนำเสนอ PowerPoint แบบไดนามิกและน่าสนใจด้วยโปรแกรมเป็นข้อกำหนดทั่วไป Aspose.Slides สำหรับ Java มีชุด API ที่ทรงพลังเพื่อให้บรรลุเป้าหมายนี้ได้อย่างง่ายดาย คุณลักษณะที่สำคัญอย่างหนึ่งคือการตั้งค่าให้พอดีข้อความโดยอัตโนมัติ เพื่อให้แน่ใจว่าข้อความจะปรับให้เข้ากับรูปร่างอย่างเรียบร้อยโดยไม่ต้องปรับด้วยตนเอง บทช่วยสอนนี้จะแนะนำคุณตลอดกระบวนการทีละขั้นตอน โดยใช้ประโยชน์จาก Aspose.Slides สำหรับ Java เพื่อทำให้การปรับข้อความในสไลด์ PowerPoint เป็นแบบอัตโนมัติ
## ข้อกำหนดเบื้องต้น
ก่อนจะเริ่มบทช่วยสอนนี้ ให้แน่ใจว่าคุณได้ตั้งค่าข้อกำหนดเบื้องต้นดังต่อไปนี้:
- ติดตั้ง Java Development Kit (JDK) บนระบบของคุณ
- ดาวน์โหลดและอ้างอิงไลบรารี Aspose.Slides สำหรับ Java ในโครงการ Java ของคุณ
- สภาพแวดล้อมการพัฒนาแบบบูรณาการ (IDE) เช่น IntelliJ IDEA หรือ Eclipse
### แพ็คเกจนำเข้า
ก่อนอื่น ตรวจสอบให้แน่ใจว่าคุณได้นำเข้าคลาส Aspose.Slides ที่จำเป็นลงในโปรเจ็กต์ Java ของคุณ:
```java
import com.aspose.slides.*;
import java.awt.*;
```
## ขั้นตอนที่ 1: สร้างงานนำเสนอใหม่
เริ่มต้นด้วยการสร้างอินสแตนซ์การนำเสนอ PowerPoint ใหม่ โดยที่คุณจะเพิ่มสไลด์และรูปร่าง
```java
// เส้นทางไปยังไดเร็กทอรีเอกสาร
String dataDir = "Your Document Directory";
// สร้างอินสแตนซ์ของคลาสการนำเสนอ
Presentation presentation = new Presentation();
```
## ขั้นตอนที่ 2: เข้าถึงสไลด์เพื่อเพิ่มรูปร่าง
เข้าถึงสไลด์แรกของการนำเสนอที่คุณต้องการเพิ่มรูปร่างพร้อมปรับข้อความที่พอดีอัตโนมัติ
```java
// เข้าถึงสไลด์แรก 
ISlide slide = presentation.getSlides().get_Item(0);
```
## ขั้นตอนที่ 3: เพิ่มรูปร่างอัตโนมัติ (สี่เหลี่ยมผืนผ้า)
เพิ่ม AutoShape (สี่เหลี่ยมผืนผ้า) ให้กับสไลด์ตามพิกัดและมิติที่เฉพาะเจาะจง
```java
// เพิ่มรูปร่างอัตโนมัติของชนิดสี่เหลี่ยมผืนผ้า
IAutoShape ashp = slide.getShapes().addAutoShape(ShapeType.Rectangle, 150, 75, 350, 350);
```
## ขั้นตอนที่ 4: เพิ่ม TextFrame ลงในสี่เหลี่ยมผืนผ้า
เพิ่มกรอบข้อความให้กับรูปสี่เหลี่ยมผืนผ้า
```java
// เพิ่ม TextFrame ลงในสี่เหลี่ยมผืนผ้า
ashp.addTextFrame(" ");
ashp.getFillFormat().setFillType(FillType.NoFill);
```
## ขั้นตอนที่ 5: ตั้งค่าให้พอดีอัตโนมัติสำหรับกรอบข้อความ
ตั้งค่าคุณสมบัติปรับพอดีอัตโนมัติให้กับกรอบข้อความเพื่อปรับข้อความตามขนาดรูปร่าง
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
บันทึกการนำเสนอที่แก้ไขแล้วโดยใช้กรอบข้อความที่ปรับพอดีอัตโนมัติ
```java
// บันทึกการนำเสนอ
presentation.save(dataDir + "formatText_out.pptx", SaveFormat.Pptx);
```

## บทสรุป
ในบทช่วยสอนนี้ คุณจะได้เรียนรู้วิธีตั้งค่าการปรับพอดีอัตโนมัติสำหรับกรอบข้อความในงานนำเสนอ PowerPoint ของ Java โดยใช้ Aspose.Slides สำหรับ Java เมื่อทำตามขั้นตอนเหล่านี้แล้ว คุณจะสามารถปรับข้อความภายในรูปร่างให้เป็นแบบอัตโนมัติได้ ซึ่งจะทำให้การนำเสนอของคุณอ่านง่ายขึ้นและสวยงามขึ้นด้วยโปรแกรม

## คำถามที่พบบ่อย
### Aspose.Slides สำหรับ Java คืออะไร?
Aspose.Slides สำหรับ Java เป็น Java API ที่แข็งแกร่งซึ่งช่วยให้นักพัฒนาสามารถสร้าง อ่าน จัดการ และแปลงงานนำเสนอ PowerPoint ได้
### ฉันจะดาวน์โหลด Aspose.Slides สำหรับ Java ได้อย่างไร?
คุณสามารถดาวน์โหลด Aspose.Slides สำหรับ Java ได้จาก [ที่นี่](https://releases-aspose.com/slides/java/).
### ฉันสามารถทดลองใช้ Aspose.Slides สำหรับ Java ได้ฟรีหรือไม่?
ใช่ คุณสามารถรับรุ่นทดลองใช้ Aspose.Slides สำหรับ Java ได้ฟรีจาก [ที่นี่](https://releases-aspose.com/).
### ฉันสามารถหาเอกสารสำหรับ Aspose.Slides สำหรับ Java ได้ที่ไหน
คุณสามารถค้นหาเอกสารรายละเอียดสำหรับ Aspose.Slides สำหรับ Java ได้ [ที่นี่](https://reference-aspose.com/slides/java/).
### ฉันจะได้รับการสนับสนุนสำหรับ Aspose.Slides สำหรับ Java ได้อย่างไร
คุณสามารถรับการสนับสนุนจากชุมชนและมืออาชีพสำหรับ Aspose.Slides สำหรับ Java ได้จาก [ที่นี่](https://forum-aspose.com/c/slides/11).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}