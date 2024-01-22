---
title: อัปเดตคุณสมบัติการนำเสนอโดยใช้การนำเสนออื่นเป็นเทมเพลตใน Java Slides
linktitle: อัปเดตคุณสมบัติการนำเสนอโดยใช้การนำเสนออื่นเป็นเทมเพลตใน Java Slides
second_title: Aspose.Slides Java PowerPoint การประมวลผล API
description: ปรับปรุงงานนำเสนอ PowerPoint ด้วยข้อมูลเมตาที่อัปเดตโดยใช้ Aspose.Slides สำหรับ Java เรียนรู้การอัปเดตคุณสมบัติ เช่น ผู้แต่ง ชื่อเรื่อง และคำสำคัญโดยใช้เทมเพลตใน Java Slides
type: docs
weight: 14
url: /th/java/media-controls/update-presentation-properties-using-another-presentation-as-a-template-in-java-slides/
---

## ข้อมูลเบื้องต้นเกี่ยวกับการอัปเดตคุณสมบัติการนำเสนอโดยใช้การนำเสนออื่นเป็นเทมเพลตใน Java Slides

ในบทช่วยสอนนี้ เราจะแนะนำคุณตลอดกระบวนการอัปเดตคุณสมบัติการนำเสนอ (เมตาดาต้า) สำหรับงานนำเสนอ PowerPoint โดยใช้ Aspose.Slides สำหรับ Java คุณสามารถใช้งานนำเสนออื่นเป็นเทมเพลตเพื่ออัปเดตคุณสมบัติ เช่น ผู้แต่ง ชื่อเรื่อง คำสำคัญ และอื่นๆ เราจะให้คำแนะนำทีละขั้นตอนและตัวอย่างซอร์สโค้ดแก่คุณ

## ข้อกำหนดเบื้องต้น

 ก่อนที่คุณจะเริ่มต้น ตรวจสอบให้แน่ใจว่าคุณได้รวมไลบรารี Aspose.Slides สำหรับ Java เข้ากับโปรเจ็กต์ Java ของคุณแล้ว คุณสามารถดาวน์โหลดได้จาก[ที่นี่](https://releases.aspose.com/slides/java/).

## ขั้นตอนที่ 1: ตั้งค่าโครงการของคุณ

ตรวจสอบให้แน่ใจว่าคุณได้สร้างโปรเจ็กต์ Java และเพิ่มไลบรารี Aspose.Slides สำหรับ Java ลงในการขึ้นต่อกันของโปรเจ็กต์ของคุณ

## ขั้นตอนที่ 2: นำเข้าแพ็คเกจที่จำเป็น

คุณจะต้องนำเข้าแพ็คเกจ Aspose.Slides ที่จำเป็นสำหรับการทำงานกับคุณสมบัติการนำเสนอ รวมคำสั่งการนำเข้าต่อไปนี้ที่จุดเริ่มต้นของคลาส Java ของคุณ:

```java
import com.aspose.slides.DocumentProperties;
import com.aspose.slides.IDocumentProperties;
import com.aspose.slides.IPresentationInfo;
import com.aspose.slides.PresentationFactory;
```

## ขั้นตอนที่ 3: อัปเดตคุณสมบัติการนำเสนอ

ตอนนี้ มาอัปเดตคุณสมบัติการนำเสนอโดยใช้งานนำเสนออื่นเป็นเทมเพลตกันดีกว่า ในตัวอย่างนี้ เราจะอัปเดตคุณสมบัติสำหรับการนำเสนอหลายรายการ แต่คุณสามารถปรับโค้ดนี้ให้เหมาะกับกรณีการใช้งานเฉพาะของคุณได้

```java
// เส้นทางไปยังไดเร็กทอรีเอกสาร
String dataDir = "Your Document Directory";

// โหลดการนำเสนอเทมเพลตที่คุณต้องการคัดลอกคุณสมบัติ
DocumentProperties template;
IPresentationInfo info = PresentationFactory.getInstance().getPresentationInfo(dataDir + "template.pptx");
template = (DocumentProperties) info.readDocumentProperties();

// ตั้งค่าคุณสมบัติที่คุณต้องการอัปเดต
template.setAuthor("Template Author");
template.setTitle("Template Title");
template.setCategory("Template Category");
template.setKeywords("Keyword1, Keyword2, Keyword3");
template.setCompany("Our Company");
template.setComments("Created from template");
template.setContentType("Template Content");
template.setSubject("Template Subject");

// อัปเดตงานนำเสนอหลายรายการโดยใช้เทมเพลตเดียวกัน
updateByTemplate(dataDir + "doc1.pptx", template);
updateByTemplate(dataDir + "doc2.odp", template);
updateByTemplate(dataDir + "doc3.ppt", template);
```

##  ขั้นตอนที่ 4: กำหนด`updateByTemplate` Method

เรามากำหนดวิธีการอัปเดตคุณสมบัติของงานนำเสนอแต่ละรายการโดยใช้เทมเพลต วิธีการนี้จะใช้เส้นทางของการนำเสนอที่จะอัปเดตและคุณสมบัติเทมเพลตเป็นพารามิเตอร์

```java
private static void updateByTemplate(String path, IDocumentProperties template)
{
    // โหลดงานนำเสนอที่จะอัปเดต
    IPresentationInfo toUpdate = PresentationFactory.getInstance().getPresentationInfo(path);
    
    // อัพเดตคุณสมบัติเอกสารโดยใช้เทมเพลต
    toUpdate.updateDocumentProperties(template);
    
    // บันทึกการนำเสนอที่อัปเดต
    toUpdate.writeBindedPresentation(path);
}
```

## กรอกซอร์สโค้ดให้สมบูรณ์เพื่ออัพเดตคุณสมบัติการนำเสนอโดยใช้การนำเสนออื่นเป็นเทมเพลตใน Java Slides

```java
	// เส้นทางไปยังไดเร็กทอรีเอกสาร
	String dataDir = "Your Document Directory";
	DocumentProperties template;
	IPresentationInfo info = PresentationFactory.getInstance().getPresentationInfo(dataDir + "template.pptx");
	template = (DocumentProperties) info.readDocumentProperties();
	template.setAuthor("Template Author");
	template.setTitle("Template Title");
	template.setCategory("Template Category");
	template.setKeywords("Keyword1, Keyword2, Keyword3");
	template.setCompany("Our Company");
	template.setComments("Created from template");
	template.setContentType("Template Content");
	template.setSubject("Template Subject");
	updateByTemplate(dataDir + "doc1.pptx", template);
	updateByTemplate(dataDir + "doc2.odp", template);
	updateByTemplate(dataDir + "doc3.ppt", template);
}
private static void updateByTemplate(String path, IDocumentProperties template)
{
	IPresentationInfo toUpdate = PresentationFactory.getInstance().getPresentationInfo(path);
	toUpdate.updateDocumentProperties(template);
	toUpdate.writeBindedPresentation(path);
```

## บทสรุป

ในบทช่วยสอนที่ครอบคลุมนี้ เราได้สำรวจวิธีอัปเดตคุณสมบัติการนำเสนอในงานนำเสนอ PowerPoint โดยใช้ Aspose.Slides สำหรับ Java เราเน้นไปที่การใช้งานนำเสนออื่นเป็นเทมเพลตเพื่ออัปเดตข้อมูลเมตาอย่างมีประสิทธิภาพ เช่น ชื่อผู้แต่ง ชื่อเรื่อง คำสำคัญ และอื่นๆ

## คำถามที่พบบ่อย

### ฉันจะอัพเดตคุณสมบัติสำหรับการนำเสนอเพิ่มเติมได้อย่างไร?

 คุณสามารถอัปเดตคุณสมบัติสำหรับการนำเสนอหลายรายการได้โดยการเรียก`updateByTemplate` วิธีการนำเสนอแต่ละครั้งด้วยเส้นทางที่ต้องการ

### ฉันสามารถปรับแต่งโค้ดนี้สำหรับคุณสมบัติต่างๆ ได้หรือไม่

ใช่ คุณสามารถปรับแต่งโค้ดเพื่ออัปเดตคุณสมบัติเฉพาะตามความต้องการของคุณได้ เพียงปรับเปลี่ยน`template` วัตถุที่มีค่าคุณสมบัติที่ต้องการ

### มีข้อจำกัดเกี่ยวกับประเภทของการนำเสนอที่สามารถอัปเดตได้หรือไม่?

ไม่ได้ คุณสามารถอัปเดตคุณสมบัติสำหรับการนำเสนอในรูปแบบต่างๆ ได้ รวมถึง PPTX, ODP และ PPT