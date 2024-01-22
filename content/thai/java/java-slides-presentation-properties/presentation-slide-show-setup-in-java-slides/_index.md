---
title: การตั้งค่าการนำเสนอสไลด์การนำเสนอใน Java Slides
linktitle: การตั้งค่าการนำเสนอสไลด์การนำเสนอใน Java Slides
second_title: Aspose.Slides Java PowerPoint การประมวลผล API
description: เพิ่มประสิทธิภาพการนำเสนอสไลด์ Java ของคุณด้วย Aspose.Slides สร้างงานนำเสนอที่น่าสนใจด้วยการตั้งค่าแบบกำหนดเอง สำรวจคำแนะนำทีละขั้นตอนและคำถามที่พบบ่อย
type: docs
weight: 16
url: /th/java/presentation-properties/presentation-slide-show-setup-in-java-slides/
---

## รู้เบื้องต้นเกี่ยวกับการตั้งค่าการนำเสนอสไลด์การนำเสนอใน Java Slides

ในบทช่วยสอนนี้ เราจะสำรวจวิธีตั้งค่าการนำเสนอสไลด์การนำเสนอโดยใช้ Aspose.Slides สำหรับ Java เราจะอธิบายกระบวนการสร้างงานนำเสนอ PowerPoint แบบทีละขั้นตอนและกำหนดการตั้งค่าสไลด์โชว์ต่างๆ

## ข้อกำหนดเบื้องต้น

 ก่อนที่คุณจะเริ่มต้น ตรวจสอบให้แน่ใจว่าคุณได้เพิ่มไลบรารี Aspose.Slides สำหรับ Java ลงในโปรเจ็กต์ของคุณแล้ว คุณสามารถดาวน์โหลดได้จาก[เว็บไซต์กำหนด](https://releases.aspose.com/slides/java/).

## ขั้นตอนที่ 1: สร้างงานนำเสนอ PowerPoint

ขั้นแรก เราต้องสร้างงานนำเสนอ PowerPoint ใหม่ นี่คือวิธีที่คุณสามารถทำได้ใน Java:

```java
String outPptxPath = RunExamples.getOutPath() + "PresentationSlideShowSetup.pptx";
Presentation pres = new Presentation();
```

 ในโค้ดด้านบน เราระบุเส้นทางของไฟล์เอาต์พุตสำหรับการนำเสนอของเราและสร้างเส้นทางใหม่`Presentation` วัตถุ.

## ขั้นตอนที่ 2: กำหนดการตั้งค่าการนำเสนอสไลด์

ต่อไป เราจะกำหนดการตั้งค่าสไลด์โชว์ต่างๆ สำหรับการนำเสนอของเรา 

### ใช้พารามิเตอร์กำหนดเวลา

เราสามารถตั้งค่าพารามิเตอร์ "การใช้ระยะเวลา" เพื่อควบคุมว่าสไลด์จะเลื่อนโดยอัตโนมัติหรือด้วยตนเองในระหว่างการแสดงสไลด์

```java
SlideShowSettings slideShow = pres.getSlideShowSettings();
slideShow.setUseTimings(false); // ตั้งค่าเป็นเท็จสำหรับการเลื่อนล่วงหน้าด้วยตนเอง
```

 ในตัวอย่างนี้ เราได้ตั้งค่าเป็น`false` เพื่อให้สามารถเลื่อนสไลด์ด้วยตนเองได้

### ตั้งค่าสีปากกา

คุณยังสามารถปรับแต่งสีปากกาที่ใช้ระหว่างการนำเสนอสไลด์ได้อีกด้วย ในตัวอย่างนี้ เราจะตั้งค่าสีปากกาเป็นสีเขียว

```java
IColorFormat penColor = (ColorFormat)slideShow.getPenColor();
penColor.setColor(Color.GREEN);
```

### เพิ่มสไลด์

มาเพิ่มสไลด์ในการนำเสนอของเรากัน เราจะโคลนสไลด์ที่มีอยู่เพื่อให้ทุกอย่างง่ายขึ้น

```java
pres.getSlides().addClone(pres.getSlides().get_Item(0));
pres.getSlides().addClone(pres.getSlides().get_Item(0));
pres.getSlides().addClone(pres.getSlides().get_Item(0));
pres.getSlides().addClone(pres.getSlides().get_Item(0));
```

ในโค้ดนี้ เรากำลังโคลนสไลด์แรกสี่ครั้ง คุณสามารถแก้ไขส่วนนี้เพื่อเพิ่มเนื้อหาของคุณเองได้

## ขั้นตอนที่ 3: กำหนดช่วงสไลด์สำหรับการนำเสนอสไลด์

คุณสามารถระบุสไลด์ที่ควรรวมไว้ในการนำเสนอสไลด์ได้ ในตัวอย่างนี้ เราจะตั้งค่าช่วงของสไลด์ตั้งแต่สไลด์ที่สองถึงสไลด์ที่ห้า

```java
SlidesRange slidesRange = new SlidesRange();
slidesRange.setStart(2);
slidesRange.setEnd(5);
slideShow.setSlides(slidesRange);
```

ด้วยการตั้งค่าหมายเลขสไลด์เริ่มต้นและสิ้นสุด คุณสามารถควบคุมได้ว่าสไลด์ใดที่จะเป็นส่วนหนึ่งของการนำเสนอสไลด์

## ขั้นตอนที่ 4: บันทึกการนำเสนอ

สุดท้าย เราจะบันทึกงานนำเสนอที่กำหนดค่าไว้เป็นไฟล์

```java
pres.save(outPptxPath, SaveFormat.Pptx);
```

ตรวจสอบให้แน่ใจว่าได้ระบุเส้นทางไฟล์เอาต์พุตที่ต้องการ

## ซอร์สโค้ดที่สมบูรณ์สำหรับการตั้งค่าการนำเสนอภาพนิ่งการนำเสนอใน Java Slides

```java
String outPptxPath = RunExamples.getOutPath() + "PresentationSlideShowSetup.pptx";
Presentation pres = new Presentation();
try {
	// รับการตั้งค่าสไลด์โชว์
	SlideShowSettings slideShow = pres.getSlideShowSettings();
	// ตั้งค่าพารามิเตอร์ "การใช้ Timing"
	slideShow.setUseTimings(false);
	// ตั้งค่าสีปากกา
	IColorFormat penColor = (ColorFormat)slideShow.getPenColor();
	penColor.setColor(Color.GREEN);
	// เพิ่มสไลด์สำหรับ
	pres.getSlides().addClone(pres.getSlides().get_Item(0));
	pres.getSlides().addClone(pres.getSlides().get_Item(0));
	pres.getSlides().addClone(pres.getSlides().get_Item(0));
	pres.getSlides().addClone(pres.getSlides().get_Item(0));
	// ตั้งค่าพารามิเตอร์แสดงสไลด์
	SlidesRange slidesRange = new SlidesRange();
	slidesRange.setStart(2);
	slidesRange.setEnd(5);
	slideShow.setSlides(slidesRange);
	// บันทึกการนำเสนอ
	pres.save(outPptxPath, SaveFormat.Pptx);
} finally {
	if (pres != null) pres.dispose();
}
```

## บทสรุป

ในบทช่วยสอนนี้ เราได้เรียนรู้วิธีตั้งค่าการนำเสนอสไลด์การนำเสนอใน Java โดยใช้ Aspose.Slides สำหรับ Java คุณสามารถปรับแต่งการตั้งค่าการนำเสนอสไลด์ต่างๆ รวมถึงการกำหนดเวลา สีปากกา และช่วงสไลด์ เพื่อสร้างงานนำเสนอเชิงโต้ตอบและน่าดึงดูด

## คำถามที่พบบ่อย

### ฉันจะเปลี่ยนระยะเวลาในการเปลี่ยนสไลด์ได้อย่างไร

 หากต้องการเปลี่ยนระยะเวลาสำหรับการเปลี่ยนสไลด์ คุณสามารถแก้ไขพารามิเตอร์ "การใช้ระยะเวลา" ในการตั้งค่าการนำเสนอสไลด์ได้ ตั้งเป็น`true` เพื่อความก้าวหน้าอัตโนมัติตามกำหนดเวลาที่กำหนดไว้ล่วงหน้าหรือ`false`สำหรับการเลื่อนแบบแมนนวลในระหว่างการแสดงสไลด์

### ฉันจะปรับแต่งสีปากกาที่ใช้ในการแสดงสไลด์ได้อย่างไร

 คุณสามารถปรับแต่งสีปากกาได้โดยเข้าไปที่การตั้งค่าสีปากกาในการตั้งค่าสไลด์โชว์ ใช้`setColor` วิธีการตั้งค่าสีที่ต้องการ ตัวอย่างเช่น หากต้องการตั้งค่าสีปากกาเป็นสีเขียว ให้ใช้`penColor.setColor(Color.GREEN)`.

### ฉันจะเพิ่มสไลด์เฉพาะลงในการนำเสนอสไลด์ได้อย่างไร

 หากต้องการรวมสไลด์เฉพาะในการนำเสนอสไลด์ ให้สร้าง`SlidesRange` object และตั้งค่าหมายเลขสไลด์เริ่มต้นและสิ้นสุดโดยใช้`setStart` และ`setEnd` วิธีการ จากนั้น กำหนดช่วงนี้ให้กับการตั้งค่าการนำเสนอสไลด์โดยใช้`slideShow.setSlides(slidesRange)`.

### ฉันสามารถเพิ่มสไลด์ในงานนำเสนอได้หรือไม่

 ใช่ คุณสามารถเพิ่มสไลด์เพิ่มเติมในงานนำเสนอของคุณได้ ใช้`pres.getSlides().addClone()` วิธีการโคลนสไลด์ที่มีอยู่หรือสร้างสไลด์ใหม่ตามต้องการ ตรวจสอบให้แน่ใจว่าได้ปรับแต่งเนื้อหาของสไลด์เหล่านี้ตามความต้องการของคุณ

### ฉันจะบันทึกงานนำเสนอที่กำหนดค่าไว้ลงในไฟล์ได้อย่างไร

 หากต้องการบันทึกงานนำเสนอที่กำหนดค่าไว้เป็นไฟล์ ให้ใช้`pres.save()`และระบุเส้นทางไฟล์เอาต์พุตพร้อมรูปแบบที่ต้องการ ตัวอย่างเช่น คุณสามารถบันทึกในรูปแบบ PPTX โดยใช้`pres.save(outPptxPath, SaveFormat.Pptx)`.

### ฉันจะปรับแต่งการตั้งค่าสไลด์โชว์เพิ่มเติมได้อย่างไร

 คุณสามารถสำรวจการตั้งค่าการนำเสนอสไลด์เพิ่มเติมที่ Aspose.Slides สำหรับ Java มอบให้ เพื่อปรับแต่งประสบการณ์การนำเสนอสไลด์ให้ตรงตามความต้องการของคุณ อ้างอิงเอกสารประกอบได้ที่[ที่นี่](https://reference.aspose.com/slides/java/) สำหรับข้อมูลโดยละเอียดเกี่ยวกับตัวเลือกและการกำหนดค่าที่มี