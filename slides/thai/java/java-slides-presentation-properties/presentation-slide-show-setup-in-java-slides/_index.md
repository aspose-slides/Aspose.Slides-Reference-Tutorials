---
"description": "เพิ่มประสิทธิภาพ Java Slide Show ของคุณด้วย Aspose.Slides สร้างการนำเสนอที่น่าสนใจด้วยการตั้งค่าที่กำหนดเอง สำรวจคำแนะนำทีละขั้นตอนและคำถามที่พบบ่อย"
"linktitle": "การตั้งค่าการนำเสนอสไลด์โชว์ใน Java Slides"
"second_title": "API การประมวลผล Java PowerPoint ของ Aspose.Slides"
"title": "การตั้งค่าการนำเสนอสไลด์โชว์ใน Java Slides"
"url": "/th/java/presentation-properties/presentation-slide-show-setup-in-java-slides/"
"weight": 16
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# การตั้งค่าการนำเสนอสไลด์โชว์ใน Java Slides


## บทนำสู่การตั้งค่าการนำเสนอสไลด์ใน Java Slides

ในบทช่วยสอนนี้ เราจะมาเรียนรู้วิธีการตั้งค่าการนำเสนอแบบสไลด์โชว์โดยใช้ Aspose.Slides สำหรับ Java เราจะแนะนำขั้นตอนต่างๆ ในการสร้างการนำเสนอ PowerPoint และกำหนดค่าการตั้งค่าการนำเสนอแบบสไลด์โชว์ต่างๆ

## ข้อกำหนดเบื้องต้น

ก่อนเริ่มต้น ตรวจสอบให้แน่ใจว่าคุณได้เพิ่มไลบรารี Aspose.Slides สำหรับ Java ลงในโปรเจ็กต์ของคุณแล้ว คุณสามารถดาวน์โหลดได้จาก [เว็บไซต์อาโพส](https://releases-aspose.com/slides/java/).

## ขั้นตอนที่ 1: สร้างการนำเสนอ PowerPoint

ขั้นแรก เราต้องสร้างการนำเสนอ PowerPoint ใหม่ ซึ่งคุณสามารถทำได้ใน Java ดังนี้:

```java
String outPptxPath = "Your Output Directory" + "PresentationSlideShowSetup.pptx";
Presentation pres = new Presentation();
```

ในโค้ดด้านบนนี้ เราได้ระบุเส้นทางไฟล์เอาต์พุตสำหรับการนำเสนอของเราและสร้างใหม่ `Presentation` วัตถุ.

## ขั้นตอนที่ 2: กำหนดค่าการตั้งค่าการนำเสนอภาพนิ่ง

ต่อไปเราจะกำหนดค่าการตั้งค่าสไลด์โชว์ต่างๆ สำหรับการนำเสนอของเรา 

### ใช้พารามิเตอร์การกำหนดเวลา

เราสามารถตั้งค่าพารามิเตอร์ "การใช้เวลา" เพื่อควบคุมว่าสไลด์จะเลื่อนไปข้างหน้าโดยอัตโนมัติหรือด้วยตนเองระหว่างการนำเสนอสไลด์

```java
SlideShowSettings slideShow = pres.getSlideShowSettings();
slideShow.setUseTimings(false); // ตั้งค่าเป็นเท็จสำหรับการเลื่อนไปข้างหน้าด้วยตนเอง
```

ในตัวอย่างนี้เราได้ตั้งค่าไว้เป็น `false` เพื่อให้สามารถเลื่อนสไลด์ด้วยตนเองได้

### ตั้งค่าสีปากกา

คุณสามารถปรับแต่งสีปากกาที่ใช้ระหว่างการนำเสนอแบบสไลด์ได้ ในตัวอย่างนี้ เราจะตั้งค่าสีปากกาเป็นสีเขียว

```java
IColorFormat penColor = (ColorFormat)slideShow.getPenColor();
penColor.setColor(Color.GREEN);
```

### เพิ่มสไลด์

มาเพิ่มสไลด์ลงในงานนำเสนอของเรากันดีกว่า เราจะโคลนสไลด์ที่มีอยู่แล้วเพื่อให้ทุกอย่างดูเรียบง่าย

```java
pres.getSlides().addClone(pres.getSlides().get_Item(0));
pres.getSlides().addClone(pres.getSlides().get_Item(0));
pres.getSlides().addClone(pres.getSlides().get_Item(0));
pres.getSlides().addClone(pres.getSlides().get_Item(0));
```

ในโค้ดนี้ เราจะโคลนสไลด์แรกสี่ครั้ง คุณสามารถแก้ไขส่วนนี้เพื่อเพิ่มเนื้อหาของคุณเองได้

## ขั้นตอนที่ 3: กำหนดช่วงสไลด์สำหรับการนำเสนอสไลด์

คุณสามารถระบุสไลด์ที่จะรวมอยู่ในสไลด์โชว์ได้ ในตัวอย่างนี้ เราจะกำหนดช่วงของสไลด์ตั้งแต่สไลด์ที่สองไปจนถึงสไลด์ที่ห้า

```java
SlidesRange slidesRange = new SlidesRange();
slidesRange.setStart(2);
slidesRange.setEnd(5);
slideShow.setSlides(slidesRange);
```

การตั้งค่าหมายเลขสไลด์เริ่มต้นและสิ้นสุดจะช่วยให้คุณควบคุมได้ว่าสไลด์ใดจะเป็นส่วนหนึ่งของสไลด์โชว์

## ขั้นตอนที่ 4: บันทึกการนำเสนอ

สุดท้ายเราจะบันทึกการนำเสนอที่กำหนดค่าไว้ในไฟล์

```java
pres.save(outPptxPath, SaveFormat.Pptx);
```

ตรวจสอบให้แน่ใจว่าคุณระบุเส้นทางไฟล์เอาท์พุตตามที่ต้องการ

## โค้ดต้นฉบับสมบูรณ์สำหรับการตั้งค่าการนำเสนอแบบสไลด์โชว์ใน Java Slides

```java
String outPptxPath = "Your Output Directory" + "PresentationSlideShowSetup.pptx";
Presentation pres = new Presentation();
try {
	// รับการตั้งค่า SlideShow
	SlideShowSettings slideShow = pres.getSlideShowSettings();
	// ตั้งค่าพารามิเตอร์ "การใช้เวลา"
	slideShow.setUseTimings(false);
	// ตั้งค่าสีปากกา
	IColorFormat penColor = (ColorFormat)slideShow.getPenColor();
	penColor.setColor(Color.GREEN);
	// เพิ่มสไลด์สำหรับ
	pres.getSlides().addClone(pres.getSlides().get_Item(0));
	pres.getSlides().addClone(pres.getSlides().get_Item(0));
	pres.getSlides().addClone(pres.getSlides().get_Item(0));
	pres.getSlides().addClone(pres.getSlides().get_Item(0));
	// ตั้งค่าพารามิเตอร์การแสดงสไลด์
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

ในบทช่วยสอนนี้ เราได้เรียนรู้วิธีการตั้งค่าการนำเสนอแบบสไลด์โชว์ใน Java โดยใช้ Aspose.Slides สำหรับ Java คุณสามารถปรับแต่งการตั้งค่าการนำเสนอแบบสไลด์โชว์ต่างๆ ได้ เช่น กำหนดเวลา สีปากกา และช่วงของสไลด์ เพื่อสร้างการนำเสนอแบบโต้ตอบและน่าสนใจ

## คำถามที่พบบ่อย

### ฉันจะเปลี่ยนจังหวะเวลาการเปลี่ยนสไลด์ได้อย่างไร

หากต้องการเปลี่ยนเวลาการเปลี่ยนสไลด์ คุณสามารถแก้ไขพารามิเตอร์ "การใช้เวลา" ในการตั้งค่าสไลด์โชว์ได้ ตั้งค่าเป็น `true` เพื่อการเลื่อนไปข้างหน้าโดยอัตโนมัติด้วยเวลาที่กำหนดไว้ล่วงหน้าหรือ `false` สำหรับการเลื่อนไปข้างหน้าด้วยตนเองในระหว่างการแสดงสไลด์

### ฉันจะปรับแต่งสีปากกาที่ใช้ในระหว่างการแสดงสไลด์ได้อย่างไร

คุณสามารถปรับแต่งสีปากกาได้โดยเข้าถึงการตั้งค่าสีปากกาในการตั้งค่าสไลด์โชว์ ใช้ `setColor` วิธีการตั้งค่าสีที่ต้องการ เช่น หากต้องการตั้งค่าสีปากกาเป็นสีเขียว ให้ใช้ `penColor-setColor(Color.GREEN)`.

### ฉันจะเพิ่มสไลด์ที่เจาะจงลงในการนำเสนอสไลด์ได้อย่างไร

หากต้องการรวมสไลด์เฉพาะในการนำเสนอสไลด์ ให้สร้าง `SlidesRange` วัตถุและกำหนดหมายเลขสไลด์เริ่มต้นและสิ้นสุดโดยใช้ `setStart` และ `setEnd` วิธีการ จากนั้นกำหนดช่วงนี้ให้กับการตั้งค่าการนำเสนอสไลด์โดยใช้ `slideShow-setSlides(slidesRange)`.

### ฉันสามารถเพิ่มสไลด์เพิ่มเติมให้กับการนำเสนอได้หรือไม่

ใช่ คุณสามารถเพิ่มสไลด์เพิ่มเติมลงในงานนำเสนอของคุณได้ ใช้ `pres.getSlides().addClone()` วิธีการโคลนสไลด์ที่มีอยู่หรือสร้างสไลด์ใหม่ตามต้องการ ตรวจสอบให้แน่ใจว่าคุณปรับแต่งเนื้อหาของสไลด์เหล่านี้ตามความต้องการของคุณ

### ฉันจะบันทึกการนำเสนอที่กำหนดค่าไว้ในไฟล์ได้อย่างไร

หากต้องการบันทึกการนำเสนอที่กำหนดค่าไว้ในไฟล์ ให้ใช้ `pres.save()` วิธีการและระบุเส้นทางไฟล์เอาท์พุตรวมถึงรูปแบบที่ต้องการ ตัวอย่างเช่น คุณสามารถบันทึกเป็นรูปแบบ PPTX ได้โดยใช้ `pres-save(outPptxPath, SaveFormat.Pptx)`.

### ฉันจะปรับแต่งการตั้งค่าสไลด์โชว์เพิ่มเติมได้อย่างไร

คุณสามารถสำรวจการตั้งค่าสไลด์โชว์เพิ่มเติมที่ Aspose.Slides สำหรับ Java จัดเตรียมไว้เพื่อปรับแต่งประสบการณ์การนำเสนอสไลด์ให้เหมาะกับความต้องการของคุณ โปรดดูเอกสารประกอบที่ [ที่นี่](https://reference.aspose.com/slides/java/) สำหรับข้อมูลโดยละเอียดเกี่ยวกับตัวเลือกและการกำหนดค่าที่มีอยู่

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}