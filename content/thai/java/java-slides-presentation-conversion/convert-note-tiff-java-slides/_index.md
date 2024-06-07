---
title: แปลงด้วย Note เป็น TIFF ใน Java Slides
linktitle: แปลงด้วย Note เป็น TIFF ใน Java Slides
second_title: Aspose.Slides Java PowerPoint การประมวลผล API
description: แปลงงานนำเสนอ PowerPoint พร้อมบันทึกของผู้บรรยายเป็นรูปแบบ TIFF ใน Java ได้อย่างง่ายดายโดยใช้ Aspose.Slides ปฏิบัติตามคำแนะนำทีละขั้นตอนพร้อมซอร์สโค้ดเพื่อการแปลงเอกสารที่ราบรื่น
type: docs
weight: 32
url: /th/java/presentation-conversion/convert-note-tiff-java-slides/
---

## ข้อมูลเบื้องต้นเกี่ยวกับการแปลงด้วย Note เป็น TIFF ใน Java Slides

ในบทช่วยสอนนี้ เราจะสาธิตวิธีการแปลงงานนำเสนอ PowerPoint ด้วยบันทึกของผู้บรรยายเป็นรูปแบบ TIFF โดยใช้ Aspose.Slides สำหรับ Java ไลบรารีนี้มีคุณสมบัติที่มีประสิทธิภาพสำหรับการทำงานกับไฟล์ PowerPoint โดยทางโปรแกรม

## ข้อกำหนดเบื้องต้น

ก่อนที่คุณจะเริ่มต้น ตรวจสอบให้แน่ใจว่าคุณมีข้อกำหนดเบื้องต้นต่อไปนี้:

1.  Aspose.Slides สำหรับไลบรารี Java: คุณควรติดตั้งไลบรารี Aspose.Slides สำหรับ Java คุณสามารถดาวน์โหลดได้จากเว็บไซต์[ที่นี่](https://downloads.aspose.com/slides/java).

2. สภาพแวดล้อมการพัฒนา Java: ตรวจสอบให้แน่ใจว่าคุณได้ตั้งค่าสภาพแวดล้อมการพัฒนา Java บนระบบของคุณ

3. การนำเสนอ PowerPoint: เตรียมการนำเสนอ PowerPoint (`ConvertWithNoteToTiff.pptx`) ที่มีบันทึกของผู้บรรยาย

## ขั้นตอนที่ 1: นำเข้าไลบรารี Aspose.Slides

นำเข้าคลาสที่จำเป็นจากไลบรารี Aspose.Slides ที่จุดเริ่มต้นของโค้ด Java ของคุณ

```java
import com.aspose.slides.INotesCommentsLayoutingOptions;
import com.aspose.slides.NotesPositions;
import com.aspose.slides.Presentation;
import com.aspose.slides.SaveFormat;
import com.aspose.slides.TiffOptions;
```

## ขั้นตอนที่ 2: ตั้งค่าตัวเลือกการนำเสนอและ TIFF

กำหนดเส้นทางไปยังไฟล์การนำเสนอของคุณ (`ConvertWithNoteToTiff.pptx` ) และสร้าง`Presentation` วัตถุ. จากนั้นให้กำหนดค่า`TiffOptions` สำหรับการแปลง

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "ConvertWithNoteToTiff.pptx");

try {
    TiffOptions opts = new TiffOptions();
    INotesCommentsLayoutingOptions notesOptions = opts.getNotesCommentsLayouting();
    notesOptions.setNotesPosition(NotesPositions.BottomFull);
    // คุณสามารถตั้งค่าตัวเลือก TIFF เพิ่มเติมได้ที่นี่ หากจำเป็น

    // ขั้นตอนที่ 3: บันทึกงานนำเสนอพร้อมบันทึกของผู้บรรยายลงใน TIFF
    pres.save(dataDir + "TestNotes_out.tiff", SaveFormat.Tiff, opts);
} finally {
    if (pres != null) pres.dispose();
}
```

## ขั้นตอนที่ 3: บันทึกงานนำเสนอพร้อมบันทึกของผู้บรรยายลงใน TIFF

 ข้างใน`try` บล็อกให้ใช้`pres.save` วิธีบันทึกงานนำเสนอพร้อมบันทึกของผู้บรรยายเป็นไฟล์ TIFF ที่`SaveFormat.Tiff` พารามิเตอร์ระบุรูปแบบผลลัพธ์

## ขั้นตอนที่ 4: ทำความสะอาดทรัพยากร

 ใน`finally` บล็อก ตรวจสอบให้แน่ใจว่าคุณได้กำจัดทิ้ง`Presentation` คัดค้านการปล่อยทรัพยากรที่ได้รับการจัดสรร

แค่นั้นแหละ! คุณได้แปลงงานนำเสนอ PowerPoint ด้วยบันทึกของผู้บรรยายเป็นรูปแบบ TIFF ได้สำเร็จโดยใช้ Aspose.Slides สำหรับ Java

## กรอกซอร์สโค้ดสำหรับการแปลงด้วยหมายเหตุเป็น TIFF ใน Java Slides

```java
// เส้นทางไปยังไดเร็กทอรีเอกสาร
String dataDir = "Your Document Directory";
// สร้างอินสแตนซ์วัตถุการนำเสนอที่แสดงถึงไฟล์การนำเสนอ
Presentation pres = new Presentation(dataDir + "ConvertWithNoteToTiff.pptx");
try
{
	TiffOptions opts = new TiffOptions();
	INotesCommentsLayoutingOptions notesOptions = opts.getNotesCommentsLayouting();
	notesOptions.setNotesPosition(NotesPositions.BottomFull);
	// การบันทึกงานนำเสนอลงในบันทึกย่อ TIFF
	pres.save(dataDir + "TestNotes_out.tiff", SaveFormat.Tiff, opts);
}
finally
{
	if (pres != null) pres.dispose();
}
```

## บทสรุป

ในบทช่วยสอนนี้ เราได้เรียนรู้วิธีแปลงงานนำเสนอ PowerPoint ด้วยบันทึกย่อเป็น TIFF ใน Java โดยใช้ไลบรารี Aspose.Slides สำหรับ Java นี่อาจเป็นเครื่องมืออันมีค่าสำหรับนักพัฒนาที่ต้องการแปลงเอกสารอัตโนมัติและรักษาบันทึกย่อที่สำคัญในการนำเสนอ

## คำถามที่พบบ่อย

### ฉันจะติดตั้ง Aspose.Slides สำหรับ Java ได้อย่างไร

 คุณสามารถดาวน์โหลด Aspose.Slides สำหรับ Java ได้จาก[ที่นี่](https://releases.aspose.com/slides/java/) และปฏิบัติตามคำแนะนำในการติดตั้งที่ให้ไว้ในเอกสารประกอบ

### ฉันสามารถแปลงงานนำเสนอ PowerPoint เป็นรูปแบบอื่นได้หรือไม่

ใช่ Aspose.Slides สำหรับ Java รองรับรูปแบบเอาต์พุตที่หลากหลาย รวมถึง PDF, HTML และรูปแบบรูปภาพ เช่น TIFF และ PNG

### จะเกิดอะไรขึ้นถ้างานนำเสนอ PowerPoint ของฉันไม่มีบันทึกย่อ

หากงานนำเสนอของคุณไม่มีบันทึก ขั้นตอนการแปลงจะยังคงใช้งานได้ และคุณจะได้ภาพ TIFF ของสไลด์ที่ไม่มีบันทึกย่อ

### Aspose.Slides สำหรับ Java เหมาะสำหรับโครงการเชิงพาณิชย์หรือไม่

ใช่ Aspose.Slides สำหรับ Java เป็นไลบรารีที่มีประสิทธิภาพและเชื่อถือได้ซึ่งธุรกิจจำนวนมากใช้สำหรับการประมวลผลและจัดการเอกสารในแอปพลิเคชัน Java ของตน

### มีข้อควรพิจารณาในการอนุญาตให้ใช้สิทธิ์สำหรับการใช้ Aspose.Slides สำหรับ Java ในโปรเจ็กต์ของฉันหรือไม่

ใช่ Aspose.Slides สำหรับ Java ต้องมีใบอนุญาตที่ถูกต้องสำหรับการใช้งานเชิงพาณิชย์ คุณสามารถค้นหารายละเอียดใบอนุญาตได้จากเว็บไซต์ Aspose