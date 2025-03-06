---
title: แปลงแต่ละสไลด์ใน Java Slides
linktitle: แปลงแต่ละสไลด์ใน Java Slides
second_title: Aspose.Slides Java PowerPoint การประมวลผล API
description: เรียนรู้วิธีแปลงสไลด์ PowerPoint แต่ละสไลด์เป็น HTML ทีละขั้นตอนพร้อมตัวอย่างโค้ดโดยใช้ Aspose.Slides สำหรับ Java
weight: 12
url: /th/java/presentation-conversion/convert-individual-slide-java-slides/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# แปลงแต่ละสไลด์ใน Java Slides


## รู้เบื้องต้นเกี่ยวกับการแปลงแต่ละสไลด์ใน Java Slides

ในบทช่วยสอนนี้ เราจะอธิบายขั้นตอนการแปลงแต่ละสไลด์จากงานนำเสนอ PowerPoint เป็น HTML โดยใช้ Aspose.Slides สำหรับ Java คำแนะนำทีละขั้นตอนนี้จะให้ซอร์สโค้ดและคำอธิบายเพื่อช่วยให้คุณบรรลุภารกิจนี้

## ข้อกำหนดเบื้องต้น

ก่อนที่เราจะเริ่ม ตรวจสอบให้แน่ใจว่าคุณมีสิ่งต่อไปนี้:

- ติดตั้ง Aspose.Slides สำหรับไลบรารี Java แล้ว
- ไฟล์นำเสนอ PowerPoint (`Individual-Slide.pptx`) ที่คุณต้องการแปลง
- ตั้งค่าสภาพแวดล้อมการพัฒนา Java

## ขั้นตอนที่ 1: ตั้งค่าโครงการ

1. สร้างโปรเจ็กต์ Java ในสภาพแวดล้อมการพัฒนาที่คุณต้องการ
2. เพิ่มไลบรารี Aspose.Slides สำหรับ Java ให้กับโปรเจ็กต์ของคุณ

## ขั้นตอนที่ 2: นำเข้าคลาสที่จำเป็น

ในคลาส Java ของคุณ ให้นำเข้าคลาสที่จำเป็นและตั้งค่าการกำหนดค่าเริ่มต้น

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

 สร้างวิธีการแปลงแต่ละสไลด์ ตรวจสอบให้แน่ใจว่าได้เปลี่ยน`"Your Document Directory"` ด้วยเส้นทางจริงไปยังไดเร็กทอรีเอกสารของคุณ

```java
public static void convertIndividualSlides() {
    String dataDir = "Your Document Directory";
    Presentation presentation = new Presentation(dataDir + "Individual-Slide.pptx");
    try {
        HtmlOptions htmlOptions = new HtmlOptions();
        htmlOptions.setHtmlFormatter(HtmlFormatter.createCustomFormatter(new CustomFormattingController()));
        INotesCommentsLayoutingOptions notesOptions = htmlOptions.getNotesCommentsLayouting();
        notesOptions.setNotesPosition(NotesPositions.BottomFull);
        
        // กำลังบันทึกไฟล์
        for (int i = 0; i < presentation.getSlides().size(); i++) {
            presentation.save(dataDir + "Individual-Slide" + (i + 1) + "_out.html", new int[]{i + 1}, SaveFormat.Html, htmlOptions);
        }
    } finally {
        if (presentation != null) presentation.dispose();
    }
}
```

## ขั้นตอนที่ 4: ใช้ CustomFormattingController

 สร้าง`CustomFormattingController` คลาสเพื่อจัดการการจัดรูปแบบที่กำหนดเองระหว่างการแปลง

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

 สุดท้ายโทรหา.`convertIndividualSlides` วิธีการดำเนินการกระบวนการแปลง

```java
public static void main(String[] args) {
    convertIndividualSlides();
}
```

## กรอกซอร์สโค้ดสำหรับการแปลงแต่ละสไลด์ใน Java Slides

```java
	String dataDir = "Your Document Directory";
	Presentation presentation = new Presentation(dataDir + "Individual-Slide.pptx");
	try
	{
		HtmlOptions htmlOptions = new HtmlOptions();
		htmlOptions.setHtmlFormatter(HtmlFormatter.createCustomFormatter(new CustomFormattingController()));
		INotesCommentsLayoutingOptions notesOptions = htmlOptions.getNotesCommentsLayouting();
		notesOptions.setNotesPosition(NotesPositions.BottomFull);
		// กำลังบันทึกไฟล์
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

คุณได้แปลงแต่ละสไลด์จากงานนำเสนอ PowerPoint เป็น HTML ได้สำเร็จโดยใช้ Aspose.Slides สำหรับ Java บทช่วยสอนนี้ให้รหัสและขั้นตอนที่จำเป็นแก่คุณเพื่อให้บรรลุงานนี้ คุณสามารถปรับแต่งเอาต์พุตและการจัดรูปแบบได้ตามต้องการตามความต้องการเฉพาะของคุณ

## คำถามที่พบบ่อย

### ฉันจะปรับแต่งเอาต์พุต HTML เพิ่มเติมได้อย่างไร

 คุณสามารถปรับแต่งเอาต์พุต HTML ได้โดยการแก้ไข`CustomFormattingController` ระดับ. ปรับ`writeSlideStart` และ`writeSlideEnd` วิธีการเปลี่ยนโครงสร้าง HTML และสไตล์ของสไลด์

### ฉันสามารถแปลงงานนำเสนอ PowerPoint หลายรายการในคราวเดียวได้หรือไม่

 ได้ คุณสามารถแก้ไขโค้ดเพื่อวนซ้ำไฟล์การนำเสนอหลายไฟล์ และแปลงทีละไฟล์ได้โดยการเรียก`convertIndividualSlides` วิธีการนำเสนอแต่ละครั้ง

### ฉันจะจัดการการจัดรูปแบบเพิ่มเติมสำหรับรูปร่างและข้อความภายในสไลด์ได้อย่างไร

 คุณสามารถขยาย`CustomFormattingController` คลาสเพื่อจัดการการจัดรูปแบบเฉพาะรูปร่างโดยการนำ`writeShapeStart` และ`writeShapeEnd` วิธีการและการใช้ตรรกะการจัดรูปแบบที่กำหนดเองภายในนั้น
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
