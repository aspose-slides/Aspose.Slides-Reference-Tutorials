---
title: เพิ่มตัวยกและข้อความตัวห้อยใน Java PowerPoint
linktitle: เพิ่มตัวยกและข้อความตัวห้อยใน Java PowerPoint
second_title: Aspose.Slides Java PowerPoint การประมวลผล API
description: เรียนรู้วิธีเพิ่มข้อความตัวยกและตัวห้อยในงานนำเสนอ Java PowerPoint โดยใช้ Aspose.Slides สำหรับ Java เหมาะสำหรับเพิ่มสไลด์ของคุณ
weight: 13
url: /th/java/java-powerpoint-text-box-manipulation/add-superscript-subscript-text-java-powerpoint/
---

{< blocks/products/pf/main-wrap-class >}
{< blocks/products/pf/main-container >}
{< blocks/products/pf/tutorial-page-section >}

## การแนะนำ
การสร้างงานนำเสนอ PowerPoint ที่น่าดึงดูดและให้ข้อมูลมักต้องใช้ฟีเจอร์การจัดรูปแบบ เช่น ตัวยกและข้อความตัวห้อย บทช่วยสอนนี้จะแนะนำคุณตลอดกระบวนการรวมข้อความตัวยกและตัวห้อยลงในงานนำเสนอ Java PowerPoint ของคุณโดยใช้ Aspose.Slides สำหรับ Java
## ข้อกำหนดเบื้องต้น
ก่อนที่คุณจะเริ่มต้น ตรวจสอบให้แน่ใจว่าคุณมีสิ่งต่อไปนี้:
- ติดตั้ง Java Development Kit (JDK) บนระบบของคุณ
-  Aspose.Slides สำหรับไลบรารี Java คุณสามารถดาวน์โหลดได้จาก[ที่นี่](https://releases.aspose.com/slides/java/).
- สภาพแวดล้อมการพัฒนาแบบรวม (IDE) เช่น IntelliJ IDEA หรือ Eclipse ที่ตั้งค่าไว้สำหรับการพัฒนา Java
- ความคุ้นเคยขั้นพื้นฐานกับการเขียนโปรแกรม Java และการนำเสนอ PowerPoint

## แพ็คเกจนำเข้า
ขั้นแรก นำเข้าแพ็คเกจที่จำเป็นจาก Aspose.Slides สำหรับ Java:
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
// สร้างรูปร่างอัตโนมัติเพื่อใช้เป็นกล่องข้อความ
IAutoShape shape = slide.getShapes().addAutoShape(ShapeType.Rectangle, 100, 100, 200, 100);
ITextFrame textFrame = shape.getTextFrame();
textFrame.getParagraphs().clear();
```
## ขั้นตอนที่ 4: เพิ่มข้อความตัวยก
```java
// สร้างย่อหน้าสำหรับข้อความหลัก
IParagraph mainParagraph = new Paragraph();
IPortion mainPortion = new Portion();
mainPortion.setText("SlideTitle");
mainParagraph.getPortions().add(mainPortion);
// สร้างส่วนสำหรับข้อความตัวยก
IPortion superPortion = new Portion();
superPortion.getPortionFormat().setEscapement(30); // ตั้งค่าการหลบหนีสำหรับตัวยก
superPortion.setText("TM");
mainParagraph.getPortions().add(superPortion);
//เพิ่มย่อหน้าหลักที่มีตัวยกลงในกล่องข้อความ
textFrame.getParagraphs().add(mainParagraph);
```
## ขั้นตอนที่ 5: เพิ่มข้อความตัวห้อย
```java
// สร้างย่อหน้าอื่นสำหรับข้อความตัวห้อย
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
ในบทช่วยสอนนี้ เราได้สำรวจวิธีปรับปรุงงานนำเสนอ Java PowerPoint ของคุณด้วยข้อความตัวยกและตัวห้อยโดยใช้ Aspose.Slides สำหรับ Java เมื่อทำตามขั้นตอนเหล่านี้ คุณจะสามารถสร้างสไลด์ที่ดึงดูดสายตาและให้ข้อมูลมากขึ้น ซึ่งสื่อสารเนื้อหาของคุณได้อย่างมีประสิทธิภาพ

## คำถามที่พบบ่อย
### Aspose.Slides สำหรับ Java คืออะไร
Aspose.Slides สำหรับ Java เป็นไลบรารีที่มีประสิทธิภาพซึ่งช่วยให้นักพัฒนาสามารถสร้าง จัดการ และแปลงงานนำเสนอ PowerPoint โดยทางโปรแกรม
### ฉันจะหาเอกสารเพิ่มเติมเกี่ยวกับ Aspose.Slides สำหรับ Java ได้ที่ไหน
 สามารถดูเอกสารรายละเอียดได้[ที่นี่](https://reference.aspose.com/slides/java/).
### ฉันจะขอรับใบอนุญาตชั่วคราวสำหรับ Aspose.Slides สำหรับ Java ได้อย่างไร
 คุณสามารถรับใบอนุญาตชั่วคราวได้[ที่นี่](https://purchase.aspose.com/temporary-license/).
### ฉันสามารถลองใช้ Aspose.Slides สำหรับ Java ได้ฟรีหรือไม่
 ใช่ คุณสามารถดาวน์โหลดเวอร์ชันทดลองใช้ฟรีได้จาก[ที่นี่](https://releases.aspose.com/).
### ฉันจะรับการสนับสนุนสำหรับ Aspose.Slides สำหรับ Java ได้ที่ไหน
 สำหรับการสนับสนุนและการสนทนาโปรดไปที่[ฟอรั่ม Aspose.Slides](https://forum.aspose.com/c/slides/11).
{< /blocks/products/pf/tutorial-page-section >}

{< /blocks/products/pf/main-container >}
{< /blocks/products/pf/main-wrap-class >}

{< blocks/products/products-backtop-button >}
