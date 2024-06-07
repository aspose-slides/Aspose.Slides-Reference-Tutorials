---
title: รับพิกัดสี่เหลี่ยมของย่อหน้าใน Java Slides
linktitle: รับพิกัดสี่เหลี่ยมของย่อหน้าใน Java Slides
second_title: Aspose.Slides Java PowerPoint การประมวลผล API
description: เรียนรู้วิธีดึงพิกัดย่อหน้าในงานนำเสนอ PowerPoint โดยใช้ Aspose.Slides สำหรับ Java ปฏิบัติตามคำแนะนำทีละขั้นตอนพร้อมซอร์สโค้ดเพื่อการวางตำแหน่งที่แม่นยำ
type: docs
weight: 13
url: /th/java/additional-utilities/get-rectangular-coordinates-of-paragraph-in-java-slides/
---

## ข้อมูลเบื้องต้นเกี่ยวกับการดึงพิกัดสี่เหลี่ยมของย่อหน้าใน Aspose.Slides สำหรับ Java

ในบทช่วยสอนนี้ เราจะสาธิตวิธีการดึงพิกัดสี่เหลี่ยมของย่อหน้าภายในงานนำเสนอ PowerPoint โดยใช้ Aspose.Slides สำหรับ Java API เมื่อทำตามขั้นตอนด้านล่าง คุณจะได้รับตำแหน่งและขนาดของย่อหน้าภายในสไลด์โดยทางโปรแกรม

## ข้อกำหนดเบื้องต้น

ก่อนที่เราจะเริ่มต้น ตรวจสอบให้แน่ใจว่าคุณได้ติดตั้งและตั้งค่าไลบรารี Aspose.Slides สำหรับ Java ในสภาพแวดล้อมการพัฒนา Java ของคุณแล้ว คุณสามารถดาวน์โหลดได้จาก[ที่นี่](https://downloads.aspose.com/slides/java).

## ขั้นตอนที่ 1: นำเข้าไลบรารีที่จำเป็น

ในการเริ่มต้น ให้นำเข้าไลบรารีที่จำเป็นสำหรับการทำงานกับ Aspose.Slides ในโปรเจ็กต์ Java ของคุณ:

```java
import com.aspose.slides.*;
import java.awt.geom.Rectangle2D;
```

## ขั้นตอนที่ 2: โหลดงานนำเสนอ

ในขั้นตอนนี้ เราจะโหลดงานนำเสนอ PowerPoint ที่มีย่อหน้าซึ่งมีพิกัดที่เราต้องการดึงข้อมูล

```java
// เส้นทางไปยังไฟล์งานนำเสนอ PowerPoint
String presentationPath = "YourPresentation.pptx";

// โหลดงานนำเสนอ
Presentation presentation = new Presentation(presentationPath);
```

 ตรวจสอบให้แน่ใจว่าได้เปลี่ยน`"YourPresentation.pptx"` พร้อมเส้นทางจริงไปยังไฟล์ PowerPoint ของคุณ

## ขั้นตอนที่ 3: ดึงพิกัดย่อหน้า

ตอนนี้ เราจะเข้าถึงย่อหน้าใดย่อหน้าภายในสไลด์ แยกพิกัดสี่เหลี่ยมของสไลด์ออก และพิมพ์ผลลัพธ์

```java
try {
 try
{
	IAutoShape shape = (IAutoShape) presentation.getSlides().get_Item(0).getShapes().get_Item(0);
	ITextFrame textFrame = shape.getTextFrame();
	Rectangle2D.Float rect = (textFrame.getParagraphs().get_Item(0)).getRect();
}
finally
{
	if (presentation != null) presentation.dispose();
}
```

## กรอกซอร์สโค้ดเพื่อรับพิกัดสี่เหลี่ยมของย่อหน้าใน Java Slides

```java
// เส้นทางไปยังไดเร็กทอรีเอกสาร
String dataDir = "Your Document Directory";
// สร้างอินสแตนซ์วัตถุการนำเสนอที่แสดงถึงไฟล์การนำเสนอ
Presentation presentation = new Presentation(dataDir + "Shapes.pptx");
try
{
	IAutoShape shape = (IAutoShape) presentation.getSlides().get_Item(0).getShapes().get_Item(0);
	ITextFrame textFrame = shape.getTextFrame();
	Rectangle2D.Float rect = (textFrame.getParagraphs().get_Item(0)).getRect();
}
finally
{
	if (presentation != null) presentation.dispose();
}
```

ข้อมูลโค้ดนี้จะดึงพิกัดสี่เหลี่ยม (X, Y, ความกว้าง และความสูง) ของย่อหน้าแรกภายในรูปร่างแรกของสไลด์แรก คุณสามารถแก้ไขดัชนีเพื่อเข้าถึงย่อหน้าภายในรูปร่างหรือสไลด์ต่างๆ ได้ตามต้องการ

## บทสรุป

ในบทช่วยสอนนี้ คุณได้เรียนรู้วิธีใช้ Aspose.Slides สำหรับ Java เพื่อดึงพิกัดสี่เหลี่ยมของย่อหน้าภายในงานนำเสนอ PowerPoint สิ่งนี้มีประโยชน์เมื่อคุณต้องการวิเคราะห์หรือจัดการตำแหน่งและขนาดของข้อความภายในสไลด์ของคุณโดยทางโปรแกรม

## คำถามที่พบบ่อย

### ฉันจะเข้าถึงย่อหน้าภายในสไลด์ PowerPoint ได้อย่างไร

หากต้องการเข้าถึงย่อหน้าภายในสไลด์ PowerPoint โดยใช้ Aspose.Slides สำหรับ Java ให้ทำตามขั้นตอนเหล่านี้:
1. โหลดงานนำเสนอ PowerPoint
2.  รับสไลด์ที่ต้องการโดยใช้`presentation.getSlides().get_Item(slideIndex)`.
3.  เข้าถึงรูปร่างที่มีข้อความโดยใช้`slide.getShapes().get_Item(shapeIndex)`.
4.  ดึงกรอบข้อความของรูปร่างโดยใช้`shape.getTextFrame()`.
5.  เข้าถึงย่อหน้าภายในกรอบข้อความโดยใช้`textFrame.getParagraphs().get_Item(paragraphIndex)`.

### ฉันสามารถดึงพิกัดของย่อหน้าในหลายสไลด์ได้หรือไม่

ได้ คุณสามารถดึงข้อมูลพิกัดของย่อหน้าในหลายสไลด์ได้โดยการวนซ้ำสไลด์และรูปร่างต่างๆ ตามต้องการ เพียงทำซ้ำขั้นตอนการเข้าถึงย่อหน้าภายในรูปร่างของแต่ละสไลด์เพื่อให้ได้พิกัด

### ฉันจะจัดการพิกัดย่อหน้าโดยทางโปรแกรมได้อย่างไร

เมื่อคุณดึงข้อมูลพิกัดของย่อหน้าแล้ว คุณสามารถใช้ข้อมูลนี้เพื่อจัดการตำแหน่งและขนาดของย่อหน้าโดยทางโปรแกรมได้ ตัวอย่างเช่น คุณสามารถเปลี่ยนตำแหน่งย่อหน้า ปรับความกว้างหรือความสูงของย่อหน้า หรือคำนวณตามพิกัดของย่อหน้าได้

### Aspose.Slides เหมาะสำหรับการประมวลผลไฟล์ PowerPoint เป็นชุดหรือไม่

ใช่ Aspose.Slides สำหรับ Java เหมาะอย่างยิ่งสำหรับการประมวลผลไฟล์ PowerPoint เป็นชุด คุณสามารถทำงานอัตโนมัติ เช่น การแยกข้อมูล การแก้ไขเนื้อหา หรือการสร้างรายงานจากงานนำเสนอ PowerPoint หลายรายการได้อย่างมีประสิทธิภาพ

### ฉันจะหาตัวอย่างและเอกสารประกอบเพิ่มเติมได้ที่ไหน

 คุณสามารถค้นหาตัวอย่างโค้ดเพิ่มเติมและเอกสารประกอบโดยละเอียดสำหรับ Aspose.Slides สำหรับ Java ได้ที่[เอกสาร Aspose.Slides](https://reference.aspose.com/slides/java/)เว็บไซต์. นอกจากนี้คุณยังสามารถสำรวจ[ฟอรั่ม Aspose.Slides](https://forum.aspose.com/c/slides) สำหรับการสนับสนุนและการอภิปรายของชุมชน

### ฉันต้องมีใบอนุญาตเพื่อใช้ Aspose.Slides สำหรับ Java หรือไม่

ใช่ โดยทั่วไปคุณจะต้องมีใบอนุญาตที่ถูกต้องเพื่อใช้ Aspose.Slides สำหรับ Java ในสภาพแวดล้อมการใช้งานจริง คุณสามารถขอรับใบอนุญาตได้จากเว็บไซต์ Aspose อย่างไรก็ตาม พวกเขาอาจเสนอเวอร์ชันทดลองใช้งานเพื่อวัตถุประสงค์ในการทดสอบและประเมินผล