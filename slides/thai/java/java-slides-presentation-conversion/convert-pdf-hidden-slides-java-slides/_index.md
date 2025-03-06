---
title: แปลงเป็น PDF ด้วยสไลด์ที่ซ่อนอยู่ใน Java Slides
linktitle: แปลงเป็น PDF ด้วยสไลด์ที่ซ่อนอยู่ใน Java Slides
second_title: Aspose.Slides Java PowerPoint การประมวลผล API
description: เรียนรู้วิธีแปลงงานนำเสนอ PowerPoint เป็น PDF ด้วยสไลด์ที่ซ่อนอยู่โดยใช้ Aspose.Slides สำหรับ Java ปฏิบัติตามคำแนะนำทีละขั้นตอนพร้อมซอร์สโค้ดเพื่อสร้าง PDF ได้อย่างราบรื่น
weight: 27
url: /th/java/presentation-conversion/convert-pdf-hidden-slides-java-slides/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# แปลงเป็น PDF ด้วยสไลด์ที่ซ่อนอยู่ใน Java Slides


## ข้อมูลเบื้องต้นเกี่ยวกับการแปลงงานนำเสนอ PowerPoint เป็น PDF พร้อมสไลด์ที่ซ่อนอยู่โดยใช้ Aspose.Slides สำหรับ Java

ในคำแนะนำทีละขั้นตอนนี้ คุณจะได้เรียนรู้วิธีแปลงงานนำเสนอ PowerPoint เป็น PDF ในขณะที่ยังคงรักษาสไลด์ที่ซ่อนไว้โดยใช้ Aspose.Slides สำหรับ Java สไลด์ที่ซ่อนคือสไลด์ที่ไม่ได้แสดงในระหว่างการนำเสนอตามปกติ แต่สามารถรวมไว้ในเอาต์พุต PDF ได้ เราจะให้ซอร์สโค้ดและคำแนะนำโดยละเอียดแก่คุณเพื่อให้บรรลุงานนี้

## ข้อกำหนดเบื้องต้น

ก่อนที่คุณจะเริ่มต้น ตรวจสอบให้แน่ใจว่าคุณมีข้อกำหนดเบื้องต้นต่อไปนี้:

1.  Aspose.Slides สำหรับไลบรารี Java: ตรวจสอบให้แน่ใจว่าคุณได้ตั้งค่าไลบรารี Aspose.Slides สำหรับ Java ในโปรเจ็กต์ Java ของคุณ คุณสามารถดาวน์โหลดได้จาก[Aspose.Slides สำหรับเอกสาร Java](https://reference.aspose.com/slides/java/).

2. สภาพแวดล้อมการพัฒนา Java: คุณควรติดตั้งสภาพแวดล้อมการพัฒนา Java บนระบบของคุณ

## ขั้นตอนที่ 1: นำเข้า Aspose.Slides สำหรับ Java

ขั้นแรก คุณต้องนำเข้าไลบรารี Aspose.Slides ไปยังโปรเจ็กต์ Java ของคุณ ตรวจสอบให้แน่ใจว่าคุณได้เพิ่มไลบรารีลงในเส้นทางการ build ของโปรเจ็กต์ของคุณแล้ว

```java
import com.aspose.slides.*;
```

## ขั้นตอนที่ 2: โหลดงานนำเสนอ PowerPoint

 คุณจะเริ่มต้นด้วยการโหลดงานนำเสนอ PowerPoint ที่คุณต้องการแปลงเป็น PDF แทนที่`"Your Document Directory"` และ`"HiddingSlides.pptx"` ด้วยเส้นทางไฟล์ที่เหมาะสม

```java
// เส้นทางไปยังไดเร็กทอรีเอกสาร
String dataDir = "Your Document Directory";
Presentation presentation = new Presentation(dataDir + "HiddingSlides.pptx");
```

## ขั้นตอนที่ 3: กำหนดค่าตัวเลือก PDF

กำหนดค่าตัวเลือก PDF เพื่อรวมสไลด์ที่ซ่อนอยู่ในเอาต์พุต PDF คุณสามารถทำได้โดยการตั้งค่า`setShowHiddenSlides` ทรัพย์สินของ`PdfOptions` ชั้นเรียนไป`true`.

```java
// สร้างอินสแตนซ์คลาส PdfOptions
PdfOptions pdfOptions = new PdfOptions();
// ระบุว่าเอกสารที่สร้างขึ้นควรมีสไลด์ที่ซ่อนอยู่
pdfOptions.setShowHiddenSlides(true);
```

## ขั้นตอนที่ 4: บันทึกงานนำเสนอเป็น PDF

 ตอนนี้ ให้บันทึกงานนำเสนอเป็นไฟล์ PDF พร้อมตัวเลือกที่ระบุ แทนที่`"PDFWithHiddenSlides_out.pdf"` ด้วยชื่อไฟล์เอาต์พุตที่คุณต้องการ

```java
// บันทึกงานนำเสนอเป็น PDF พร้อมตัวเลือกที่ระบุ
presentation.save(dataDir + "PDFWithHiddenSlides_out.pdf", SaveFormat.Pdf, pdfOptions);
```

## ขั้นตอนที่ 5: ทรัพยากรการล้างข้อมูล

ตรวจสอบให้แน่ใจว่าได้เผยแพร่ทรัพยากรที่ใช้โดยงานนำเสนอเมื่อคุณทำเสร็จแล้ว

```java
finally
{
    if (presentation != null) presentation.dispose();
}
```

## กรอกซอร์สโค้ดสำหรับการแปลงเป็น PDF พร้อมสไลด์ที่ซ่อนอยู่ใน Java Slides

```java
// เส้นทางไปยังไดเร็กทอรีเอกสาร
String dataDir = "Your Document Directory";
Presentation presentation = new Presentation(dataDir + "HiddingSlides.pptx");
try
{
	// สร้างอินสแตนซ์คลาส PdfOptions
	PdfOptions pdfOptions = new PdfOptions();
	// ระบุว่าเอกสารที่สร้างขึ้นควรมีสไลด์ที่ซ่อนอยู่
	pdfOptions.setShowHiddenSlides(true);
	// บันทึกงานนำเสนอเป็น PDF พร้อมตัวเลือกที่ระบุ
	presentation.save(dataDir + "PDFWithHiddenSlides_out.pdf", SaveFormat.Pdf, pdfOptions);
}
finally
{
	if (presentation != null) presentation.dispose();
}
```

## บทสรุป

ในคู่มือที่ครอบคลุมนี้ คุณได้เรียนรู้วิธีแปลงงานนำเสนอ PowerPoint เป็น PDF ในขณะที่ยังคงรักษาสไลด์ที่ซ่อนอยู่โดยใช้ Aspose.Slides สำหรับ Java เราได้จัดเตรียมบทช่วยสอนแบบทีละขั้นตอนพร้อมกับซอร์สโค้ดที่จำเป็นเพื่อให้งานนี้สำเร็จลุล่วงได้อย่างราบรื่น

## คำถามที่พบบ่อย

### ฉันจะซ่อนสไลด์ในงานนำเสนอ PowerPoint ได้อย่างไร

หากต้องการซ่อนสไลด์ในงานนำเสนอ PowerPoint ให้ทำตามขั้นตอนเหล่านี้:
1. เลือกสไลด์ที่คุณต้องการซ่อนในมุมมองตัวเรียงลำดับสไลด์
2. คลิกขวาที่สไลด์ที่เลือก
3. เลือก "ซ่อนสไลด์" จากเมนูบริบท

### ฉันสามารถยกเลิกการซ่อนสไลด์ที่ซ่อนอยู่ใน Aspose.Slides สำหรับ Java โดยทางโปรแกรมได้หรือไม่

 ได้ คุณสามารถเลิกซ่อนสไลด์ที่ซ่อนอยู่ใน Aspose.Slides สำหรับ Java โดยทางโปรแกรมได้โดยการตั้งค่า`Hidden` ทรัพย์สินของ`Slide` ชั้นเรียนไป`false`- นี่คือตัวอย่าง:

```java
Slide slide = presentation.getSlides().get_Item(slideIndex); // แทนที่ slideIndex ด้วยดัชนีของสไลด์ที่ซ่อนอยู่
slide.setHidden(false);
```

### ฉันจะดาวน์โหลด Aspose.Slides สำหรับ Java ได้อย่างไร

 คุณสามารถดาวน์โหลด Aspose.Slides สำหรับ Java ได้จากเว็บไซต์ Aspose เยี่ยมชม[Aspose.Slides สำหรับหน้าดาวน์โหลด Java](https://releases.aspose.com/slides/java/) เพื่อรับเวอร์ชันล่าสุด
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
