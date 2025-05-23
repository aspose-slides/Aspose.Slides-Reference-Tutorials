---
"description": "เรียนรู้วิธีการแปลงงานนำเสนอ PowerPoint เป็นรูปภาพ TIFF ด้วยขนาดที่กำหนดเองโดยใช้ Aspose.Slides สำหรับ Java คำแนะนำทีละขั้นตอนพร้อมตัวอย่างโค้ดสำหรับนักพัฒนา"
"linktitle": "แปลงด้วยขนาดที่กำหนดเองใน Java Slides"
"second_title": "API การประมวลผล Java PowerPoint ของ Aspose.Slides"
"title": "แปลงด้วยขนาดที่กำหนดเองใน Java Slides"
"url": "/th/java/presentation-conversion/convert-custom-size-java-slides/"
"weight": 31
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# แปลงด้วยขนาดที่กำหนดเองใน Java Slides


## บทนำเกี่ยวกับการแปลงด้วยขนาดที่กำหนดเองใน Java Slides

ในบทความนี้ เราจะมาสำรวจวิธีการแปลงไฟล์นำเสนอ PowerPoint เป็นรูปภาพ TIFF ด้วยขนาดที่กำหนดเองโดยใช้ Aspose.Slides for Java API Aspose.Slides for Java เป็นไลบรารีที่มีประสิทธิภาพที่ช่วยให้ผู้พัฒนาสามารถทำงานกับไฟล์ PowerPoint ได้ด้วยโปรแกรม เราจะอธิบายทีละขั้นตอนและให้โค้ด Java ที่จำเป็นแก่คุณเพื่อทำงานนี้ให้สำเร็จ

## ข้อกำหนดเบื้องต้น

ก่อนที่เราจะเริ่ม โปรดตรวจสอบให้แน่ใจว่าคุณมีข้อกำหนดเบื้องต้นดังต่อไปนี้:

- ติดตั้ง Java Development Kit (JDK) แล้ว
- Aspose.Slides สำหรับไลบรารี Java

คุณสามารถดาวน์โหลดไลบรารี Aspose.Slides สำหรับ Java ได้จากเว็บไซต์: [ดาวน์โหลด Aspose.Slides สำหรับ Java](https://releases.aspose.com/slides/java/)

## ขั้นตอนที่ 1: นำเข้าไลบรารี Aspose.Slides

ในการเริ่มต้น คุณต้องนำเข้าไลบรารี Aspose.Slides เข้าสู่โปรเจ็กต์ Java ของคุณ โดยคุณสามารถทำได้ดังนี้:

```java
// เพิ่มคำสั่งนำเข้าที่จำเป็น
import com.aspose.slides.*;
```

## ขั้นตอนที่ 2: โหลดงานนำเสนอ PowerPoint

ต่อไป คุณจะต้องโหลดงานนำเสนอ PowerPoint ที่คุณต้องการแปลงเป็นภาพ TIFF แทนที่ `"Your Document Directory"` พร้อมเส้นทางจริงไปยังไฟล์การนำเสนอของคุณ

```java
// เส้นทางไปยังไดเร็กทอรีเอกสาร
String dataDir = "Your Document Directory";

// สร้างอินสแตนซ์ของวัตถุการนำเสนอที่แสดงไฟล์การนำเสนอ
Presentation pres = new Presentation(dataDir + "Convert_Tiff_Custom.pptx");
```

## ขั้นตอนที่ 3: ตั้งค่าตัวเลือกการแปลง TIFF

ตอนนี้เรามาตั้งค่าตัวเลือกสำหรับการแปลง TIFF กัน เราจะระบุประเภทการบีบอัด DPI (จุดต่อนิ้ว) ขนาดรูปภาพ และตำแหน่งของโน้ต คุณสามารถปรับแต่งตัวเลือกเหล่านี้ได้ตามความต้องการของคุณ

```java
// สร้างอินสแตนซ์ของคลาส TiffOptions
TiffOptions opts = new TiffOptions();

// การตั้งค่าประเภทการบีบอัด
opts.setCompressionType(TiffCompressionTypes.Default);

// การตั้งค่า DPI ของภาพ
opts.setDpiX(200);
opts.setDpiY(100);

// ตั้งค่าขนาดรูปภาพ
opts.setImageSize(new Dimension(1728, 1078));

// ตั้งค่าตำแหน่งโน้ต
INotesCommentsLayoutingOptions notesOptions = opts.getNotesCommentsLayouting();
notesOptions.setNotesPosition(NotesPositions.BottomFull);
```

## ขั้นตอนที่ 4: บันทึกเป็น TIFF

เมื่อกำหนดค่าตัวเลือกทั้งหมดแล้ว คุณสามารถบันทึกงานนำเสนอเป็นรูปภาพ TIFF พร้อมการตั้งค่าที่ระบุได้

```java
// บันทึกการนำเสนอเป็น TIFF ด้วยขนาดภาพที่ระบุ
pres.save(dataDir + "TiffWithCustomSize_out.tiff", SaveFormat.Tiff, opts);
```

## โค้ดต้นฉบับสมบูรณ์สำหรับการแปลงด้วยขนาดที่กำหนดเองใน Java Slides

```java
// เส้นทางไปยังไดเร็กทอรีเอกสาร
String dataDir = "Your Document Directory";
// สร้างอินสแตนซ์ของวัตถุการนำเสนอที่แสดงไฟล์การนำเสนอ
Presentation pres = new Presentation(dataDir + "Convert_Tiff_Custom.pptx");
try
{
	// สร้างอินสแตนซ์ของคลาส TiffOptions
	TiffOptions opts = new TiffOptions();
	// การตั้งค่าประเภทการบีบอัด
	opts.setCompressionType(TiffCompressionTypes.Default);
	INotesCommentsLayoutingOptions notesOptions = opts.getNotesCommentsLayouting();
	notesOptions.setNotesPosition(NotesPositions.BottomFull);
	// ประเภทการบีบอัด
	// ค่าเริ่มต้น - ระบุรูปแบบการบีบอัดเริ่มต้น (LZW)
	// None - ไม่ระบุการบีบอัด
	// ซีซีทีที3
	// ซีซีทีที4
	// แอลแซดดับบลิว
	// อาร์แอลอี
	// ความลึกขึ้นอยู่กับประเภทของการบีบอัดและไม่สามารถตั้งค่าด้วยตนเองได้
	// หน่วยความละเอียดจะเท่ากับ “2” (จุดต่อนิ้ว) เสมอ
	// การตั้งค่า DPI ของภาพ
	opts.setDpiX(200);
	opts.setDpiY(100);
	// ตั้งค่าขนาดรูปภาพ
	opts.setImageSize(new Dimension(1728, 1078));
	// บันทึกการนำเสนอเป็น TIFF ด้วยขนาดภาพที่ระบุ
	pres.save(dataDir + "TiffWithCustomSize_out.tiff", SaveFormat.Tiff, opts);
}
finally
{
	if (pres != null) pres.dispose();
}
```

## บทสรุป

ขอแสดงความยินดี! คุณได้แปลงงานนำเสนอ PowerPoint เป็นรูปภาพ TIFF ด้วยขนาดที่กำหนดเองโดยใช้ Aspose.Slides สำหรับ Java สำเร็จแล้ว ฟีเจอร์นี้มีประโยชน์เมื่อคุณต้องสร้างรูปภาพคุณภาพสูงจากงานนำเสนอของคุณเพื่อจุดประสงค์ต่างๆ

## คำถามที่พบบ่อย

### ฉันจะเปลี่ยนประเภทการบีบอัดสำหรับภาพ TIFF ได้อย่างไร

คุณสามารถเปลี่ยนประเภทการบีบอัดได้โดยการแก้ไข `setCompressionType` วิธีการใน `TiffOptions` คลาส มีประเภทการบีบอัดที่แตกต่างกันให้เลือก เช่น Default, None, CCITT3, CCITT4, LZW และ RLE

### ฉันสามารถปรับ DPI (จุดต่อนิ้ว) ของภาพ TIFF ได้หรือไม่

ใช่ คุณสามารถปรับ DPI ได้โดยใช้ `setDpiX` และ `setDpiY` วิธีการใน `TiffOptions` คลาส เพียงตั้งค่าที่ต้องการเพื่อควบคุมความละเอียดของภาพ

### มีตัวเลือกอะไรบ้างสำหรับตำแหน่งโน้ตในภาพ TIFF?

ตำแหน่งโน้ตในภาพ TIFF สามารถกำหนดค่าได้โดยใช้ `setNotesPosition` วิธีการที่มีทางเลือกเช่น BottomFull, BottomTruncated และ SlideOnly เลือกวิธีที่เหมาะสมกับความต้องการของคุณมากที่สุด

### สามารถระบุขนาดรูปภาพที่กำหนดเองสำหรับการแปลง TIFF ได้หรือไม่

แน่นอน! คุณสามารถตั้งค่าขนาดรูปภาพที่กำหนดเองได้โดยใช้ `setImageSize` วิธีการใน `TiffOptions` คลาส ระบุขนาด (ความกว้างและความสูง) ที่คุณต้องการสำหรับรูปภาพเอาท์พุต

### ฉันสามารถหาข้อมูลเพิ่มเติมเกี่ยวกับ Aspose.Slides สำหรับ Java ได้ที่ไหน

สำหรับเอกสารโดยละเอียดและข้อมูลเพิ่มเติมเกี่ยวกับ Aspose.Slides สำหรับ Java โปรดไปที่เอกสาร: [เอกสารอ้างอิง API ของ Aspose.Slides สำหรับ Java](https://reference-aspose.com/slides/java/).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}