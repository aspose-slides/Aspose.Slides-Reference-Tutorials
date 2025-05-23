---
"description": "เรียนรู้วิธีการแปลงสไลด์ PowerPoint แต่ละสไลด์เป็น HTML ทีละขั้นตอนด้วยตัวอย่างโค้ดโดยใช้ Aspose.Slides สำหรับ Java"
"linktitle": "แปลงสไลด์แต่ละสไลด์ใน Java Slides"
"second_title": "API การประมวลผล Java PowerPoint ของ Aspose.Slides"
"title": "แปลงสไลด์แต่ละสไลด์ใน Java Slides"
"url": "/th/java/presentation-conversion/convert-individual-slide-java-slides/"
"weight": 12
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# แปลงสไลด์แต่ละสไลด์ใน Java Slides


## บทนำการแปลงสไลด์แต่ละสไลด์ใน Java Slides

ในบทช่วยสอนนี้ เราจะแนะนำขั้นตอนการแปลงสไลด์แต่ละสไลด์จากงานนำเสนอ PowerPoint เป็น HTML โดยใช้ Aspose.Slides สำหรับ Java คำแนะนำทีละขั้นตอนนี้จะให้โค้ดต้นฉบับและคำอธิบายเพื่อช่วยให้คุณบรรลุภารกิจนี้ได้

## ข้อกำหนดเบื้องต้น

ก่อนที่เราจะเริ่ม โปรดตรวจสอบให้แน่ใจว่าคุณมีสิ่งต่อไปนี้:

- ติดตั้งไลบรารี Aspose.Slides สำหรับ Java แล้ว
- ไฟล์นำเสนอ PowerPoint (`Individual-Slide.pptx`) ที่คุณต้องการแปลง
- การตั้งค่าสภาพแวดล้อมการพัฒนา Java

## ขั้นตอนที่ 1: ตั้งค่าโครงการ

1. สร้างโครงการ Java ในสภาพแวดล้อมการพัฒนาที่คุณต้องการ
2. เพิ่มไลบรารี Aspose.Slides สำหรับ Java ลงในโปรเจ็กต์ของคุณ

## ขั้นตอนที่ 2: นำเข้าคลาสที่จำเป็น

ในคลาส Java ของคุณ โปรดนำเข้าคลาสที่จำเป็นและตั้งค่าคอนฟิกูเรชันเริ่มต้น

```java
import com.aspose.slides.HtmlOptions;
import com.aspose.slides.HtmlFormatter;
import com.aspose.slides.INotesCommentsLayoutingOptions;
import com.aspose.slides.NotesPositions;
import com.aspose.slides.Presentation;
import com.aspose.slides.SaveFormat;
import com.aspose.slides.IHtmlFormattingController;
import com.aspose.slides.IHtmlGenerator;
import com.aspose.slides.ISlide;
import com.aspose.slides.IShape;
```

## ขั้นตอนที่ 3: กำหนดวิธีการแปลงหลัก

สร้างวิธีการแปลงสไลด์แต่ละสไลด์ อย่าลืมเปลี่ยน `"Your Document Directory"` พร้อมเส้นทางจริงไปยังไดเร็กทอรีเอกสารของคุณ

```java
public static void convertIndividualSlides() {
    String dataDir = "Your Document Directory";
    Presentation presentation = new Presentation(dataDir + "Individual-Slide.pptx");
    try {
        HtmlOptions htmlOptions = new HtmlOptions();
        htmlOptions.setHtmlFormatter(HtmlFormatter.createCustomFormatter(new CustomFormattingController()));
        INotesCommentsLayoutingOptions notesOptions = htmlOptions.getNotesCommentsLayouting();
        notesOptions.setNotesPosition(NotesPositions.BottomFull);
        
        // การบันทึกไฟล์
        for (int i = 0; i < presentation.getSlides().size(); i++) {
            presentation.save(dataDir + "Individual-Slide" + (i + 1) + "_out.html", new int[]{i + 1}, SaveFormat.Html, htmlOptions);
        }
    } finally {
        if (presentation != null) presentation.dispose();
    }
}
```

## ขั้นตอนที่ 4: นำ CustomFormattingController มาใช้

สร้าง `CustomFormattingController` คลาสสำหรับจัดการการจัดรูปแบบแบบกำหนดเองในระหว่างการแปลง

```java
public static class CustomFormattingController implements IHtmlFormattingController {
    public void writeDocumentStart(IHtmlGenerator generator, IPresentation presentation) {
    }
    
    public void writeDocumentEnd(IHtmlGenerator generator, IPresentation presentation) {
    }
    
    public void writeSlideStart(IHtmlGenerator generator, ISlide slide) {
        generator.addHtml(String.format(SlideHeader, generator.getSlideIndex() + 1));
    }
    
    public void writeSlideEnd(IHtmlGenerator generator, ISlide slide) {
        generator.addHtml(SlideFooter);
    }
    
    public void writeShapeStart(IHtmlGenerator generator, IShape shape) {
    }
    
    public void writeShapeEnd(IHtmlGenerator generator, IShape shape) {
    }
    
    private static String SlideHeader = "<div class=\"slide\" name=\"slide\" id=\"slide{0}\">";
    private static String SlideFooter = "</div>";
}
```

## ขั้นตอนที่ 5: ดำเนินการแปลง

สุดท้ายให้โทรหา `convertIndividualSlides` วิธีการดำเนินการกระบวนการแปลง

```java
public static void main(String[] args) {
    convertIndividualSlides();
}
```

## โค้ดต้นฉบับสมบูรณ์สำหรับการแปลงสไลด์แต่ละสไลด์ใน Java Slides

```java
	String dataDir = "Your Document Directory";
	Presentation presentation = new Presentation(dataDir + "Individual-Slide.pptx");
	try
	{
		HtmlOptions htmlOptions = new HtmlOptions();
		htmlOptions.setHtmlFormatter(HtmlFormatter.createCustomFormatter(new CustomFormattingController()));
		INotesCommentsLayoutingOptions notesOptions = htmlOptions.getNotesCommentsLayouting();
		notesOptions.setNotesPosition(NotesPositions.BottomFull);
		// การบันทึกไฟล์              
		for (int i = 0; i < presentation.getSlides().size(); i++)
			presentation.save(dataDir + "Individual Slide" + i + 1 + "_out.html", new int[]{i + 1}, SaveFormat.Html, htmlOptions);
	}
	finally
	{
		if (presentation != null) presentation.dispose();
	}
}
public static class CustomFormattingController implements IHtmlFormattingController
{
	public void writeDocumentStart(IHtmlGenerator generator, IPresentation presentation)
	{
	}
	public void writeDocumentEnd(IHtmlGenerator generator, IPresentation presentation)
	{
	}
	public void writeSlideStart(IHtmlGenerator generator, ISlide slide)
	{
		generator.addHtml(String.format(SlideHeader, generator.getSlideIndex() + 1));
	}
	public void writeSlideEnd(IHtmlGenerator generator, ISlide slide)
	{
		generator.addHtml(SlideFooter);
	}
	public void writeShapeStart(IHtmlGenerator generator, IShape shape)
	{
	}
	public void writeShapeEnd(IHtmlGenerator generator, IShape shape)
	{
	}
	private static String SlideHeader = "<div class=\"slide\" name=\"slide\" id=\"slide{0}\">";
	private static String SlideFooter = "</div>";
```

## บทสรุป

คุณได้แปลงสไลด์แต่ละสไลด์จากงานนำเสนอ PowerPoint เป็น HTML สำเร็จแล้วโดยใช้ Aspose.Slides สำหรับ Java บทช่วยสอนนี้ให้โค้ดและขั้นตอนที่จำเป็นแก่คุณในการบรรลุภารกิจนี้ คุณสามารถปรับแต่งผลลัพธ์และการจัดรูปแบบตามความต้องการเฉพาะของคุณได้

## คำถามที่พบบ่อย

### ฉันจะปรับแต่งเอาต์พุต HTML เพิ่มเติมได้อย่างไร

คุณสามารถปรับแต่งผลลัพธ์ HTML ได้โดยการแก้ไข `CustomFormattingController` คลาส. ปรับแต่ง `writeSlideStart` และ `writeSlideEnd` วิธีการเปลี่ยนโครงสร้างและรูปแบบของสไลด์ HTML

### ฉันสามารถแปลงการนำเสนอ PowerPoint หลาย ๆ ไฟล์ในครั้งเดียวได้ไหม

ใช่ คุณสามารถปรับเปลี่ยนโค้ดเพื่อวนซ้ำไฟล์การนำเสนอหลายไฟล์และแปลงทีละไฟล์โดยเรียกใช้ `convertIndividualSlides` วิธีการสำหรับการนำเสนอแต่ละครั้ง

### ฉันจะจัดการการจัดรูปแบบเพิ่มเติมสำหรับรูปร่างและข้อความภายในสไลด์ได้อย่างไร

คุณสามารถขยายเวลาได้ `CustomFormattingController` คลาสสำหรับจัดการการจัดรูปแบบเฉพาะรูปร่างโดยการใช้งาน `writeShapeStart` และ `writeShapeEnd` วิธีการและการใช้ตรรกะการจัดรูปแบบแบบกำหนดเองภายในนั้น

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}