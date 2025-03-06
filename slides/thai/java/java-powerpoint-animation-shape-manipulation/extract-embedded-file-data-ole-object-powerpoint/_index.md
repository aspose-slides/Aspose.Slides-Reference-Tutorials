---
title: แยกข้อมูลไฟล์ที่ฝังตัวจากวัตถุ OLE ใน PowerPoint
linktitle: แยกข้อมูลไฟล์ที่ฝังตัวจากวัตถุ OLE ใน PowerPoint
second_title: Aspose.Slides Java PowerPoint การประมวลผล API
description: เรียนรู้วิธีแยกข้อมูลไฟล์ที่ฝังตัวออกจากงานนำเสนอ PowerPoint โดยใช้ Aspose.Slides สำหรับ Java ซึ่งช่วยเพิ่มความสามารถในการจัดการเอกสาร
weight: 22
url: /th/java/java-powerpoint-animation-shape-manipulation/extract-embedded-file-data-ole-object-powerpoint/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# แยกข้อมูลไฟล์ที่ฝังตัวจากวัตถุ OLE ใน PowerPoint


## การแนะนำ
ในขอบเขตของการเขียนโปรแกรม Java การแตกข้อมูลไฟล์ที่ฝังตัวออกจากออบเจ็กต์ OLE (Object Linking and Embedding) ภายในงานนำเสนอ PowerPoint เป็นงานที่มักเกิดขึ้น โดยเฉพาะอย่างยิ่งในการจัดการเอกสารหรือแอปพลิเคชันการแยกข้อมูล Aspose.Slides สำหรับ Java นำเสนอโซลูชันที่มีประสิทธิภาพสำหรับการจัดการงานนำเสนอ PowerPoint โดยทางโปรแกรม ในบทช่วยสอนนี้ เราจะสำรวจวิธีแยกข้อมูลไฟล์ที่ฝังจากออบเจ็กต์ OLE โดยใช้ Aspose.Slides สำหรับ Java
## ข้อกำหนดเบื้องต้น
ก่อนที่เราจะเจาะลึกบทช่วยสอน ตรวจสอบให้แน่ใจว่าคุณมีข้อกำหนดเบื้องต้นต่อไปนี้:
- ความรู้พื้นฐานเกี่ยวกับการเขียนโปรแกรม Java
- ติดตั้ง JDK (Java Development Kit) บนระบบของคุณ
- Aspose.Slides สำหรับไลบรารี Java ที่ดาวน์โหลดและอ้างอิงในโครงการของคุณ

## แพ็คเกจนำเข้า
ประการแรก ตรวจสอบให้แน่ใจว่าคุณนำเข้าแพ็คเกจที่จำเป็นในโปรเจ็กต์ Java ของคุณเพื่อใช้ฟังก์ชันการทำงานที่ Aspose.Slides สำหรับ Java มอบให้
```java
import com.aspose.slides.IShape;
import com.aspose.slides.ISlide;
import com.aspose.slides.OleObjectFrame;
import com.aspose.slides.Presentation;

import java.io.FileOutputStream;
import java.io.IOException;
```

ตอนนี้ เรามาแบ่งกระบวนการออกเป็นหลายขั้นตอน:
## ขั้นตอนที่ 1: ระบุเส้นทางไดเรกทอรีเอกสาร
```java
String dataDir = "Your Document Directory";
```
 แทนที่`"Your Document Directory"` พร้อมเส้นทางไปยังไดเร็กทอรีที่มีงานนำเสนอ PowerPoint ของคุณ
## ขั้นตอนที่ 2: ระบุชื่อไฟล์ PowerPoint
```java
String pptxFileName = dataDir + "TestOlePresentation.pptx";
```
 ให้แน่ใจว่าจะเปลี่ยน`"TestOlePresentation.pptx"` ด้วยชื่อไฟล์งานนำเสนอ PowerPoint ของคุณ
## ขั้นตอนที่ 3: โหลดการนำเสนอ
```java
Presentation pres = new Presentation(pptxFileName);
```
 บรรทัดนี้เริ่มต้นอินสแตนซ์ใหม่ของ`Presentation` คลาสกำลังโหลดไฟล์งานนำเสนอ PowerPoint ที่ระบุ
## ขั้นตอนที่ 4: วนซ้ำผ่านสไลด์และรูปร่าง
```java
for (ISlide sld : pres.getSlides()) {
    for (IShape shape : sld.getShapes()) {
```
ที่นี่ เราจะวนซ้ำแต่ละสไลด์และรูปร่างภายในงานนำเสนอ
## ขั้นตอนที่ 5: ตรวจสอบวัตถุ OLE
```java
if (shape instanceof OleObjectFrame) {
```
เงื่อนไขนี้จะตรวจสอบว่ารูปร่างเป็นวัตถุ OLE หรือไม่
## ขั้นตอนที่ 6: แยกข้อมูลไฟล์ที่ฝังไว้
```java
OleObjectFrame oleFrame = (OleObjectFrame) shape;
byte[] data = oleFrame.getEmbeddedData().getEmbeddedFileData();
```
หากรูปร่างเป็นวัตถุ OLE เราจะแยกข้อมูลไฟล์ที่ฝังไว้
## ขั้นตอนที่ 7: กำหนดนามสกุลไฟล์
```java
String fileExtention = oleFrame.getEmbeddedData().getEmbeddedFileExtension();
```
บรรทัดนี้จะดึงนามสกุลไฟล์ของไฟล์ฝังตัวที่แตกออกมา
## ขั้นตอนที่ 8: บันทึกไฟล์ที่แยกแล้ว
```java
String extractedPath = dataDir + "ExtractedObject_out" + objectnum + fileExtention;
FileOutputStream fs = new FileOutputStream(extractedPath);
fs.write(data, 0, data.length);
```
สุดท้าย เราจะบันทึกข้อมูลไฟล์ที่แยกออกมาไปยังไดเร็กทอรีที่ระบุ

## บทสรุป
ในบทช่วยสอนนี้ เราได้เรียนรู้วิธีใช้ Aspose.Slides สำหรับ Java เพื่อแยกข้อมูลไฟล์ที่ฝังจากออบเจ็กต์ OLE ภายในงานนำเสนอ PowerPoint ด้วยการทำตามขั้นตอนที่ให้ไว้ คุณสามารถรวมฟังก์ชันการทำงานนี้เข้ากับแอปพลิเคชัน Java ของคุณได้อย่างราบรื่น ช่วยเพิ่มความสามารถในการจัดการเอกสาร
## คำถามที่พบบ่อย
### Aspose.Slides สามารถดึงข้อมูลจากวัตถุฝังตัวทุกประเภทได้หรือไม่
Aspose.Slides ให้การสนับสนุนอย่างกว้างขวางในการแยกข้อมูลจากออบเจ็กต์ที่ฝังไว้ต่างๆ รวมถึงออบเจ็กต์ OLE แผนภูมิ และอื่นๆ
### Aspose.Slides เข้ากันได้กับ PowerPoint เวอร์ชันต่างๆ หรือไม่
ใช่ Aspose.Slides รับประกันความเข้ากันได้กับงานนำเสนอ PowerPoint ในเวอร์ชันต่างๆ ทำให้มั่นใจได้ว่าการแยกข้อมูลที่ฝังไว้จะราบรื่น
### Aspose.Slides จำเป็นต้องมีใบอนุญาตสำหรับการใช้งานเชิงพาณิชย์หรือไม่
 ใช่ จำเป็นต้องมีใบอนุญาตที่ถูกต้องสำหรับการใช้งาน Aspose.Slides ในเชิงพาณิชย์ คุณสามารถขอรับใบอนุญาตจาก Aspose[เว็บไซต์](https://purchase.aspose.com/temporary-license/).
### ฉันสามารถทำให้กระบวนการแยกข้อมูลโดยอัตโนมัติโดยใช้ Aspose.Slides ได้หรือไม่
แน่นอนว่า Aspose.Slides มี API ที่ครอบคลุมสำหรับงานอัตโนมัติ เช่น การแยกข้อมูลไฟล์ที่ฝังไว้ ช่วยให้การประมวลผลเอกสารมีประสิทธิภาพและคล่องตัว
### ฉันจะขอความช่วยเหลือหรือการสนับสนุนเพิ่มเติมสำหรับ Aspose.Slides ได้ที่ไหน
 หากมีข้อสงสัย ความช่วยเหลือทางเทคนิค หรือการสนับสนุนชุมชน คุณสามารถไปที่ฟอรัม Aspose.Slides หรือดูเอกสารประกอบ[Aspose.Slides](https://reference.aspose.com/slides/java/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
