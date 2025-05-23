---
"description": "เรียนรู้วิธีการแปลงงานนำเสนอ PowerPoint เป็น PDF พร้อมสไลด์ที่ซ่อนอยู่โดยใช้ Aspose.Slides สำหรับ Java ปฏิบัติตามคำแนะนำทีละขั้นตอนของเราพร้อมโค้ดต้นฉบับเพื่อสร้าง PDF ได้อย่างราบรื่น"
"linktitle": "แปลงเป็น PDF ด้วยสไลด์ที่ซ่อนอยู่ใน Java Slides"
"second_title": "API การประมวลผล Java PowerPoint ของ Aspose.Slides"
"title": "แปลงเป็น PDF ด้วยสไลด์ที่ซ่อนอยู่ใน Java Slides"
"url": "/th/java/presentation-conversion/convert-pdf-hidden-slides-java-slides/"
"weight": 27
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# แปลงเป็น PDF ด้วยสไลด์ที่ซ่อนอยู่ใน Java Slides


## บทนำสู่การแปลงงานนำเสนอ PowerPoint เป็น PDF พร้อมสไลด์ที่ซ่อนอยู่โดยใช้ Aspose.Slides สำหรับ Java

ในคู่มือทีละขั้นตอนนี้ คุณจะได้เรียนรู้วิธีแปลงงานนำเสนอ PowerPoint เป็น PDF โดยยังคงรักษาสไลด์ที่ซ่อนไว้โดยใช้ Aspose.Slides สำหรับ Java สไลด์ที่ซ่อนไว้คือสไลด์ที่ไม่แสดงในระหว่างการนำเสนอปกติ แต่สามารถรวมอยู่ในผลลัพธ์ PDF ได้ เราจะให้โค้ดต้นฉบับและคำแนะนำโดยละเอียดในการบรรลุภารกิจนี้แก่คุณ

## ข้อกำหนดเบื้องต้น

ก่อนที่คุณจะเริ่มต้น โปรดตรวจสอบให้แน่ใจว่าคุณมีข้อกำหนดเบื้องต้นดังต่อไปนี้:

1. Aspose.Slides สำหรับไลบรารี Java: ตรวจสอบให้แน่ใจว่าคุณได้ตั้งค่าไลบรารี Aspose.Slides สำหรับ Java ไว้ในโปรเจ็กต์ Java ของคุณแล้ว คุณสามารถดาวน์โหลดได้จาก [เอกสาร Aspose.Slides สำหรับ Java](https://reference-aspose.com/slides/java/).

2. สภาพแวดล้อมการพัฒนา Java: คุณควรมีการติดตั้งสภาพแวดล้อมการพัฒนา Java ไว้ในระบบของคุณ

## ขั้นตอนที่ 1: นำเข้า Aspose.Slides สำหรับ Java

ขั้นแรก คุณต้องนำเข้าไลบรารี Aspose.Slides เข้าสู่โปรเจ็กต์ Java ของคุณ ตรวจสอบให้แน่ใจว่าคุณได้เพิ่มไลบรารีลงในเส้นทางการสร้างของโปรเจ็กต์แล้ว

```java
import com.aspose.slides.*;
```

## ขั้นตอนที่ 2: โหลดงานนำเสนอ PowerPoint

คุณจะเริ่มต้นด้วยการโหลดงานนำเสนอ PowerPoint ที่คุณต้องการแปลงเป็น PDF แทนที่ `"Your Document Directory"` และ `"HiddingSlides.pptx"` ด้วยเส้นทางไฟล์ที่เหมาะสม

```java
// เส้นทางไปยังไดเร็กทอรีเอกสาร
String dataDir = "Your Document Directory";
Presentation presentation = new Presentation(dataDir + "HiddingSlides.pptx");
```

## ขั้นตอนที่ 3: กำหนดค่าตัวเลือก PDF

กำหนดค่าตัวเลือก PDF เพื่อรวมสไลด์ที่ซ่อนอยู่ในผลลัพธ์ PDF คุณสามารถทำได้โดยตั้งค่า `setShowHiddenSlides` ทรัพย์สินของ `PdfOptions` ชั้นเรียนถึง `true`-

```java
// สร้างอินสแตนซ์ของคลาส PdfOptions
PdfOptions pdfOptions = new PdfOptions();
// ระบุว่าเอกสารที่สร้างขึ้นควรมีสไลด์ที่ซ่อนอยู่
pdfOptions.setShowHiddenSlides(true);
```

## ขั้นตอนที่ 4: บันทึกการนำเสนอเป็น PDF

ตอนนี้บันทึกการนำเสนอไปยังไฟล์ PDF พร้อมตัวเลือกที่ระบุ แทนที่ `"PDFWithHiddenSlides_out.pdf"` พร้อมชื่อไฟล์เอาท์พุตที่คุณต้องการ

```java
// บันทึกการนำเสนอเป็น PDF พร้อมตัวเลือกที่ระบุ
presentation.save(dataDir + "PDFWithHiddenSlides_out.pdf", SaveFormat.Pdf, pdfOptions);
```

## ขั้นตอนที่ 5: การทำความสะอาดทรัพยากร

อย่าลืมปล่อยทรัพยากรที่ใช้ในการนำเสนอเมื่อคุณทำเสร็จแล้ว

```java
finally
{
    if (presentation != null) presentation.dispose();
}
```

## โค้ดต้นฉบับสมบูรณ์สำหรับการแปลงเป็น PDF พร้อมสไลด์ที่ซ่อนอยู่ใน Java Slides

```java
// เส้นทางไปยังไดเร็กทอรีเอกสาร
String dataDir = "Your Document Directory";
Presentation presentation = new Presentation(dataDir + "HiddingSlides.pptx");
try
{
	// สร้างอินสแตนซ์ของคลาส PdfOptions
	PdfOptions pdfOptions = new PdfOptions();
	// ระบุว่าเอกสารที่สร้างขึ้นควรมีสไลด์ที่ซ่อนอยู่
	pdfOptions.setShowHiddenSlides(true);
	// บันทึกการนำเสนอเป็น PDF พร้อมตัวเลือกที่ระบุ
	presentation.save(dataDir + "PDFWithHiddenSlides_out.pdf", SaveFormat.Pdf, pdfOptions);
}
finally
{
	if (presentation != null) presentation.dispose();
}
```

## บทสรุป

ในคู่มือที่ครอบคลุมนี้ คุณจะได้เรียนรู้วิธีการแปลงงานนำเสนอ PowerPoint เป็น PDF พร้อมรักษาสไลด์ที่ซ่อนอยู่โดยใช้ Aspose.Slides สำหรับ Java เราได้จัดเตรียมบทช่วยสอนแบบทีละขั้นตอนพร้อมโค้ดต้นฉบับที่จำเป็นเพื่อให้ทำงานนี้ได้อย่างราบรื่น

## คำถามที่พบบ่อย

### ฉันจะซ่อนสไลด์ในการนำเสนอ PowerPoint ได้อย่างไร

หากต้องการซ่อนสไลด์ในงานนำเสนอ PowerPoint ให้ทำตามขั้นตอนเหล่านี้:
1. เลือกสไลด์ที่คุณต้องการซ่อนในมุมมองตัวเรียงลำดับสไลด์
2. คลิกขวาที่สไลด์ที่เลือก
3. เลือก “ซ่อนสไลด์” จากเมนูบริบท

### ฉันสามารถแสดงสไลด์ที่ซ่อนอยู่ใน Aspose.Slides สำหรับ Java โดยใช้โปรแกรมได้หรือไม่

ใช่ คุณสามารถแสดงสไลด์ที่ซ่อนอยู่ใน Aspose.Slides สำหรับ Java ได้ด้วยการตั้งค่า `Hidden` ทรัพย์สินของ `Slide` ชั้นเรียนถึง `false`นี่คือตัวอย่าง:

```java
Slide slide = presentation.getSlides().get_Item(slideIndex); // แทนที่ slideIndex ด้วยดัชนีของสไลด์ที่ซ่อนอยู่
slide.setHidden(false);
```

### ฉันจะดาวน์โหลด Aspose.Slides สำหรับ Java ได้อย่างไร?

คุณสามารถดาวน์โหลด Aspose.Slides สำหรับ Java ได้จากเว็บไซต์ Aspose เยี่ยมชม [หน้าดาวน์โหลด Aspose.Slides สำหรับ Java](https://releases.aspose.com/slides/java/) เพื่อรับเวอร์ชันล่าสุด

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}