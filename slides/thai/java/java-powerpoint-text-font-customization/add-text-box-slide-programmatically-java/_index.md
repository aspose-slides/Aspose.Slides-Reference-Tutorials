---
"description": "เรียนรู้วิธีการเพิ่มกล่องข้อความลงในสไลด์ PowerPoint โดยใช้ Aspose.Slides สำหรับ Java เพิ่มประสิทธิภาพการทำงานของคุณด้วยคู่มือทีละขั้นตอนนี้"
"linktitle": "เพิ่มกล่องข้อความบนสไลด์ด้วยโปรแกรมด้วย Java"
"second_title": "API การประมวลผล Java PowerPoint ของ Aspose.Slides"
"title": "เพิ่มกล่องข้อความบนสไลด์ด้วยโปรแกรมด้วย Java"
"url": "/th/java/java-powerpoint-text-font-customization/add-text-box-slide-programmatically-java/"
"weight": 24
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# เพิ่มกล่องข้อความบนสไลด์ด้วยโปรแกรมด้วย Java

## การแนะนำ
การสร้างและจัดการการนำเสนอ PowerPoint ด้วยโปรแกรมสามารถเพิ่มประสิทธิภาพเวิร์กโฟลว์ต่างๆ ได้มากมาย ตั้งแต่การสร้างรายงานไปจนถึงการนำเสนออัตโนมัติ Aspose.Slides สำหรับ Java มอบ API ที่ทรงพลังซึ่งช่วยให้ผู้พัฒนาสามารถดำเนินการงานเหล่านี้ได้อย่างมีประสิทธิภาพ ในบทช่วยสอนนี้ เราจะแนะนำคุณเกี่ยวกับการเพิ่มกล่องข้อความลงในสไลด์โดยใช้ Aspose.Slides สำหรับ Java เมื่ออ่านบทช่วยสอนนี้จบ คุณจะเข้าใจอย่างชัดเจนว่าจะผสานฟังก์ชันนี้เข้ากับแอปพลิเคชัน Java ของคุณได้อย่างไร
## ข้อกำหนดเบื้องต้น
ก่อนที่เราจะเริ่ม ให้แน่ใจว่าคุณมีสิ่งต่อไปนี้:
- ติดตั้ง Java Development Kit (JDK) แล้ว
- IDE (Integrated Development Environment) เช่น IntelliJ IDEA หรือ Eclipse
- Aspose.Slides สำหรับไลบรารี Java คุณสามารถดาวน์โหลดได้จาก [ที่นี่](https://releases.aspose.com/slides/java/)
- ความรู้พื้นฐานเกี่ยวกับการเขียนโปรแกรมภาษา Java
## แพ็คเกจนำเข้า
ขั้นแรก นำเข้าแพ็คเกจที่จำเป็นจาก Aspose.Slides และไลบรารีหลักของ Java เพื่อเริ่มการเขียนโค้ด
```java
import com.aspose.slides.*;
import java.io.File;
```
## ขั้นตอนที่ 1: ตั้งค่าโครงการของคุณ
สร้างโปรเจ็กต์ Java ใหม่ใน IDE ของคุณ และเพิ่มไลบรารี Aspose.Slides สำหรับ Java ลงในเส้นทางการสร้างโปรเจ็กต์ของคุณ หากคุณยังไม่ได้ดาวน์โหลด ให้ดาวน์โหลดจาก [ที่นี่](https://releases-aspose.com/slides/java/).
## ขั้นตอนที่ 2: เริ่มต้นวัตถุการนำเสนอ
เริ่มต้น `Presentation` วัตถุซึ่งแสดงถึงไฟล์ PowerPoint
```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
```
## ขั้นตอนที่ 3: เข้าถึงสไลด์และเพิ่มรูปร่างอัตโนมัติ
รับสไลด์แรกจากการนำเสนอและเพิ่มรูปร่างอัตโนมัติ (สี่เหลี่ยมผืนผ้า) ลงไป
```java
ISlide slide = pres.getSlides().get_Item(0);
IAutoShape shape = slide.getShapes().addAutoShape(ShapeType.Rectangle, 150, 75, 150, 50);
```
## ขั้นตอนที่ 4: เพิ่มกรอบข้อความลงใน AutoShape
เพิ่มกรอบข้อความลงใน AutoShape เพื่อใส่ข้อความ
```java
shape.addTextFrame(" ");
ITextFrame textFrame = shape.getTextFrame();
```
## ขั้นตอนที่ 5: ตั้งค่าเนื้อหาข้อความ
กำหนดเนื้อหาข้อความภายในกรอบข้อความ
```java
IParagraph para = textFrame.getParagraphs().get_Item(0);
IPortion portion = para.getPortions().get_Item(0);
portion.setText("Aspose TextBox");
```
## ขั้นตอนที่ 6: บันทึกการนำเสนอ
บันทึกงานนำเสนอที่แก้ไขแล้วลงในไฟล์
```java
pres.save(dataDir + "TextBox_out.pptx", SaveFormat.Pptx);
```

## บทสรุป
ในบทช่วยสอนนี้ เราได้ศึกษาวิธีการเพิ่มกล่องข้อความลงในสไลด์โดยใช้โปรแกรม Aspose.Slides สำหรับ Java ความสามารถนี้ช่วยให้นักพัฒนาสามารถสร้างและปรับแต่งการนำเสนอ PowerPoint โดยอัตโนมัติ ซึ่งช่วยเพิ่มประสิทธิภาพและประสิทธิผลในแอปพลิเคชันต่างๆ
## คำถามที่พบบ่อย
### Aspose.Slides สำหรับ Java สามารถจัดการรูปทรงอื่น ๆ นอกเหนือจากรูปสี่เหลี่ยมผืนผ้าได้หรือไม่
ใช่ Aspose.Slides รองรับรูปทรงต่างๆ เช่น วงกลม เส้น และอื่นๆ อีกมากมาย
### Aspose.Slides สำหรับ Java เหมาะกับแอปพลิเคชันองค์กรขนาดใหญ่หรือไม่
แน่นอน มันได้รับการออกแบบมาเพื่อจัดการกับงานที่ซับซ้อนอย่างมีประสิทธิภาพ
### ฉันสามารถหาตัวอย่างและเอกสารประกอบเพิ่มเติมสำหรับ Aspose.Slides ได้จากที่ใด
เยี่ยมชม [เอกสารประกอบ Aspose.Slides](https://reference.aspose.com/slides/java/) สำหรับคำแนะนำและตัวอย่างที่ครอบคลุม
### ฉันจะได้รับใบอนุญาตชั่วคราวเพื่อการทดสอบได้อย่างไร?
คุณสามารถรับได้ [ใบอนุญาตชั่วคราว](https://purchase.aspose.com/temporary-license/) จาก Aspose
### Aspose.Slides รองรับการแปลงงานนำเสนอเป็นรูปแบบอื่นหรือไม่
ใช่ รองรับรูปแบบต่างๆ รวมถึง PDF และรูปภาพ

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}