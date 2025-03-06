---
title: แปลงด้วยขนาดที่กำหนดเองใน Java Slides
linktitle: แปลงด้วยขนาดที่กำหนดเองใน Java Slides
second_title: Aspose.Slides Java PowerPoint การประมวลผล API
description: เรียนรู้วิธีแปลงงานนำเสนอ PowerPoint เป็นภาพ TIFF ด้วยขนาดที่กำหนดเองโดยใช้ Aspose.Slides สำหรับ Java คำแนะนำทีละขั้นตอนพร้อมตัวอย่างโค้ดสำหรับนักพัฒนา
weight: 31
url: /th/java/presentation-conversion/convert-custom-size-java-slides/
---

{< blocks/products/pf/main-wrap-class >}
{< blocks/products/pf/main-container >}
{< blocks/products/pf/tutorial-page-section >}


## ข้อมูลเบื้องต้นเกี่ยวกับการแปลงด้วยขนาดที่กำหนดเองใน Java Slides

ในบทความนี้ เราจะสำรวจวิธีการแปลงงานนำเสนอ PowerPoint เป็นรูปภาพ TIFF ด้วยขนาดที่กำหนดเองโดยใช้ Aspose.Slides สำหรับ Java API Aspose.Slides for Java เป็นไลบรารีอันทรงพลังที่ช่วยให้นักพัฒนาสามารถทำงานกับไฟล์ PowerPoint โดยทางโปรแกรม เราจะดำเนินการทีละขั้นตอนและมอบโค้ด Java ที่จำเป็นให้กับคุณเพื่อให้งานนี้สำเร็จ

## ข้อกำหนดเบื้องต้น

ก่อนที่เราจะเริ่มต้น ตรวจสอบให้แน่ใจว่าคุณมีข้อกำหนดเบื้องต้นต่อไปนี้:

- ติดตั้ง Java Development Kit (JDK) แล้ว
- Aspose.Slides สำหรับไลบรารี Java

 คุณสามารถดาวน์โหลดไลบรารี Aspose.Slides สำหรับ Java ได้จากเว็บไซต์:[ดาวน์โหลด Aspose.Slides สำหรับ Java](https://releases.aspose.com/slides/java/)

## ขั้นตอนที่ 1: นำเข้าไลบรารี Aspose.Slides

ในการเริ่มต้น คุณต้องนำเข้าไลบรารี Aspose.Slides ไปยังโปรเจ็กต์ Java ของคุณ ต่อไปนี้คือวิธีที่คุณสามารถทำได้:

```java
// เพิ่มคำสั่งการนำเข้าที่จำเป็น
import com.aspose.slides.*;
```

## ขั้นตอนที่ 2: โหลดงานนำเสนอ PowerPoint

 ถัดไป คุณจะต้องโหลดงานนำเสนอ PowerPoint ที่คุณต้องการแปลงเป็นรูปภาพ TIFF แทนที่`"Your Document Directory"` พร้อมเส้นทางจริงไปยังไฟล์การนำเสนอของคุณ

```java
// เส้นทางไปยังไดเร็กทอรีเอกสาร
String dataDir = "Your Document Directory";

// สร้างอินสแตนซ์วัตถุการนำเสนอที่แสดงถึงไฟล์การนำเสนอ
Presentation pres = new Presentation(dataDir + "Convert_Tiff_Custom.pptx");
```

## ขั้นตอนที่ 3: ตั้งค่าตัวเลือกการแปลง TIFF

ตอนนี้ มาตั้งค่าตัวเลือกสำหรับการแปลง TIFF กัน เราจะระบุประเภทการบีบอัด DPI (จุดต่อนิ้ว) ขนาดภาพ และตำแหน่งบันทึก คุณสามารถปรับแต่งตัวเลือกเหล่านี้ได้ตามความต้องการของคุณ

```java
// สร้างอินสแตนซ์คลาส TiffOptions
TiffOptions opts = new TiffOptions();

// การตั้งค่าประเภทการบีบอัด
opts.setCompressionType(TiffCompressionTypes.Default);

// การตั้งค่า DPI ของภาพ
opts.setDpiX(200);
opts.setDpiY(100);

// ตั้งค่าขนาดภาพ
opts.setImageSize(new Dimension(1728, 1078));

// กำหนดตำแหน่งบันทึกย่อ
INotesCommentsLayoutingOptions notesOptions = opts.getNotesCommentsLayouting();
notesOptions.setNotesPosition(NotesPositions.BottomFull);
```

## ขั้นตอนที่ 4: บันทึกเป็น TIFF

เมื่อกำหนดค่าตัวเลือกทั้งหมดแล้ว ตอนนี้คุณสามารถบันทึกงานนำเสนอเป็นภาพ TIFF ด้วยการตั้งค่าที่ระบุได้แล้ว

```java
// บันทึกงานนำเสนอเป็น TIFF ด้วยขนาดภาพที่ระบุ
pres.save(dataDir + "TiffWithCustomSize_out.tiff", SaveFormat.Tiff, opts);
```

## กรอกซอร์สโค้ดให้สมบูรณ์สำหรับการแปลงด้วยขนาดที่กำหนดเองใน Java Slides

```java
// เส้นทางไปยังไดเร็กทอรีเอกสาร
String dataDir = "Your Document Directory";
// สร้างอินสแตนซ์วัตถุการนำเสนอที่แสดงถึงไฟล์การนำเสนอ
Presentation pres = new Presentation(dataDir + "Convert_Tiff_Custom.pptx");
try
{
	// สร้างอินสแตนซ์คลาส TiffOptions
	TiffOptions opts = new TiffOptions();
	// การตั้งค่าประเภทการบีบอัด
	opts.setCompressionType(TiffCompressionTypes.Default);
	INotesCommentsLayoutingOptions notesOptions = opts.getNotesCommentsLayouting();
	notesOptions.setNotesPosition(NotesPositions.BottomFull);
	// ประเภทการบีบอัด
	// ค่าเริ่มต้น - ระบุรูปแบบการบีบอัดเริ่มต้น (LZW)
	// ไม่มี - ระบุว่าไม่มีการบีบอัด
	// CCITT3
	// CCITT4
	// LZW
	// อาร์แอลอี
	// ความลึกขึ้นอยู่กับประเภทการบีบอัด และไม่สามารถตั้งค่าด้วยตนเองได้
	// หน่วยความละเอียดจะเท่ากับ “2” เสมอ (จุดต่อนิ้ว)
	// การตั้งค่า DPI ของภาพ
	opts.setDpiX(200);
	opts.setDpiY(100);
	// ตั้งค่าขนาดภาพ
	opts.setImageSize(new Dimension(1728, 1078));
	// บันทึกงานนำเสนอเป็น TIFF ด้วยขนาดภาพที่ระบุ
	pres.save(dataDir + "TiffWithCustomSize_out.tiff", SaveFormat.Tiff, opts);
}
finally
{
	if (pres != null) pres.dispose();
}
```

## บทสรุป

ยินดีด้วย! คุณได้แปลงงานนำเสนอ PowerPoint เป็นรูปภาพ TIFF ด้วยขนาดที่กำหนดเองได้สำเร็จโดยใช้ Aspose.Slides สำหรับ Java นี่อาจเป็นคุณสมบัติที่มีคุณค่าเมื่อคุณต้องการสร้างภาพคุณภาพสูงจากการนำเสนอของคุณเพื่อวัตถุประสงค์ต่างๆ

## คำถามที่พบบ่อย

### ฉันจะเปลี่ยนประเภทการบีบอัดสำหรับอิมเมจ TIFF ได้อย่างไร

 คุณสามารถเปลี่ยนประเภทการบีบอัดได้โดยการแก้ไข`setCompressionType` วิธีการใน`TiffOptions` ระดับ. มีประเภทการบีบอัดที่แตกต่างกัน เช่น Default, None, CCITT3, CCITT4, LZW และ RLE

### ฉันสามารถปรับ DPI (จุดต่อนิ้ว) ของภาพ TIFF ได้หรือไม่

ใช่ คุณสามารถปรับ DPI ได้โดยใช้`setDpiX` และ`setDpiY` วิธีการใน`TiffOptions` ระดับ. เพียงตั้งค่าที่ต้องการเพื่อควบคุมความละเอียดของภาพ

### ตัวเลือกที่ใช้ได้สำหรับตำแหน่งบันทึกย่อในภาพ TIFF มีอะไรบ้าง

 ตำแหน่งบันทึกย่อในภาพ TIFF สามารถกำหนดค่าได้โดยใช้`setNotesPosition` วิธีการพร้อมตัวเลือกเช่น BottomFull, BottomTruncated และ SlideOnly เลือกอันที่เหมาะกับความต้องการของคุณมากที่สุด

### เป็นไปได้หรือไม่ที่จะระบุขนาดภาพที่กำหนดเองสำหรับการแปลง TIFF

 อย่างแน่นอน! คุณสามารถกำหนดขนาดภาพที่กำหนดเองได้โดยใช้`setImageSize` วิธีการใน`TiffOptions` ระดับ. ระบุขนาด (ความกว้างและความสูง) ที่คุณต้องการสำหรับภาพที่ส่งออก

### ฉันจะหาข้อมูลเพิ่มเติมเกี่ยวกับ Aspose.Slides สำหรับ Java ได้ที่ไหน

 สำหรับเอกสารโดยละเอียดและข้อมูลเพิ่มเติมเกี่ยวกับ Aspose.Slides สำหรับ Java โปรดไปที่เอกสารประกอบ:[Aspose.Slides สำหรับการอ้างอิง Java API](https://reference.aspose.com/slides/java/).
{< /blocks/products/pf/tutorial-page-section >}

{< /blocks/products/pf/main-container >}
{< /blocks/products/pf/main-wrap-class >}

{< blocks/products/products-backtop-button >}
