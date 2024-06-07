---
title: แปลง Notes Slide View เป็น PDF ใน Java Slides
linktitle: แปลง Notes Slide View เป็น PDF ใน Java Slides
second_title: Aspose.Slides Java PowerPoint การประมวลผล API
description: เรียนรู้วิธีแปลงงานนำเสนอ PowerPoint พร้อมบันทึกย่อเป็น PDF โดยใช้ Aspose.Slides สำหรับ Java ปฏิบัติตามคำแนะนำทีละขั้นตอนของเราพร้อมซอร์สโค้ด
type: docs
weight: 16
url: /th/java/presentation-conversion/convert-notes-slide-view-pdf-java-slides/
---

## ข้อมูลเบื้องต้นเกี่ยวกับการแปลงมุมมองสไลด์ Notes เป็น PDF ใน Java Slides

ในบทช่วยสอนนี้ เราจะแนะนำคุณตลอดขั้นตอนการแปลงงานนำเสนอ PowerPoint ด้วยมุมมองสไลด์บันทึกย่อเป็น PDF โดยใช้ไลบรารี Aspose.Slides สำหรับ Java ไลบรารีนี้มีคุณสมบัติที่มีประสิทธิภาพสำหรับการทำงานกับงานนำเสนอ PowerPoint ใน Java

## ข้อกำหนดเบื้องต้น
1. ติดตั้ง Java Development Kit (JDK) แล้ว
2. เพิ่ม Aspose.Slides สำหรับไลบรารี Java ในโครงการของคุณ

## ขั้นตอนที่ 1: นำเข้าคลาสที่จำเป็น
ในการเริ่มต้น คุณจะต้องนำเข้าคลาสที่จำเป็นจากไลบรารี Aspose.Slides นี่คือรหัสที่ต้องทำ:

```java
import com.aspose.slides.*;
```

## ขั้นตอนที่ 2: โหลดงานนำเสนอ PowerPoint
 คุณควรเตรียมไฟล์งานนำเสนอ PowerPoint ของคุณให้พร้อม แทนที่`"Your Document Directory"` พร้อมเส้นทางไปยังไดเร็กทอรีที่มีไฟล์งานนำเสนอของคุณอยู่ นี่คือโค้ดสำหรับโหลดงานนำเสนอ:

```java
String dataDir = "Your Document Directory";
Presentation presentation = new Presentation(dataDir + "NotesFile.pptx");
```

## ขั้นตอนที่ 3: กำหนดค่าตัวเลือก PDF
ตอนนี้ มากำหนดค่าตัวเลือกการส่งออก PDF กัน โดยเฉพาะ เราจะตั้งค่าตำแหน่งบันทึกย่อเป็น "BottomFull" เพื่อรวมบันทึกย่อไว้ใต้สไลด์ใน PDF นี่คือรหัส:

```java
PdfOptions pdfOptions = new PdfOptions();
INotesCommentsLayoutingOptions options = pdfOptions.getNotesCommentsLayouting();
options.setNotesPosition(NotesPositions.BottomFull);
```

คุณสามารถปรับแต่งตัวเลือก PDF อื่นๆ ได้ตามความต้องการของคุณ

## ขั้นตอนที่ 4: บันทึกงานนำเสนอเป็น PDF พร้อมบันทึกย่อ
สุดท้ายนี้ มาบันทึกงานนำเสนอเป็นไฟล์ PDF รวมถึงบันทึกย่อด้วย คุณสามารถระบุชื่อไฟล์เอาต์พุต (เช่น`"Pdf_Notes_out.pdf"`) และเลือกรูปแบบ (`SaveFormat.Pdf`- นี่คือรหัสที่ต้องทำ:

```java
presentation.save(dataDir + "Pdf_Notes_out.pdf", SaveFormat.Pdf, pdfOptions);
```

## ขั้นตอนที่ 5: ทำความสะอาดทรัพยากร
อย่าลืมเผยแพร่แหล่งข้อมูลเมื่อคุณนำเสนอเสร็จแล้ว:

```java
if (presentation != null) presentation.dispose();
```

## กรอกซอร์สโค้ดสำหรับแปลงมุมมองสไลด์บันทึกย่อเป็น PDF ใน Java Slides

```java
// เส้นทางไปยังไดเร็กทอรีเอกสาร
String dataDir = "Your Document Directory";
// สร้างอินสแตนซ์วัตถุการนำเสนอที่แสดงถึงไฟล์การนำเสนอ
Presentation presentation = new Presentation(dataDir + "NotesFile.pptx");
try
{
	PdfOptions pdfOptions = new PdfOptions();
	INotesCommentsLayoutingOptions options = pdfOptions.getNotesCommentsLayouting();
	options.setNotesPosition(NotesPositions.BottomFull);
	// บันทึกการนำเสนอเป็นบันทึกย่อ PDF
	presentation.save(dataDir + "Pdf_Notes_out.pdf", SaveFormat.Pdf, pdfOptions);
}
finally
{
	if (presentation != null) presentation.dispose();
}
```

## บทสรุป

ในบทช่วยสอนนี้ เราได้ศึกษาวิธีการแปลงงานนำเสนอ PowerPoint ด้วยมุมมองสไลด์บันทึกย่อเป็น PDF โดยใช้ไลบรารี Aspose.Slides สำหรับ Java เราทำตามคำแนะนำทีละขั้นตอนพร้อมซอร์สโค้ดเพื่อให้ได้การแปลงนี้ ประเด็นสำคัญมีดังนี้:

## คำถามที่พบบ่อย

### ฉันจะเปลี่ยนตำแหน่งบันทึกย่อใน PDF ได้อย่างไร

 คุณสามารถเปลี่ยนตำแหน่งบันทึกย่อใน PDF ได้โดยการแก้ไข`setNotesPosition` อาร์กิวเมนต์วิธีการ ตัวอย่างเช่น คุณสามารถตั้งค่าเป็น`NotesPositions.RightFull` เพื่อวางตำแหน่งบันทึกย่อทางด้านขวาของสไลด์

```java
options.setNotesPosition(NotesPositions.RightFull);
```

### ฉันสามารถปรับแต่งการส่งออก PDF เพิ่มเติมได้หรือไม่

ใช่ คุณสามารถปรับแต่งการส่งออก PDF ได้โดยการปรับตัวเลือกต่างๆ ในไฟล์`PdfOptions` วัตถุ. ตัวอย่างเช่น คุณสามารถตั้งค่าคุณภาพ การบีบอัด และพารามิเตอร์อื่นๆ ตามความต้องการของคุณได้

### ฉันจะรับ Aspose.Slides สำหรับ Java ได้อย่างไร

 คุณสามารถดาวน์โหลด Aspose.Slides สำหรับ Java ได้จากเว็บไซต์ที่[ที่นี่](https://releases.aspose.com/slides/java/).

### มีข้อกำหนดสิทธิ์การใช้งานสำหรับการใช้ Aspose.Slides หรือไม่

ใช่ Aspose.Slides ต้องมีใบอนุญาตที่ถูกต้องสำหรับการใช้งานเชิงพาณิชย์ คุณสามารถขอรับใบอนุญาตได้จากเว็บไซต์ Aspose

### ฉันจะหาเอกสารและตัวอย่างเพิ่มเติมได้ที่ไหน

 คุณสามารถค้นหาเอกสารและตัวอย่างที่ครอบคลุมสำหรับ Aspose.Slides สำหรับ Java ได้ที่[ที่นี่](https://reference.aspose.com/slides/java/).