---
title: แปลงสไลด์เป็น PDF ด้วย Notes ใน Java Slides
linktitle: แปลงสไลด์เป็น PDF ด้วย Notes ใน Java Slides
second_title: Aspose.Slides Java PowerPoint การประมวลผล API
description: เรียนรู้วิธีแปลงสไลด์ PowerPoint เป็น PDF ด้วยบันทึกย่อใน Java โดยใช้ Aspose.Slides สำหรับ Java คำแนะนำทีละขั้นตอนสำหรับนักพัฒนา Java ปรับปรุงการแบ่งปันการนำเสนอของคุณ
weight: 19
url: /th/java/presentation-conversion/convert-slides-pdf-notes-java-slides/
---

{< blocks/products/pf/main-wrap-class >}
{< blocks/products/pf/main-container >}
{< blocks/products/pf/tutorial-page-section >}


## ข้อมูลเบื้องต้นเกี่ยวกับการแปลงสไลด์เป็น PDF ด้วย Notes ใน Java

ในโลกของการนำเสนอแบบดิจิทัล ความสามารถในการแปลงสไลด์เป็น PDF พร้อมหมายเหตุประกอบถือเป็นคุณสมบัติที่มีคุณค่า นักพัฒนา Java สามารถทำได้โดยใช้ไลบรารี Aspose.Slides สำหรับ Java ซึ่งมีชุดเครื่องมือที่มีประสิทธิภาพสำหรับการทำงานกับงานนำเสนอ PowerPoint โดยทางโปรแกรม ในคำแนะนำทีละขั้นตอนนี้ เราจะสำรวจวิธีการแปลงสไลด์เป็น PDF ด้วยบันทึกย่อโดยใช้ Java และ Aspose.Slides สำหรับ Java

## ข้อกำหนดเบื้องต้น

ก่อนที่เราจะเจาะลึกโค้ด ตรวจสอบให้แน่ใจว่าคุณมีข้อกำหนดเบื้องต้นต่อไปนี้:

- ติดตั้ง Java Development Kit (JDK) บนระบบของคุณ
-  Aspose.Slides สำหรับไลบรารี Java คุณสามารถดาวน์โหลดได้จาก[ที่นี่](https://releases.aspose.com/slides/java/).

ตอนนี้เรามีโครงร่างแล้ว เรามาเจาะลึกการใช้งานทีละขั้นตอนกันดีกว่า
## ขั้นตอนที่ 1: การตั้งค่าโครงการ

ขั้นแรก สร้างโปรเจ็กต์ Java และเพิ่มไลบรารี Aspose.Slides สำหรับ Java ไปยังการขึ้นต่อกันของโปรเจ็กต์ของคุณ

## ขั้นตอนที่ 2: กำลังโหลดการนำเสนอ

```java
String dataDir = "Your Document Directory";
Presentation presentation = new Presentation(dataDir + "SelectedSlides.pptx");
```

## ขั้นตอนที่ 3: การสร้างงานนำเสนอใหม่

```java
Presentation auxPresentation = new Presentation();
```

## ขั้นตอนที่ 4: การคัดลอกสไลด์

```java
ISlide slide = presentation.getSlides().get_Item(0);
auxPresentation.getSlides().insertClone(0, slide);
```

## ขั้นตอนที่ 5: การปรับขนาดสไลด์

```java
auxPresentation.getSlideSize().setSize(612F, 792F, SlideSizeScaleType.EnsureFit);
```

## ขั้นตอนที่ 6: การกำหนดค่าตัวเลือก PDF

```java
PdfOptions pdfOptions = new PdfOptions();
INotesCommentsLayoutingOptions options = pdfOptions.getNotesCommentsLayouting();
options.setNotesPosition(NotesPositions.BottomFull);
```

## ขั้นตอนที่ 7: บันทึกเป็น PDF

```java
auxPresentation.save(dataDir + "PDFnotes_out.pdf", SaveFormat.Pdf, pdfOptions);
```

## กรอกซอร์สโค้ดสำหรับการแปลงสไลด์เป็น PDF พร้อมบันทึกย่อใน Java Slides

```java
// เส้นทางไปยังไดเร็กทอรีเอกสาร
String dataDir = "Your Document Directory";
// สร้างอินสแตนซ์วัตถุการนำเสนอที่แสดงถึงไฟล์การนำเสนอ
Presentation presentation = new Presentation(dataDir + "SelectedSlides.pptx");
try
{
	Presentation auxPresentation = new Presentation();
	try
	{
		ISlide slide = presentation.getSlides().get_Item(0);
		auxPresentation.getSlides().insertClone(0, slide);
		// การตั้งค่าประเภทและขนาดสไลด์
		//auxPresentation.getSlideSize().setSize(presentation.getSlideSize().getSize().getWidth(), Presentation.getSlideSize().getSize().getHeight(),SlideSizeScaleType.EnsureFit);
		auxPresentation.getSlideSize().setSize(612F, 792F, SlideSizeScaleType.EnsureFit);
		PdfOptions pdfOptions = new PdfOptions();
		INotesCommentsLayoutingOptions options = pdfOptions.getNotesCommentsLayouting();
		options.setNotesPosition(NotesPositions.BottomFull);
		auxPresentation.save(dataDir + "PDFnotes_out.pdf", SaveFormat.Pdf, pdfOptions);
	}
	finally
	{
		if (auxPresentation != null) auxPresentation.dispose();
	}
}
finally
{
	if (presentation != null) presentation.dispose();
}
```

## บทสรุป

ในบทช่วยสอนนี้ เราได้เรียนรู้วิธีแปลงสไลด์เป็น PDF ด้วยบันทึกย่อใน Java โดยใช้ Aspose.Slides สำหรับ Java เราครอบคลุมถึงการตั้งค่าโปรเจ็กต์ การโหลดงานนำเสนอ การสร้างงานนำเสนอใหม่ การคัดลอกสไลด์ การปรับขนาดสไลด์ การกำหนดค่าตัวเลือก PDF และสุดท้ายคือการบันทึกงานนำเสนอเป็น PDF พร้อมบันทึกย่อ

## คำถามที่พบบ่อย

### ฉันจะติดตั้ง Aspose.Slides สำหรับ Java ได้อย่างไร

หากต้องการติดตั้ง Aspose.Slides สำหรับ Java ให้ทำตามขั้นตอนเหล่านี้:
1.  ดาวน์โหลดห้องสมุดได้จาก[ที่นี่](https://releases.aspose.com/slides/java/).
2. เพิ่มไฟล์ JAR ให้กับ classpath ของโปรเจ็กต์ Java ของคุณ

### ฉันสามารถปรับแต่งตำแหน่งบันทึกย่อใน PDF ที่สร้างขึ้นได้หรือไม่

 ใช่ คุณสามารถปรับแต่งตำแหน่งบันทึกย่อได้โดยการแก้ไข`NotesPositions` enum ในตัวเลือก PDF ในบทช่วยสอนนี้ เราตั้งค่าเป็น`BottomFull`แต่คุณสามารถสำรวจตัวเลือกอื่นๆ ได้เช่นกัน

### มีข้อกำหนดสิทธิ์การใช้งานสำหรับการใช้ Aspose.Slides สำหรับ Java หรือไม่

ใช่ Aspose.Slides สำหรับ Java เป็นไลบรารีเชิงพาณิชย์ และคุณอาจต้องได้รับใบอนุญาตเพื่อใช้ในการผลิต เยี่ยมชมเว็บไซต์ Aspose เพื่อดูรายละเอียดใบอนุญาต

### ฉันสามารถแปลงหลายสไลด์พร้อมกันได้หรือไม่

แน่นอน! คุณสามารถวนซ้ำสไลด์ในงานนำเสนอของคุณและลอกแบบเป็นงานนำเสนอใหม่ได้ ซึ่งช่วยให้คุณสามารถแปลงหลายสไลด์เป็น PDF ด้วยบันทึกย่อได้ในครั้งเดียว

### ฉันจะหาเอกสารเพิ่มเติมเกี่ยวกับ Aspose.Slides สำหรับ Java ได้ที่ไหน

 คุณสามารถค้นหาเอกสารโดยละเอียดสำหรับ Aspose.Slides สำหรับ Java บนเว็บไซต์:[Aspose.Slides สำหรับการอ้างอิง Java API](https://reference.aspose.com/slides/java/).
{< /blocks/products/pf/tutorial-page-section >}

{< /blocks/products/pf/main-container >}
{< /blocks/products/pf/main-wrap-class >}

{< blocks/products/products-backtop-button >}
