---
title: แปลงรูปภาพที่ฝัง HTML ใน Java Slides
linktitle: แปลงรูปภาพที่ฝัง HTML ใน Java Slides
second_title: Aspose.Slides Java PowerPoint การประมวลผล API
description: แปลง PowerPoint เป็น HTML ด้วยรูปภาพที่ฝังไว้ คำแนะนำทีละขั้นตอนโดยใช้ Aspose.Slides สำหรับ Java เรียนรู้การแปลงการนำเสนออัตโนมัติใน Java ได้อย่างง่ายดาย
weight: 11
url: /th/java/presentation-conversion/convert-html-embedding-images-java-slides/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# แปลงรูปภาพที่ฝัง HTML ใน Java Slides


## ข้อมูลเบื้องต้นเกี่ยวกับการแปลงรูปภาพที่ฝัง HTML ใน Java Slides

ในคำแนะนำทีละขั้นตอนนี้ เราจะแนะนำคุณตลอดขั้นตอนการแปลงงานนำเสนอ PowerPoint เป็นเอกสาร HTML ในขณะที่ฝังรูปภาพโดยใช้ Aspose.Slides สำหรับ Java บทช่วยสอนนี้จะถือว่าคุณได้ตั้งค่าสภาพแวดล้อมการพัฒนาของคุณแล้วและติดตั้งไลบรารี Aspose.Slides สำหรับ Java แล้ว

## ความต้องการ

ก่อนที่เราจะเริ่ม ตรวจสอบให้แน่ใจว่าคุณมีสิ่งต่อไปนี้:

1.  ติดตั้ง Aspose.Slides สำหรับไลบรารี Java แล้ว คุณสามารถดาวน์โหลดได้จาก[ที่นี่](https://downloads.aspose.com/slides/java).

2. ไฟล์งานนำเสนอ PowerPoint (รูปแบบ PPTX) ที่คุณต้องการแปลงเป็น HTML

3. ตั้งค่าสภาพแวดล้อมการพัฒนา Java

## ขั้นตอนที่ 1: นำเข้าไลบรารีที่จำเป็น

ขั้นแรก คุณต้องนำเข้าไลบรารีและคลาสที่จำเป็นสำหรับโปรเจ็กต์ Java ของคุณ

```java
import com.aspose.slides.Html5Options;
import com.aspose.slides.Presentation;
import com.aspose.slides.SaveFormat;
import java.io.File;
```

## ขั้นตอนที่ 2: โหลดงานนำเสนอ PowerPoint

 ถัดไป คุณจะโหลดงานนำเสนอ PowerPoint ที่คุณต้องการแปลงเป็น HTML ตรวจสอบให้แน่ใจว่าได้เปลี่ยน`presentationName` พร้อมเส้นทางจริงไปยังไฟล์การนำเสนอของคุณ

```java
String presentationName = "path/to/your/presentation.pptx";
Presentation pres = new Presentation(presentationName);
```

## ขั้นตอนที่ 3: กำหนดค่าตัวเลือกการแปลง HTML

ตอนนี้ คุณจะกำหนดค่าตัวเลือกการแปลง HTML แล้ว ในตัวอย่างนี้ เราจะฝังรูปภาพในเอกสาร HTML และระบุไดเร็กทอรีเอาต์พุตสำหรับรูปภาพภายนอก

```java
Html5Options options = new Html5Options();
// บังคับไม่บันทึกรูปภาพในเอกสาร HTML5
options.setEmbedImages(true); // ตั้งค่าเป็นจริงเพื่อฝังรูปภาพ
//กำหนดเส้นทางสำหรับภาพภายนอก (หากจำเป็น)
options.setOutputPath("path/to/output/directory/");
```

## ขั้นตอนที่ 4: สร้างไดเรกทอรีผลลัพธ์

ก่อนที่จะบันทึกเอกสาร HTML ให้สร้างไดเร็กทอรีเอาต์พุตหากไม่มีอยู่

```java
File outputDirectory = new File(options.getOutputPath());
if (!outputDirectory.exists()) {
    outputDirectory.mkdirs();
}
```

## ขั้นตอนที่ 5: บันทึกการนำเสนอเป็น HTML

ตอนนี้ บันทึกงานนำเสนอในรูปแบบ HTML5 ด้วยตัวเลือกที่ระบุ

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

## ซอร์สโค้ดที่สมบูรณ์สำหรับการแปลงรูปภาพที่ฝัง HTML ใน Java Slides

```java
// เส้นทางสู่การนำเสนอแหล่งที่มา
String presentationName = "Your Document Directory";
// เส้นทางไปยังเอกสาร HTML
String outFilePath = "Your Output Directory" + "HTMLConvertion" + File.separator;
Presentation pres = new Presentation(presentationName);
try {
	Html5Options options = new Html5Options();
	// บังคับไม่บันทึกรูปภาพในเอกสาร HTML5
	options.setEmbedImages(false);
	// กำหนดเส้นทางสำหรับภาพภายนอก
	options.setOutputPath(outFilePath);
	// สร้างไดเร็กทอรีสำหรับเอกสาร HTML เอาท์พุต
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

ในคู่มือที่ครอบคลุมนี้ เราได้เรียนรู้วิธีแปลงงานนำเสนอ PowerPoint เป็นเอกสาร HTML ในขณะที่ฝังรูปภาพโดยใช้ Aspose.Slides สำหรับ Java ด้วยการทำตามคำแนะนำทีละขั้นตอน คุณสามารถรวมฟังก์ชันการทำงานนี้เข้ากับแอปพลิเคชัน Java ของคุณได้อย่างราบรื่น และปรับปรุงกระบวนการแปลงเอกสารของคุณ

## คำถามที่พบบ่อย

### ฉันจะเปลี่ยนชื่อไฟล์เอาต์พุตได้อย่างไร

 คุณสามารถเปลี่ยนชื่อไฟล์เอาต์พุตได้โดยการแก้ไขอาร์กิวเมนต์ใน`pres.save()` วิธี.

### ฉันสามารถปรับแต่งเทมเพลต HTML ได้หรือไม่

ใช่ คุณสามารถปรับแต่งเทมเพลต HTML ได้โดยแก้ไขไฟล์ HTML และ CSS ที่สร้างโดย Aspose.Slides คุณจะพบพวกมันในไดเรกทอรีผลลัพธ์

### ฉันจะจัดการกับข้อผิดพลาดระหว่างการแปลงได้อย่างไร

คุณสามารถล้อมโค้ดการแปลงไว้ในบล็อก try-catch เพื่อจัดการกับข้อยกเว้นที่อาจเกิดขึ้นระหว่างกระบวนการแปลง

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
