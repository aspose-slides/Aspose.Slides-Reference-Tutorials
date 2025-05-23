---
"description": "เรียนรู้วิธีการเพิ่มข้อความแบบยกกำลังและแบบลงท้ายในงานนำเสนอ PowerPoint ที่ใช้ Java โดยใช้ Aspose.Slides สำหรับ Java เหมาะอย่างยิ่งสำหรับการปรับปรุงสไลด์ของคุณ"
"linktitle": "เพิ่มข้อความยกกำลังและตัวห้อยใน Java PowerPoint"
"second_title": "API การประมวลผล Java PowerPoint ของ Aspose.Slides"
"title": "เพิ่มข้อความยกกำลังและตัวห้อยใน Java PowerPoint"
"url": "/th/java/java-powerpoint-text-box-manipulation/add-superscript-subscript-text-java-powerpoint/"
"weight": 13
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# เพิ่มข้อความยกกำลังและตัวห้อยใน Java PowerPoint

## การแนะนำ
การสร้างงานนำเสนอ PowerPoint ที่น่าสนใจและให้ข้อมูลมักต้องใช้คุณลักษณะการจัดรูปแบบ เช่น ข้อความยกกำลังและข้อความลงท้าย บทช่วยสอนนี้จะแนะนำคุณเกี่ยวกับกระบวนการรวมข้อความยกกำลังและข้อความลงท้ายในงานนำเสนอ PowerPoint ที่ใช้ Java โดยใช้ Aspose.Slides สำหรับ Java
## ข้อกำหนดเบื้องต้น
ก่อนที่คุณจะเริ่มต้น ให้แน่ใจว่าคุณมีสิ่งต่อไปนี้:
- Java Development Kit (JDK) ติดตั้งอยู่บนระบบของคุณ
- Aspose.Slides สำหรับไลบรารี Java คุณสามารถดาวน์โหลดได้จาก [ที่นี่](https://releases-aspose.com/slides/java/).
- สภาพแวดล้อมการพัฒนาแบบบูรณาการ (IDE) เช่น IntelliJ IDEA หรือ Eclipse ที่ถูกตั้งค่าสำหรับการพัฒนา Java
- ความคุ้นเคยเบื้องต้นกับการเขียนโปรแกรม Java และการนำเสนอ PowerPoint

## แพ็คเกจนำเข้า
ขั้นตอนแรก นำเข้าแพ็คเกจที่จำเป็นจาก Aspose.Slides สำหรับ Java:
```java
import com.aspose.slides.*;
```
## ขั้นตอนที่ 1: ตั้งค่าการนำเสนอ
```java
// เส้นทางไปยังไดเร็กทอรีเอกสาร
String dataDir = "Your Document Directory";
Presentation presentation = new Presentation();
```
## ขั้นตอนที่ 2: เข้าถึงสไลด์
```java
// รับสไลด์แรก
ISlide slide = presentation.getSlides().get_Item(0);
```
## ขั้นตอนที่ 3: สร้างกล่องข้อความ
```java
// สร้าง AutoShape เพื่อใช้เป็นกล่องข้อความ
IAutoShape shape = slide.getShapes().addAutoShape(ShapeType.Rectangle, 100, 100, 200, 100);
ITextFrame textFrame = shape.getTextFrame();
textFrame.getParagraphs().clear();
```
## ขั้นตอนที่ 4: เพิ่มข้อความยกกำลัง
```java
// สร้างย่อหน้าสำหรับข้อความหลัก
IParagraph mainParagraph = new Paragraph();
IPortion mainPortion = new Portion();
mainPortion.setText("SlideTitle");
mainParagraph.getPortions().add(mainPortion);
// สร้างส่วนสำหรับข้อความยกกำลัง
IPortion superPortion = new Portion();
superPortion.getPortionFormat().setEscapement(30); // ตั้งค่าการหนีภัยสำหรับตัวห้อย
superPortion.setText("TM");
mainParagraph.getPortions().add(superPortion);
// เพิ่มย่อหน้าหลักด้วยอักษรยกกำลังในกล่องข้อความ
textFrame.getParagraphs().add(mainParagraph);
```
## ขั้นตอนที่ 5: เพิ่มข้อความตัวห้อย
```java
// สร้างย่อหน้าใหม่สำหรับข้อความตัวห้อย
IParagraph subscriptParagraph = new Paragraph();
IPortion subscriptPortion = new Portion();
subscriptPortion.setText("a");
subscriptParagraph.getPortions().add(subscriptPortion);
// สร้างส่วนสำหรับข้อความตัวห้อย
IPortion subPortion = new Portion();
subPortion.getPortionFormat().setEscapement(-25); // ตั้งค่าการหลบหนีสำหรับตัวห้อย
subPortion.setText("i");
subscriptParagraph.getPortions().add(subPortion);
// เพิ่มย่อหน้าตัวห้อยลงในกล่องข้อความ
textFrame.getParagraphs().add(subscriptParagraph);
```
## ขั้นตอนที่ 6: บันทึกการนำเสนอ
```java
// บันทึกการนำเสนอ
presentation.save(dataDir + "TestOut.pptx", SaveFormat.Pptx);
```

## บทสรุป
ในบทช่วยสอนนี้ เราได้เรียนรู้วิธีปรับปรุงการนำเสนอ Java PowerPoint ของคุณด้วยข้อความแบบยกกำลังและแบบลงท้ายโดยใช้ Aspose.Slides สำหรับ Java เมื่อทำตามขั้นตอนเหล่านี้ คุณก็สามารถสร้างสไลด์ที่ดึงดูดสายตาและให้ข้อมูลมากขึ้นเพื่อสื่อสารเนื้อหาของคุณได้อย่างมีประสิทธิภาพ

## คำถามที่พบบ่อย
### Aspose.Slides สำหรับ Java คืออะไร?
Aspose.Slides สำหรับ Java เป็นไลบรารีที่แข็งแกร่งที่ช่วยให้นักพัฒนาสามารถสร้าง จัดการ และแปลงการนำเสนอ PowerPoint ได้ด้วยโปรแกรม
### ฉันสามารถหาเอกสารเพิ่มเติมเกี่ยวกับ Aspose.Slides สำหรับ Java ได้ที่ไหน
สามารถดูเอกสารรายละเอียดได้ [ที่นี่](https://reference-aspose.com/slides/java/).
### ฉันจะรับใบอนุญาตชั่วคราวสำหรับ Aspose.Slides สำหรับ Java ได้อย่างไร
คุณสามารถรับใบอนุญาตชั่วคราวได้ [ที่นี่](https://purchase-aspose.com/temporary-license/).
### ฉันสามารถทดลองใช้ Aspose.Slides สำหรับ Java ได้ฟรีหรือไม่?
ใช่ คุณสามารถดาวน์โหลดเวอร์ชันทดลองใช้งานฟรีได้จาก [ที่นี่](https://releases-aspose.com/).
### ฉันจะได้รับการสนับสนุนสำหรับ Aspose.Slides สำหรับ Java ได้จากที่ไหน
สำหรับการสนับสนุนและการหารือ โปรดไปที่ [ฟอรั่ม Aspose.Slides](https://forum-aspose.com/c/slides/11).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}