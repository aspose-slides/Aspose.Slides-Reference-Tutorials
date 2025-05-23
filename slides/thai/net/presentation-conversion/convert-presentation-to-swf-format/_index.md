---
"description": "เรียนรู้วิธีการแปลงงานนำเสนอ PowerPoint เป็นรูปแบบ SWF โดยใช้ Aspose.Slides สำหรับ .NET สร้างเนื้อหาแบบไดนามิกได้อย่างง่ายดาย!"
"linktitle": "แปลงงานนำเสนอเป็นรูปแบบ SWF"
"second_title": "API การประมวลผล PowerPoint ของ Aspose.Slides .NET"
"title": "แปลงงานนำเสนอเป็นรูปแบบ SWF"
"url": "/th/net/presentation-conversion/convert-presentation-to-swf-format/"
"weight": 28
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# แปลงงานนำเสนอเป็นรูปแบบ SWF


ในยุคดิจิทัลทุกวันนี้ การนำเสนอแบบมัลติมีเดียถือเป็นช่องทางการสื่อสารที่ทรงพลัง บางครั้งคุณอาจต้องการแบ่งปันการนำเสนอของคุณในรูปแบบที่ไดนามิกมากขึ้น เช่น การแปลงเป็นรูปแบบ SWF (Shockwave Flash) คู่มือนี้จะแนะนำคุณเกี่ยวกับขั้นตอนการแปลงการนำเสนอเป็นรูปแบบ SWF โดยใช้ Aspose.Slides สำหรับ .NET

## สิ่งที่คุณต้องการ

ก่อนที่จะเริ่มเรียนรู้บทช่วยสอนนี้ ให้แน่ใจว่าคุณมีสิ่งต่อไปนี้:

- Aspose.Slides สำหรับ .NET: หากคุณยังไม่มี คุณสามารถทำได้ [ดาวน์โหลดได้ที่นี่](https://releases-aspose.com/slides/net/).

- ไฟล์งานนำเสนอ: คุณจะต้องมีไฟล์งานนำเสนอ PowerPoint ที่คุณต้องการแปลงเป็นรูปแบบ SWF

## ขั้นตอนที่ 1: ตั้งค่าสภาพแวดล้อมของคุณ

ในการเริ่มต้น ให้สร้างไดเรกทอรีสำหรับโครงการของคุณ เรียกว่า "ไดเรกทอรีโครงการของคุณ" ภายในไดเรกทอรีนี้ คุณจะต้องวางโค้ดต้นฉบับต่อไปนี้:

```csharp
string dataDir = "Your Document Directory";
string outPath = "Your Output Directory";

// สร้างอินสแตนซ์ของวัตถุการนำเสนอที่แสดงไฟล์การนำเสนอ
using (Presentation presentation = new Presentation(dataDir + "HelloWorld.pptx"))
{
    SwfOptions swfOptions = new SwfOptions();
    swfOptions.ViewerIncluded = false;

    INotesCommentsLayoutingOptions notesOptions = swfOptions.NotesCommentsLayouting;
    notesOptions.NotesPosition = NotesPositions.BottomFull;

    // การบันทึกหน้าการนำเสนอและบันทึกย่อ
    presentation.Save(dataDir + "SaveAsSwf_out.swf", SaveFormat.Swf, swfOptions);
    swfOptions.ViewerIncluded = true;
    presentation.Save(dataDir + "SaveNotes_out.swf", SaveFormat.Swf, swfOptions);
}
```

ให้แน่ใจว่าคุณเปลี่ยน `"Your Document Directory"` และ `"Your Output Directory"` พร้อมด้วยเส้นทางจริงที่ไฟล์การนำเสนอของคุณตั้งอยู่และตำแหน่งที่คุณต้องการบันทึกไฟล์ SWF

## ขั้นตอนที่ 2: การโหลดงานนำเสนอ

ในขั้นตอนนี้ เราจะโหลดการนำเสนอ PowerPoint โดยใช้ Aspose.Slides:

```csharp
using (Presentation presentation = new Presentation(dataDir + "HelloWorld.pptx"))
```

แทนที่ `"HelloWorld.pptx"` พร้อมชื่อไฟล์นำเสนอของคุณ

## ขั้นตอนที่ 3: กำหนดค่าตัวเลือกการแปลง SWF

เราตั้งค่าตัวเลือกการแปลง SWF เพื่อปรับแต่งผลลัพธ์:

```csharp
SwfOptions swfOptions = new SwfOptions();
swfOptions.ViewerIncluded = false;

INotesCommentsLayoutingOptions notesOptions = swfOptions.NotesCommentsLayouting;
notesOptions.NotesPosition = NotesPositions.BottomFull;
```

คุณสามารถปรับเปลี่ยนตัวเลือกเหล่านี้ได้ตามความต้องการของคุณ

## ขั้นตอนที่ 4: บันทึกเป็น SWF

ตอนนี้เราบันทึกงานนำเสนอเป็นไฟล์ SWF:

```csharp
presentation.Save(dataDir + "SaveAsSwf_out.swf", SaveFormat.Swf, swfOptions);
```

บรรทัดนี้จะบันทึกงานนำเสนอหลักเป็นไฟล์ SWF

## ขั้นตอนที่ 5: บันทึกด้วยหมายเหตุ

หากคุณต้องการรวมหมายเหตุให้ใช้รหัสนี้:

```csharp
swfOptions.ViewerIncluded = true;
presentation.Save(dataDir + "SaveNotes_out.swf", SaveFormat.Swf, swfOptions);
```

รหัสนี้จะบันทึกการนำเสนอพร้อมหมายเหตุในรูปแบบ SWF

## บทสรุป

ขอแสดงความยินดี! คุณได้แปลงงานนำเสนอ PowerPoint เป็นรูปแบบ SWF สำเร็จแล้วโดยใช้ Aspose.Slides สำหรับ .NET วิธีนี้มีประโยชน์อย่างยิ่งเมื่อคุณต้องการแชร์งานนำเสนอของคุณทางออนไลน์หรือฝังไว้ในหน้าเว็บ

สำหรับข้อมูลเพิ่มเติมและเอกสารรายละเอียด คุณสามารถเยี่ยมชมได้ที่ [การอ้างอิง Aspose.Slides สำหรับ .NET](https://reference-aspose.com/slides/net/).

## คำถามที่พบบ่อย

### รูปแบบ SWF คืออะไร?
SWF (Shockwave Flash) เป็นรูปแบบมัลติมีเดียที่ใช้สำหรับแอนิเมชัน เกม และเนื้อหาแบบโต้ตอบบนเว็บ

### Aspose.Slides สำหรับ .NET ใช้ได้ฟรีหรือไม่
Aspose.Slides สำหรับ .NET นำเสนอรุ่นทดลองใช้งานฟรี แต่หากต้องการฟังก์ชันการทำงานเต็มรูปแบบ คุณอาจต้องซื้อใบอนุญาต คุณสามารถตรวจสอบราคาและรายละเอียดใบอนุญาตได้ [ที่นี่](https://purchase-aspose.com/buy).

### ฉันสามารถทดลองใช้ Aspose.Slides สำหรับ .NET ก่อนซื้อใบอนุญาตได้หรือไม่
ใช่ คุณสามารถทดลองใช้ Aspose.Slides สำหรับ .NET ได้ฟรี [ที่นี่](https://releases-aspose.com/).

### ฉันจำเป็นต้องมีทักษะการเขียนโปรแกรมหรือไม่เพื่อใช้ Aspose.Slides สำหรับ .NET?
ใช่ คุณควรมีความรู้เกี่ยวกับการเขียนโปรแกรม C# เพื่อใช้ Aspose.Slides ได้อย่างมีประสิทธิภาพ

### ฉันจะได้รับการสนับสนุนสำหรับ Aspose.Slides สำหรับ .NET ได้จากที่ไหน
หากคุณมีคำถามหรือต้องการความช่วยเหลือ คุณสามารถเยี่ยมชมได้ที่ [ฟอรั่ม Aspose.Slides สำหรับ .NET](https://forum.aspose.com/) สำหรับการสนับสนุนและช่วยเหลือชุมชน


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}