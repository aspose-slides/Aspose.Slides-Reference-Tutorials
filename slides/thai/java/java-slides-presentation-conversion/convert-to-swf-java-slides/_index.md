---
title: แปลงเป็น SWF ใน Java Slides
linktitle: แปลงเป็น SWF ใน Java Slides
second_title: Aspose.Slides Java PowerPoint การประมวลผล API
description: แปลงงานนำเสนอ PowerPoint เป็นรูปแบบ SWF ใน Java โดยใช้ Aspose.Slides ปฏิบัติตามคำแนะนำทีละขั้นตอนพร้อมซอร์สโค้ดเพื่อการแปลงที่ราบรื่น
weight: 35
url: /th/java/presentation-conversion/convert-to-swf-java-slides/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# แปลงเป็น SWF ใน Java Slides


## ข้อมูลเบื้องต้นเกี่ยวกับการแปลงงานนำเสนอ PowerPoint เป็น SWF ใน Java โดยใช้ Aspose.Slides

ในบทช่วยสอนนี้ คุณจะได้เรียนรู้วิธีแปลงงานนำเสนอ PowerPoint (PPTX) เป็นรูปแบบ SWF (Shockwave Flash) โดยใช้ Aspose.Slides สำหรับ Java Aspose.Slides เป็นไลบรารีที่ทรงพลังที่ให้คุณทำงานกับงานนำเสนอ PowerPoint โดยทางโปรแกรม

## ข้อกำหนดเบื้องต้น

ก่อนที่คุณจะเริ่มต้น ตรวจสอบให้แน่ใจว่าคุณมีสิ่งต่อไปนี้:

- ติดตั้ง Java Development Kit (JDK) แล้ว
-  Aspose.Slides สำหรับไลบรารี Java คุณสามารถดาวน์โหลดได้จาก[ที่นี่](https://downloads.aspose.com/slides/java).

## ขั้นตอนที่ 1: นำเข้าไลบรารี Aspose.Slides

ขั้นแรก คุณต้องนำเข้าไลบรารี Aspose.Slides ไปยังโปรเจ็กต์ Java ของคุณ คุณสามารถเพิ่มไฟล์ JAR ให้กับ classpath ของโปรเจ็กต์ของคุณได้

## ขั้นตอนที่ 2: เริ่มต้นวัตถุการนำเสนอ Aspose.Slides

ในขั้นตอนนี้ คุณจะสร้างไฟล์`Presentation` วัตถุเพื่อโหลดงานนำเสนอ PowerPoint ของคุณ แทนที่`"Your Document Directory"` พร้อมเส้นทางจริงไปยังไฟล์ PowerPoint ของคุณ

```java
String dataDir = "Your Document Directory";
Presentation presentation = new Presentation(dataDir + "HelloWorld.pptx");
```

## ขั้นตอนที่ 3: ตั้งค่าตัวเลือกการแปลง SWF

 ตอนนี้ คุณจะตั้งค่าตัวเลือกการแปลง SWF โดยใช้`SwfOptions` ระดับ. คุณสามารถปรับแต่งกระบวนการแปลงได้โดยระบุตัวเลือกต่างๆ ในตัวอย่างนี้ เราจะตั้งค่า`viewerIncluded` ตัวเลือกในการ`false`ซึ่งหมายความว่าเราจะไม่รวมโปรแกรมดูไว้ในไฟล์ SWF

```java
SwfOptions swfOptions = new SwfOptions();
swfOptions.setViewerIncluded(false);
```

คุณยังสามารถกำหนดค่าตัวเลือกที่เกี่ยวข้องกับเค้าโครงบันทึกย่อและความคิดเห็นได้หากจำเป็น ในตัวอย่างนี้ เราจะตั้งค่าตำแหน่งบันทึกย่อเป็น "BottomFull"

```java
INotesCommentsLayoutingOptions notesOptions = swfOptions.getNotesCommentsLayouting();
notesOptions.setNotesPosition(NotesPositions.BottomFull);
```

## ขั้นตอนที่ 4: แปลงเป็น SWF

 ตอนนี้คุณสามารถแปลงงานนำเสนอ PowerPoint เป็นรูปแบบ SWF โดยใช้ไฟล์`save` วิธีการของ`Presentation` วัตถุ.

```java
presentation.save(dataDir + "SaveAsSwf_out.swf", SaveFormat.Swf, swfOptions);
```

บรรทัดโค้ดนี้จะบันทึกงานนำเสนอเป็นไฟล์ SWF พร้อมตัวเลือกที่ระบุ

## ขั้นตอนที่ 5: รวมโปรแกรมดู (ไม่บังคับ)

 หากคุณต้องการรวมวิวเวอร์ไว้ในไฟล์ SWF คุณสามารถเปลี่ยนไฟล์`viewerIncluded` ตัวเลือกในการ`true` และบันทึกการนำเสนออีกครั้ง

```java
swfOptions.setViewerIncluded(true);
presentation.save(dataDir + "SaveNotes_out.swf", SaveFormat.Swf, swfOptions);
```

## ขั้นตอนที่ 6: ทำความสะอาด

 สุดท้ายนี้ ให้แน่ใจว่าได้กำจัดทิ้ง`Presentation`คัดค้านการปล่อยทรัพยากรใด ๆ

```java
if (presentation != null) presentation.dispose();
```

## กรอกซอร์สโค้ดสำหรับการแปลงเป็น SWF ใน Java Slides

```java
// เส้นทางไปยังไดเร็กทอรีเอกสาร
String dataDir = "Your Document Directory";
// สร้างอินสแตนซ์วัตถุการนำเสนอที่แสดงถึงไฟล์การนำเสนอ
Presentation presentation = new Presentation(dataDir + "HelloWorld.pptx");
try
{
	SwfOptions swfOptions = new SwfOptions();
	swfOptions.setViewerIncluded(false);
	INotesCommentsLayoutingOptions notesOptions = swfOptions.getNotesCommentsLayouting();
	notesOptions.setNotesPosition(NotesPositions.BottomFull);
	// การบันทึกหน้าการนำเสนอและบันทึกย่อ
	presentation.save(dataDir + "SaveAsSwf_out.swf", SaveFormat.Swf, swfOptions);
	swfOptions.setViewerIncluded(true);
	presentation.save(dataDir + "SaveNotes_out.swf", SaveFormat.Swf, swfOptions);
}
finally
{
	if (presentation != null) presentation.dispose();
}
```

## บทสรุป

คุณได้แปลงงานนำเสนอ PowerPoint เป็นรูปแบบ SWF สำเร็จโดยใช้ Aspose.Slides สำหรับ Java คุณสามารถปรับแต่งกระบวนการแปลงเพิ่มเติมได้โดยการสำรวจตัวเลือกต่างๆ ที่ Aspose.Slides ให้มา

## คำถามที่พบบ่อย

### ฉันจะตั้งค่าตัวเลือกการแปลง SWF ต่างๆ ได้อย่างไร

 คุณสามารถปรับแต่งตัวเลือกการแปลง SWF ได้โดยการแก้ไข`SwfOptions` วัตถุ. โปรดดูเอกสารประกอบของ Aspose.Slides สำหรับรายการตัวเลือกที่พร้อมใช้งาน

### ฉันสามารถรวมบันทึกย่อและความคิดเห็นในไฟล์ SWF ได้หรือไม่

 ได้ คุณสามารถรวมบันทึกย่อและความคิดเห็นไว้ในไฟล์ SWF ได้โดยการกำหนดค่า`SwfOptions` ตามนั้น ใช้`setViewerIncluded` วิธีการควบคุมว่าจะรวมบันทึกย่อและข้อคิดเห็นไว้หรือไม่

### ตำแหน่งบันทึกย่อเริ่มต้นในไฟล์ SWF คืออะไร

ตำแหน่งบันทึกย่อเริ่มต้นในไฟล์ SWF คือ "ไม่มี" คุณสามารถเปลี่ยนเป็น "BottomFull" หรือตำแหน่งอื่นๆ ได้ตามต้องการ

### Aspose.Slides รองรับรูปแบบเอาต์พุตอื่น ๆ หรือไม่

ใช่ Aspose.Slides รองรับรูปแบบเอาต์พุตที่หลากหลาย รวมถึง PDF, HTML, รูปภาพ และอื่นๆ คุณสามารถสำรวจตัวเลือกเหล่านี้ได้ในเอกสารประกอบ

### ฉันจะจัดการกับข้อผิดพลาดระหว่างการแปลงได้อย่างไร

คุณสามารถใช้บล็อก try-catch เพื่อจัดการกับข้อยกเว้นที่อาจเกิดขึ้นระหว่างกระบวนการแปลง อย่าลืมตรวจสอบเอกสารประกอบของ Aspose.Slides เพื่อดูคำแนะนำในการจัดการข้อผิดพลาดเฉพาะ
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
