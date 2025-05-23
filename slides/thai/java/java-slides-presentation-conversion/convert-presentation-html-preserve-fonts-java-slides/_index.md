---
"description": "แปลงงานนำเสนอ PowerPoint เป็น HTML โดยยังคงแบบอักษรดั้งเดิมไว้โดยใช้ Aspose.Slides สำหรับ Java"
"linktitle": "การแปลงงานนำเสนอเป็น HTML พร้อมรักษาแบบอักษรดั้งเดิมใน Java Slides"
"second_title": "API การประมวลผล Java PowerPoint ของ Aspose.Slides"
"title": "การแปลงงานนำเสนอเป็น HTML พร้อมรักษาแบบอักษรดั้งเดิมใน Java Slides"
"url": "/th/java/presentation-conversion/convert-presentation-html-preserve-fonts-java-slides/"
"weight": 14
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# การแปลงงานนำเสนอเป็น HTML พร้อมรักษาแบบอักษรดั้งเดิมใน Java Slides


## บทนำสู่การแปลงงานนำเสนอเป็น HTML พร้อมการรักษาแบบอักษรดั้งเดิมในสไลด์ Java

ในบทช่วยสอนนี้ เราจะมาเรียนรู้วิธีการแปลงงานนำเสนอ PowerPoint (PPTX) เป็น HTML โดยยังคงรักษาแบบอักษรดั้งเดิมไว้โดยใช้ Aspose.Slides สำหรับ Java วิธีนี้จะช่วยให้ HTML ที่ได้มีลักษณะใกล้เคียงกับงานนำเสนอดั้งเดิมมากที่สุด

## ขั้นตอนที่ 1: การตั้งค่าโครงการ
ก่อนที่เราจะเจาะลึกโค้ด เรามาตรวจสอบก่อนว่าคุณได้ตั้งค่าที่จำเป็นเรียบร้อยแล้ว:

1. ดาวน์โหลด Aspose.Slides สำหรับ Java: หากคุณยังไม่ได้ดาวน์โหลดและรวมไลบรารี Aspose.Slides สำหรับ Java ลงในโปรเจ็กต์ของคุณ

2. สร้างโปรเจ็กต์ Java: ตั้งค่าโปรเจ็กต์ Java ใน IDE ที่คุณชื่นชอบ และตรวจสอบให้แน่ใจว่าคุณมีโฟลเดอร์ "lib" ที่คุณสามารถวางไฟล์ JAR Aspose.Slides ได้

3. นำเข้าคลาสที่จำเป็น: นำเข้าคลาสที่จำเป็นในตอนต้นของไฟล์ Java ของคุณ:

```java
import com.aspose.slides.EmbedAllFontsHtmlController;
import com.aspose.slides.HtmlFormatter;
import com.aspose.slides.HtmlOptions;
import com.aspose.slides.Presentation;
import com.aspose.slides.SaveFormat;
```

## ขั้นตอนที่ 2: แปลงงานนำเสนอเป็น HTML ด้วยแบบอักษรดั้งเดิม

ตอนนี้มาแปลงการนำเสนอ PowerPoint เป็น HTML โดยยังคงแบบอักษรดั้งเดิมไว้:

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
    
    // บันทึกการนำเสนอเป็น HTML
    pres.save("output.html", SaveFormat.Html, htmlOptionsEmbed);
} finally {
    // กำจัดวัตถุนำเสนอ
    if (pres != null) pres.dispose();
}
```

ในชิ้นส่วนโค้ดนี้:

- เราโหลดอินพุตการนำเสนอ PowerPoint โดยใช้ `Presentation`-

- เราจะกำหนดรายการแบบอักษร (`fontNameExcludeList`) ที่เราต้องการยกเว้นไม่ให้ฝังใน HTML ซึ่งมีประโยชน์ในการยกเว้นฟอนต์ทั่วไป เช่น Calibri และ Arial เพื่อลดขนาดไฟล์

- เราสร้างอินสแตนซ์ของ `EmbedAllFontsHtmlController` และส่งรายการยกเว้นแบบอักษรให้กับมัน

- เราสร้าง `HtmlOptions` และตั้งค่าตัวจัดรูปแบบ HTML แบบกำหนดเองโดยใช้ `HtmlFormatter-createCustomFormatter(embedFontsController)`.

- สุดท้ายเราบันทึกการนำเสนอเป็น HTML พร้อมตัวเลือกตามที่ระบุ

## โค้ดต้นฉบับที่สมบูรณ์สำหรับการแปลงงานนำเสนอเป็น HTML พร้อมรักษาแบบอักษรดั้งเดิมในสไลด์ Java

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

ในบทช่วยสอนนี้ คุณจะได้เรียนรู้วิธีการแปลงงานนำเสนอ PowerPoint เป็น HTML โดยยังคงรักษาแบบอักษรดั้งเดิมไว้โดยใช้ Aspose.Slides สำหรับ Java ซึ่งมีประโยชน์เมื่อคุณต้องการรักษาความเที่ยงตรงของภาพของงานนำเสนอของคุณเมื่อแชร์บนเว็บ

## คำถามที่พบบ่อย

### ฉันจะดาวน์โหลด Aspose.Slides สำหรับ Java ได้อย่างไร?

คุณสามารถดาวน์โหลด Aspose.Slides สำหรับ Java ได้จากเว็บไซต์ Aspose เข้าไปที่ [ที่นี่](https://downloads.aspose.com/slides/java/) เพื่อรับเวอร์ชันล่าสุด

### ฉันสามารถปรับแต่งรายการแบบอักษรที่ถูกแยกออกได้หรือไม่

ใช่ คุณสามารถปรับแต่งได้ `fontNameExcludeList` อาร์เรย์เพื่อรวมหรือไม่รวมแบบอักษรเฉพาะตามความต้องการของคุณ

### วิธีนี้ใช้ได้กับรูปแบบ PowerPoint เก่าๆ เช่น PPT หรือไม่

ตัวอย่างโค้ดนี้ได้รับการออกแบบมาสำหรับไฟล์ PPTX หากคุณจำเป็นต้องแปลงไฟล์ PPT เก่า คุณอาจต้องปรับเปลี่ยนโค้ด

### ฉันจะปรับแต่งเอาท์พุต HTML เพิ่มเติมได้อย่างไร

คุณสามารถสำรวจได้ `HtmlOptions` คลาสเพื่อปรับแต่งด้านต่างๆ ของผลลัพธ์ HTML เช่น ขนาดสไลด์ คุณภาพของรูปภาพ และอื่นๆ

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}