---
"description": "เรียนรู้วิธีแยกข้อมูลไฟล์ที่ฝังไว้จากงานนำเสนอ PowerPoint โดยใช้ Aspose.Slides สำหรับ Java ซึ่งจะช่วยเสริมความสามารถในการจัดการเอกสาร"
"linktitle": "แยกข้อมูลไฟล์ที่ฝังไว้จากวัตถุ OLE ใน PowerPoint"
"second_title": "API การประมวลผล Java PowerPoint ของ Aspose.Slides"
"title": "แยกข้อมูลไฟล์ที่ฝังไว้จากวัตถุ OLE ใน PowerPoint"
"url": "/th/java/java-powerpoint-animation-shape-manipulation/extract-embedded-file-data-ole-object-powerpoint/"
"weight": 22
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# แยกข้อมูลไฟล์ที่ฝังไว้จากวัตถุ OLE ใน PowerPoint


## การแนะนำ
ในแวดวงการเขียนโปรแกรม Java การดึงข้อมูลไฟล์ที่ฝังไว้จากอ็อบเจ็กต์ OLE (Object Linking and Embedding) ภายในงานนำเสนอ PowerPoint เป็นงานที่มักเกิดขึ้น โดยเฉพาะในแอปพลิเคชันการจัดการเอกสารหรือการแยกข้อมูล Aspose.Slides สำหรับ Java นำเสนอโซลูชันที่มีประสิทธิภาพสำหรับการจัดการงานนำเสนอ PowerPoint ด้วยโปรแกรม ในบทช่วยสอนนี้ เราจะสำรวจวิธีการดึงข้อมูลไฟล์ที่ฝังไว้จากอ็อบเจ็กต์ OLE โดยใช้ Aspose.Slides สำหรับ Java
## ข้อกำหนดเบื้องต้น
ก่อนที่จะเจาะลึกเข้าไปในบทช่วยสอน ให้แน่ใจว่าคุณมีข้อกำหนดเบื้องต้นดังต่อไปนี้:
- ความรู้พื้นฐานเกี่ยวกับการเขียนโปรแกรมภาษา Java
- JDK (Java Development Kit) ติดตั้งอยู่บนระบบของคุณ
- Aspose.Slides สำหรับไลบรารี Java ดาวน์โหลดและอ้างอิงในโปรเจ็กต์ของคุณ

## แพ็คเกจนำเข้า
ประการแรก ให้แน่ใจว่าคุณนำเข้าแพ็กเกจที่จำเป็นเข้าสู่โปรเจ็กต์ Java ของคุณ เพื่อใช้ฟังก์ชันที่ Aspose.Slides สำหรับ Java จัดทำไว้
```java
import com.aspose.slides.IShape;
import com.aspose.slides.ISlide;
import com.aspose.slides.OleObjectFrame;
import com.aspose.slides.Presentation;

import java.io.FileOutputStream;
import java.io.IOException;
```

ตอนนี้เรามาแบ่งกระบวนการออกเป็นหลายขั้นตอน:
## ขั้นตอนที่ 1: ระบุเส้นทางไดเรกทอรีเอกสาร
```java
String dataDir = "Your Document Directory";
```
แทนที่ `"Your Document Directory"` พร้อมเส้นทางไปยังไดเร็กทอรีที่เก็บงานนำเสนอ PowerPoint ของคุณ
## ขั้นตอนที่ 2: ระบุชื่อไฟล์ PowerPoint
```java
String pptxFileName = dataDir + "TestOlePresentation.pptx";
```
ให้แน่ใจว่าจะเปลี่ยน `"TestOlePresentation.pptx"` ด้วยชื่อไฟล์งานนำเสนอ PowerPoint ของคุณ
## ขั้นตอนที่ 3: โหลดงานนำเสนอ
```java
Presentation pres = new Presentation(pptxFileName);
```
บรรทัดนี้จะเริ่มต้นอินสแตนซ์ใหม่ของ `Presentation` คลาสที่กำลังโหลดไฟล์นำเสนอ PowerPoint ที่ระบุ
## ขั้นตอนที่ 4: ทำซ้ำผ่านสไลด์และรูปร่าง
```java
for (ISlide sld : pres.getSlides()) {
    for (IShape shape : sld.getShapes()) {
```
ที่นี่ เราจะทำซ้ำผ่านแต่ละสไลด์และรูปร่างภายในงานนำเสนอ
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
หากรูปร่างเป็นวัตถุ OLE เราจะแยกข้อมูลไฟล์ที่ฝังไว้ออกมา
## ขั้นตอนที่ 7: กำหนดนามสกุลไฟล์
```java
String fileExtention = oleFrame.getEmbeddedData().getEmbeddedFileExtension();
```
บรรทัดนี้จะดึงนามสกุลไฟล์ของไฟล์ฝังตัวที่แยกออกมา
## ขั้นตอนที่ 8: บันทึกไฟล์ที่แยกออกมา
```java
String extractedPath = dataDir + "ExtractedObject_out" + objectnum + fileExtention;
FileOutputStream fs = new FileOutputStream(extractedPath);
fs.write(data, 0, data.length);
```
สุดท้ายเราบันทึกข้อมูลไฟล์ที่แยกออกมาไปยังไดเร็กทอรีที่ระบุ

## บทสรุป
ในบทช่วยสอนนี้ เราได้เรียนรู้วิธีใช้ Aspose.Slides สำหรับ Java เพื่อแยกข้อมูลไฟล์ที่ฝังไว้จากวัตถุ OLE ในงานนำเสนอ PowerPoint เมื่อทำตามขั้นตอนที่ให้ไว้ คุณจะสามารถผสานฟังก์ชันนี้เข้ากับแอปพลิเคชัน Java ได้อย่างราบรื่น ช่วยเพิ่มความสามารถในการจัดการเอกสาร
## คำถามที่พบบ่อย
### Aspose.Slides สามารถดึงข้อมูลจากวัตถุฝังตัวทุกประเภทได้หรือไม่
Aspose.Slides ให้การสนับสนุนอย่างครอบคลุมสำหรับการดึงข้อมูลจากวัตถุฝังตัวต่างๆ รวมถึงวัตถุ OLE แผนภูมิและอื่นๆ อีกมากมาย
### Aspose.Slides เข้ากันได้กับ PowerPoint เวอร์ชันต่างๆ ได้หรือไม่
ใช่ Aspose.Slides รับประกันความเข้ากันได้กับการนำเสนอ PowerPoint ในเวอร์ชันต่างๆ ช่วยให้แยกข้อมูลที่ฝังไว้ได้อย่างราบรื่น
### Aspose.Slides ต้องมีใบอนุญาตสำหรับการใช้งานเชิงพาณิชย์หรือไม่
ใช่ ต้องมีใบอนุญาตที่ถูกต้องสำหรับการใช้ Aspose.Slides ในเชิงพาณิชย์ คุณสามารถขอรับใบอนุญาตได้จาก Aspose [เว็บไซต์](https://purchase-aspose.com/temporary-license/).
### ฉันสามารถใช้ Aspose.Slides เพื่อดำเนินการแยกข้อมูลแบบอัตโนมัติได้หรือไม่
แน่นอน Aspose.Slides มอบ API ที่ครอบคลุมสำหรับงานอัตโนมัติ เช่น การแยกข้อมูลไฟล์ที่ฝังไว้ ช่วยให้ประมวลผลเอกสารได้อย่างมีประสิทธิภาพและราบรื่น
### ฉันสามารถค้นหาความช่วยเหลือหรือการสนับสนุนเพิ่มเติมสำหรับ Aspose.Slides ได้จากที่ใด
สำหรับคำถาม ความช่วยเหลือด้านเทคนิค หรือการสนับสนุนจากชุมชน คุณสามารถเยี่ยมชมฟอรัม Aspose.Slides หรือดูเอกสารประกอบ [แอสโพส สไลด์](https://reference-aspose.com/slides/java/).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}