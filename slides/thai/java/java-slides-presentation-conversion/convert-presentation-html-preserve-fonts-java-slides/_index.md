---
title: การแปลงการนำเสนอเป็น HTML ด้วยการรักษาแบบอักษรดั้งเดิมใน Java Slides
linktitle: การแปลงการนำเสนอเป็น HTML ด้วยการรักษาแบบอักษรดั้งเดิมใน Java Slides
second_title: Aspose.Slides Java PowerPoint การประมวลผล API
description: แปลงงานนำเสนอ PowerPoint เป็น HTML ในขณะที่ยังคงรักษาแบบอักษรดั้งเดิมโดยใช้ Aspose.Slides สำหรับ Java
weight: 14
url: /th/java/presentation-conversion/convert-presentation-html-preserve-fonts-java-slides/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# การแปลงการนำเสนอเป็น HTML ด้วยการรักษาแบบอักษรดั้งเดิมใน Java Slides


## ข้อมูลเบื้องต้นเกี่ยวกับการแปลงงานนำเสนอเป็น HTML ด้วยการรักษาแบบอักษรดั้งเดิมใน Java Slides

ในบทช่วยสอนนี้ เราจะสำรวจวิธีการแปลงงานนำเสนอ PowerPoint (PPTX) เป็น HTML ในขณะที่ยังคงรักษาแบบอักษรดั้งเดิมโดยใช้ Aspose.Slides สำหรับ Java เพื่อให้แน่ใจว่าผลลัพธ์ HTML ที่ได้จะมีลักษณะใกล้เคียงกับรูปลักษณ์ของงานนำเสนอต้นฉบับ

## ขั้นตอนที่ 1: การตั้งค่าโครงการ
ก่อนที่เราจะเจาะลึกโค้ด โปรดตรวจสอบให้แน่ใจว่าคุณมีการตั้งค่าที่จำเป็น:

1. ดาวน์โหลด Aspose.Slides สำหรับ Java: หากคุณยังไม่ได้ดาวน์โหลด ให้ดาวน์โหลดและรวมไลบรารี Aspose.Slides สำหรับ Java ในโปรเจ็กต์ของคุณ

2. สร้างโปรเจ็กต์ Java: ตั้งค่าโปรเจ็กต์ Java ใน IDE ที่คุณชื่นชอบ และตรวจสอบให้แน่ใจว่าคุณมีโฟลเดอร์ "lib" ที่คุณสามารถวางไฟล์ JAR ของ Aspose.Slides ได้

3. นำเข้าคลาสที่จำเป็น: นำเข้าคลาสที่จำเป็นที่จุดเริ่มต้นของไฟล์ Java ของคุณ:

```java
import com.aspose.slides.EmbedAllFontsHtmlController;
import com.aspose.slides.HtmlFormatter;
import com.aspose.slides.HtmlOptions;
import com.aspose.slides.Presentation;
import com.aspose.slides.SaveFormat;
```

## ขั้นตอนที่ 2: การแปลงงานนำเสนอเป็น HTML ด้วยแบบอักษรดั้งเดิม

ตอนนี้ เรามาแปลงงานนำเสนอ PowerPoint เป็น HTML โดยที่ยังคงแบบอักษรดั้งเดิมไว้:

```java
// เส้นทางไปยังไดเร็กทอรีเอกสาร
String dataDir = "Your Document Directory";

// โหลดงานนำเสนอ
Presentation pres = new Presentation("input.pptx");

try {
    // ไม่รวมแบบอักษรการนำเสนอเริ่มต้นเช่น Calibri และ Arial
    String[] fontNameExcludeList = {"Calibri", "Arial"};
    EmbedAllFontsHtmlController embedFontsController = new EmbedAllFontsHtmlController(fontNameExcludeList);
    
    // สร้างตัวเลือก HTML และตั้งค่าตัวจัดรูปแบบ HTML แบบกำหนดเอง
    HtmlOptions htmlOptionsEmbed = new HtmlOptions();
    htmlOptionsEmbed.setHtmlFormatter(HtmlFormatter.createCustomFormatter(embedFontsController));
    
    // บันทึกงานนำเสนอเป็น HTML
    pres.save("output.html", SaveFormat.Html, htmlOptionsEmbed);
} finally {
    // กำจัดวัตถุการนำเสนอ
    if (pres != null) pres.dispose();
}
```

ในข้อมูลโค้ดนี้:

-  เราโหลดการนำเสนอ PowerPoint อินพุตโดยใช้`Presentation`.

- เรากำหนดรายการแบบอักษร (`fontNameExcludeList`ที่เราต้องการแยกออกจากการฝังใน HTML สิ่งนี้มีประโยชน์สำหรับการยกเว้นแบบอักษรทั่วไปเช่น Calibri และ Arial เพื่อลดขนาดไฟล์

-  เราสร้างอินสแตนซ์ของ`EmbedAllFontsHtmlController` และส่งรายการยกเว้นแบบอักษรไปให้

-  เราสร้าง`HtmlOptions` และตั้งค่าตัวจัดรูปแบบ HTML ที่กำหนดเองโดยใช้`HtmlFormatter.createCustomFormatter(embedFontsController)`.

- สุดท้าย เราบันทึกงานนำเสนอเป็น HTML พร้อมตัวเลือกที่ระบุ

## ซอร์สโค้ดที่สมบูรณ์สำหรับการแปลงงานนำเสนอเป็น HTML พร้อมการรักษาแบบอักษรดั้งเดิมใน Java Slides

```java
// เส้นทางไปยังไดเร็กทอรีเอกสาร
String dataDir = "Your Document Directory";
Presentation pres = new Presentation("input.pptx");
try
{
	// ไม่รวมแบบอักษรการนำเสนอเริ่มต้น
	String[] fontNameExcludeList = {"Calibri", "Arial"};
	EmbedAllFontsHtmlController embedFontsController = new EmbedAllFontsHtmlController(fontNameExcludeList);
	HtmlOptions htmlOptionsEmbed = new HtmlOptions();
	htmlOptionsEmbed.setHtmlFormatter(HtmlFormatter.createCustomFormatter(embedFontsController));
	pres.save("input-PFDinDisplayPro-Regular-installed.html", SaveFormat.Html, htmlOptionsEmbed);
}
finally
{
	if (pres != null) pres.dispose();
}
```

## บทสรุป

ในบทช่วยสอนนี้ คุณได้เรียนรู้วิธีแปลงงานนำเสนอ PowerPoint เป็น HTML ในขณะที่ยังคงรักษาแบบอักษรดั้งเดิมโดยใช้ Aspose.Slides สำหรับ Java สิ่งนี้มีประโยชน์เมื่อคุณต้องการรักษาความถูกต้องของภาพของงานนำเสนอของคุณเมื่อแชร์บนเว็บ

## คำถามที่พบบ่อย

### ฉันจะดาวน์โหลด Aspose.Slides สำหรับ Java ได้อย่างไร

 คุณสามารถดาวน์โหลด Aspose.Slides สำหรับ Java ได้จากเว็บไซต์ Aspose เยี่ยม[ที่นี่](https://downloads.aspose.com/slides/java/) เพื่อรับเวอร์ชันล่าสุด

### ฉันสามารถปรับแต่งรายการแบบอักษรที่แยกออกได้หรือไม่

 ใช่ คุณสามารถปรับแต่งได้`fontNameExcludeList` อาร์เรย์เพื่อรวมหรือแยกแบบอักษรเฉพาะตามความต้องการของคุณ

### วิธีนี้ใช้ได้กับรูปแบบ PowerPoint รุ่นเก่าเช่น PPT หรือไม่

ตัวอย่างโค้ดนี้ออกแบบมาสำหรับไฟล์ PPTX หากคุณต้องการแปลงไฟล์ PPT รุ่นเก่า คุณอาจต้องปรับเปลี่ยนโค้ด

### ฉันจะปรับแต่งเอาต์พุต HTML เพิ่มเติมได้อย่างไร

 คุณสามารถสำรวจ`HtmlOptions` คลาสเพื่อปรับแต่งแง่มุมต่างๆ ของเอาต์พุต HTML เช่น ขนาดสไลด์ คุณภาพของภาพ และอื่นๆ
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
