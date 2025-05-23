---
"description": "แปลง PowerPoint เป็น HTML ด้วยรูปภาพที่ฝังไว้ คำแนะนำทีละขั้นตอนโดยใช้ Aspose.Slides สำหรับ Java เรียนรู้วิธีการแปลงงานนำเสนอเป็นอัตโนมัติใน Java ได้อย่างง่ายดาย"
"linktitle": "แปลงภาพฝัง HTML ใน Java Slides"
"second_title": "API การประมวลผล Java PowerPoint ของ Aspose.Slides"
"title": "แปลงภาพฝัง HTML ใน Java Slides"
"url": "/th/java/presentation-conversion/convert-html-embedding-images-java-slides/"
"weight": 11
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# แปลงภาพฝัง HTML ใน Java Slides


## บทนำการแปลงภาพฝัง HTML ใน Java Slides

ในคู่มือทีละขั้นตอนนี้ เราจะแนะนำคุณเกี่ยวกับขั้นตอนการแปลงงานนำเสนอ PowerPoint เป็นเอกสาร HTML ขณะฝังรูปภาพโดยใช้ Aspose.Slides สำหรับ Java บทช่วยสอนนี้ถือว่าคุณได้ตั้งค่าสภาพแวดล้อมการพัฒนาและติดตั้งไลบรารี Aspose.Slides สำหรับ Java เรียบร้อยแล้ว

## ความต้องการ

ก่อนที่เราจะเริ่ม โปรดตรวจสอบให้แน่ใจว่าคุณมีสิ่งต่อไปนี้:

1. ติดตั้งไลบรารี Aspose.Slides สำหรับ Java แล้ว คุณสามารถดาวน์โหลดได้จาก [ที่นี่](https://downloads-aspose.com/slides/java).

2. ไฟล์งานนำเสนอ PowerPoint (รูปแบบ PPTX) ที่คุณต้องการแปลงเป็น HTML

3. การตั้งค่าสภาพแวดล้อมการพัฒนา Java

## ขั้นตอนที่ 1: นำเข้าไลบรารีที่จำเป็น

ก่อนอื่น คุณต้องนำเข้าไลบรารีและคลาสที่จำเป็นสำหรับโปรเจ็กต์ Java ของคุณ

```java
import com.aspose.slides.Html5Options;
import com.aspose.slides.Presentation;
import com.aspose.slides.SaveFormat;
import java.io.File;
```

## ขั้นตอนที่ 2: โหลดงานนำเสนอ PowerPoint

ต่อไปคุณจะโหลดงานนำเสนอ PowerPoint ที่คุณต้องการแปลงเป็น HTML อย่าลืมแทนที่ `presentationName` พร้อมเส้นทางจริงไปยังไฟล์การนำเสนอของคุณ

```java
String presentationName = "path/to/your/presentation.pptx";
Presentation pres = new Presentation(presentationName);
```

## ขั้นตอนที่ 3: กำหนดค่าตัวเลือกการแปลง HTML

ตอนนี้คุณจะกำหนดค่าตัวเลือกการแปลง HTML ในตัวอย่างนี้ เราจะฝังรูปภาพในเอกสาร HTML และระบุไดเรกทอรีเอาต์พุตสำหรับรูปภาพภายนอก

```java
Html5Options options = new Html5Options();
// บังคับไม่บันทึกภาพลงในเอกสาร HTML5
options.setEmbedImages(true); // ตั้งค่าเป็นจริงเพื่อฝังรูปภาพ
// ตั้งค่าเส้นทางสำหรับภาพภายนอก (ถ้าจำเป็น)
options.setOutputPath("path/to/output/directory/");
```

## ขั้นตอนที่ 4: สร้างไดเรกทอรีผลลัพธ์

ก่อนที่จะบันทึกเอกสาร HTML ให้สร้างไดเร็กทอรีเอาต์พุต ถ้ายังไม่มีอยู่

```java
File outputDirectory = new File(options.getOutputPath());
if (!outputDirectory.exists()) {
    outputDirectory.mkdirs();
}
```

## ขั้นตอนที่ 5: บันทึกการนำเสนอเป็น HTML

ตอนนี้ให้บันทึกการนำเสนอในรูปแบบ HTML5 พร้อมตัวเลือกที่ระบุ

```java
pres.save(options.getOutputPath() + "output.html", SaveFormat.Html5, options);
```

## ขั้นตอนที่ 6: ทำความสะอาดทรัพยากร

อย่าลืมกำจัดวัตถุการนำเสนอเพื่อปล่อยทรัพยากรที่ได้รับการจัดสรร

```java
if (pres != null) {
    pres.dispose();
}
```

## โค้ดต้นฉบับสมบูรณ์สำหรับการแปลงภาพฝัง HTML ใน Java Slides

```java
// การนำเสนอเส้นทางสู่แหล่งที่มา
String presentationName = "Your Document Directory";
// เส้นทางสู่เอกสาร HTML
String outFilePath = "Your Output Directory" + "HTMLConvertion" + File.separator;
Presentation pres = new Presentation(presentationName);
try {
	Html5Options options = new Html5Options();
	// บังคับไม่บันทึกภาพลงในเอกสาร HTML5
	options.setEmbedImages(false);
	// ตั้งค่าเส้นทางสำหรับภาพภายนอก
	options.setOutputPath(outFilePath);
	// สร้างไดเรกทอรีสำหรับการส่งออกเอกสาร HTML
	File f = new File(outFilePath);
	if (!f.exists())
		f.mkdir();
	// บันทึกการนำเสนอในรูปแบบ HTML5
	pres.save(outFilePath + "pres.html", SaveFormat.Html5, options);
} finally {
	if (pres != null) pres.dispose();
}
```

## บทสรุป

ในคู่มือที่ครอบคลุมนี้ เราได้เรียนรู้วิธีการแปลงงานนำเสนอ PowerPoint เป็นเอกสาร HTML ขณะฝังรูปภาพโดยใช้ Aspose.Slides สำหรับ Java เมื่อปฏิบัติตามคำแนะนำทีละขั้นตอนแล้ว คุณสามารถผสานฟังก์ชันนี้เข้ากับแอปพลิเคชัน Java ของคุณได้อย่างราบรื่นและปรับปรุงกระบวนการแปลงเอกสารของคุณ

## คำถามที่พบบ่อย

### ฉันจะเปลี่ยนชื่อไฟล์เอาท์พุตได้อย่างไร?

คุณสามารถเปลี่ยนชื่อไฟล์เอาท์พุตโดยการแก้ไขอาร์กิวเมนต์ใน `pres.save()` วิธี.

### ฉันสามารถปรับแต่งเทมเพลต HTML ได้หรือไม่

ใช่ คุณสามารถปรับแต่งเทมเพลต HTML ได้โดยแก้ไขไฟล์ HTML และ CSS ที่สร้างโดย Aspose.Slides คุณจะพบไฟล์เหล่านี้ในไดเร็กทอรีเอาต์พุต

### ฉันจะจัดการข้อผิดพลาดระหว่างการแปลงอย่างไร

คุณสามารถห่อโค้ดการแปลงในบล็อก try-catch เพื่อจัดการข้อยกเว้นที่อาจเกิดขึ้นในระหว่างกระบวนการแปลงได้


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}