---
title: บันทึก PowerPoint ด้วยแบบอักษรปกติเริ่มต้นโดยใช้ Java
linktitle: บันทึก PowerPoint ด้วยแบบอักษรปกติเริ่มต้นโดยใช้ Java
second_title: Aspose.Slides Java PowerPoint การประมวลผล API
description: เรียนรู้วิธีจัดการงานนำเสนอ PowerPoint โดยทางโปรแกรมโดยใช้ Aspose.Slides สำหรับ Java การจัดการ Java PowerPoint ระดับปรมาจารย์พร้อมบทช่วยสอนแบบทีละขั้นตอน
weight: 12
url: /th/java/java-powerpoint-text-font-customization/save-powerpoint-default-regular-font-java/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# บันทึก PowerPoint ด้วยแบบอักษรปกติเริ่มต้นโดยใช้ Java

## การแนะนำ
ในขอบเขตของการพัฒนา Java การสร้างและจัดการงานนำเสนอ PowerPoint โดยทางโปรแกรมสามารถเพิ่มประสิทธิภาพการทำงานและตัวเลือกการปรับแต่งได้อย่างมาก Aspose.Slides สำหรับ Java เป็นไลบรารีที่มีประสิทธิภาพซึ่งช่วยให้นักพัฒนาสามารถจัดการไฟล์ PowerPoint ได้อย่างมีประสิทธิภาพ โดยนำเสนอชุดคุณสมบัติที่ครอบคลุมตั้งแต่การแก้ไขอย่างง่ายไปจนถึงการนำเสนอที่ซับซ้อน
## ข้อกำหนดเบื้องต้น
ก่อนที่จะเริ่มใช้ Aspose.Slides สำหรับ Java ตรวจสอบให้แน่ใจว่าคุณได้ตั้งค่าข้อกำหนดเบื้องต้นต่อไปนี้:
1. Java Development Kit (JDK): Aspose.Slides สำหรับ Java ต้องใช้ JDK 1.8 ขึ้นไปเพื่อให้ทำงานได้อย่างถูกต้อง
2. Aspose.Slides สำหรับ Java JAR: ดาวน์โหลด Aspose.Slides สำหรับ Java เวอร์ชันล่าสุดจาก[ที่นี่](https://releases.aspose.com/slides/java/).
3. สภาพแวดล้อมการพัฒนาแบบรวม (IDE): ใช้ IntelliJ IDEA, Eclipse หรือ Java IDE อื่นที่คุณเลือก
4. ความเข้าใจพื้นฐานของ Java: ความคุ้นเคยกับพื้นฐานภาษาการเขียนโปรแกรม Java เป็นสิ่งจำเป็น

## แพ็คเกจนำเข้า
หากต้องการเริ่มใช้ Aspose.Slides สำหรับ Java ให้นำเข้าแพ็คเกจที่จำเป็น:
```java
import com.aspose.slides.HtmlOptions;
import com.aspose.slides.PdfOptions;
import com.aspose.slides.Presentation;
import com.aspose.slides.SaveFormat;
```
สิ่งนี้ทำให้แน่ใจได้ว่าคุณจะสามารถเข้าถึงคลาสและวิธีการทั้งหมดที่มีให้โดย Aspose.Slides สำหรับ Java
## ขั้นตอนที่ 1: ตั้งค่าโครงการของคุณ
ขั้นแรก สร้างโปรเจ็กต์ Java ใหม่ใน IDE ของคุณและรวมไฟล์ Aspose.Slides สำหรับ Java JAR ไว้ในพาธการ build ของโปรเจ็กต์ของคุณ
## ขั้นตอนที่ 2: เริ่มต้นวัตถุการนำเสนอ
 ยกตัวอย่าง`Presentation` วัตถุโดยการโหลดไฟล์ PowerPoint ที่มีอยู่ (.pptx) จากไดเร็กทอรีในเครื่องของคุณ
```java
String dataDir = "Your Document Directory";
String outPath = "Your Output Directory";
// โหลดการนำเสนอ
Presentation pres = new Presentation(dataDir + "DefaultFonts.pptx");
```
 แทนที่`"Your Document Directory"` และ`"Your Output Directory"` ด้วยเส้นทางไฟล์จริงของคุณ
## ขั้นตอนที่ 3: บันทึกงานนำเสนอด้วยแบบอักษรปกติเริ่มต้น
 ระบุแบบอักษรปกติเริ่มต้นสำหรับรูปแบบเอาต์พุต (HTML และ PDF) โดยใช้`HtmlOptions` และ`PdfOptions` ตามลำดับ
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
 ให้แน่ใจว่าจะเปลี่ยน`"Arial Black"` และ`"Lucida Console"` ด้วยแบบอักษรปกติเริ่มต้นที่คุณต้องการ

## บทสรุป
เมื่อทำตามขั้นตอนเหล่านี้ คุณได้เรียนรู้วิธีจัดการงานนำเสนอ PowerPoint โดยใช้ Aspose.Slides สำหรับ Java อย่างมีประสิทธิภาพ ความสามารถนี้ช่วยให้คุณทำงานอัตโนมัติ ปรับแต่งการนำเสนอ และปรับปรุงแอปพลิเคชัน Java ของคุณด้วยฟังก์ชันการจัดการ PowerPoint ขั้นสูง
## คำถามที่พบบ่อย
### Aspose.Slides สำหรับ Java สามารถทำงานร่วมกับ JDK เวอร์ชันเก่าได้หรือไม่
Aspose.Slides สำหรับ Java ต้องใช้ JDK 1.8 ขึ้นไปเพื่อความเข้ากันได้
### ฉันจะรับสิทธิ์ใช้งานชั่วคราวสำหรับ Aspose.Slides สำหรับ Java ได้อย่างไร
 คุณสามารถขอรับใบอนุญาตชั่วคราวได้จาก[ที่นี่](https://purchase.aspose.com/temporary-license/).
### ฉันจะหาเอกสารรายละเอียดเพิ่มเติมเกี่ยวกับ Aspose.Slides สำหรับ Java ได้ที่ไหน
 สำรวจเอกสารที่ครอบคลุม[ที่นี่](https://reference.aspose.com/slides/java/).
### มีการสนับสนุนจากชุมชนสำหรับ Aspose.Slides สำหรับ Java หรือไม่
 ใช่ คุณสามารถรับการสนับสนุนจากชุมชนได้[ที่นี่](https://forum.aspose.com/c/slides/11).
### ฉันสามารถลองใช้ Aspose.Slides สำหรับ Java ได้ฟรีหรือไม่
 ใช่ ดาวน์โหลดเวอร์ชันทดลองใช้ฟรี[ที่นี่](https://releases.aspose.com/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
