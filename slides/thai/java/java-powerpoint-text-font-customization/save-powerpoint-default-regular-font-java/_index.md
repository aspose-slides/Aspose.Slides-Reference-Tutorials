---
"description": "เรียนรู้วิธีการจัดการการนำเสนอ PowerPoint ด้วยโปรแกรมโดยใช้ Aspose.Slides สำหรับ Java เชี่ยวชาญการจัดการ PowerPoint ในรูปแบบ Java ด้วยบทช่วยสอนแบบทีละขั้นตอน"
"linktitle": "บันทึก PowerPoint ด้วยแบบอักษรปกติเริ่มต้นโดยใช้ Java"
"second_title": "API การประมวลผล Java PowerPoint ของ Aspose.Slides"
"title": "บันทึก PowerPoint ด้วยแบบอักษรปกติเริ่มต้นโดยใช้ Java"
"url": "/th/java/java-powerpoint-text-font-customization/save-powerpoint-default-regular-font-java/"
"weight": 12
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# บันทึก PowerPoint ด้วยแบบอักษรปกติเริ่มต้นโดยใช้ Java

## การแนะนำ
ในขอบเขตของการพัฒนา Java การสร้างและจัดการการนำเสนอ PowerPoint ด้วยโปรแกรมสามารถเพิ่มประสิทธิภาพการทำงานและตัวเลือกการปรับแต่งได้อย่างมาก Aspose.Slides สำหรับ Java เป็นไลบรารีที่มีประสิทธิภาพที่ช่วยให้ผู้พัฒนาสามารถจัดการไฟล์ PowerPoint ได้อย่างมีประสิทธิภาพ โดยนำเสนอชุดคุณลักษณะที่ครอบคลุมตั้งแต่การปรับเปลี่ยนเล็กน้อยไปจนถึงการนำเสนอที่ซับซ้อน
## ข้อกำหนดเบื้องต้น
ก่อนที่จะเริ่มใช้ Aspose.Slides สำหรับ Java โปรดตรวจสอบให้แน่ใจว่าคุณได้ตั้งค่าข้อกำหนดเบื้องต้นดังต่อไปนี้:
1. Java Development Kit (JDK): Aspose.Slides สำหรับ Java ต้องใช้ JDK 1.8 ขึ้นไปจึงจะทำงานได้อย่างถูกต้อง
2. Aspose.Slides สำหรับ Java JAR: ดาวน์โหลด Aspose.Slides สำหรับ Java เวอร์ชันล่าสุดได้จาก [ที่นี่](https://releases-aspose.com/slides/java/).
3. สภาพแวดล้อมการพัฒนาแบบบูรณาการ (IDE): ใช้ IntelliJ IDEA, Eclipse หรือ Java IDE อื่นๆ ตามที่คุณเลือก
4. ความเข้าใจพื้นฐานเกี่ยวกับ Java: มีความคุ้นเคยกับพื้นฐานของภาษาการเขียนโปรแกรม Java เป็นสิ่งจำเป็น

## แพ็คเกจนำเข้า
ในการเริ่มใช้ Aspose.Slides สำหรับ Java ให้ทำการนำเข้าแพ็กเกจที่จำเป็น:
```java
import com.aspose.slides.HtmlOptions;
import com.aspose.slides.PdfOptions;
import com.aspose.slides.Presentation;
import com.aspose.slides.SaveFormat;
```
ซึ่งทำให้แน่ใจว่าคุณสามารถเข้าถึงคลาสและวิธีการทั้งหมดที่ Aspose.Slides สำหรับ Java จัดทำไว้
## ขั้นตอนที่ 1: ตั้งค่าโครงการของคุณ
ขั้นแรก ให้สร้างโปรเจ็กต์ Java ใหม่ใน IDE ของคุณ และรวมไฟล์ Aspose.Slides สำหรับ Java JAR ลงในเส้นทางการสร้างโปรเจ็กต์ของคุณ
## ขั้นตอนที่ 2: เริ่มต้นวัตถุการนำเสนอ
สร้างตัวอย่าง `Presentation` วัตถุโดยการโหลดไฟล์ PowerPoint ที่มีอยู่ (.pptx) จากไดเร็กทอรีภายในเครื่องของคุณ
```java
String dataDir = "Your Document Directory";
String outPath = "Your Output Directory";
// โหลดการนำเสนอ
Presentation pres = new Presentation(dataDir + "DefaultFonts.pptx");
```
แทนที่ `"Your Document Directory"` และ `"Your Output Directory"` ด้วยเส้นทางไฟล์จริงของคุณ
## ขั้นตอนที่ 3: บันทึกการนำเสนอด้วยแบบอักษรปกติเริ่มต้น
ระบุแบบอักษรปกติเริ่มต้นสำหรับรูปแบบเอาต์พุต (HTML และ PDF) โดยใช้ `HtmlOptions` และ `PdfOptions` ตามลำดับ
```java
try {
    // ตัวเลือกการบันทึก HTML
    HtmlOptions htmlOpts = new HtmlOptions();
    htmlOpts.setDefaultRegularFont("Arial Black");
    pres.save(outPath + "Presentation-out-ArialBlack.html", SaveFormat.Html, htmlOpts);
    htmlOpts.setDefaultRegularFont("Lucida Console");
    pres.save(outPath + "Presentation-out-LucidaConsole.html", SaveFormat.Html, htmlOpts);
    // ตัวเลือกการบันทึก PDF
    PdfOptions pdfOpts = new PdfOptions();
    pdfOpts.setDefaultRegularFont("Arial Black");
    pres.save(outPath + "Presentation-out-ArialBlack.pdf", SaveFormat.Pdf, pdfOpts);
} finally {
    if (pres != null) pres.dispose();
}
```
ให้แน่ใจว่าจะเปลี่ยน `"Arial Black"` และ `"Lucida Console"` ด้วยแบบอักษรปกติเริ่มต้นตามที่คุณต้องการ

## บทสรุป
หากทำตามขั้นตอนเหล่านี้ คุณจะได้เรียนรู้วิธีการจัดการการนำเสนอ PowerPoint โดยใช้ Aspose.Slides สำหรับ Java ได้อย่างมีประสิทธิภาพ ความสามารถนี้ช่วยให้คุณสามารถทำงานอัตโนมัติ ปรับแต่งการนำเสนอ และปรับปรุงแอปพลิเคชัน Java ของคุณด้วยฟังก์ชันการจัดการ PowerPoint ขั้นสูง
## คำถามที่พบบ่อย
### Aspose.Slides สำหรับ Java สามารถทำงานร่วมกับ JDK เวอร์ชันเก่าได้หรือไม่
Aspose.Slides สำหรับ Java ต้องใช้ JDK 1.8 ขึ้นไปจึงจะเข้ากันได้
### ฉันจะได้รับใบอนุญาตชั่วคราวสำหรับ Aspose.Slides สำหรับ Java ได้อย่างไร
คุณสามารถขอใบอนุญาตชั่วคราวได้จาก [ที่นี่](https://purchase-aspose.com/temporary-license/).
### ฉันสามารถหาเอกสารโดยละเอียดเพิ่มเติมเกี่ยวกับ Aspose.Slides สำหรับ Java ได้ที่ไหน
สำรวจเอกสารที่ครอบคลุม [ที่นี่](https://reference-aspose.com/slides/java/).
### มีการสนับสนุนชุมชนสำหรับ Aspose.Slides สำหรับ Java หรือไม่
ใช่ คุณสามารถรับการสนับสนุนจากชุมชนได้ [ที่นี่](https://forum-aspose.com/c/slides/11).
### ฉันสามารถทดลองใช้ Aspose.Slides สำหรับ Java ได้ฟรีหรือไม่?
ใช่ ดาวน์โหลดเวอร์ชันทดลองใช้งานฟรี [ที่นี่](https://releases-aspose.com/).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}