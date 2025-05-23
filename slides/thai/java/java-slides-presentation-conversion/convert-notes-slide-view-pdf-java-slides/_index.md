---
"description": "เรียนรู้วิธีการแปลงงานนำเสนอ PowerPoint ที่มีบันทึกย่อเป็น PDF โดยใช้ Aspose.Slides สำหรับ Java ปฏิบัติตามคำแนะนำทีละขั้นตอนของเราพร้อมโค้ดต้นฉบับ"
"linktitle": "แปลงมุมมองสไลด์บันทึกเป็น PDF ใน Java Slides"
"second_title": "API การประมวลผล Java PowerPoint ของ Aspose.Slides"
"title": "แปลงมุมมองสไลด์บันทึกเป็น PDF ใน Java Slides"
"url": "/th/java/presentation-conversion/convert-notes-slide-view-pdf-java-slides/"
"weight": 16
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# แปลงมุมมองสไลด์บันทึกเป็น PDF ใน Java Slides


## บทนำเกี่ยวกับการแปลง Notes Slide View เป็น PDF ใน Java Slides

ในบทช่วยสอนนี้ เราจะแนะนำคุณเกี่ยวกับขั้นตอนการแปลงงานนำเสนอ PowerPoint ที่มีมุมมองสไลด์โน้ตเป็น PDF โดยใช้ไลบรารี Aspose.Slides สำหรับ Java ไลบรารีนี้มีคุณสมบัติอันทรงพลังสำหรับการทำงานกับงานนำเสนอ PowerPoint ใน Java

## ข้อกำหนดเบื้องต้น
1. ติดตั้ง Java Development Kit (JDK) แล้ว
2. เพิ่มไลบรารี Aspose.Slides สำหรับ Java ลงในโปรเจ็กต์ของคุณแล้ว

## ขั้นตอนที่ 1: นำเข้าคลาสที่จำเป็น
ในการเริ่มต้น คุณจะต้องนำเข้าคลาสที่จำเป็นจากไลบรารี Aspose.Slides นี่คือโค้ดสำหรับดำเนินการดังกล่าว:

```java
import com.aspose.slides.*;
```

## ขั้นตอนที่ 2: โหลดงานนำเสนอ PowerPoint
คุณควรมีไฟล์นำเสนอ PowerPoint ของคุณพร้อมแล้ว แทนที่ `"Your Document Directory"` พร้อมเส้นทางไปยังไดเร็กทอรีที่ไฟล์งานนำเสนอของคุณตั้งอยู่ นี่คือโค้ดสำหรับโหลดงานนำเสนอ:

```java
String dataDir = "Your Document Directory";
Presentation presentation = new Presentation(dataDir + "NotesFile.pptx");
```

## ขั้นตอนที่ 3: กำหนดค่าตัวเลือก PDF
ตอนนี้เรามาตั้งค่าตัวเลือกการส่งออก PDF กัน โดยเฉพาะอย่างยิ่ง เราจะตั้งตำแหน่งของโน้ตเป็น "BottomFull" เพื่อรวมโน้ตไว้ด้านล่างสไลด์ใน PDF นี่คือโค้ด:

```java
PdfOptions pdfOptions = new PdfOptions();
INotesCommentsLayoutingOptions options = pdfOptions.getNotesCommentsLayouting();
options.setNotesPosition(NotesPositions.BottomFull);
```

คุณสามารถปรับแต่งตัวเลือก PDF อื่น ๆ ตามความต้องการของคุณได้

## ขั้นตอนที่ 4: บันทึกการนำเสนอเป็น PDF พร้อมหมายเหตุ
สุดท้ายนี้ ให้บันทึกงานนำเสนอเป็นไฟล์ PDF รวมถึงหมายเหตุด้วย คุณสามารถระบุชื่อไฟล์เอาต์พุตได้ (เช่น `"Pdf_Notes_out.pdf"`) และเลือกรูปแบบ (`SaveFormat.Pdf`) นี่คือโค้ดที่จะทำสิ่งนั้น:

```java
presentation.save(dataDir + "Pdf_Notes_out.pdf", SaveFormat.Pdf, pdfOptions);
```

## ขั้นตอนที่ 5: ทำความสะอาดทรัพยากร
อย่าลืมปล่อยทรัพยากรเมื่อคุณเสร็จสิ้นการนำเสนอ:

```java
if (presentation != null) presentation.dispose();
```

## โค้ดต้นฉบับสมบูรณ์สำหรับการแปลง Notes Slide View เป็น PDF ใน Java Slides

```java
// เส้นทางไปยังไดเร็กทอรีเอกสาร
String dataDir = "Your Document Directory";
// สร้างอินสแตนซ์ของวัตถุการนำเสนอที่แสดงไฟล์การนำเสนอ
Presentation presentation = new Presentation(dataDir + "NotesFile.pptx");
try
{
	PdfOptions pdfOptions = new PdfOptions();
	INotesCommentsLayoutingOptions options = pdfOptions.getNotesCommentsLayouting();
	options.setNotesPosition(NotesPositions.BottomFull);
	// บันทึกการนำเสนอลงในบันทึก PDF
	presentation.save(dataDir + "Pdf_Notes_out.pdf", SaveFormat.Pdf, pdfOptions);
}
finally
{
	if (presentation != null) presentation.dispose();
}
```

## บทสรุป

ในบทช่วยสอนนี้ เราได้ศึกษาวิธีการแปลงงานนำเสนอ PowerPoint ที่มีมุมมองสไลด์โน้ตเป็น PDF โดยใช้ไลบรารี Aspose.Slides สำหรับ Java เราปฏิบัติตามคำแนะนำทีละขั้นตอนพร้อมโค้ดต้นฉบับเพื่อให้บรรลุการแปลงนี้ ต่อไปนี้คือสิ่งสำคัญที่ต้องเรียนรู้:

## คำถามที่พบบ่อย

### ฉันจะเปลี่ยนตำแหน่งบันทึกใน PDF ได้อย่างไร?

คุณสามารถเปลี่ยนตำแหน่งบันทึกใน PDF ได้โดยการแก้ไข `setNotesPosition` อาร์กิวเมนต์วิธีการ ตัวอย่างเช่น คุณสามารถตั้งค่าเป็น `NotesPositions.RightFull` เพื่อวางโน้ตไว้ทางด้านขวาของสไลด์

```java
options.setNotesPosition(NotesPositions.RightFull);
```

### ฉันสามารถปรับแต่งการส่งออก PDF เพิ่มเติมได้หรือไม่

ใช่ คุณสามารถปรับแต่งการส่งออก PDF ได้โดยปรับตัวเลือกต่างๆ ใน `PdfOptions` วัตถุ ตัวอย่างเช่น คุณสามารถตั้งค่าคุณภาพ การบีบอัด และพารามิเตอร์อื่นๆ ตามความต้องการของคุณได้

### ฉันจะได้รับ Aspose.Slides สำหรับ Java ได้อย่างไร?

คุณสามารถดาวน์โหลด Aspose.Slides สำหรับ Java ได้จากเว็บไซต์ที่ [ที่นี่](https://releases-aspose.com/slides/java/).

### มีข้อกำหนดการออกใบอนุญาตสำหรับการใช้ Aspose.Slides หรือไม่

ใช่ Aspose.Slides ต้องมีใบอนุญาตที่ถูกต้องสำหรับการใช้งานเชิงพาณิชย์ คุณสามารถขอใบอนุญาตได้จากเว็บไซต์ของ Aspose

### ฉันสามารถหาเอกสารและตัวอย่างเพิ่มเติมได้ที่ไหน

คุณสามารถค้นหาเอกสารและตัวอย่างที่ครอบคลุมสำหรับ Aspose.Slides สำหรับ Java ได้ที่ [ที่นี่](https://reference-aspose.com/slides/java/).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}