---
"description": "ปรับปรุงการนำเสนอ PowerPoint ด้วยข้อมูลเมตาที่อัปเดตโดยใช้ Aspose.Slides สำหรับ Java เรียนรู้การอัปเดตคุณสมบัติ เช่น ผู้เขียน ชื่อเรื่อง และคำสำคัญโดยใช้เทมเพลตใน Java Slides"
"linktitle": "อัปเดตคุณสมบัติการนำเสนอโดยใช้การนำเสนออื่นเป็นเทมเพลตใน Java Slides"
"second_title": "API การประมวลผล Java PowerPoint ของ Aspose.Slides"
"title": "อัปเดตคุณสมบัติการนำเสนอโดยใช้การนำเสนออื่นเป็นเทมเพลตใน Java Slides"
"url": "/th/java/media-controls/update-presentation-properties-using-another-presentation-as-a-template-in-java-slides/"
"weight": 14
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# อัปเดตคุณสมบัติการนำเสนอโดยใช้การนำเสนออื่นเป็นเทมเพลตใน Java Slides


## บทนำเกี่ยวกับการอัปเดตคุณสมบัติการนำเสนอโดยใช้การนำเสนออื่นเป็นเทมเพลตใน Java Slides

ในบทช่วยสอนนี้ เราจะแนะนำคุณเกี่ยวกับกระบวนการอัปเดตคุณสมบัติการนำเสนอ (ข้อมูลเมตา) สำหรับการนำเสนอ PowerPoint โดยใช้ Aspose.Slides สำหรับ Java คุณสามารถใช้การนำเสนออื่นเป็นเทมเพลตเพื่ออัปเดตคุณสมบัติ เช่น ผู้เขียน ชื่อเรื่อง คำสำคัญ และอื่นๆ เราจะให้คำแนะนำทีละขั้นตอนและตัวอย่างโค้ดต้นฉบับแก่คุณ

## ข้อกำหนดเบื้องต้น

ก่อนเริ่มต้น ตรวจสอบให้แน่ใจว่าคุณได้รวมไลบรารี Aspose.Slides สำหรับ Java ไว้ในโปรเจ็กต์ Java ของคุณแล้ว คุณสามารถดาวน์โหลดได้จาก [ที่นี่](https://releases-aspose.com/slides/java/).

## ขั้นตอนที่ 1: ตั้งค่าโครงการของคุณ

ตรวจสอบให้แน่ใจว่าคุณได้สร้างโปรเจ็กต์ Java และเพิ่มไลบรารี Aspose.Slides สำหรับ Java ลงในส่วนที่ต้องมีของโปรเจ็กต์ของคุณแล้ว

## ขั้นตอนที่ 2: นำเข้าแพ็คเกจที่จำเป็น

คุณจะต้องนำเข้าแพ็กเกจ Aspose.Slides ที่จำเป็นสำหรับการใช้งานคุณสมบัติการนำเสนอ ใส่คำสั่งนำเข้าต่อไปนี้ไว้ที่จุดเริ่มต้นของคลาส Java ของคุณ:

```java
import com.aspose.slides.DocumentProperties;
import com.aspose.slides.IDocumentProperties;
import com.aspose.slides.IPresentationInfo;
import com.aspose.slides.PresentationFactory;
```

## ขั้นตอนที่ 3: อัปเดตคุณสมบัติการนำเสนอ

ตอนนี้เรามาอัปเดตคุณสมบัติของการนำเสนอโดยใช้การนำเสนออื่นเป็นเทมเพลต ในตัวอย่างนี้ เราจะอัปเดตคุณสมบัติของการนำเสนอหลายรายการ แต่คุณสามารถปรับเปลี่ยนโค้ดนี้ให้เหมาะกับกรณีการใช้งานเฉพาะของคุณได้

```java
// เส้นทางไปยังไดเร็กทอรีเอกสาร
String dataDir = "Your Document Directory";

// โหลดเทมเพลตการนำเสนอที่คุณต้องการคัดลอกคุณสมบัติ
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

// อัปเดตการนำเสนอหลายรายการโดยใช้เทมเพลตเดียวกัน
updateByTemplate(dataDir + "doc1.pptx", template);
updateByTemplate(dataDir + "doc2.odp", template);
updateByTemplate(dataDir + "doc3.ppt", template);
```

## ขั้นตอนที่ 4: กำหนด `updateByTemplate` วิธี

เรามากำหนดวิธีการอัปเดตคุณสมบัติของงานนำเสนอแต่ละรายการโดยใช้เทมเพลตกัน วิธีการนี้จะใช้เส้นทางของงานนำเสนอที่จะอัปเดตและคุณสมบัติของเทมเพลตเป็นพารามิเตอร์

```java
private static void updateByTemplate(String path, IDocumentProperties template)
{
    // โหลดงานนำเสนอเพื่ออัพเดต
    IPresentationInfo toUpdate = PresentationFactory.getInstance().getPresentationInfo(path);
    
    // อัปเดตคุณสมบัติของเอกสารโดยใช้เทมเพลต
    toUpdate.updateDocumentProperties(template);
    
    // บันทึกการนำเสนอที่อัปเดต
    toUpdate.writeBindedPresentation(path);
}
```

## โค้ดต้นฉบับที่สมบูรณ์สำหรับการอัปเดตคุณสมบัติการนำเสนอโดยใช้การนำเสนออื่นเป็นเทมเพลตใน Java Slides

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

ในบทช่วยสอนที่ครอบคลุมนี้ เราได้ศึกษาวิธีการอัปเดตคุณสมบัติการนำเสนอในงานนำเสนอ PowerPoint โดยใช้ Aspose.Slides สำหรับ Java โดยเน้นไปที่การใช้การนำเสนออื่นเป็นเทมเพลตเพื่ออัปเดตข้อมูลเมตาอย่างมีประสิทธิภาพ เช่น ชื่อผู้เขียน ชื่อเรื่อง คำหลัก และอื่นๆ

## คำถามที่พบบ่อย

### ฉันจะอัปเดตคุณสมบัติสำหรับการนำเสนอเพิ่มเติมได้อย่างไร

คุณสามารถอัปเดตคุณสมบัติสำหรับการนำเสนอหลายรายการได้โดยเรียกใช้ `updateByTemplate` วิธีการสำหรับการนำเสนอแต่ละครั้งตามเส้นทางที่ต้องการ

### ฉันสามารถปรับแต่งโค้ดนี้สำหรับคุณสมบัติที่แตกต่างกันได้หรือไม่

ใช่ คุณสามารถปรับแต่งโค้ดเพื่ออัปเดตคุณสมบัติเฉพาะตามความต้องการของคุณ เพียงแก้ไข `template` วัตถุที่มีค่าคุณสมบัติตามที่ต้องการ

### มีข้อจำกัดใด ๆ เกี่ยวกับประเภทของการนำเสนอที่สามารถอัปเดตได้หรือไม่?

ไม่ คุณสามารถอัปเดตคุณสมบัติสำหรับการนำเสนอในรูปแบบต่างๆ รวมถึง PPTX, ODP และ PPT

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}