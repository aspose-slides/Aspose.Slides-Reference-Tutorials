---
"description": "เรียนรู้วิธีการแปลงสไลด์ PowerPoint เป็น PDF พร้อมบันทึกย่อใน Java โดยใช้ Aspose.Slides สำหรับ Java คำแนะนำทีละขั้นตอนสำหรับนักพัฒนา Java เพิ่มประสิทธิภาพการแชร์งานนำเสนอของคุณ"
"linktitle": "แปลงสไลด์เป็น PDF ด้วย Notes ใน Java Slides"
"second_title": "API การประมวลผล Java PowerPoint ของ Aspose.Slides"
"title": "แปลงสไลด์เป็น PDF ด้วย Notes ใน Java Slides"
"url": "/th/java/presentation-conversion/convert-slides-pdf-notes-java-slides/"
"weight": 19
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# แปลงสไลด์เป็น PDF ด้วย Notes ใน Java Slides


## บทนำสู่การแปลงสไลด์เป็น PDF ด้วย Notes ใน Java

ในโลกของการนำเสนอแบบดิจิทัล ความสามารถในการแปลงสไลด์เป็น PDF พร้อมบันทึกย่อถือเป็นคุณสมบัติที่มีประโยชน์ นักพัฒนา Java สามารถทำได้โดยใช้ไลบรารี Aspose.Slides สำหรับ Java ซึ่งให้ชุดเครื่องมืออันแข็งแกร่งสำหรับการทำงานกับการนำเสนอ PowerPoint ด้วยโปรแกรม ในคู่มือทีละขั้นตอนนี้ เราจะสำรวจวิธีการแปลงสไลด์เป็น PDF พร้อมบันทึกย่อโดยใช้ Java และ Aspose.Slides สำหรับ Java

## ข้อกำหนดเบื้องต้น

ก่อนที่จะเจาะลึกโค้ด โปรดตรวจสอบให้แน่ใจว่าคุณมีข้อกำหนดเบื้องต้นดังต่อไปนี้:

- Java Development Kit (JDK) ติดตั้งอยู่บนระบบของคุณ
- Aspose.Slides สำหรับไลบรารี Java คุณสามารถดาวน์โหลดได้จาก [ที่นี่](https://releases-aspose.com/slides/java/).

ตอนนี้เรามีโครงร่างแล้ว มาเจาะลึกการนำไปใช้งานทีละขั้นตอนกัน
## ขั้นตอนที่ 1: การตั้งค่าโครงการ

ขั้นแรก ให้สร้างโปรเจ็กต์ Java และเพิ่มไลบรารี Aspose.Slides สำหรับ Java ลงในส่วนที่ต้องมีของโปรเจ็กต์ของคุณ

## ขั้นตอนที่ 2: การโหลดงานนำเสนอ

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

## โค้ดต้นฉบับสมบูรณ์สำหรับการแปลงสไลด์เป็น PDF พร้อมหมายเหตุใน Java Slides

```java
// เส้นทางไปยังไดเร็กทอรีเอกสาร
String dataDir = "Your Document Directory";
// สร้างอินสแตนซ์ของวัตถุการนำเสนอที่แสดงไฟล์การนำเสนอ 
Presentation presentation = new Presentation(dataDir + "SelectedSlides.pptx");
try
{
	Presentation auxPresentation = new Presentation();
	try
	{
		ISlide slide = presentation.getSlides().get_Item(0);
		auxPresentation.getSlides().insertClone(0, slide);
		// การตั้งค่าชนิดและขนาดของสไลด์
		//auxPresentation.getSlideSize().setSize(presentation.getSlideSize().getSize().getWidth(), presentation.getSlideSize().getSize().getHeight(), SlideSizeScaleType.EnsureFit);
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

ในบทช่วยสอนนี้ เราได้เรียนรู้วิธีการแปลงสไลด์เป็น PDF พร้อมหมายเหตุใน Java โดยใช้ Aspose.Slides สำหรับ Java โดยครอบคลุมตั้งแต่การตั้งค่าโครงการ การโหลดงานนำเสนอ การสร้างงานนำเสนอใหม่ การคัดลอกสไลด์ การปรับขนาดสไลด์ การกำหนดค่าตัวเลือก PDF และสุดท้ายคือการบันทึกงานนำเสนอเป็น PDF พร้อมหมายเหตุ

## คำถามที่พบบ่อย

### ฉันจะติดตั้ง Aspose.Slides สำหรับ Java ได้อย่างไร?

หากต้องการติดตั้ง Aspose.Slides สำหรับ Java ให้ทำตามขั้นตอนเหล่านี้:
1. ดาวน์โหลดห้องสมุดได้จาก [ที่นี่](https://releases-aspose.com/slides/java/).
2. เพิ่มไฟล์ JAR ลงในคลาสพาธของโปรเจ็กต์ Java ของคุณ

### ฉันสามารถปรับแต่งตำแหน่งบันทึกใน PDF ที่สร้างขึ้นได้หรือไม่

ใช่ คุณสามารถปรับแต่งตำแหน่งโน้ตได้โดยการแก้ไข `NotesPositions` enum ในตัวเลือก PDF ในบทช่วยสอนนี้ เราตั้งค่าเป็น `BottomFull`แต่คุณสามารถสำรวจตัวเลือกอื่นได้เช่นกัน

### มีข้อกำหนดการออกใบอนุญาตสำหรับการใช้ Aspose.Slides สำหรับ Java หรือไม่

ใช่ Aspose.Slides สำหรับ Java เป็นไลบรารีเชิงพาณิชย์ และคุณอาจต้องซื้อใบอนุญาตเพื่อใช้ในระบบการผลิต เข้าไปที่เว็บไซต์ Aspose เพื่อดูรายละเอียดใบอนุญาต

### ฉันสามารถแปลงสไลด์หลาย ๆ ภาพในครั้งเดียวได้ไหม

แน่นอน! คุณสามารถวนซ้ำสไลด์ในงานนำเสนอของคุณและโคลนลงในงานนำเสนอใหม่ ทำให้คุณสามารถแปลงสไลด์หลาย ๆ สไลด์เป็น PDF พร้อมบันทึกย่อได้ในครั้งเดียว

### ฉันสามารถหาเอกสารเพิ่มเติมสำหรับ Aspose.Slides สำหรับ Java ได้ที่ไหน

คุณสามารถค้นหาเอกสารโดยละเอียดสำหรับ Aspose.Slides สำหรับ Java ได้ที่ไซต์: [เอกสารอ้างอิง API ของ Aspose.Slides สำหรับ Java](https://reference-aspose.com/slides/java/).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}